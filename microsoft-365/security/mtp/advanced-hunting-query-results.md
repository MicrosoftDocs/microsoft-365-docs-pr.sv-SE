---
title: Arbeta med avancerade frågeresultat för sökning i Microsoft 365 Defender
description: Få ut mesta av sökresultaten som returneras av avancerad sökning i Microsoft 365 Defender
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, anpassade identifieringar, schema, kusto, microsoft 365, Microsoft Threat Protection, visualisering, diagram, filter, drill-down
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
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932328"
---
# <a name="work-with-advanced-hunting-query-results"></a>Arbeta med avancerade frågeresultat för sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Du kan skapa [](advanced-hunting-overview.md) avancerade sökfrågor för att returnera mycket exakt information, men du kan också arbeta med frågeresultatet för att få ytterligare insikter och undersöka specifika aktiviteter och indikatorer. Du kan utföra följande åtgärder på dina frågeresultat:

- Visa resultat som en tabell eller ett diagram
- Exportera tabeller och diagram
- Öka detaljgranskningen för detaljerad entitetsinformation
- Justera frågorna direkt efter resultatet eller använd filter

## <a name="view-query-results-as-a-table-or-chart"></a>Visa frågeresultat som en tabell eller ett diagram
Som standard visar avancerad sökning frågeresultat som tabelldata. Du kan också visa samma data som ett diagram. Avancerad sökning har stöd för följande vyer:

| Vytyp | Beskrivning |
| -- | -- |
| **Tabell** | Visar frågeresultatet i tabellformat |
| **Stapeldiagram** | Återger en serie unika objekt på x-axeln som lodräta staplar vars höjd representerar numeriska värden från ett annat fält |
| **Staplat stapeldiagram** | Återger en serie unika element på x-axeln som staplade lodräta staplar vars höjd representerar numeriska värden från ett eller flera andra fält |
| **Cirkeldiagram** | Återger avsnittsdiagram som representerar unika objekt. Storleken på varje cirkel representerar numeriska värden från ett annat fält. |
| **Ringdiagram** | Återger avsnittsbåge som representerar unika objekt. Längden på varje båge representerar numeriska värden från ett annat fält. |
| **Linjediagram** | Ritar numeriska värden för en serie unika objekt och kopplar samman de ritade värdena |
| **Punktdiagram** | Ritar numeriska värden för en serie unika objekt |
| **Områdesdiagram** | Ritar numeriska värden för en serie unika objekt och fyller avsnitten under de utritade värdena |

### <a name="construct-queries-for-effective-charts"></a>Skapa frågor för effektiva diagram
Vid rendering av diagram identifierar avancerad sökning automatiskt kolumner av intresse och de numeriska värden som ska aggregeras. För att få meningsfulla diagram skapar du frågorna för att returnera de specifika värden som du vill se visualiserade. Här är några exempelfrågor och de resulterande diagrammen.

#### <a name="alerts-by-severity"></a>Varningar efter allvarlighetsgrad
Använd `summarize` operatorn för att räkna antalet numeriska värden som du vill visa i diagrammet. I frågan nedan används `summarize` operatorn för att få antalet varningar med allvarlighetsgrad.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
När resultatet återges visas varje allvarlighetsgrad i ett stapeldiagram som en separat kolumn:

![Bild av avancerade frågeresultat för sökning som visas som ett stapeldiagram Med frågeresultat visas varningar efter ](../../media/advanced-hunting-column-chart.jpg)
 *allvarlighetsgrad som ett stapeldiagram*

#### <a name="alert-severity-by-operating-system"></a>Aviserings allvarlighetsgrad per operativsystem
Du kan också använda `summarize` operatorn för att förbereda resultat för diagramvärden från flera fält. Du kanske till exempel vill förstå hur allvarlighetsgraderna för varningar är fördelade mellan operativsystem (OS). 

Frågan nedan använder en operator för att hämta OS-information från tabellen och använder `join` sedan för att räkna värden i både kolumner och `DeviceInfo` `summarize` `OSPlatform` `Severity` kolumner:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
De här resultaten visualiseras bäst med hjälp av ett staplat diagram:

