---
title: Lär dig språket för avancerad fråga om sökning i Microsoft 365 Defender
description: Skapa din första fråga om hot och lär dig mer om vanliga operatorer och andra aspekter av det avancerade frågespråket för sökfrågor
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types, powershell download, query example
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 14287fb6dea9dda8accb580246b383f0427c3b3f
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952626"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Lär dig språket för avancerad fråga om sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint

Avancerad sökning är baserad på [språket i Kusto-frågan.](/azure/kusto/query/) Du kan använda kustooperatorer och -uttryck till att skapa frågor som söker efter information i ett särskilt [schema.](advanced-hunting-schema-tables.md) För att förstå begreppen bättre bör du köra din första fråga.

## <a name="try-your-first-query"></a>Prova den första frågan

I Microsoft 365 säkerhetscenter går du till **Söka för** att köra den första frågan. Använd följande exempel:

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

**[Kör den här frågan för avancerad sökning](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Beskriv frågan och ange vilka tabeller som ska sökas
En kort kommentar har lagts till i början av frågan för att beskriva vad den används till. Den här kommentaren hjälper dig om du senare bestämmer dig för att spara frågan och dela den med andra i organisationen. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Själva frågan börjar vanligtvis med ett tabellnamn följt av flera element som börjar med en pipe `|` (). I det här exemplet börjar vi med att skapa en union av två tabeller och , och  `DeviceProcessEvents` `DeviceNetworkEvents` lägger till rörelement efter behov.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Ange tidsperiod
Det första pipade elementet är ett tidsfilter som är inderat i de föregående sju dagarna. Genom att begränsa tidsperioden ser du till att frågorna fungerar bra, returnerar hanterbara resultat och inte time out.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Kontrollera specifika processer
Tidsperioden följs omedelbart av en sökning efter processfilnamn som representerar PowerShell-programmet.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Söka efter specifika kommandosträngar
Därefter söker frågan efter strängar i kommandorader som vanligtvis används för att ladda ned filer med PowerShell.

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a>Anpassa resultatkolumner och längd 
Nu när frågan tydligt identifierar de data du vill hitta kan du definiera hur resultatet ska se ut. `project` returnerar specifika kolumner `top` och begränsar antalet resultat. De här operatorerna hjälper till att säkerställa att resultatet är väl formaterat och ganska stort och lätt att bearbeta.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Välj **Kör fråga** för att se resultatet. Använd expanderikonen längst upp till höger i frågeredigeraren om du vill fokusera på din sökfråga och resultaten. 

![Bild av utökad kontroll i den avancerade frågeredigeraren för sökning](../../media/advanced-hunting-expand.png)

>[!TIP]
>Du kan visa frågeresultat som diagram och snabbt justera filter. Mer information finns [i arbeta med frågeresultat](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Lär dig vanliga frågeoperatorer

Du kör den första frågan och har en övergripande uppfattning om dess komponenter. Det är dags att gå tillbaka lite och lära dig grunderna. Frågespråket Kusto som används av avancerad sökning har stöd för ett antal operatorer, bland annat följande vanliga.

| Operator | Beskrivning och användning |
|--|--|
| `where` | Filtrera en tabell till den delmängd rader som uppfyller ett predikat. |
| `summarize` | Skapa en tabell som aggregerar innehållet i indatatabellen. |
| `join` | Slå samman raderna i två tabeller för att skapa en ny tabell genom att matcha värden för de angivna kolumnerna från varje tabell. |
| `count` | Returnera antalet poster i uppsättningen med indataposter. |
| `top` | Returnera de första N-posterna som sorteras efter de angivna kolumnerna. |
| `limit` | Returnera upp till det angivna antalet rader. |
| `project` | Markera de kolumner som du vill ta med, byt namn på eller släpp och infoga nya beräknade kolumner. |
| `extend` | Skapa beräknade kolumner och lägg till dem i resultatuppsättningen. |
| `makeset` |  Returnera en dynamisk (JSON) matris med uppsättningen distinkta värden som Uttr tar i gruppen. |
| `find` | Hitta rader som matchar ett predikat i en uppsättning tabeller. |

Om du vill se ett live-exempel på dessa operatorer kör du dem från **avsnittet Komma** igång vid avancerad sökning.

## <a name="understand-data-types"></a>Förstå datatyper

Avancerad sökning stöder Kusto-datatyper, bland annat följande vanliga typer:

| Datatyp | Beskrivning och frågekonsekvenser |
|--|--|
| `datetime` | Data och tidsinformation representerar vanligtvis tidsstämplar för händelser. [Visa datumtidsformat som stöds](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Teckensträng i UTF-8 inom enkla citattecken ( `'` ) eller dubbla citattecken ( `"` ). [Läs mer om strängar](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Den här datatypen stöder `true` eller `false` tillstånd. [Visa literaler och operatorer som stöds](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32-bitars heltal  |
| `long` | 64-bitars heltal |

Mer information om dessa datatyper finns [i Kusto skalära datatyper.](/azure/data-explorer/kusto/query/scalar-data-types/)

## <a name="get-help-as-you-write-queries"></a>Få hjälp medan du skriver frågor
Dra nytta av följande funktioner för att skriva frågor snabbare:
- **Automatiska förslag – när** du skriver frågor får du förslag från IntelliSense med avancerad sökning. 
- **Schematräd**– en schemarepresentation som innehåller listan med tabeller och deras kolumner visas bredvid ditt arbetsområde. Hovra över ett objekt om du vill ha mer information. Dubbelklicka på ett objekt för att infoga det i frågeredigeraren.
- **[Schemareferens](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**– referens i portalen med tabell- och kolumnbeskrivningar samt händelsetyper (värden) och exempelfrågor som `ActionType` stöds

## <a name="work-with-multiple-queries-in-the-editor"></a>Arbeta med flera frågor i redigeraren
Du kan använda frågeredigeraren när du experimenterar med flera frågor. Så här använder du flera frågor:

- Avgränsa varje fråga med en tom rad.
- Placera markören på någon del av en fråga för att markera frågan innan du kör den. Då körs endast den markerade frågan. Om du vill köra en annan fråga flyttar du markören därefter och väljer **Kör fråga**.

![Bild av frågeredigeraren med flera frågor](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Använda exempelfrågor

I **avsnittet Komma** igång finns några enkla frågor som används med vanliga operatorer. Prova att köra dessa frågor och göra små ändringar i dem.

![Bild av fönstret för avancerad sökning](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Förutom de grundläggande frågeexempelen kan du också komma åt [delade frågor för](advanced-hunting-shared-queries.md) specifika fall av hot efter hot. Utforska de delade frågorna till vänster på sidan eller lagringsplatsen för [GitHub-frågan.](https://aka.ms/hunting-queries)

## <a name="access-query-language-documentation"></a>Dokumentation om frågespråk i Access

Mer information om Kusto-frågespråk och operatorer som stöds finns i [Kusto-frågespråks dokumentation.](/azure/kusto/query/)

>[!NOTE]
>Vissa tabeller i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint. [Aktivera Microsoft 365 Defender för](m365d-enable.md) att leta efter hot med hjälp av fler datakällor. Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Slutpunkt till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)