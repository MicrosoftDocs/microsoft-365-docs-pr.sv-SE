---
title: Arbeta med avancerade jaktfrågeresultat i Microsoft Threat Protection
description: Få ut det mesta av frågeresultaten som returneras av avancerad jakt i Microsoft Threat Protection
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade identifieringar, schema, kusto, microsoft 365, Microsoft Threat Protection, visualisering, diagram, filter, drill-down
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
ms.openlocfilehash: 14afd3c098c99a6e1e6ccfc7e9f6accbf8bf0e7d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899092"
---
# <a name="work-with-advanced-hunting-query-results"></a>Arbeta med avancerade jaktfrågeresultat

**Gäller:**
- Microsoft Hotskydd

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
| **Cirkeldiagram** | Återger avsnittspajer som representerar unika objekt. Storleken på varje cirkel representerar numeriska värden från ett annat fält. |
| **Donut diagram** | Återger sektionsbågar som representerar unika objekt. Längden på varje båge representerar numeriska värden från ett annat fält. |
| **Linjediagram** | Ritar numeriska värden för en serie unika objekt och kopplar samman de ritade värdena |
| **Punktdiagram** | Ritar numeriska värden för en serie unika objekt |
| **Områdesdiagram** | Ritar numeriska värden för en serie unika objekt och fyller avsnitten under de ritade värdena |

### <a name="construct-queries-for-effective-charts"></a>Konstruera frågor för effektiva diagram
Vid rendering av diagram identifierar avancerad jakt automatiskt kolumner av intresse och de numeriska värdena som ska sammanställas. Skapa dina frågor för att returnera de specifika värden som du vill se visualiseras för att få meningsfulla diagram. Här är några exempelfrågor och de resulterande diagrammen.

#### <a name="alerts-by-severity"></a>Aviseringar efter allvarlighetsgrad
Använd `summarize` operatorn för att få ett numeriskt antal av de värden som du vill kartlägga. Frågan nedan använder `summarize` operatorn för att få antalet aviseringar efter allvarlighetsgrad.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
När resultaten återges visas varje allvarlighetsgrad i ett stapeldiagram:

![Bild av avancerade jaktfrågeresultat som visas som ett stapeldiagram ](../../media/advanced-hunting-column-chart.jpg)
 *Frågeresultat för aviseringar efter allvarlighetsgrad som visas som ett stapeldiagram*

#### <a name="alert-severity-by-operating-system"></a>Allvarlighetsgrad för aviseringar efter operativsystem
Du kan också använda `summarize` operatorn för att förbereda resultat för att kartlägga värden från flera fält. Du kanske till exempel vill förstå hur allvarlighetsgrader för aviseringar fördelas över operativsystem (OS). 

Frågan nedan använder en `join` operator för att hämta OS-information från tabellen och sedan används för att räkna värden i både `DeviceInfo` `summarize` `OSPlatform` kolumnerna och `Severity` kolumnerna:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Dessa resultat visualiseras bäst med hjälp av ett staplat stapeldiagram:

![Bild av avancerade jaktfrågeresultat som visas som ett staplat diagram ](../../media/advanced-hunting-stacked-chart.jpg)
 *Frågeresultat för aviseringar efter operativsystem och allvarlighetsgrad som visas som ett staplat diagram*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Nätfiskemeddelanden på de tio bästa avsändarna
Om du har att göra med en lista med värden som inte är begränsad kan du använda `Top` operatorn för att bara kartlägga de värden som har flest instanser. Om du till exempel vill få de tio bästa avsändarna med de mest nätfiskemeddelanden använder du frågan nedan:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Använd cirkeldiagramvyn för att effektivt visa distributionen mellan de populäraste domänerna:

![Bild av avancerade jaktfrågeresultat som visas som ett cirkeldiagram ](../../media/advanced-hunting-pie-chart.jpg)
 *Cirkeldiagram som visar distribution av nätfiskemeddelanden mellan de vanligaste avsändande domänerna*

#### <a name="file-activities-over-time"></a>Filaktiviteter över tid
Med hjälp av `summarize` operatören med funktionen kan du söka efter händelser som `bin()` involverar en viss indikator över tid. Frågan nedan räknar händelser som involverar filen `invoice.doc` med 30 minuters intervall för att visa toppar i aktivitet som är relaterade till filen:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
Linjediagrammet nedan belyser tydligt tidsperioder med mer aktivitet som `invoice.doc` omfattar: 

![Bild av avancerade jaktfrågeresultat som visas som ett linjediagram ](../../media/advanced-hunting-line-chart.jpg)
 *Linjediagram som visar antalet händelser som involverar en fil över tid*


## <a name="export-tables-and-charts"></a>Exportera tabeller och diagram
När du har kört en fråga väljer du **Exportera** för att spara resultaten i den lokala filen. Den valda vyn avgör hur resultaten exporteras:

- **Tabellvy** – frågeresultaten exporteras i tabellform som en Microsoft Excel-arbetsbok
- **Alla diagram** – frågeresultaten exporteras som en JPEG-bild av det renderade diagrammet

## <a name="drill-down-from-query-results"></a>Öka detaljnivån från frågeresultat
Om du snabbt vill granska en post i frågeresultatet markerar du motsvarande rad för att öppna **inspelningspanelen Inspektera.** Panelen innehåller följande information baserat på den valda posten:

- **Tillgångar** – sammanfattad vy över de viktigaste tillgångarna (postlådor, enheter och användare) som finns i posten, berikade med tillgänglig information, till exempel risk- och exponeringsnivåer
- **Processträd** – som genereras för poster med processinformation och berikas med hjälp av tillgänglig kontextuell information. I allmänhet kan frågor som returnerar fler kolumner resultera i rikare processträd.
- **Alla detaljer** – alla värden från kolumnerna i posten  

![Bild på vald post med panel för att kontrollera posten](../../media/mtp-ah/inspect-record.png)

Om du vill visa mer information om en viss entitet i frågeresultaten, till exempel en dator, fil, användare, IP-adress eller URL, väljer du entitetsidentifieraren för att öppna en detaljerad profilsida för den entiteten.

## <a name="tweak-your-queries-from-the-results"></a>Justera dina frågor från resultaten
Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan. Du kan använda alternativen för att:

- Leta uttryckligen efter det valda värdet ( `==` )
- Uteslut det markerade värdet från frågan ( `!=` )
- Få mer avancerade operatorer för att lägga till värdet i frågan, till exempel `contains` `starts with``ends with` 

![Bild på avancerad jaktresultatuppsättning](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrera frågeresultaten
Filtren som visas till höger ger en sammanfattning av resultatuppsättningen. Varje kolumn har ett eget avsnitt med de distinkta värden som hittats för den kolumnen och antalet instanser.

Förfina frågan genom att markera `+` knapparna eller `-` på de värden som du vill inkludera eller utesluta och sedan välja Kör **fråga**.

![Bild på avancerat jaktfilter](../../media/advanced-hunting-filter.png)

När du har tillämpat filtret för att ändra frågan och sedan köra frågan uppdateras resultaten i enlighet med detta.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
