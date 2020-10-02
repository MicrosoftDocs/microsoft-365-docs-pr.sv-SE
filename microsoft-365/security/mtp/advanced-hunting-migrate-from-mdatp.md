---
title: Migrera avancerade frågor från Microsoft Defender ATP
description: Lär dig hur du justerar dina Microsoft Defender ATP-frågor så att du kan använda dem i Microsoft Threat Protection
keywords: Avancerad jakt, Hot jakt, cyberterrorism Threat stöldskydd, Microsoft Threat Protection, Microsoft 365, MTP, m365, Microsoft Defender ATP, mdatp, Sök, fråga, telemetri, anpassade identifieringar, schema, kusto, Microsoft 365, mappning
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: daa89ebf39f8fc6d2110720f61b8d02c074fb484
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338752"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>Migrera avancerade frågor från Microsoft Defender ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft Threat Protection

Flytta dina avancerade arbets flöden från Microsoft Defender ATP för att proaktivt använda en bredare uppsättning data. I Microsoft Threat Protection får du till gång till data från andra Microsoft 365-säkerhetslösningar, bland annat:

- Microsoft Defender Avancerat skydd
- Office 365 Avancerat skydd
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

>[!NOTE]
>De flesta Microsoft Defender ATP-kunder kan [använda Microsoft Threat Protection utan ytterligare licenser](prerequisites.md#licensing-requirements). Om du vill börja överföra dina avancerade arbets flöden från Microsoft Defender ATP [aktiverar du skydd mot Microsoft Threat](mtp-enable.md).

Du kan gå över utan att påverka dina befintliga Microsoft Defender ATP-arbetsflöden. Sparade frågor är oförändrade och anpassade identifierings regler fortsätter att köra och generera aviseringar. De kommer att synas i skydd mot Microsoft Threat. 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>Endast schema tabeller i Microsoft Threat Protection
Ett [Avancerat Antivirus schema för Microsoft Threat Protection](advanced-hunting-schema-tables.md) ger ytterligare tabeller med data från olika Microsoft 365-säkerhetslösningar. Följande tabeller är endast tillgängliga i Microsoft Threat Protection:

| Tabellnamn | Beskrivning |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Filer, IP-adresser, URL: er, användare eller enheter associerade med aviseringar |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP, inklusive allvarlighets GRADS information och hot kategorier  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Filrelaterade aktiviteter i moln program och-tjänster |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Information om bifogade filer i e-postmeddelanden |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365-e-posthändelser, inklusive händelser för e-postleverans och blockering |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Säkerhets händelser som inträffar efter leverans efter att Microsoft 365 har levererat e-postmeddelandet till mottagar post lådan |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Information om URL: er för e-postmeddelanden |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Händelser som berör en lokal domänkontrollant som kör Active Directory (AD). I den här tabellen beskrivs ett antal identitets relaterade händelser och system händelser på domänkontrollanten. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Konto information från olika källor, inklusive Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Autentiseringsproblem för Active Directory och Microsoft Online-tjänster |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner |

## <a name="map-devicealertevents-table"></a>Kart DeviceAlertEvents tabell
`AlertInfo`Tabellerna och `AlertEvidence` ersätter `DeviceAlertEvents` tabellen i Microsoft Defender ATP-schemat. Utöver data om enhets aviseringar innehåller de här två tabellerna data om aviseringar för identiteter, appar och e-postmeddelanden.

Använd följande tabell för att kontrol lera hur `DeviceAlertEvents` kolumnerna mappas till kolumner i `AlertInfo` `AlertEvidence` tabellerna och.

>[!TIP]
>Förutom kolumnerna i följande tabell `AlertEvidence` innehåller tabellen många andra kolumner som ger en mer holistisk bild av notifieringar från olika källor. [Se alla AlertEvidence-kolumner](advanced-hunting-alertevidence-table.md) 

| Kolumnen DeviceAlertEvents | Här hittar du samma data i Microsoft Threat Protection |
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
| `ReportId` | Den här kolumnen används vanligt vis i Microsoft Defender ATP för att hitta relaterade poster i andra tabeller. I Microsoft Threat Protection kan du hämta relaterade data direkt från `AlertEvidence` tabellen. |
| `Table` | Den här kolumnen används vanligt vis i Microsoft Defender ATP för ytterligare information i andra tabeller. I Microsoft Threat Protection kan du hämta relaterade data direkt från `AlertEvidence` tabellen. |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>Justera befintliga Microsoft Defender ATP-frågor
Microsoft Defender ATP-frågor fungerar på samma sätt såvida de inte refererar till `DeviceAlertEvents` tabellen. Tillämpa dessa ändringar för att använda dessa frågor i skydd mot Microsoft Threats:

- Ersätt `DeviceAlertEvents` med `AlertInfo` .
- Gå med i `AlertInfo` och till `AlertEvidence` tabellerna för `AlertId` att få motsvarande data.

### <a name="original-query"></a>Ursprunglig fråga
I följande fråga används `DeviceAlertEvents` Microsoft Defender ATP för att få de meddelanden som berör _powershell.exe_:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Ändrad fråga
Följande fråga har ställts in för användning i Microsoft Threat Protection. I stället för att kontrol lera fil namnet direkt från `DeviceAlertEvents` går det `AlertEvidence` att kontrol lera fil namnet i tabellen.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Relaterade ämnen
- [Aktivera Microsoft Hotskydd](advanced-hunting-query-language.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Avancerad jakt i Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)