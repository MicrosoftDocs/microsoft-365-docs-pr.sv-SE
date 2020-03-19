---
title: Datatabeller i Microsoft Threat Protection avancerade jaktschema
description: Läs mer om tabellerna i det avancerade jaktschemat för att förstå de data du kan köra hotjaktsfrågor på
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, data
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
ms.openlocfilehash: bb3eae9fff658ee1cbb7f80fa3ff15f2335a9a3a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809004"
---
# <a name="understand-the-advanced-hunting-schema"></a>Förstå det avancerade jaktschemat

**Gäller:**
- Skydd av Hot mot Microsoft



Det [avancerade jaktschemat](advanced-hunting-overview.md) består av flera tabeller som tillhandahåller antingen händelseinformation eller information om datorer och entiteter. Om du vill skapa frågor som sträcker sig över flera tabeller måste du förstå tabellerna och kolumnerna i det avancerade jaktschemat.

## <a name="schema-tables"></a>Schematabeller

Följande referens visar alla tabeller i schemat. Varje tabellnamn länkar till en sida som beskriver kolumnnamnen för den tabellen. Tabell- och kolumnnamn visas också i säkerhetscentret som en del av schemarepresentationen på den avancerade jaktskärmen.

| Tabellnamn | Beskrivning |
|------------|-------------|
| **[DeviceInfo (på plats)](advanced-hunting-deviceinfo-table.md)** | Maskininformation, inklusive OS-information |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Nätverksegenskaper för datorer, inklusive kort, IP- och MAC-adresser, samt anslutna nätverk och domäner |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Skapa processer och relaterade händelser |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Nätverksanslutning och relaterade händelser |
| **[DeviceFileEvents (På video)](advanced-hunting-devicefileevents-table.md)** | Filskapande, ändring och andra filsystemhändelser |
| **[EnhetsregisterHändelser](advanced-hunting-deviceregistryevents-table.md)** | Skapande och ändring av registerposter |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inloggningar och andra autentiseringshändelser |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-inläsningshändelser |
| **[Enhetshändelser](advanced-hunting-deviceevents-table.md)** | Flera händelsetyper, inklusive händelser som utlöses av säkerhetskontroller som Windows Defender Antivirus och utnyttja skydd |
| **[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)** | Certifikatinformation om signerade filer som erhållits från certifikatverifieringshändelser på slutpunkter |
| **[E-postHändelser](advanced-hunting-emailevents-table.md)** | Office 365-e-posthändelser, inklusive e-postleverans och blockering av händelser |
| **[E-postAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Information om filer som är kopplade till Office 365-e-postmeddelanden |
| **[E-postUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Information om webbadresser i Office 365-e-postmeddelanden |
| **[DeviceTvmSoftwareInventorySårbarheter](advanced-hunting-tvm-softwareinventory-table.md)** | Inventering av programvara på enheter samt alla kända sårbarheter i dessa programvaruprodukter |
| **[DeviceTvmSoftwareSårbarheterKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | Kunskapsbas för offentligt avslöjade sårbarheter, inklusive om exploaterar kod är allmänt tillgänglig |
| **[DeviceTvmSecureConfigurationBedömning](advanced-hunting-tvm-configassessment-table.md)** | Hot & sårbarhetshanteringsbedömningshändelser, som anger status för olika säkerhetskonfigurationer på enheter |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Kunskapsbas för olika säkerhetskonfigurationer som används av Threat & Sårbarhetshantering för att bedöma enheter. omfattar kartläggningar till olika standarder och riktmärken  |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
