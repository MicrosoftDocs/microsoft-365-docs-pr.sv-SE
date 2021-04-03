---
title: Avancerad referens för sökschema
description: Läs mer om tabellerna i det avancerade sökschemat för att förstå vilka data du kan köra sökning efter hot på.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, data
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: ce87b6e9e462ba5bd1bab1542c41ac72092dabd4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500594"
---
# <a name="understand-the-advanced-hunting-schema"></a>Förstå det avancerade sökschemat

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Det [avancerade schemat för](advanced-hunting-overview.md) sökning består av flera tabeller som innehåller händelseinformation eller information om enheter och andra enheter. För att skapa frågor som sträcker sig över flera tabeller effektivt måste du förstå tabellerna och kolumnerna i det avancerade sökschemat.

## <a name="get-schema-information-in-the-security-center"></a>Hämta schemainformation i säkerhetscentret
När du skapar frågor kan du använda den inbyggda schemareferensen för att snabbt få följande information om varje tabell i schemat:

- **Tabellbeskrivning**– typ av data som finns i tabellen och källan till dessa data.
- **Kolumner**– alla kolumner i tabellen.
- **Åtgärdstyper**– möjliga värden i `ActionType` kolumnen som representerar de händelsetyper som stöds av tabellen. Detta tillhandahålls endast för tabeller som innehåller händelseinformation.
- **Exempelfråga**– exempelfrågor som innehåller hur tabellen kan användas.

### <a name="access-the-schema-reference"></a>Komma åt schemareferensen
Om du snabbt vill komma åt schemareferensen **väljer du åtgärden** Visa referens bredvid tabellnamnet i schemarepresentationen. Du kan också välja **Schemareferens om** du vill söka efter en tabell.

![Bild som visar hur du kommer åt schemareferensen i portalen](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a>Lär dig schematabellerna

I följande referens visas alla tabeller i det avancerade sökschemat. Varje tabellnamn länkar till en sida som beskriver kolumnnamnen för tabellen.

Tabell- och kolumnnamn visas också i Microsoft Defender Säkerhetscenter, i schemarepresentationen på den avancerade sökskärmen.

| Tabellnamn | Beskrivning |
|------------|-------------|
| **[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)** | Varningar i Microsoft Defender Säkerhetscenter |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Enhetsinformation, inklusive OS-information |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Nätverksegenskaper för enheter, inklusive adaptrar, IP- och MAC-adresser, samt anslutna nätverk och domäner |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Skapa processer och relaterade händelser |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Nätverksanslutning och relaterade händelser |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Skapa, ändra filer och andra filsystemhändelser |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Skapa och ändra registerposter |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inloggningar och andra autentiseringshändelser |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-inläsningshändelser |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Flera händelsetyper, inklusive händelser som utlöses av säkerhetskontroller, till exempel Microsoft Defender Antivirus och sårbarhetsskydd |
| **[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)** | Certifikatinformation för signerade filer som erhållits från certifikatverifieringshändelser i slutpunkter |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventering av programvara installerad på enheter, inklusive deras versionsinformation och status vid slutet av supporten |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Sårbarheter i programvaran som finns på enheter och listan över tillgängliga säkerhetsuppdateringar som är tillgängliga för varje sårbarhet |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Kunskapsbas för offentligt avslöjat säkerhetsproblem, inklusive om sårbarhetskod är offentligt tillgänglig |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Hot & sårbarhetshanteringsutvärderingshändelser, som anger status för olika säkerhetskonfigurationer på enheter |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Kunskapsbas av olika säkerhetskonfigurationer som används av Threat & Vulnerability Management för att utvärdera enheter; inkluderar mappningar till olika standarder och riktvärde |


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](overview-custom-detections.md)
- [Avancerade dataschemaändringar för sökning](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
