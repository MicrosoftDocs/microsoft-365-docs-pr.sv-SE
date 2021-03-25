---
title: Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint
description: Läs om hur du justerar dina Frågor om Microsoft Defender för slutpunkt så att du kan använda dem i Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, search, query, telemetry, custom detections, schema, kusto, microsoft 365, mapping
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: c0575b5eaf5a4683f86d4a48dd1076fa2c423acf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076353"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Endpoint till att proaktivt leta efter hot med en bredare uppsättning data. I Microsoft 365 Defender får du åtkomst till data från andra Microsoft 365-säkerhetslösningar, bland annat:

- Microsoft Defender för Endpoint
- Microsoft Defender för Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>De flesta Microsoft Defender för slutpunktskunder [kan använda Microsoft 365 Defender utan ytterligare licenser.](prerequisites.md#licensing-requirements) Om du vill börja gå över dina avancerade arbetsflöden för sökning från Defender för Endpoint [aktiverar du Microsoft 365 Defender.](m365d-enable.md)

Du kan gå över utan att påverka dina befintliga Defender för slutpunktsarbetsflöden. Sparade frågor förblir intakta, och anpassade identifieringsregler fortsätter att köras och generera aviseringar. De kommer dock att visas i Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Schematabeller endast i Microsoft 365 Defender
I [det avancerade sökschemat för Microsoft 365 Defender](advanced-hunting-schema-tables.md) finns ytterligare tabeller som innehåller data från olika säkerhetslösningar för Microsoft 365. Följande tabeller är endast tillgängliga i Microsoft 365 Defender:

| Tabellnamn | Beskrivning |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Filer, IP-adresser, URL:er, användare eller enheter som associeras med aviseringar |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Varningar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive information om allvarlighetsgrad och hotkategorier  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Filrelaterade aktiviteter i molnappar och -tjänster |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Information om bifogade filer i e-postmeddelanden |
| [EmailEvents](advanced-hunting-emailevents-table.md) | E-posthändelser i Microsoft 365, inklusive e-postleverans och blockeringshändelser |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Säkerhetshändelser som inträffar efter leverans, när Microsoft 365 har levererat e-postmeddelanden till mottagarens postlåda |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Information om URL:er för e-postmeddelanden |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD). Den här tabellen omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Kontoinformation från olika källor, inklusive Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Autentiseringshändelser i Active Directory och Microsoft-onlinetjänster |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner |

>[!IMPORTANT]
> Frågor och anpassade identifieringar som använder schematabeller som bara är tillgängliga i Microsoft 365 Defender kan endast visas i Microsoft 365 Defender.

## <a name="map-devicealertevents-table"></a>Karta DeviceAlertEvents-tabell
Tabellerna `AlertInfo` `AlertEvidence` och ersätter tabellen i Microsoft Defender `DeviceAlertEvents` för Endpoint-schemat. Utöver data om enhetsaviseringar innehåller de här två tabellerna data om aviseringar om identiteter, appar och e-postmeddelanden.

Använd följande tabell för att kontrollera hur `DeviceAlertEvents` kolumner mapps till kolumner i `AlertInfo` `AlertEvidence` tabellerna.

>[!TIP]
>Utöver kolumnerna i tabellen nedan innehåller tabellen många andra kolumner som ger en mer holistisk bild `AlertEvidence` av aviseringar från olika källor. [Visa alla kolumner för AviseringVidens](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents-kolumn | Här hittar du samma data i Microsoft 365 Defender |
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
Microsoft Defender för slutpunktsfrågor fungerar som de är såvida de inte refererar till `DeviceAlertEvents` tabellen. Använd de här ändringarna om du vill använda dessa frågor i Microsoft 365 Defender:

- Ersätt `DeviceAlertEvents` med `AlertInfo` .
- Sammanfoga och `AlertInfo` `AlertEvidence` tabellerna för att `AlertId` få motsvarande data.

### <a name="original-query"></a>Ursprunglig fråga
Följande fråga använder i `DeviceAlertEvents` Microsoft Defender för Slutpunkt för att få aviseringar som involverar _powershell.exe:_

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Ändrad fråga
Följande fråga har justerats för användning i Microsoft 365 Defender. I stället för att kontrollera filnamnet direkt `DeviceAlertEvents` från , ansluts `AlertEvidence` filen och söker efter filnamnet i tabellen.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>Migrera anpassade identifieringsregler

När Microsoft Defender för slutpunktsregler redigeras på Microsoft 365 Defender fortsätter de att fungera som förut om den resulterande frågan bara tittar på enhetstabeller. 

Till exempel kommer aviseringar som genereras av anpassade identifieringsregler som endast gäller enhetstabeller att fortsätta levereras till SIEM och generera e-postaviseringar, beroende på hur du har konfigurerat dessa i Microsoft Defender för Slutpunkt. Befintliga regelregler i Defender för Endpoint fortsätter också att gälla.

När du redigerar en Defender för slutpunktsregel så att den frågar om identitets- och e-posttabeller, som bara är tillgängliga i Microsoft 365 Defender, flyttas regeln automatiskt till Microsoft 365 Defender. 

Varningar som genereras av den migrerade regeln:

- Visas inte längre i Defender för Slutpunktsportalen (Microsoft Defender Säkerhetscenter)
- Sluta levereras till din SIEM eller generera e-postaviseringar. Du kan komma runt den här ändringen genom att konfigurera aviseringarna via Microsoft 365 Defender för att få aviseringarna. Du kan använda [Microsoft 365 Defender API för](api-incident.md) att få aviseringar om aviseringar för identifiering av kunder eller relaterade incidenter.
- Kommer inte att döljas av Microsoft Defender för slutpunktsreglerna. För att förhindra att aviseringar skapas för vissa användare, enheter eller postlådor ändrar du motsvarande frågor för att uttryckligen utesluta dessa enheter.

Om du redigerar en regel på det här sättet uppmanas du att bekräfta ändringarna innan de tillämpas.

Nya aviseringar som genereras av anpassade identifieringsregler i Microsoft 365 Defender-portalen visas på en aviseringssida med följande information:

- Aviseringstitel och beskrivning 
- Påverkade tillgångar
- Åtgärder som vidtas som svar på aviseringen
- Frågeresultat som utlöste aviseringen 
- Information om den anpassade identifieringsregeln 
 
![Bild på ny aviseringssida](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a>Skriv frågor utan DeviceAlertEvents

I Microsoft 365 Defender-schemat finns tabellerna och dem för den diverse uppsättningen information som medföljer aviseringar `AlertInfo` `AlertEvidence` från olika källor. 

Om du vill ha samma aviseringsinformation som du fick från tabellen i Microsoft Defender för Endpoint-schemat filtrerar du tabellen efter och sammanar sedan varje unikt ID med tabellen, som ger detaljerad information om händelser och `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` enheter. 

Se exempelfrågan nedan:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Den här frågan ger många fler kolumner än `DeviceAlertEvents` i Microsoft Defender för Endpoint-schemat. Använd bara kolumnerna du är `project` intresserad av för att hålla resultaten hanterbara. I exemplet nedan visas kolumner för projekt som du kan vara intresserad av när undersökningen upptäckte PowerShell-aktivitet:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Om du vill filtrera efter specifika enheter som är inblandade i aviseringarna kan du göra det genom att ange enhetstypen i och det värde du vill `EntityType` filtrera efter. Följande exempel söker efter en specifik IP-adress:

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
- [Avancerad sökning i Microsoft Defender för Slutpunkt](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)