---
title: Datatabeller i det avancerade sökschemat i Microsoft 365 Defender
description: Läs mer om tabellerna i det avancerade sökschemat så att du förstår vilka data du kan köra sökning efter hot på
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, data
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
ms.openlocfilehash: b335ba90479c670d918226caa18f80ee5535f0a1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925067"
---
# <a name="understand-the-advanced-hunting-schema"></a>Förstå det avancerade sökschemat

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Det [avancerade sökschemat](advanced-hunting-overview.md) består av flera tabeller som innehåller händelseinformation eller information om enheter, aviseringar, identiteter och andra entitetstyper. För att skapa frågor som sträcker sig över flera tabeller på ett effektivt sätt måste du förstå tabellerna och kolumnerna i det avancerade sökschemat.

## <a name="get-schema-information-in-the-security-center"></a>Hämta schemainformation i säkerhetscentret
När du skapar frågor kan du använda den inbyggda schemareferensen för att snabbt få följande information om varje tabell i schemat:

- **Tabellbeskrivning**– typ av data som finns i tabellen och datakällan.
- **Kolumner**– alla kolumner i tabellen.
- **Åtgärdstyper**– möjliga värden i `ActionType` kolumnen som representerar de händelsetyper som stöds av tabellen. Den här informationen tillhandahålls endast för tabeller som innehåller händelseinformation.
- **Exempelfråga**– exempelfrågor som innehåller hur tabellen kan användas.

### <a name="access-the-schema-reference"></a>Komma åt schemareferensen
Om du snabbt vill komma åt schemareferensen väljer du **referensåtgärden** Visa bredvid tabellnamnet i schemarepresentationen. Du kan också välja **schemareferens om** du vill söka efter en tabell.   

![Bild som visar hur du kommer åt schemareferensen i portalen ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Lär dig schematabellerna
I följande referens visas alla tabeller i schemat. Varje tabellnamn länkar till en sida som beskriver kolumnnamnen för tabellen. Tabell- och kolumnnamn visas också i säkerhetscentret som en del av schemarepresentationen på den avancerade sökskärmen.

| Tabellnamn | Beskrivning |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Filer, IP-adresser, URL:er, användare eller enheter som är associerade med aviseringar |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Varningar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive allvarlighetsinformation och hotkategorisering  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Filrelaterade aktiviteter i molnappar och -tjänster |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Händelser som innefattar konton och objekt i Office 365 och andra molnappar och -tjänster |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Flera händelsetyper, inklusive händelser som utlöses av säkerhetskontroller som Windows Defender Antivirus och sårbarhetsskydd |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Certifikatinformation för signerade filer som hämtas från certifikatverifieringshändelser på slutpunkter |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Skapa, ändra filer och andra filsystemhändelser |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-inläsningshändelser |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Maskininformation, inklusive OS-information |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inloggningar och andra autentiseringshändelser på enheter |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Nätverksanslutning och relaterade händelser |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Nätverksegenskaper för enheter, inklusive fysiska adaptrar, IP- och MAC-adresser, samt anslutna nätverk och domäner |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Skapa processer och relaterade händelser |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Skapa och ändra registerposter |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Hot & utvärderingshändelser för sårbarhetshantering, som anger status för olika säkerhetskonfigurationer på enheter |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Kunskapsbas av olika säkerhetskonfigurationer som används av & sårbarhetshantering för att utvärdera enheter; inkluderar mappningar till olika standarder och riktvärden  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventering av programvara på enheter och alla kända svagheter i dessa programvaruprodukter |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Kunskapsbas för offentligt säkerhetsproblem, inklusive om sårbarhetskod är allmänt tillgänglig |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Information om bifogade filer i e-postmeddelanden |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | E-posthändelser i Microsoft 365, inklusive e-postleverans och blockeringshändelser |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Säkerhetshändelser som inträffar efter leverans, när Microsoft 365 har levererat e-postmeddelandena till mottagarens postlåda |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Information om URL:er för e-postmeddelanden |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD). Den här tabellen omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Kontoinformation från olika källor, bland annat Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Autentiseringshändelser i Active Directory och Microsofts onlinetjänster |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
