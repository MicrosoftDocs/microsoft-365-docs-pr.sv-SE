---
title: Hantera fel i avancerad sökning för Microsoft 365 Defender
description: Förstå fel som visas när du använder avancerad sökning
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schema, kusto, tidsgräns, resurser, fel, okända fel, begränsningar, kvot, parameter, tilldelning
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
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929652"
---
# <a name="handle-advanced-hunting-errors"></a>Hantera avancerade sökfel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Avancerad sökning visar fel för att meddela om syntaxfel och när frågor träffar fördefinierade [kvoter och användningsparametrar.](advanced-hunting-limits.md) I tabellen nedan finns tips om hur du löser eller undviker fel.

| Feltyp | Orsak | Lösning | Exempel på felmeddelanden |
|--|--|--|--|
| Syntaxfel | Frågan innehåller okända namn, inklusive referenser till operatorer, kolumner, funktioner eller tabeller som inte finns. | Kontrollera att referenser [till kustooperatorer och funktioner](https://docs.microsoft.com/azure/data-explorer/kusto/query/) är korrekta. Kontrollera [schemat för](advanced-hunting-schema-tables.md) rätt avancerad sökning av kolumner, funktioner och tabeller. Omge variabla strängar med citattecken så att de känns igen. När du skriver dina frågor kan du använda Komplettera automatiskt-förslag från IntelliSense. | `A recognition error occurred.` |
| Semantikfel | Frågan använder giltiga operatorer, kolumner, funktioner eller tabellnamn, men det finns fel i strukturen och den resulterande logiken. I vissa fall identifierar avancerad sökning den specifika operatorn som orsakade felet. | Sök efter fel i frågans struktur. Mer information [finns i kustodokumentationen.](https://docs.microsoft.com/azure/data-explorer/kusto/query/) När du skriver dina frågor kan du använda Komplettera automatiskt-förslag från IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeouts | En fråga kan endast köras inom en [begränsad tidsperiod innan den tidsinställning som används används.](advanced-hunting-limits.md) Det här felet kan inträffa oftare när du kör komplexa frågor. | [Optimera frågan](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-begränsning | Frågor i samma klientorganisation har överskridit [cpu-resurserna som](advanced-hunting-limits.md) har tilldelats baserat på klientorganisationens storlek. | Tjänsten kontrollerar CPU-resursanvändningen var 15:e minut och visar varningar efter att användningen överskrider 10 % av den tilldelade kvoten. Om användningen når 100 % blockeras frågor tills nästa dag eller 15-minuterscykel. [Optimera dina frågor för att undvika att nå CPU-kvoter](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Överskriden storleksgräns för resultat  | Den sammantagna storleken på resultatuppsättningen för frågan har överskridit den maximala storleken. Det här felet kan uppstå om resultatuppsättningen är så stor att trunkeringen vid gränsen på 10 000 poster inte kan minska den till en godtagbar storlek. Resultat som har flera kolumner med ansbart innehåll är mer sannolikt att påverkas av det här felet. | [Optimera frågan](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Överflödig resursanvändning | Frågan har förbrukat för mycket resurser och har slutat slutföras. I vissa fall identifierar avancerad sökning den specifika operatorn som inte optimerades. | [Optimera frågan](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Okända fel | Frågan misslyckades på grund av en okänd orsak. | Försök köra frågan igen. Kontakta Microsoft via portalen om frågor fortsätter att returnera okända fel. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Relaterade ämnen
- [Avancerade söktips](advanced-hunting-best-practices.md)
- [Kvoter och användningsparametrar](advanced-hunting-limits.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Översikt över kustofrågespråk](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
