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
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094813"
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
>De flesta Microsoft Defender för slutpunktskunder [kan använda Microsoft 365 Defender utan ytterligare licenser.](prerequisites.md#licensing-requirements) Om du vill börja gå över dina avancerade arbetsflöden för sökning från Defender för Endpoint aktiverar du [Microsoft 365 Defender.](mtp-enable.md)

Du kan gå över utan att påverka dina befintliga Defender för slutpunktsarbetsflöden. Sparade frågor förblir intakta, och anpassade identifieringsregler fortsätter att köra och generera aviseringar. De visas däremot i Microsoft 365 Defender. 

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
Tabellerna `AlertInfo` `AlertEvidence` ersätter tabellen `DeviceAlertEvents` i Microsoft Defender för Endpoint-schemat. Utöver data om enhetsaviseringar innehåller dessa två tabeller data om aviseringar om identiteter, appar och e-postmeddelanden.

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



## <a name="see-also"></a>Se även
- [Aktivera Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Avancerad sökning i Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)