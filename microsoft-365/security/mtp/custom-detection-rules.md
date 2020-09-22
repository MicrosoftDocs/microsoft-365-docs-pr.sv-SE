---
title: Skapa och hantera anpassade identifierings regler i Microsoft Threat Protection
description: Lär dig hur du skapar och hanterar anpassade identifierings regler baserat på avancerade jakt frågor
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, regler, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, behörigheter, Microsoft Defender ATP
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
ms.openlocfilehash: e3388bd0d3a7ac6afff0109eb80945d3ddc362fd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198903"
---
# <a name="create-and-manage-custom-detections-rules"></a>Skapa och hantera regler för anpassat identifiering

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

Anpassade identifierings regler är regler som du kan utforma och anpassa med hjälp av [avancerade](advanced-hunting-overview.md) frågor. Med dessa regler kan du proaktivt övervaka olika händelser och system tillstånd, inklusive misstänkt överträdelse och felkonfigurerade slut punkter. Du kan ange att de ska köras med jämna mellanrum, skapa aviseringar och vidta åtgärder när det finns träffar.

## <a name="required-permissions-for-managing-custom-detections"></a>Nödvändiga behörigheter för att hantera anpassade identifieringar

För att hantera anpassade identifieringar måste du tilldela en av följande roller:

- **Säkerhets administratören**– användare med den här [Azure Active Directory-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera säkerhets inställningar i Microsoft 365 säkerhets Center och andra portaler och tjänster.

- **Säkerhets ansvarig**– användare med den här [Azure Active Directory-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera aviseringar och ha global åtkomst till säkerhetsrelaterade funktioner, inklusive all information i Microsoft 365 säkerhets Center. Den här rollen räcker bara till för att hantera anpassade identifieringar om RBAC (rollbaserad åtkomst kontroll) är inaktiverat i Microsoft Defender ATP. Om du har en RBAC-konfiguration behöver du även behörigheten **hantera säkerhets inställningar** för Microsoft Defender ATP.

För att hantera nödvändiga behörigheter kan en **Global administratör** :

- Koppla rollen som **säkerhets administratör** eller **säkerhets ansvarig** i [administrations centret för Microsoft 365](https://admin.microsoft.com/) under **roll**  >  **säkerhets administratör**.
- Kontrol lera inställningar för RBAC för Microsoft Defender ATP i [Microsoft Defender säkerhets Center](https://securitycenter.windows.com/) under **Inställningar**för  >  **behörighets**  >  **roller**. Välj motsvarande roll för att tilldela behörigheten **hantera säkerhets inställningar** .

> [!NOTE]
> För att hantera anpassade identifieringar måste **säkerhets operatörerna** **hantera säkerhets inställningar** i Microsoft Defender ATP om RBAC är aktiverat.

## <a name="create-a-custom-detection-rule"></a>Skapa en anpassad detektions regel
### <a name="1-prepare-the-query"></a>1. förbereda frågan.

I Microsoft 365 säkerhets Center går du till **Avancerad jakt** och väljer en befintlig fråga eller skapar en ny fråga. Kör frågan för att identifiera fel och förstå möjliga resultat när du använder en ny fråga.

>[!IMPORTANT]
>För att förhindra att tjänsten returnerar för många aviseringar begränsas varje regel för att bara generera 100-varningar när den körs. Innan du skapar en regel kan du ställa in din fråga för att undvika att aviseringar visas för normal, daglig aktivitet.


#### <a name="required-columns-in-the-query-results"></a>Kolumner som krävs i frågeresultatet
Om du vill skapa en anpassad detektions regel måste frågan returnera följande kolumner:

- `Timestamp`— används för att ställa in tidsstämpeln för genererade aviseringar
- `ReportId`– aktiverar uppslag för de ursprungliga posterna
- En av följande kolumner som identifierar specifika enheter, användare eller post lådor:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (kuvert avsändare eller RETUR adress)
    - `SenderMailFromAddress` (avsändar adress som visas i e-postklienten)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Stöd för ytterligare enheter läggs till när nya tabeller läggs till i det [avancerade jakt schemat](advanced-hunting-schema-tables.md).

Enkla frågor, till exempel dem som inte använder `project` `summarize` operatorn eller för att anpassa resultat, returnerar normalt dessa vanliga kolumner.

Det finns olika sätt att se till att komplexa frågor returnerar de här kolumnerna. Om du till exempel föredrar att aggregera och inventera efter entitet under en kolumn, `DeviceId` kan du ändå återgå till `Timestamp` och `ReportId` genom att hämta den från den senaste händelsen som rör varje unikt `DeviceId` .

I exempel frågan nedan räknas antalet unika enheter ( `DeviceId` ) med Antivirus identifieringar och använder det här antalet för att endast hitta enheter med fler än fem identifieringar. Om du vill returnera det senaste `Timestamp` och det motsvarande `ReportId` används `summarize` operatorn med `arg_max` funktionen.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> För bättre prestanda för frågor kan du ange ett tids filter som matchar den avsedda användnings frekvensen för regeln. Eftersom den minst oftare är i _24 timmar_täcker filtreringen för den förflutna dagen alla nya data.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. skapa en ny regel och ange aviserings information.

Med frågan i Frågeredigeraren väljer du **skapa detektions regel** och anger följande aviserings information:

- **Identifierings namn**– namnet på identifierings regeln
- **Frekvens**– ett tidsintervall som används för att köra frågan och vidta åtgärder. [Se ytterligare vägledning nedan](#rule-frequency)
- **Aviserings rubrik**– titeln visas med notifieringar utlöst av regeln
- **Allvarlighets grad**— den komponent eller aktivitet som identifieras av regeln
- **Kategori**– hot komponent eller aktivitet som identifieras av regeln
- **Mitre to&CK-teknik**– en eller flera angrepp som identifieras av regeln enligt anvisningarna i [&MITREs ramverk](https://attack.mitre.org/). Det här avsnittet är dolt för vissa aviserings kategorier, inklusive skadlig program vara
- **Beskrivning**– mer information om komponenten eller aktiviteten som identifieras av regeln 
- **Rekommenderade åtgärder**– ytterligare åtgärder som svars handlingar kan ta emot när det gäller en avisering

#### <a name="rule-frequency"></a>Regel frekvens
När du sparar eller redigerar en ny regel körs den och söker efter matchningar från de senaste 30 dagarna. Regeln körs sedan igen med fasta tidsintervall, med en lookback längd utifrån den frekvens du väljer:

- Med ett **dygn**– löper ett dygn runt data från de senaste 30 dagarna
- **Var 12: e**timme – kör var tolfte timme och kontrol lera data från de senaste 24 timmarna
- **Var tredje timme**– kör var tredje timme, kontrol lera data från de senaste 6 timmarna
- **Varje timme**– kör per timme för att kontrol lera data från de senaste 2 timmarna

>[!TIP]
> Matcha tids filtren i frågan med lookback längd. Resultat utanför lookback varaktighet ignoreras.  

Välj den frekvens som motsvarar hur nära du vill övervaka identifieringarna. Överväg organisationens kapacitet för att svara på aviseringarna.

### <a name="3-choose-the-impacted-entities"></a>3. Välj de enheter som påverkas.
Identifiera kolumnerna i frågeresultatet där du förväntar dig att hitta den huvud enhet som påverkas eller påverkas. En fråga kan till exempel returnera avsändare ( `SenderFromAddress` eller `SenderMailFromAddress` )-och mottagar `RecipientEmailAddress` adresser. Att identifiera vilka av de här kolumnerna som representerar huvud enheten som påverkas hjälper tjänsten att aggregera relevanta aviseringar, korrelera problem och åtgärder för mål svar.

Du kan bara välja en kolumn för varje entitetstyp (post låda, användare eller enhet). Kolumner som inte returneras av frågan kan inte markeras.

### <a name="4-specify-actions"></a>4. ange åtgärder.
Din regel för anpassad avkänning kan automatiskt utföra åtgärder på enheter, filer eller användare som returneras av frågan.

#### <a name="actions-on-devices"></a>Åtgärder på enheter
De här åtgärderna tillämpas på enheter i `DeviceId` kolumnen i frågeresultatet:
- **Isolera enhet**– använder Microsoft Defender ATP för att tillämpa fullständig nätverks isolering, så att enheten inte kan ansluta till något program eller någon tjänst. [Läs mer om dator isolering för Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Samla in undersöknings paket**– samlar in enhets information i en zip-fil. [Läs mer om Microsoft Defender-gransknings paketet för ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Kör antivirus-genomsökning**– utför en fullständig Windows Defender Antivirus-genomsökning på enheten
- **Inleda undersökning**– initierar en [Automatisk undersökning](mtp-autoir.md) på enheten
- **Begränsa program körning**– anger begränsningar för enheter för att endast tillåta att filer som är signerade med ett Microsoft-utfärdat certifikat körs. [Läs mer om program begränsningar med Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Åtgärder på filer
När du väljer det här alternativet kan du välja att använda **karantän fil** åtgärden för filer `SHA1` i `InitiatingProcessSHA1` `SHA256` kolumnerna,, eller i `InitiatingProcessSHA256` frågeresultatet. Den här åtgärden tar bort filen från dess nuvarande plats och placerar en kopia i karantän.

#### <a name="actions-on-users"></a>Åtgärder för användare
När **det här** alternativet är markerat vidtas användare i `AccountObjectId` `InitiatingProcessAccountObjectId` kolumnen, eller, eller i `RecipientObjectId` frågeresultatet. Den här åtgärden anger risk nivån för användare till "hög" i Azure Active Directory och utlöser motsvarande [identitets skydds principer](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

> [!NOTE]
> Åtgärden tillåta eller blockera för anpassade identifierings regler stöds för närvarande inte för skydd mot Microsoft-hotet.

### <a name="5-set-the-rule-scope"></a>5. Ange regel omfånget.
Ange omfattningen för att ange vilka enheter som omfattas av regeln. Omfattningen påverkar regler som kontrollerar enheter och påverkar inte regler som bara kontrollerar post lådor och användar konton eller identiteter.

När du ställer in omfattningen kan du välja:

- Alla enheter
- Specifika enhets grupper

Endast data från enheter i omfattning kommer att frågas. Åtgärder kommer också att vidtas för dessa enheter.

### <a name="6-review-and-turn-on-the-rule"></a>6. granska och aktivera regeln.
När du har granskat regeln väljer du **skapa** för att spara den. Den anpassade detektions regeln körs omedelbart. Det körs igen baserat på konfigurerat frekvens för att kontrol lera träffar, generera aviseringar och vidta åtgärder.

## <a name="manage-existing-custom-detection-rules"></a>Hantera befintliga regler för anpassat identifiering
Du kan visa en lista med befintliga regler för anpassad avkänning, kontrol lera deras tidigare körningar och granska de notifieringar de har utlöst. Du kan också köra en regel på begäran och ändra den.

### <a name="view-existing-rules"></a>Visa befintliga regler

Om du vill visa alla befintliga regler för anpassat identifiering navigerar du till **jakt**i  >  **anpassat**läge. På sidan visas alla regler med följande kör information:

- **Senaste körning**– när en regel senast kördes för att kontrol lera frågan och generera aviseringar
- **Senaste körnings status**– oavsett om en regel kördes
- **Nästa kör**-nästa schemalagda körning
- **Status**– om en regel har Aktiver ATS eller inaktiverats

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Visa regel detaljer, ändra regel och kör regel

Om du vill visa omfattande information om en anpassad detektions regel går **du till**  >  **anpassade identifierings** regler och väljer sedan namnet på regeln. Du kan sedan Visa allmän information om regeln, inklusive information om programmets kör status och omfattning. Sidan innehåller också en lista över utlösta varningar och åtgärder.

![Sidan information om anpassad identifierings regel](../../media/custom-detection-details.png)<br>
*Information om anpassade identifierings regler*

Du kan också vidta följande åtgärder på regeln från den här sidan:

- **Kör**– kör regeln omedelbart. Detta återställer också intervallet för nästa körning.
- **Redigera**– ändra regeln utan att ändra frågan
- **Ändra fråga**– redigera frågan i avancerad jakt
- **Aktivera**  /  **Inaktivera**– aktivera regeln eller förhindra att den körs
- **Ta bort**– inaktivera regeln och ta bort den

### <a name="view-and-manage-triggered-alerts"></a>Visa och hantera utlösta aviseringar

I fönstret med regel information (**jakt**efter  >  **anpassade identifieringar**  >  **[regel namn]**) går du till **utlösnings bara aviseringar**som visar de varningar som genererats av matchningar till regeln. Välj en avisering om du vill visa detaljerad information om den och vidta följande åtgärder:

- Hantera varningen genom att ange dess status och klassificering (sant eller falsk)
- Länka aviseringen till en olycka
- Kör frågan som utlöste aviseringen om avancerad jakt

### <a name="review-actions"></a>Gransknings åtgärder
I fönstret med regel detaljer (**jakt**på  >  **anpassade identifieringar**  >  **[regel namn]**) går du till **utlösta åtgärder**som visar vilka åtgärder som utförs baserat på matchningar till regeln.

>[!TIP]
>Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du kolumn kolumnen [&#10003;] till vänster i tabellen.

## <a name="related-topic"></a>Närliggande ämne
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig mer om det avancerade frågespråket](advanced-hunting-query-language.md)
