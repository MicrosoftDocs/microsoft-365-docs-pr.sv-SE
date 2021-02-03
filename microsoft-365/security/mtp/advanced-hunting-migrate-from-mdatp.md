---
title: Migrera avancerade sökfrågor från Microsoft Defender för Slutpunkt
description: Läs om hur du justerar frågor för Microsoft Defender för slutpunkt så att du kan använda dem i Microsoft 365 Defender
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, sökning, fråga, telemetri, anpassade identifieringar, schema, kusto, microsoft 365, mappning
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080751"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrera avancerade sökfrågor från Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Endpoint till att proaktivt leta efter hot med en bredare uppsättning data. I Microsoft 365 Defender får du åtkomst till data från andra säkerhetslösningar för Microsoft 365, bland annat:

- Microsoft Defender för Endpoint
- Microsoft Defender för Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>De flesta Microsoft Defender för slutpunktskunder [kan använda Microsoft 365 Defender utan ytterligare licenser.](prerequisites.md#licensing-requirements) Om du vill börja gå över dina avancerade arbetsflöden för sökning från Defender för Endpoint [aktiverar du Microsoft 365 Defender.](mtp-enable.md)

Du kan gå över utan att påverka dina befintliga Defender för slutpunktsarbetsflöden. Sparade frågor förblir intakta, och anpassade identifieringsregler fortsätter att köras och genererar aviseringar. De visas däremot i Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Schematabeller endast i Microsoft 365 Defender
I [det avancerade sökschemat i Microsoft 365 Defender finns](advanced-hunting-schema-tables.md) fler tabeller som innehåller data från olika säkerhetslösningar från Microsoft 365. Följande tabeller är endast tillgängliga i Microsoft 365 Defender:

| Tabellnamn | Beskrivning |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Filer, IP-adresser, URL:er, användare eller enheter som är associerade med aviseringar |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Varningar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive information om allvarlighetsgrad och hotkategorier  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Filrelaterade aktiviteter i molnappar och -tjänster |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Information om bifogade filer i e-postmeddelanden |
| [EmailEvents](advanced-hunting-emailevents-table.md) | E-posthändelser i Microsoft 365, inklusive e-postleverans och blockeringshändelser |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Säkerhetshändelser som inträffar efter leverans, när Microsoft 365 har levererat e-postmeddelandena till mottagarens postlåda |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Information om URL:er för e-postmeddelanden |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD). Den här tabellen omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Kontoinformation från olika källor, bland annat Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Autentiseringshändelser i Active Directory och Microsofts onlinetjänster |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner |

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents-tabell
Tabellerna `AlertInfo` `AlertEvidence` ersätter tabellen `DeviceAlertEvents` i Microsoft Defender för slutpunktsschemat. Utöver data om enhetsaviseringar innehåller dessa två tabeller data om aviseringar om identiteter, appar och e-postmeddelanden.

Använd följande tabell för att kontrollera hur `DeviceAlertEvents` kolumner mappar till kolumner i `AlertInfo` och `AlertEvidence` tabeller.

