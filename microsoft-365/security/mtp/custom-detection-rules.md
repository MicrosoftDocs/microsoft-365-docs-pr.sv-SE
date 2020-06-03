---
title: Skapa och hantera anpassade identifieringsregler i Microsoft Threat Protection
description: Lär dig hur du skapar och hanterar anpassade identifieringsregler baserat på avancerade jaktfrågor
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade upptäckter, regler, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, behörigheter, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1a84c568d1411cf21c23e59cabad955c40c18ac6
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498369"
---
# <a name="create-and-manage-custom-detections-rules"></a>Skapa och hantera regler för anpassade identifieringar

**Gäller:**
- Microsoft Hotskydd

Med anpassade identifieringsregler som skapats från [avancerade jaktfrågor](advanced-hunting-overview.md) kan du proaktivt övervaka olika händelser och systemtillstånd, inklusive misstänkt överträdelseaktivitet och felkonfigurerade slutpunkter. Du kan ställa in dem så att de körs med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.

## <a name="required-permissions-for-managing-custom-detections"></a>Nödvändiga behörigheter för att hantera anpassade identifieringar

Om du vill hantera anpassade identifieringar måste du tilldelas en av dessa roller:

- **Säkerhetsadministratör** – säkerhetsadministratören eller säkerhetsadministratörsrollen är en [Azure Active Directory-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) för att hantera olika säkerhetsinställningar i Microsoft 365-säkerhetscenter och olika portaler och tjänster.

- **Säkerhetsoperatör** – säkerhetsoperatörsrollen är en [Azure Active Directory-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) för att hantera aviseringar och har global skrivskyddad åtkomst på säkerhetsrelaterade funktioner, inklusive all information i Microsoft 365-säkerhetscenter. Den här rollen är endast tillräcklig för att hantera anpassade identifieringar om rbac (Role-based Access Control) är inaktiverat i Microsoft Defender ATP. Om du har konfigurerat RBAC behöver du också behörigheten **hantera säkerhetsinställningar** för Microsoft Defender ATP.

För att hantera nödvändiga behörigheter kan en **global administratör** göra följande:

