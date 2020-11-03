---
title: Migrera frågor om avancerade jakt från Microsoft Defender för slut punkt
description: Lär dig hur du justerar Microsoft Defender för slut punkts frågor så att du kan använda dem i Microsoft 365 Defender
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846862"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrera frågor om avancerade jakt från Microsoft Defender för slut punkt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Flytta dina avancerade jakt arbets flöden från Microsoft Defender för slut punkt för att proaktivt använda en bredare uppsättning data. I Microsoft 365 Defender får du till gång till data från andra säkerhetslösningar från Microsoft 365, till exempel:

- Microsoft Defender för slut punkt
- Microsoft Defender för Office 365
- Microsoft Cloud App Security
- Microsoft Defender för identitet

>[!NOTE]
>De flesta Microsoft Defender för slut punkter kan [använda Microsoft 365 Defender utan ytterligare licenser](prerequisites.md#licensing-requirements). Om du vill börja överta dina avancerade arbets flöden från Defender för slut punkt [aktiverar du Microsoft 365 Defender](mtp-enable.md).

Du kan gå över utan att påverka dina befintliga Defender för slut arbets flöden. Sparade frågor är oförändrade och anpassade identifierings regler fortsätter att köra och generera aviseringar. De kommer att synas i Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Schema tabeller i Microsoft 365 Defender
[Microsoft 365 Defender Advanced jakt-schemat](advanced-hunting-schema-tables.md) innehåller ytterligare tabeller med data från olika Microsoft 365-säkerhetslösningar. Följande tabeller är endast tillgängliga i Microsoft 365 Defender:

| Tabellnamn | Beskrivning |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Filer, IP-adresser, URL: er, användare eller enheter associerade med aviseringar |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Aviseringar från Microsoft Defender för slut punkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive allvarlighets GRADS information och hot kategorier  |
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
`AlertInfo`Tabellerna och `AlertEvidence` ersätter `DeviceAlertEvents` tabellen i Microsoft Defender för slut punkts schema. Utöver data om enhets aviseringar innehåller de här två tabellerna data om aviseringar för identiteter, appar och e-postmeddelanden.

Använd följande tabell för att kontrol lera hur `DeviceAlertEvents` kolumnerna mappas till kolumner i `AlertInfo` `AlertEvidence` tabellerna och.

>[!TIP]
>Förutom kolumnerna i följande tabell `AlertEvidence` innehåller tabellen många andra kolumner som ger en mer holistisk bild av notifieringar från olika källor. [Se alla AlertEvidence-kolumner](advanced-hunting-alertevidence-table.md) 

| Kolumnen DeviceAlertEvents | Här hittar du samma data i Microsoft 365 Defender |
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
| `ReportId` | Den här kolumnen används vanligt vis i Microsoft Defender för slut punkter för att hitta relaterade poster i andra tabeller. I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen. |
| `Table` | Den här kolumnen används vanligt vis i Microsoft Defender för att få ytterligare information i andra tabeller. I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Justera befintliga Microsoft Defender för slut punkts frågor
Microsoft Defender för slut punkts frågor fungerar på samma sätt såvida den inte refererar till `DeviceAlertEvents` tabellen. Tillämpa dessa ändringar för att använda dessa frågor i Microsoft 365 Defender:

- Ersätt `DeviceAlertEvents` med `AlertInfo` .
- Gå med i `AlertInfo` och till `AlertEvidence` tabellerna för `AlertId` att få motsvarande data.

### <a name="original-query"></a>Ursprunglig fråga
I följande fråga används `DeviceAlertEvents` Microsoft Defender för slut punkt för att få aviseringar som berör _powershell.exe_ :

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Ändrad fråga
Följande fråga har ställts in för användning i Microsoft 365 Defender. I stället för att kontrol lera fil namnet direkt från `DeviceAlertEvents` går det `AlertEvidence` att kontrol lera fil namnet i tabellen.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Relaterade ämnen
- [Aktivera Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Avancerad jakt i Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)