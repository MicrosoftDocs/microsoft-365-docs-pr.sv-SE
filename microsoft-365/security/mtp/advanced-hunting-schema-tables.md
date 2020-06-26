---
title: Datatabeller i Microsoft Threat Protection avancerade jaktschema
description: Lär dig mer om tabellerna i det avancerade jaktschemat för att förstå de data du kan köra frågor om hotjakt på
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, data
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
ms.openlocfilehash: 032368e35cdfc991df4c01643e49cee538549f39
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899369"
---
# <a name="understand-the-advanced-hunting-schema"></a>Förstå det avancerade jaktschemat

**Gäller:**
- Microsoft Hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Det [avancerade jaktschemat](advanced-hunting-overview.md) består av flera tabeller som ger antingen händelseinformation eller information om datorer och entiteter. Om du effektivt vill skapa frågor som sträcker sig över flera tabeller måste du förstå tabellerna och kolumnerna i det avancerade jaktschemat.

## <a name="schema-tables"></a>Schematabeller

Följande referens visar alla tabeller i schemat. Varje tabellnamn länkar till en sida som beskriver kolumnnamnen för den tabellen. Tabell- och kolumnnamn visas också i säkerhetscentret som en del av schemarepresentationen på den avancerade jaktskärmen.

| Tabellnamn | Beskrivning |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Filer, IP-adresser, webbadresser, användare eller enheter som är associerade med aviseringar |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP, inklusive allvarlighetsgradinformation och hotkategorisering  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Filrelaterade aktiviteter i molnappar och molntjänster |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Flera händelsetyper, inklusive händelser som utlöses av säkerhetskontroller som Windows Defender Antivirus och utnyttja skydd |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Certifikatinformation för signerade filer som erhållits från certifikatverifieringshändelser på slutpunkter |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Filskapande, ändring och andra filsystemhändelser |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-inläsning av händelser |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Maskininformation, inklusive OS-information |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inloggningar och andra autentiseringshändelser |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Nätverksanslutning och relaterade händelser |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Nätverksegenskaper för datorer, inklusive kort, IP- och MAC-adresser, samt anslutna nätverk och domäner |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Processskapande och relaterade händelser |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Skapande och ändring av registerposter |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Hot & bedömning av sårbarhetshantering, som anger status för olika säkerhetskonfigurationer på enheter |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Kunskapsbas för olika säkerhetskonfigurationer som används av Threat & Vulnerability Management för att bedöma enheter. omfattar kartläggningar till olika standarder och riktmärken  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventering av programvara på enheter samt eventuella kända sårbarheter i dessa programvaruprodukter |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Kunskapsbas för offentliggjorda sårbarheter, inklusive om utnyttjande av kod är allmänt tillgänglig |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Information om filer som är kopplade till e-postmeddelanden |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 e-posthändelser, inklusive e-postleverans och blockering av händelser |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Säkerhetshändelser som inträffar efter leverans, efter att Microsoft 365 har levererat e-postmeddelandena till mottagarens postlåda |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Information om webbadresser i e-postmeddelanden |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Kontoinformation från olika källor, inklusive Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Autentiseringshändelser som registrerats av Active Directory och andra Microsoft-onlinetjänster |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Frågeaktiviteter som utförs mot Active Directory-objekt, till exempel användare, grupper, enheter och domäner |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