- Tilldela **säkerhetsadministratören** eller **säkerhetsoperatörsrollen** i [Microsoft 365-administrationscentret](https://admin.microsoft.com/) under **Roles**  >  **Rollsäkerhetsadministratör**.
- Kontrollera RBAC-inställningarna för Microsoft Defender ATP i [Microsoft Defender Security Center](https://securitycenter.windows.com/) under Roller för **inställningar**  >  **behörigheter**  >  **Roles**. Välj motsvarande roll om du vill tilldela behörigheten **hantera säkerhetsinställningar.**

> [!NOTE]
> För att hantera anpassade identifieringar behöver **säkerhetsoperatörer** behörigheten **hantera säkerhetsinställningar** i Microsoft Defender ATP om RBAC är aktiverat.

## <a name="create-a-custom-detection-rule"></a>Skapa en anpassad identifieringsregel
### <a name="1-prepare-the-query"></a>1. Förbered frågan.

I Microsoft 365 security center går du till **Avancerad jakt** och väljer en befintlig fråga eller skapar en ny fråga. När du använder en ny fråga kör du frågan för att identifiera fel och förstå möjliga resultat.

#### <a name="required-columns-in-the-query-results"></a>Obligatoriska kolumner i frågeresultatet
Om du vill skapa en anpassad identifieringsregel måste frågan returnera följande kolumner:

- `Timestamp`
- En av följande enhets-, användar- eller postlådekolumner:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(kuvertavsändare eller Retursökvägsadress)
    - `SenderMailFromAddress`(avsändaradress visas av e-postklienten)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>Stöd för ytterligare entiteter läggs till när nya tabeller läggs till i det [avancerade jaktschemat](advanced-hunting-schema-tables.md).

Enkla frågor, till exempel de som inte använder `project` operatorn eller `summarize` för att anpassa eller aggregera resultat, returnerar vanligtvis dessa vanliga kolumner.

Det finns olika sätt att se till att mer komplexa frågor returnerar dessa kolumner. Om du till exempel föredrar att aggregera och räkna efter entitet under en kolumn, till `DeviceId` exempel, kan du fortfarande returnera `Timestamp` den genom att hämta den från den senaste händelsen som involverar varje unik `DeviceId` .

Exempelfrågan nedan räknar antalet unika enheter ( `DeviceId` ) med antivirusidentifieringar och använder det här antalet för att bara hitta enheter med fler än fem identifieringar. För att returnera det senaste `Timestamp` använder den `summarize` operatorn med `arg_max` funktionen.

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Skapa ny regel och ge varningsinformation.

Med frågan i frågeredigeraren väljer du **Skapa identifieringsregel** och anger följande varningsinformation:

- **Identifieringsnamn** – namnet på identifieringsregeln
- **Frekvens** – intervall för att köra frågan och vidta åtgärder. [Se ytterligare vägledning nedan](#rule-frequency)
- **Varningstitel** – titel som visas med aviseringar som utlöses av regeln
- **Allvarlighetsgrad** – potentiell risk för den komponent eller aktivitet som identifierats i regeln
- **Kategori** – hotkomponent eller hotaktivitet som identifierats i regeln
- **MITRE ATT&CK-teknik** – en eller flera angreppstekniker som identifierats av regeln enligt beskrivningen i [MITRE ATT-&CK-ramverket.](https://attack.mitre.org/) Det här avsnittet gäller inte och döljs för vissa varningskategorier, inklusive skadlig kod, ransomware, misstänkt aktivitet och oönskad programvara
- **Beskrivning** – mer information om den komponent eller aktivitet som identifieras i regeln 
- **Rekommenderade åtgärder** – ytterligare åtgärder som de som svarar på en avisering

#### <a name="rule-frequency"></a>Regelfrekvens
När den sparas körs en ny eller redigerad anpassad identifieringsregel omedelbart och söker efter matchningar från de senaste 30 dagarnas data. Regeln körs sedan igen med fasta intervall och tillbakablickslängder baserat på den frekvens du väljer:

- **Var 24:e timme** – körs var 24:e timme, kontrollerar data från de senaste 30 dagarna
- **Var 12:e timme** – körs var 12:e timme, kontrollerar data från de senaste 24 timmarna
- **Var tredje timme** – körs var tredje timme, kontrollerar data från de senaste 6 timmarna
- **Varje timme** – går varje timme, kontrollerar data från de senaste 2 timmarna

Välj den frekvens som matchar hur nära du vill övervaka identifieringar och tänk på organisationens förmåga att svara på aviseringarna.

### <a name="3-choose-the-impacted-entities"></a>3. Välj de påverkade enheterna.
Identifiera kolumnerna i frågeresultaten där du förväntar dig att hitta de viktigaste berörda eller påverkade entiteten. En fråga kan till exempel returnera avsändaradresser ( `SenderFromAddress` eller ) och mottagare ( `SenderMailFromAddress` `RecipientEmailAddress` ). Identifiera vilka av dessa kolumner som representerar de viktigaste påverkade entiteten hjälper tjänsten att aggregera relevanta aviseringar, korrelera incidenter och målsvarsåtgärder.

Du kan bara välja en kolumn för varje entitetstyp (postlåda, användare eller enhet). Kolumner som inte returneras av frågan kan inte markeras.

### <a name="4-specify-actions"></a>4. Ange åtgärder.
Din anpassade identifieringsregel kan automatiskt vidta åtgärder på enheter, filer eller användare som returneras av frågan.

#### <a name="actions-on-devices"></a>Åtgärder på enheter
Dessa åtgärder tillämpas på enheter i `DeviceId` kolumnen i frågeresultaten:
- **Isolera enheten** – använder Microsoft Defender ATP för att tillämpa fullständig nätverksisolering, vilket förhindrar att enheten ansluter till något program eller någon tjänst. [Läs mer om isolering av Microsoft Defender ATP-datorer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- **Samla in undersökningspaket** – samlar in enhetsinformation i en ZIP-fil. [Läs mer om microsoft Defender ATP-undersökningspaketet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- **Kör antivirussökning** – utför en fullständig Windows Defender Antivirus-genomsökning på enheten
- **Inleder undersökning** – inleder en [automatiserad undersökning](mtp-autoir.md) på enheten
- **Begränsa appkörning** – anger begränsningar för enheten så att endast filer som är signerade med ett Microsoft-utfärdat certifikat körs. [Läs mer om appbegränsningar med Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Åtgärder på filer
När du väljer det här alternativet kan du välja att använda **karantänfilåtgärden** på filer i `SHA1` `InitiatingProcessSHA1` `SHA256` frågeresultaten , , eller `InitiatingProcessSHA256` kolumnen. Den här åtgärden tar bort filen från den aktuella platsen och placerar en kopia i karantän.

#### <a name="actions-on-users"></a>Åtgärder för användare
När det här alternativet är markerat utförs **åtgärden Markera som komprometterade** åtgärder för användare i `AccountObjectId` , eller kolumnen i `InitiatingProcessAccountObjectId` `RecipientObjectId` frågeresultatet. Den här åtgärden anger att användarnas risknivå är "hög" i Azure Active Directory, vilket utlöser motsvarande [principer för identitetsskydd](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

> [!NOTE]
> Tillåt- eller blockeringsåtgärder för anpassade identifieringsregler stöds för närvarande inte på Microsoft Threat Protection.

### <a name="5-set-the-rule-scope"></a>5. Ställ in regelomfattningen.
Ange omfånget för att ange vilka enheter som omfattas av regeln. Omfattningen påverkar regler som kontrollerar enheter och påverkar inte regler som bara kontrollerar postlådor och användarkonton eller identiteter.

När du ställer in scopet kan du välja:

- Alla enheter
- Specifika enhetsgrupper

Endast data från enheter i omfånget kommer att efterfrågas. Dessutom kommer åtgärder endast att vidtas på dessa enheter.

### <a name="6-review-and-turn-on-the-rule"></a>6. Granska och slå på regeln.
När du har granskat regeln klickar du på **Skapa** för att spara den. Den anpassade identifieringsregeln körs omedelbart. Den körs igen baserat på konfigurerad frekvens för att söka efter matchningar, generera aviseringar och vidta svarsåtgärder.

## <a name="manage-existing-custom-detection-rules"></a>Hantera befintliga anpassade identifieringsregler
Du kan visa listan över befintliga anpassade identifieringsregler, kontrollera deras tidigare körningar och granska de aviseringar som de har utlöst. Du kan också köra en regel på begäran och ändra den.

### <a name="view-existing-rules"></a>Visa befintliga regler

Om du vill visa alla befintliga anpassade identifieringsregler navigerar du till **Jakt**  >  **anpassade identifieringar**. På sidan visas alla regler med följande körinformation:

- **Senaste körningen** – när en regel senast kördes för att söka efter frågematchningar och generera aviseringar
- **Senaste körningsstatus** – om en regel har körts
- **Nästa körning** – nästa schemalagda körning
- **Status** – om en regel har aktiverats eller inaktiverats

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Visa regelinformation, ändra regel och kör regel

Om du vill visa omfattande information om en anpassad identifieringsregel väljer du namnet på regeln i listan över regler i **Jakt**  >  **anpassade identifieringar**. Då öppnas en sida om den anpassade identifieringsregeln med allmän information om regeln, inklusive information om aviseringen, körstatusen och scopet. Den innehåller också en lista över utlösta aviseringar och utlösta åtgärder.

![Informationssida för anpassad identifieringsregel](../../media/custom-detection-details.png)<br>
*Information om anpassad identifieringsregel*

Du kan också vidta följande åtgärder på regeln från den här sidan:

- **Kör** – kör regeln omedelbart. Detta återställer också intervallet för nästa körning.
- **Redigera** – ändra regeln utan att ändra frågan
- **Ändra fråga** – redigera frågan i avancerad jakt
- **Slå på**  /  **Inaktivera** – aktivera regeln eller stoppa den från att köras
- **Ta bort** – inaktivera regeln och ta bort den

### <a name="view-and-manage-triggered-alerts"></a>Visa och hantera utlösta aviseringar

På skärmen Regelinformation (**Jakt**  >  **anpassade identifieringar**  >  **[Regelnamn]**) går du till **Utlösta aviseringar** för att visa listan över aviseringar som genereras av matchningar till regeln. Välj en avisering om du vill visa detaljerad information om aviseringen och vidta följande åtgärder för den aviseringen:

- Hantera aviseringen genom att ange dess status och klassificering (sann eller falsk avisering)
- Länka aviseringen till en incident
- Kör frågan som utlöste aviseringen vid avancerad jakt

### <a name="review-actions"></a>Granska åtgärder
På skärmen Regelinformation (**Hunting**  >  **Custom detections**  >  **[Rule name]**) går du till Utlösta åtgärder för att visa listan över åtgärder som **vidtagits** baserat på matchningar till regeln.

>[!TIP]
>Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du markeringskolumnen [&#10003;] till vänster i tabellen.

## <a name="related-topic"></a>Relaterat ämne
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig det avancerade jaktfrågespråket](advanced-hunting-query-language.md)