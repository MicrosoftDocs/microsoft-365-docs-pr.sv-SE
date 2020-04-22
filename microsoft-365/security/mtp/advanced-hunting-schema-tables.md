---
title: Datatabeller i microsofts avancerade jaktschema för skydd mot hotskydd
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
ms.openlocfilehash: 93da55287c3b7d7498a9c25f4deeb2615da81675
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633501"
---
# <a name="understand-the-advanced-hunting-schema"></a>Förstå det avancerade jaktschemat

**Gäller:**
- Microsoft Hotskydd



Det [avancerade jaktschemat](advanced-hunting-overview.md) består av flera tabeller som ger antingen händelseinformation eller information om datorer och entiteter. Om du effektivt vill skapa frågor som sträcker sig över flera tabeller måste du förstå tabellerna och kolumnerna i det avancerade jaktschemat.

## <a name="schema-tables"></a>Schematabeller

Följande referens listar alla tabeller i schemat. Varje tabellnamn länkar till en sida som beskriver kolumnnamnen för den tabellen. Tabell- och kolumnnamn visas också i säkerhetscentret som en del av schemarepresentationen på den avancerade jaktskärmen.

| Tabellnamn | Beskrivning |
|------------|-------------|
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP, inklusive allvarlighetsgradinformation och hotkategorisering  |
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Filer, IP-adresser, webbadresser, användare eller enheter som är associerade med aviseringar |
| **[AccountInfo](advanced-hunting-accountinfo-table.md)** | Kontoinformation från olika källor, inklusive Azure Active Directory |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 e-posthändelser, inklusive e-postleverans och blockering av händelser |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Information om filer som är kopplade till e-postmeddelanden |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Information om webbadresser i Microsoft 365-e-postmeddelanden |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Maskininformation, inklusive OS-information |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Nätverksegenskaper för datorer, inklusive kort, IP- och MAC-adresser, samt anslutna nätverk och domäner |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Processskapande och relaterade händelser |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Nätverksanslutning och relaterade händelser |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Filskapande, ändring och andra filsystemhändelser |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Skapande och ändring av registerposter |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inloggningar och andra autentiseringshändelser |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-inläsning av händelser |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Flera händelsetyper, inklusive händelser som utlöses av säkerhetskontroller som Windows Defender Antivirus och utnyttja skydd |
| **[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)** | Certifikatinformation för signerade filer som erhållits från certifikatverifieringshändelser på slutpunkter |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Inventering av programvara på enheter samt alla kända sårbarheter i dessa programvaruprodukter |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | Kunskapsbas för offentliggjorda sårbarheter, inklusive om det är allmänt tillgängligt för att utnyttja kod |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | Hot & bedömningshändelser för sårbarhetshantering, som anger status för olika säkerhetskonfigurationer på enheter |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Kunskapsbas för olika säkerhetskonfigurationer som används av Threat & Vulnerability Management för att bedöma enheter. omfattar kartläggningar till olika standarder och riktmärken  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Filrelaterade aktiviteter i molnappar och molntjänster |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Autentiseringshändelser som registrerats av Active Directory och andra Microsoft-onlinetjänster |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Frågeaktiviteter som utförs mot Active Directory-objekt, till exempel användare, grupper, enheter och domäner |


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