>[!TIP]
>Utöver kolumnerna i tabellen nedan innehåller tabellen många andra kolumner som ger en mer övergripande bild `AlertEvidence` av aviseringar från olika källor. [Visa alla kolumner med Aviseringsvidens](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents-kolumn | Så här hittar du samma data i Microsoft 365 Defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` och  `AlertEvidence` tabeller |
| `Timestamp` | `AlertInfo` och  `AlertEvidence` tabeller |
| `DeviceId` | `AlertEvidence` tabell |
| `DeviceName` | `AlertEvidence` tabell |
| `Severity` | `AlertInfo` tabell |
| `Category` | `AlertInfo` tabell |
| `Title` | `AlertInfo` tabell |
| `FileName` | `AlertEvidence` tabell |
| `SHA1` | `AlertEvidence` tabell |
| `RemoteUrl` | `AlertEvidence` tabell |
| `RemoteIP` | `AlertEvidence` tabell |
| `AttackTechniques` | `AlertInfo` tabell |
| `ReportId` | Den här kolumnen används vanligtvis i Microsoft Defender för Slutpunkt för att hitta relaterade poster i andra tabeller. I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen. |
| `Table` | Den här kolumnen används vanligtvis i Microsoft Defender för Slutpunkt för ytterligare händelseinformation i andra tabeller. I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Justera befintliga Microsoft Defender för slutpunktsfrågor
Microsoft Defender för slutpunktsfrågor fungerar som de är om de inte refererar till `DeviceAlertEvents` tabellen. Använd de här ändringarna om du vill använda dessa frågor i Microsoft 365 Defender:

- Ersätt `DeviceAlertEvents` med `AlertInfo` .
- Sammanfoga `AlertInfo` tabellerna och `AlertEvidence` koppla dem för att få motsvarande `AlertId` data.

### <a name="original-query"></a>Ursprunglig fråga
Följande fråga använder i `DeviceAlertEvents` Microsoft Defender för Slutpunkt för att få aviseringar som innebär att _powershell.exe:_

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Ändrad fråga
Följande fråga har justerats för användning i Microsoft 365 Defender. I stället för att kontrollera filnamnet `DeviceAlertEvents` direkt från, sammanfogas `AlertEvidence` det och söker efter filnamnet i tabellen.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>Migrera anpassade identifieringsregler

När Microsoft Defender för slutpunktsregler redigeras i Microsoft 365 Defender fortsätter de att fungera som tidigare om den resulterande frågan bara tittar på enhetstabeller. Till exempel kommer aviseringar som genereras av anpassade identifieringsregler som endast skickar frågor till enhetstabeller att fortsätta levereras till DIN SIEM och generera e-postaviseringar, beroende på hur du har konfigurerat dessa i Microsoft Defender för Endpoint. Befintliga regelregler i Defender för Endpoint fortsätter också att gälla.

När du redigerar en Defender för slutpunktsregel så att den frågar om identitets- och e-posttabeller, som bara är tillgängliga i Microsoft 365 Defender, flyttas regeln automatiskt till Microsoft 365 Defender. 

Varningar som genereras av den migrerade regeln:

- Visas inte längre i Defender för slutpunktsportalen (Microsoft Defender Säkerhetscenter)
- Sluta levereras till din SIEM eller generera e-postaviseringar. Du kan komma runt den här ändringen genom att konfigurera aviseringarna via Microsoft 365 Defender för att få aviseringarna. Du kan använda [Microsoft 365 Defender API](api-incident.md) för att få aviseringar om aviseringar om identifiering av kunder eller relaterade incidenter.
- Kommer inte att döljas av Microsoft Defender för slutpunktsreglerna. För att förhindra att aviseringar skapas för vissa användare, enheter eller postlådor ändrar du motsvarande frågor så att de uttryckligen utesluts.

Om du redigerar en regel på det här sättet uppmanas du att bekräfta att du inte har gjort de här ändringarna.

Nya aviseringar som genereras av anpassade identifieringsregler i Microsoft 365 Defender-portalen visas på en aviseringssida med följande information:

- Aviseringstitel och beskrivning 
- Påverkade tillgångar
- Åtgärder som vidtas som svar på aviseringen
- Frågeresultat som utlöste aviseringen 
- Information om den anpassade identifieringsregeln 
 
![Bild på ny aviseringssida](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a>Skriva frågor utan DeviceAlertEvents

I Microsoft 365 Defender-schemat finns tabeller och tabeller för att passa den diverse uppsättningen information som medföljer `AlertInfo` `AlertEvidence` aviseringar från olika källor. 

Om du vill ha samma aviseringsinformation som du använde för att komma från tabellen i Microsoft Defender för slutpunktsschemat filtrerar du tabellen och sammanfogar sedan varje unikt ID med tabellen, som ger detaljerad information om händelser och `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` enheter. 

Se exempelfrågan nedan:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Den här frågan ger många fler kolumner än `DeviceAlertEvents` i Microsoft Defender för Endpoint-schemat. Använd bara de kolumner du är intresserad av för att hålla resultaten `project` hanterbara. I exemplet nedan visas kolumner som du kan vara intresserad av när undersökningen upptäckte PowerShell-aktivitet:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Om du vill filtrera efter specifika enheter som ingår i aviseringarna kan du göra det genom att ange enhetstypen och värdet du vill `EntityType` filtrera efter. I följande exempel söker du efter en specifik IP-adress:

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>Se även
- [Aktivera Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Avancerad sökning i Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)