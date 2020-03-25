---
title: Lär dig det avancerade jaktfrågespråket i Microsoft Threat Protection
description: Skapa din första hotjaktsfråga och lär dig mer om vanliga operatörer och andra aspekter av det avancerade jaktfrågespråket
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, språk, lär dig, första frågan, telemetri, händelser, telemetri, anpassade upptäckter, schema, kusto, operatörer, datatyper, powershell ladda ned, frågeexempel
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
ms.openlocfilehash: e093bd9c5a76b44cf66591b4212f37014189186e
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929002"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Lär dig det avancerade jaktfrågespråket

**Gäller:**
- Microsofts hotskydd

Avancerad jakt baseras på [Kusto-frågespråket](https://docs.microsoft.com/azure/kusto/query/). Du kan använda Kusto-syntax och operatorer för att konstruera frågor som hittar information i [schemat](advanced-hunting-schema-tables.md) som är särskilt strukturerat för avancerad jakt. Om du vill förstå dessa begrepp bättre kör du din första fråga.

## <a name="try-your-first-query"></a>Prova din första fråga

I Microsoft 365 security center går du till **Jakt** för att köra din första fråga. Använd följande exempel:

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

Så här kommer det att se ut i avancerad jakt.

![Bild av avancerad jaktfråga för Microsoft Threat Protection](../../media/advanced-hunting-query-example.png)

En kort kommentar har lagts till i början av frågan för att beskriva vad den är till för. Detta hjälper om du senare bestämmer dig för att spara frågan och dela den med andra i organisationen. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Själva frågan börjar vanligtvis med ett tabellnamn följt av en`|`serie element som startats av en pipe ( ). I det här exemplet börjar vi med `DeviceProcessEvents` att `DeviceNetworkEvents`skapa en union med två tabeller och lägga till rörelement efter behov.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
Det första rörelementet är ett tidsfilter som har scopets till de föregående sju dagarna. Om du håller tidsintervallet så smalt som möjligt säkerställer du att frågor presterar bra, returnerar hanterbara resultat och inte time out.

```kusto
| where Timestamp > ago(7d)
```

Tidsintervallet följs omedelbart av en sökning efter processfilnamn som representerar PowerShell-programmet.

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

Därefter söker frågan efter strängar på kommandorader som vanligtvis används för att hämta filer med PowerShell.

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
Nu när frågan tydligt identifierar de data du vill hitta kan du lägga till element som definierar hur resultaten ser ut. `project`returnerar specifika `top` kolumner och begränsar antalet resultat, vilket säkerställer att resultaten är välformaterade och någorlunda stora och lätta att bearbeta.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Klicka på **Kör fråga** om du vill se resultatet. Välj ikonen expandera längst upp till höger i frågeredigeraren för att fokusera på jaktfrågan och resultaten.

![Bild av utöka kontrollen i den avancerade jaktfråge redigeraren](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Lär dig vanliga frågeoperatorer för avancerad jakt

Nu när du har kört din första fråga och har en allmän uppfattning om dess komponenter, är det dags att backa lite och lära sig grunderna. Kusto-frågespråket som används av avancerad jakt stöder en rad operatörer, inklusive följande vanliga.

| Operatör | Beskrivning och användning |
|--|--|
| `where` | Filtrera en tabell till den delmängd av rader som uppfyller ett predikat. |
| `summarize` | Skapa en tabell som sammanställer innehållet i indatatabellen. |
| `join` | Sammanfoga raderna med två tabeller för att skapa en ny tabell genom att matcha värden för de angivna kolumnerna från varje tabell. |
| `count` | Returnera antalet poster i indatapostuppsättningen. |
| `top` | Returnera de första N-posterna sorterade efter de angivna kolumnerna. |
| `limit` | Returnera upp till angivet antal rader. |
| `project` | Markera de kolumner som ska inkluderas, byta namn på eller släppa och infoga nya beräknade kolumner. |
| `extend` | Skapa beräknade kolumner och lägg till dem i resultatuppsättningen. |
| `makeset` |  Returnera en dynamisk (JSON) matris för uppsättningen distinkta värden som Uttr tar i gruppen. |
| `find` | Hitta rader som matchar ett predikat över en uppsättning tabeller. |

Om du vill se ett levande exempel på dessa operatörer kör du dem från avsnittet **Kom igång** i avancerad jakt.

## <a name="understand-data-types-and-their-query-syntax-implications"></a>Förstå datatyper och deras frågesyntax implicationer

Uppgifter i avancerade jakttabeller är i allmänhet indelade i följande datatyper.

| Datatyp | Beskrivnings- och frågekonsekvenser |
|--|--|
| `datetime` | Data- och tidsinformation som vanligtvis representerar händelsetidsstämplar |
| `string` | Teckensträng |
| `bool` | Sant eller falskt |
| `int` | 32-bitars numeriskt värde  |
| `long` | 64-bitars numeriskt värde |

## <a name="use-sample-queries"></a>Använda exempelfrågor

Avsnittet **Kom igång** innehåller några enkla frågor med vanliga operatorer. Prova att köra dessa frågor och göra små ändringar i dem.

![Bild på avancerat jaktfönster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Förutom de grundläggande frågeexemplen kan du också komma åt delade frågor för specifika [hotjaktsscenarier.](advanced-hunting-shared-queries.md) Utforska de delade frågorna till vänster på sidan eller GitHub-frågedatabasen.

## <a name="access-query-language-documentation"></a>Dokumentation för åtkomst till frågespråk

Mer information om Kusto-frågespråk och operatörer som stöds finns i [Kusto-frågespråkdokumentation](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Relaterade ämnen
- [Avancerad jaktöversikt](advanced-hunting-overview.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Tillämpa metodtips för frågor](advanced-hunting-best-practices.md)
