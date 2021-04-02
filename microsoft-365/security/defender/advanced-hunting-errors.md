---
title: Hantera fel vid avancerad sökning för Microsoft 365 Defender
description: Förstå felmeddelanden som visas när du använder avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, timeout, resources, errors, unknown error, limits, quota, parameter, allocation
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
ms.openlocfilehash: 83f2603b00062633ce61a3a8f364e33cbc5b029d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499732"
---
# <a name="handle-advanced-hunting-errors"></a>Hantera avancerade sökfel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Avancerad sökning visar fel för att meddela om syntaxfel och när frågor träffar fördefinierade [kvoter och användningsparametrar.](advanced-hunting-limits.md) I tabellen nedan finns tips om hur du löser eller undviker fel.

| Feltyp | Orsak | Lösning | Exempel på felmeddelanden |
|--|--|--|--|
| Syntaxfel | Frågan innehåller okända namn, inklusive referenser till icke-existenta operatorer, kolumner, funktioner eller tabeller. | Kontrollera att [referenserna till Kusto-operatorer och funktioner](/azure/data-explorer/kusto/query/) är korrekta. I [schemat finns](advanced-hunting-schema-tables.md) rätt kolumner, funktioner och tabeller för avancerad sökning. Omge variabla strängar med citattecken så att de kan identifieras. När du skriver dina frågor kan du använda Komplettera automatiskt-förslag från IntelliSense. | `A recognition error occurred.` |
| Semantiska fel | Även om frågan använder giltiga operator-, kolumn-, funktions- eller tabellnamn finns det fel i strukturen och den resulterande logiken. I vissa fall identifieras den specifika operatorn som orsakade felet av avancerad sökning. | Sök efter fel i frågans struktur. Mer information [finns i kustodokumentationen.](/azure/data-explorer/kusto/query/) När du skriver dina frågor kan du använda Komplettera automatiskt-förslag från IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Tidsgränser | En fråga kan endast köras inom en [begränsad tid innan den tidsinställning som används .](advanced-hunting-limits.md) Det här felet kan inträffa oftare när du kör komplexa frågor. | [Optimera frågan](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-begränsning | Frågor i samma klientorganisation har överskridit [cpu-resurserna som](advanced-hunting-limits.md) har tilldelats baserat på klientorganisationens storlek. | Tjänsten kontrollerar CPU-resursanvändningen var 15:e minut och varje dag och visar varningar efter att användningen överskrider 10 % av den tilldelade kvoten. Om användningen av tjänsten når 100 % blockeras frågor till efter nästa dagliga eller 15-minuterscykel. [Optimera dina frågor för att undvika att nå CPU-kvoter](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Överskriden storleksgräns för resultat  | Den sammanlagda storleken på resultatuppsättningen för frågan har överskridit den maximala storleken. Det här felet kan uppstå om resultatuppsättningen är så stor att trunkeringen vid gränsen på 10 000 poster inte kan minska den till en godtagbar storlek. Resultat som har flera kolumner med anpassningsbart innehåll är mer sannolikt att påverkas av det här felet. | [Optimera frågan](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Överflödig resursanvändning | Frågan har förbrukat alltför mycket resurser och har slutat slutföras. I vissa fall identifierar avancerad sökning den specifika operatorn som inte optimerades. | [Optimera frågan](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Okända fel | Frågan misslyckades på grund av en okänd orsak. | Försök att köra frågan igen. Kontakta Microsoft via portalen om frågor fortsätter att returnera okända fel. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Relaterade ämnen
- [Avancerade metodtips för sökning](advanced-hunting-best-practices.md)
- [Kvoter och användningsparametrar](advanced-hunting-limits.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Översikt över Kusto Query-språk](/azure/data-explorer/kusto/query/)