![Bild av avancerade frågeresultat för sökning visade som ett staplat diagram, frågeresultat för varningar efter ](../../media/advanced-hunting-stacked-chart.jpg)
 *OS och allvarlighetsgrad visad som ett staplat diagram*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Nätfiskemeddelanden i de tio översta avsändardomänerna
Om du hanterar en lista med värden som inte är ändliga kan du använda operatorn för att visa endast de värden som `Top` innehåller de flesta förekomster. Om du till exempel vill ha de tio vanligaste avsändardomänerna med flest nätfiskemeddelanden använder du frågan nedan:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Använd cirkeldiagramvyn för att effektivt visa fördelningen över de översta domänerna:

![Bild av avancerade frågeresultat för sökning som visas som ett cirkeldiagram som visar ](../../media/advanced-hunting-pie-chart.jpg)
 *fördelningen av nätfiskemeddelanden över de översta avsändardomänerna*

#### <a name="file-activities-over-time"></a>Filaktiviteter över tid
Med hjälp `summarize` av operatorn `bin()` med funktionen kan du söka efter händelser som innefattar en viss indikator över tid. Frågan nedan räknar händelser som innefattar filen med 30 minuters intervall för `invoice.doc` att visa insamlingar i aktiviteter relaterade till den filen:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
I linjediagrammet nedan markeras tidsperioder tydligt med mer aktivitet som `invoice.doc` innefattar: 

![Bild av avancerade sökresultat för sökning som visas som ett linjediagram som visar antalet ](../../media/advanced-hunting-line-chart.jpg)
 *händelser som innefattar en fil över tid*


## <a name="export-tables-and-charts"></a>Exportera tabeller och diagram
När du har kört en fråga **väljer du Exportera** för att spara resultaten i en lokal fil. Den valda vyn avgör hur resultatet exporteras:

- **Tabellvy** – frågeresultatet exporteras i tabellform som en Microsoft Excel-arbetsbok
- **Alla diagram** – frågeresultatet exporteras som en JPEG-bild av det renderade diagrammet

## <a name="drill-down-from-query-results"></a>Granska nedåt från frågeresultat
Om du snabbt vill granska en post i frågeresultatet markerar du motsvarande rad för att öppna **panelen Kontrollera** post. Panelen innehåller följande information baserat på den valda posten:

- **Tillgångar** – sammanfattad vy över huvudtillgångarna (postlådor, enheter och användare) som finns i posten, som är bättre beskad med tillgänglig information, t.ex. risk- och exponeringsnivåer
- **Processträd** – som genereras för arkivhandlingar med processinformation och som är bättre genom att använda tillgänglig kontextinformation. I allmänhet kan frågor som returnerar fler kolumner resultera i rikare processträd.
- **All information** – alla värden från kolumnerna i posten  

![Bild på markerad post med panel för att kontrollera posten](../../media/mtp-ah/inspect-record.png)

Om du vill visa mer information om en viss enhet i frågeresultatet, till exempel en dator, fil, användare, IP-adress eller URL, väljer du entitetsidentifieraren för att öppna en detaljerad profilsida för enheten.

## <a name="tweak-your-queries-from-the-results"></a>Justera frågorna från resultatet
Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan. Du kan använda alternativen för att:

- Leta explicit efter det valda värdet `==` ()
- Exkludera det valda värdet från frågan ( `!=` )
- Få mer avancerade operatorer för att lägga till värdet i frågan, till exempel `contains` `starts with` och `ends with` 

![Bild av avancerad uppsättning med resultat för sökning](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrera frågeresultatet
Filtren som visas till höger ger en sammanfattning av resultatuppsättningen. Varje kolumn har ett eget avsnitt med distinkta värden för kolumnen och antalet förekomster.

Förfina frågan genom att välja eller knapparna för de värden som du `+` vill inkludera eller exkludera och sedan välja Kör `-` **fråga.**

![Bild av avancerat sökfilter](../../media/advanced-hunting-filter.png)

När du använder filtret för att ändra frågan och sedan kör frågan uppdateras resultaten i enlighet med detta.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
