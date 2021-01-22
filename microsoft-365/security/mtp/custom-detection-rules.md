---
title: Skapa och hantera anpassade identifieringsregler i Microsoft 365 Defender
description: Lär dig hur du skapar och hanterar anpassade identifieringsregler baserat på avancerade sökfrågor
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, anpassade identifieringar, regler, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, behörigheter, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8c7e47e66f9e5543cc122c5b5154207cae836d2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932928"
---
# <a name="create-and-manage-custom-detections-rules"></a>Skapa och hantera regler för anpassade identifieringar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Anpassade identifieringsregler är regler som du kan utforma och modifiera [med avancerade sökfrågor.](advanced-hunting-overview.md) Med dessa regler kan du proaktivt övervaka olika händelser och systemhändelser, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter. Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.

## <a name="required-permissions-for-managing-custom-detections"></a>Behörigheter som krävs för att hantera anpassade identifieringar

För att kunna hantera anpassade identifieringar måste du tilldelas en av följande roller:

- **Säkerhetsadministratör**– Användare med den här [Azure Active Directory-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera säkerhetsinställningar i Microsoft 365 säkerhetscenter och andra portaler och tjänster.

- **Säkerhetsoperator**– Användare med den här [Azure Active Directory-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera aviseringar och ha global skrivskyddsåtkomst till säkerhetsrelaterade funktioner, inklusive all information i Microsoft 365 säkerhetscenter. Den här rollen är tillräcklig för att hantera anpassade identifieringar endast om rollbaserad åtkomstkontroll (RBAC) har inaktiverats i Microsoft Defender för Slutpunkt. Om du har konfigurerat RBAC behöver du också behörigheten **Hantera säkerhetsinställningar för** Defender för Endpoint.

För att hantera behörigheter som krävs **kan en global administratör:**

- Tilldela rollen **som säkerhetsadministratör** **eller säkerhetsoperator** i [administrationscentret för Microsoft 365](https://admin.microsoft.com/) under **Roller**  >  **– säkerhetsadministratör.**
- Kontrollera RBAC-inställningarna för Microsoft Defender för slutpunkt i [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com/) under **Inställningsbehörighetsroller.**  >    >   Välj motsvarande roll för att tilldela **behörigheten Hantera säkerhetsinställningar.**

> [!NOTE]
> Om du vill hantera anpassade identifieringar **behöver** säkerhetsoperatorerna behörigheten hantera säkerhetsinställningar i Microsoft Defender för Endpoint om RBAC är aktiverat. 

## <a name="create-a-custom-detection-rule"></a>Skapa en anpassad identifieringsregel
### <a name="1-prepare-the-query"></a>1. Förbereda frågan.

I Microsoft 365 säkerhetscenter går du till **Avancerad** sökning och väljer en befintlig fråga eller skapar en ny fråga. När du använder en ny fråga kör du frågan för att identifiera fel och förstå möjliga resultat.

>[!IMPORTANT]
>För att förhindra att tjänsten returnerar för många aviseringar är varje regel begränsad till att generera endast 100 aviseringar när den körs. Innan du skapar en regel kan du justera frågan så att du inte aviserar om vanliga dagliga aktiviteter.


#### <a name="required-columns-in-the-query-results"></a>Obligatoriska kolumner i frågeresultatet
Om du vill skapa en anpassad identifieringsregel måste frågan returnera följande kolumner:

- `Timestamp`– används för att ange tidsstämpeln för genererade aviseringar
- `ReportId`– aktiverar uppslag för de ursprungliga posterna
- En av följande kolumner som identifierar specifika enheter, användare eller postlådor:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (kuvertavsändare Return-Path adress)
    - `SenderMailFromAddress` (avsändaradress visas i e-postklienten)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Stöd för ytterligare enheter läggs till när nya tabeller läggs till i det [avancerade sökschemat.](advanced-hunting-schema-tables.md)

Enkla frågor, till exempel de som inte använder operatorn eller för att anpassa eller sammanställa resultat, returnerar `project` `summarize` vanligtvis dessa gemensamma kolumner.

Det finns olika sätt att se till att mer komplexa frågor returnerar dessa kolumner. Om du till exempel föredrar att aggregera och räkna efter entitet under en kolumn, till exempel, kan du fortfarande returnera och genom att hämta den från den senaste händelsen som innefattar `DeviceId` `Timestamp` varje `ReportId` `DeviceId` unik.

I exempelfrågan nedan räknas antalet unika enheter () med antivirusidentifiering och antalet används för att endast hitta de enheter som har `DeviceId` fler än fem identifieringar. För att returnera det `Timestamp` senaste och motsvarande används `ReportId` `summarize` operatorn med `arg_max` funktionen.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> För bättre frågeprestanda kan du ange ett tidsfilter som matchar den avsedda körfrekvensen för regeln. Eftersom det minsta antalet körningar _är en gång per_ dygn täcker filtreringen för den senaste dagen alla nya data.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Skapa en ny regel och ange aviseringsinformation.

Med frågan i frågeredigeraren väljer du **Skapa identifieringsregel** och anger följande aviseringsinformation:

- **Identifieringsnamn**– namnet på identifieringsregeln
- **Frekvens**– intervall för att köra frågan och vidta åtgärder. [Se ytterligare vägledning nedan](#rule-frequency)
- **Aviseringsrubrik**– rubrik som visas med aviseringar som utlöses av regeln
- **Allvarlighetsgrad**– potentiell risk för komponenten eller aktiviteten som identifieras av regeln
- **Kategori**– hotkomponent eller aktivitet som identifieras av regeln
- **MITRE ATT&CK-tekniker –** en eller flera attacktekniker som identifieras av regeln enligt [MITRE ATT&CK-ramverket.](https://attack.mitre.org/) Det här avsnittet är dolt för vissa aviseringskategorier, till exempel skadlig kod, utpressningstrojaner, misstänkt aktivitet och oönskad programvara
- **Beskrivning**– mer information om komponenten eller aktiviteten som identifieras av regeln 
- **Rekommenderade åtgärder**– ytterligare åtgärder som svarare kan vidta för att svara på en avisering

#### <a name="rule-frequency"></a>Regelfrekvens
När du sparar eller redigerar en ny regel körs den och söker efter matchningar från de senaste 30 dagarnas data. Regeln körs sedan igen med fasta intervall och tillämpar en sökvaraktighet baserat på den frekvens du väljer:

- **Körs en gång per dygn** och kontrollerar data från de senaste 30 dagarna
- **En gång per dygn** körs var 12:e timme och data från de senaste 24 timmarna kontrolleras
- **Var 3:e** timme körs var tredje timme och kontrollerar data från de senaste 6 timmarna
- **Varje timme** körs varje timme och du kontrollerar data från de senaste två timmarna

>[!TIP]
> Matcha tidsfiltren i frågan med söktiden. Resultat utanför återställningsvaraktigheten ignoreras.  

Välj hur ofta du vill övervaka identifieringar. Tänk på organisationens kapacitet att svara på aviseringarna.

### <a name="3-choose-the-impacted-entities"></a>3. Välj de enheter som påverkas.
Identifiera kolumnerna i frågeresultatet där du förväntar dig att hitta den primära påverkade eller påverkade enheten. En fråga kan till exempel returnera avsändarens ( `SenderFromAddress` `SenderMailFromAddress` eller) och mottagarens ( `RecipientEmailAddress` ) adresser. Genom att identifiera vilka av dessa kolumner som representerar den viktigaste påverkade enheten bidrar du till att tjänsten sammanställer relevanta aviseringar, korrelerar incidenter och målsvarsåtgärder.

Du kan bara välja en kolumn för varje entitetstyp (postlåda, användare eller enhet). Kolumner som inte returneras av frågan kan inte väljas.

### <a name="4-specify-actions"></a>4. Ange åtgärder.
Den anpassade identifieringsregeln kan automatiskt utföra åtgärder på enheter, filer eller användare som returneras av frågan.

#### <a name="actions-on-devices"></a>Åtgärder på enheter
De här åtgärderna tillämpas på enheter `DeviceId` i kolumnen med frågeresultat:
- **Identifiera enhet**– använder Microsoft Defender för Endpoint för att tillämpa fullständig nätverksisolering och hindra enheten från att ansluta till ett program eller en tjänst. [Läs mer om Microsoft Defender för slutpunktsisolering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- Samla in **undersökningspaket**– samlar in enhetsinformation i en ZIP-fil. [Läs mer om undersökningspaket för Microsoft Defender för slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Kör en antivirussökning**– utför en fullständig genomsökning av Windows Defender Antivirus på enheten
- **Initiera undersökning**– initierar [en automatiserad](mtp-autoir.md) undersökning på enheten
- **Begränsa programkörning –** anger begränsningar för enheten så att endast filer som har signerats med ett microsoft-utfärdat certifikat kan köras. [Läs mer om appbegränsningar med Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Åtgärder för filer
Med det här alternativet kan du välja att **tillämpa** filåtgärden karantän för filer i `SHA1` , eller kolumnen i `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` frågeresultaten. Den här åtgärden tar bort filen från dess aktuella plats och placerar en kopia i karantän.

#### <a name="actions-on-users"></a>Åtgärder för användare
Med det här **alternativet vidtas åtgärden** Markera användare som komprometterad för användare i eller kolumnen i `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` frågeresultaten. Den här åtgärden anger att användarnas risknivå ska vara "hög" i Azure Active Directory, vilket utlöser motsvarande [principer för identitetsskydd.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> Åtgärden tillåt eller blockering för anpassade identifieringsregler stöds för närvarande inte i Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Ange regelns omfattning.
Ange omfattningen för att ange vilka enheter som omfattas av regeln. Omfattningen påverkar regler som kontrollerar enheter och påverkar inte regler som bara kontrollerar postlådor och användarkonton eller identiteter.

När du anger omfattningen kan du välja:

- Alla enheter
- Specifika enhetsgrupper

Endast data från enheter i omfattningen kommer att tillfrågas. Dessutom vidtas åtgärder endast på de enheterna.

### <a name="6-review-and-turn-on-the-rule"></a>6. Granska och aktivera regeln.
När du har granskat regeln väljer du **Skapa för** att spara den. Regeln för anpassad identifiering körs direkt. Körs igen baserat på konfigurerad frekvens för att söka efter matchningar, generera aviseringar och vidta svarsåtgärder.

## <a name="manage-existing-custom-detection-rules"></a>Hantera befintliga regler för anpassad identifiering
Du kan visa listan över befintliga anpassade identifieringsregler, kontrollera deras tidigare körningar och granska de aviseringar som de har utlöst. Du kan även köra en regel på begäran och ändra den.

### <a name="view-existing-rules"></a>Visa befintliga regler

Om du vill visa alla befintliga anpassade identifieringsregler går du till  >  **Söka efter anpassade identifieringar.** På sidan visas alla regler med följande körinformation:

- **Senaste körningen**– när en regel senast körts för att söka efter frågematchningar och generera aviseringar
- **Status för senaste körningen**– om en regel kördes som den ska
- **Nästa körning**– nästa schemalagda körning
- **Status**– om en regel har aktiverats eller inaktiverats

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Visa regeldetaljer, ändra regel och kör regel

Om du vill visa omfattande information om en anpassad identifieringsregel går du till Anpassade  >  **identifieringar för** söka och väljer sedan namnet på regeln. Du kan sedan visa allmän information om regeln, inklusive information om dess körningsstatus och omfattning. På sidan finns också en lista med utlösande aviseringar och åtgärder.

![Informationssida för anpassad identifieringsregel](../../media/custom-detection-details.png)<br>
*Information om anpassad identifieringsregel*

Du kan också utföra följande åtgärder på regeln från den här sidan:

- **Kör**– kör regeln direkt. Detta återställer också intervallet för nästa körning.
- **Redigera**– ändra regeln utan att ändra frågan
- **Ändra fråga**– redigera frågan i avancerad sökning
- **Aktivera**  /  **Inaktivera –** aktivera regeln eller hindra den från att köras
- **Ta** bort – inaktivera regeln och ta bort den

### <a name="view-and-manage-triggered-alerts"></a>Visa och hantera utlösande aviseringar

På skärmen med regeldetaljer **(Om** anpassade identifieringar av uppgifter  >    >  **[Regelnamn]**), går du till Utlösade aviseringar, som visar de aviseringar som genereras av matchningar mot regeln. Välj en avisering om du vill visa detaljerad information om den och vidta följande åtgärder:

- Hantera aviseringen genom att ange dess status och klassificering (sant eller falskt meddelande)
- Länka aviseringen till en händelse
- Kör frågan som utlöste aviseringen på avancerad sökning

### <a name="review-actions"></a>Granska åtgärder
På skärmen med regeldetaljer **(För** anpassade identifieringar av uppgifter  >    >  **[Regelnamn]**) går du till Åtgärder som utlöses och visar de åtgärder som vidtas baserat på matchningar mot regeln.

>[!TIP]
>Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du markeringskolumnen [&#10003;] till vänster om tabellen.

## <a name="related-topic"></a>Relaterat ämne
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig det avancerade språket för sökfrågor](advanced-hunting-query-language.md)
