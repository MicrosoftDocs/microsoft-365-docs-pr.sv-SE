---
title: Arbeta med avancerade jaktfrågeresultat i Microsoft Threat Protection
description: Få ut det mesta av frågeresultaten som returneras genom avancerad jakt i Microsoft Threat Protection
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade upptäckter, schema, kusto, microsoft 365, Microsoft Threat Protection, visualisering, diagram, filter, detaljgranskning
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
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929248"
---
# <a name="work-with-advanced-hunting-query-results"></a>Arbeta med avancerade jaktfrågeresultat

**Gäller:**
- Microsofts hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Även om du kan konstruera dina [avancerade jaktfrågor](advanced-hunting-overview.md) för att returnera mycket exakt information, kan du också arbeta med frågeresultaten för att få ytterligare insikt och undersöka specifika aktiviteter och indikatorer. Du kan vidta följande åtgärder för frågeresultaten:

- Visa resultat som en tabell eller ett diagram
- Exportera tabeller och diagram
- Öka detaljnivån till detaljerad information om entitet
- Justera dina frågor direkt från resultaten eller tillämpa filter

## <a name="view-query-results-as-a-table-or-chart"></a>Visa frågeresultat som en tabell eller ett diagram
Som standard visar avancerad jakt frågeresultat som tabelldata. Du kan också visa samma data som ett diagram. Avancerad jakt stöder följande vyer:

| Visa typ | Beskrivning |
| -- | -- |
| **Tabell** | Visar frågeresultatet i tabellformat |
| **Stapeldiagram** | Återger en serie unika objekt på x-axeln som lodräta staplar vars höjder representerar numeriska värden från ett annat fält |
| **Staplat stapeldiagram** | Återger en serie unika objekt på x-axeln som staplade lodräta staplar vars höjder representerar numeriska värden från ett eller flera andra fält |
| **Cirkeldiagram** | Återger avsnittspäror som representerar unika objekt. Storleken på varje cirkel representerar numeriska värden från ett annat fält. |
| **Donut diagram** | Återger avsnittsbågar som representerar unika objekt. Längden på varje båge representerar numeriska värden från ett annat fält. |
| **Linjediagram** | Ritar numeriska värden för en serie unika objekt och kopplar samman de ritade värdena |
| **Punktdiagram** | Ritar numeriska värden för en serie unika objekt |
| **Områdesdiagram** | Ritar numeriska värden för en serie unika objekt och fyller avsnitten under de ritade värdena |

### <a name="construct-queries-for-effective-charts"></a>Konstruera frågor för effektiva diagram
Vid rendering av diagram identifierar avancerad jakt automatiskt kolumner av intresse och de numeriska värdena som ska aggregeras. Skapa dina frågor för att returnera de specifika värden som du vill se visualiseras för att få meningsfulla diagram. Här är några exempelfrågor och de resulterande diagrammen.

#### <a name="alerts-by-severity"></a>Varningar efter allvarlighetsgrad
Använd `summarize` operatorn för att få ett numeriskt antal av de värden som du vill kartlägga. Frågan nedan använder `summarize` operatorn för att få antalet aviseringar efter allvarlighetsgrad.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
När resultaten återges visas varje allvarlighetsgrad i ett stapeldiagram:

![Bild av avancerade jaktfrågeresultat](../../media/advanced-hunting-column-chart.jpg)
som visas som ett stapeldiagram*Frågeresultat för aviseringar efter allvarlighetsgrad som visas som ett stapeldiagram*

#### <a name="alert-severity-by-operating-system"></a>Allvarlighetsgrad för aviseringar efter operativsystem
Du kan också `summarize` använda operatorn för att förbereda resultat för att kartlägga värden från flera fält. Du kanske till exempel vill förstå hur allvarlighetsgrader för aviseringar fördelas över operativsystem (OS). 

Frågan nedan använder `join` en operator för att `DeviceInfo` hämta OS-information från tabellen och sedan används `summarize` för att räkna värden i både kolumnerna `OSPlatform` och `Severity` kolumnerna:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Dessa resultat visualiseras bäst med hjälp av ett staplat stapeldiagram:

![Bild av avancerade jaktfrågeresultat som](../../media/advanced-hunting-stacked-chart.jpg)
visas som ett staplat diagram*Frågeresultat för aviseringar efter operativsystem och allvarlighetsgrad som visas som ett staplat diagram*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Nätfiskemeddelanden på de tio bästa avsändarna
Om du har att göra med en lista med värden som `Top` inte är begränsad kan du använda operatorn för att bara kartlägga de värden som har flest instanser. Om du till exempel vill hämta de tio bästa avsändarna med de mest nätfiskemeddelanden använder du frågan nedan:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Använd cirkeldiagramvyn för att effektivt visa distributionen mellan de populäraste domänerna:

![Bild av avancerade jaktfrågeresultat](../../media/advanced-hunting-pie-chart.jpg)
som visas som ett*cirkeldiagram Cirkeldiagram som visar distribution av nätfiskemeddelanden över de vanligaste avsändande domänerna*

#### <a name="file-activities-over-time"></a>Filaktiviteter över tid
Med `summarize` hjälp av `bin()` operatören med funktionen kan du söka efter händelser som involverar en viss indikator över tid. Frågan nedan räknar händelser `invoice.doc` som involverar filen med 30 minuters intervall för att visa toppar i aktivitet som är relaterade till filen:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
Linjediagrammet nedan belyser tydligt `invoice.doc`tidsperioder med mer aktivitet som omfattar: 

![Bild av avancerade jaktfrågeresultat](../../media/advanced-hunting-line-chart.jpg)
som visas som ett linjediagram*Linjediagram som visar antalet händelser som involverar en fil över tid*


## <a name="export-tables-and-charts"></a>Exportera tabeller och diagram
När du har kört en fråga väljer du **Exportera** för att spara resultaten i den lokala filen. Den valda vyn avgör hur resultaten exporteras:

- **Tabellvy** – frågeresultaten exporteras i tabellform som en Microsoft Excel-arbetsbok
- **Alla diagram** – frågeresultaten exporteras som en JPEG-bild av det renderade diagrammet

## <a name="drill-down-from-query-results"></a>Öka detaljnivån från frågeresultat
Om du vill visa mer information om entiteter, till exempel datorer, filer, användare, IP-adresser och webbadresser, klickar du bara på entitetsidentifieraren i frågeresultatet. Då öppnas en detaljerad profilsida för den valda entiteten i Microsoft Defender Security Center.

## <a name="tweak-your-queries-from-the-results"></a>Justera dina frågor från resultaten
Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan. Du kan använda alternativen för att:

- Leta uttryckligen efter det`==`valda värdet ( )
- Uteslut det valda värdet`!=`från frågan ( )
- Få mer avancerade operatorer för att lägga `contains`till `starts with` värdet i frågan, till exempel`ends with` 

![Bild på avancerad jaktresultatuppsättning](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrera frågeresultaten
Filtren som visas till höger ger en sammanfattning av resultatuppsättningen. Varje kolumn har ett eget avsnitt som visar de distinkta värden som hittats för den kolumnen och antalet instanser.

Förfina frågan genom att `+` `-` markera knapparna eller på de värden som du vill inkludera eller utesluta och sedan välja **Kör fråga**.

![Bild på avancerat jaktfilter](../../media/advanced-hunting-filter.png)

När du har tillämpat filtret för att ändra frågan och sedan köra frågan uppdateras resultaten i enlighet med detta.

## <a name="related-topics"></a>Relaterade ämnen
- [Avancerad jaktöversikt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Tillämpa metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
