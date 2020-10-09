---
title: Lär dig mer om det avancerade frågespråket för jakt i Microsoft Threat Protection
description: Skapa din första hot-fråga och lär dig mer om vanliga operatörer och andra aspekter av det avancerade frågespråket
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, språk, lära sig, första frågan, telemetri, händelser, telemetri, anpassade identifieringar, schema, kusto, operatorer, data typer, PowerShell-nedladdning, exempel på frågor
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
ms.openlocfilehash: de8a2c3d55d887a28500bb82a97e4453861aef46
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399223"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Lär dig mer om det avancerade frågespråket

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

Avancerad jakt är baserat på [Kusto frågespråk](https://docs.microsoft.com/azure/kusto/query/). Du kan använda Kusto syntax och operatorer för att skapa frågor som hittar information i ett specialiserat [schema](advanced-hunting-schema-tables.md). Kör den första frågan för att förstå de här begreppen bättre.

## <a name="try-your-first-query"></a>Prova den första frågan

I Microsoft 365 säkerhets Center går du till **jakt** för att köra den första frågan. Använd följande exempel:

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

**[Kör den här frågan i avancerad jakt](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Beskriv frågan och ange vilka tabeller som ska sökas igenom
En kort kommentar har lagts till i början av frågan för att beskriva vad den är för. Den här kommentaren hjälper dig om du senare bestämmer dig för att spara frågan och dela den med andra i organisationen. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Frågan börjar normalt med ett tabell namn följt av flera element som börjar med ett vertikalstreck ( `|` ). I det här exemplet börjar vi med att skapa en union av två tabeller  `DeviceProcessEvents` och `DeviceNetworkEvents` lägga till piped-element efter behov.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Ange tidsintervall
Det första piped-elementet är ett tids filter som är begränsat till de föregående sju dagarna. Om du begränsar tidsintervallet ser du till att frågor fungerar bra, returnerar hanterbara resultat och inte tids gräns.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Kontrol lera specifika processer
Tidsintervallet följs omedelbart av en sökning efter process fil namn som representerar PowerShell-programmet.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Sök efter specifika kommando strängar
Därefter söker frågan efter strängar i kommando rader som vanligt vis används för att ladda ned filer med PowerShell.

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

### <a name="customize-result-columns-and-length"></a>Anpassa resultat kolumner och längd 
Nu när frågan tydligt identifierar de data som du vill hitta kan du ange hur resultatet ska se ut. `project` Returnerar specifika kolumner och `top` begränsar antalet resultat. Dessa operatörer ser till att resultaten är välformaterade och rimligt stora och lätta att bearbeta.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Välj **Kör fråga** för att visa resultatet. Använd ikonen Expandera längst upp till höger i Frågeredigeraren för att fokusera på frågan och resultaten. 

![Bild av kontrollen Expand i den avancerade Frågeredigeraren](../../media/advanced-hunting-expand.png)

>[!TIP]
>Du kan visa frågeresultat som diagram och snabbt justera filter. [Läs mer om hur du arbetar med frågeresultat](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Lär dig vanliga frågor

Du har precis kört den första frågan och har en allmän uppfattning om dess komponenter. Det är dags att gå tillbaka något och lära dig grunderna. Kusto Query-språk som används i Advanced jakt har stöd för en rad operatörer, bland annat följande.

| Ansvaret | Beskrivning och användning |
|--|--|
| `where` | Filtrera en tabell till den del av rader som uppfyller ett predikat. |
| `summarize` | Skapa en tabell som aggregerar innehållet i inmatnings tabellen. |
| `join` | Sammanfoga raderna i två tabeller för att skapa en ny tabell genom att matcha värden för de angivna kolumnerna från respektive tabell. |
| `count` | Returnera antalet poster i Indataposten. |
| `top` | Returnera de första N posterna sorterade efter de angivna kolumnerna. |
| `limit` | Gå tillbaka till angivet antal rader. |
| `project` | Markera kolumnerna som du vill ta med, byta namn på eller ta bort och infoga nya beräknade kolumner. |
| `extend` | Skapa beräknade kolumner och Lägg till dem i resultatet. |
| `makeset` |  Returnera en dynamisk (JSON) matris av uppsättningen med distinkta värden som uttryck används i gruppen. |
| `find` | Hitta rader som matchar ett predikat i en uppsättning tabeller. |

Om du vill se ett exempel på dessa operatörer kan du köra det från avsnittet **komma igång** i avancerad jakt.

## <a name="understand-data-types"></a>Förstå data typer

Advanced jakt stöder Kusto-datatyper, inklusive följande vanliga typer:

| Datatyp | Beskrivningar och frågor |
|--|--|
| `datetime` | Data-och tidsinformation representerar vanligt vis händelse tidsstämplar. [Se datetime-format som stöds](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Tecken sträng i UTF-8 som omges av enkla citat tecken ( `'` ) eller dubbla citat tecken ( `"` ). [Läs mer om strängar](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Denna datatyp stöder `true` eller `false` lägen. [Se litteraler och operatorer som stöds](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32-bitars heltal  |
| `long` | 64-bitars heltal |

Mer information om de här data typerna finns i [om Kusto skalära data typer](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Få hjälp medan du skriver frågor
Dra nytta av följande funktioner när du vill skriva frågor snabbare:
- **Autoföreslå**– när du skriver frågor kan du med hjälp av en avancerad jakt förslag från IntelliSense. 
- **Schema träd**– en schema representation som innehåller listan med tabeller och deras kolumner visas bredvid arbets ytan. För mer information, Hovra över ett objekt. Dubbelklicka på ett objekt om du vill infoga det i Frågeredigeraren.
- **[Schema referens](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**– i-Portal referens med tabell-och kolumn beskrivningar samt de händelse typer som stöds `ActionType` och urvals frågor

## <a name="work-with-multiple-queries-in-the-editor"></a>Arbeta med flera frågor i redigeraren
Du kan använda Frågeredigeraren för att experimentera med flera frågor. Så här använder du flera frågor:

- Avgränsa varje fråga med en tom rad.
- Placera markören på en del av en fråga för att välja frågan innan den körs. Detta kommer bara att köra den valda frågan. Om du vill köra en ny fråga flyttar du markören i enlighet med den och väljer **Kör fråga**.

![Bild av Frågeredigeraren med flera frågor](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Använda exempel frågor

Avsnittet **komma igång** innehåller några enkla frågor med vanliga operatorer. Prova att köra de här frågorna och gör små ändringar i dem.

![Bild av fönstret för avancerad jakt](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Förutom de grundläggande fråge exemplen kan du även komma åt [delade frågor](advanced-hunting-shared-queries.md) för speciella scenarier med hot. Utforska de delade frågorna på vänster sida av sidan eller i [GitHub](https://aka.ms/hunting-queries).

## <a name="access-query-language-documentation"></a>Dokumentation för Access-frågespråk

Mer information om Kusto-frågespråk och operatorer som stöds finns i [dokumentationen om Kusto-språk](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
