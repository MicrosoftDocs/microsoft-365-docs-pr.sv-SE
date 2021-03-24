---
title: Datatabeller i det avancerade sökschemat i Microsoft 365 Defender
description: Läs mer om tabellerna i det avancerade sökschemat för att förstå vilka data du kan köra sökning efter hot på
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data
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
ms.technology: m365d
ms.openlocfilehash: 40cf4404df79ca7d25a9f2ad148ec25dabd32496
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072769"
---
# <a name="understand-the-advanced-hunting-schema"></a>Förstå det avancerade sökschemat

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Det [avancerade sökschemat](advanced-hunting-overview.md) består av flera tabeller som innehåller händelseinformation eller information om enheter, aviseringar, identiteter och andra entitetstyper. För att skapa frågor som sträcker sig över flera tabeller effektivt måste du förstå tabellerna och kolumnerna i det avancerade sökschemat.

## <a name="get-schema-information-in-the-security-center"></a>Hämta schemainformation i säkerhetscentret
När du skapar frågor kan du använda den inbyggda schemareferensen för att snabbt få följande information om varje tabell i schemat:

- **Tabellbeskrivning**– typ av data som finns i tabellen och källan till dessa data.
- **Kolumner**– alla kolumner i tabellen.
- **Åtgärdstyper**– möjliga värden i `ActionType` kolumnen som representerar de händelsetyper som stöds av tabellen. Den här informationen tillhandahålls endast för tabeller som innehåller händelseinformation.
- **Exempelfråga**– exempelfrågor som innehåller hur tabellen kan användas.

### <a name="access-the-schema-reference"></a>Komma åt schemareferensen
Om du snabbt vill komma åt schemareferensen **väljer du åtgärden** Visa referens bredvid tabellnamnet i schemarepresentationen. Du kan också välja **Schemareferens om** du vill söka efter en tabell.   

![Bild som visar hur du kommer åt schemareferensen i portalen ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Lär dig schematabellerna
I följande referens visas alla tabeller i schemat. Varje tabellnamn länkar till en sida som beskriver kolumnnamnen för tabellen. Tabell- och kolumnnamn visas också i säkerhetscentret som en del av schemarepresentationen på den avancerade sökskärmen.

| Tabellnamn | Beskrivning |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Filer, IP-adresser, URL:er, användare eller enheter som associeras med aviseringar |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Varningar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive information om allvarlighetsgrad och hotkategorisering  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Filrelaterade aktiviteter i molnappar och -tjänster |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Händelser som innefattar konton och objekt i Office 365 och andra molnappar och -tjänster |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Flera händelsetyper, inklusive händelser som utlöses av säkerhetskontroller, till exempel Windows Defender Antivirus och sårbarhetsskydd |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Certifikatinformation för signerade filer som erhållits från certifikatverifieringshändelser i slutpunkter |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Skapa, ändra filer och andra filsystemhändelser |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-inläsningshändelser |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Maskininformation, inklusive OS-information |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inloggningar och andra autentiseringshändelser på enheter |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Nätverksanslutning och relaterade händelser |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Nätverksegenskaper för enheter, inklusive fysiska adaptrar, IP- och MAC-adresser, samt anslutna nätverk och domäner |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Skapa processer och relaterade händelser |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Skapa och ändra registerposter |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Hot & sårbarhetshanteringsutvärderingshändelser, som anger status för olika säkerhetskonfigurationer på enheter |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Kunskapsbas av olika säkerhetskonfigurationer som används av Threat & Vulnerability Management för att utvärdera enheter; inkluderar mappningar till olika standarder och riktvärde  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventering av programvara installerad på enheter, inklusive deras versionsinformation och status vid slutet av supporten |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Sårbarheter i programvaran som finns på enheter och listan över tillgängliga säkerhetsuppdateringar som är tillgängliga för varje sårbarhet |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Kunskapsbas för offentligt avslöjat säkerhetsproblem, inklusive om sårbarhetskod är offentligt tillgänglig |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Information om bifogade filer i e-postmeddelanden |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | E-posthändelser i Microsoft 365, inklusive e-postleverans och blockeringshändelser |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Säkerhetshändelser som inträffar efter leverans, när Microsoft 365 har levererat e-postmeddelanden till mottagarens postlåda |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Information om URL:er för e-postmeddelanden |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD). Den här tabellen omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Kontoinformation från olika källor, inklusive Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Autentiseringshändelser i Active Directory och Microsoft-onlinetjänster |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
