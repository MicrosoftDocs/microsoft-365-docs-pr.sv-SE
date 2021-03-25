---
title: Hantera fel under avancerad sökning efter Microsoft Defender ATP
description: Förstå felmeddelanden som visas när du använder avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp, m365, search, query, telemetry, schema, kusto, timeout, resources, errors, unknown error
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 64c8a13ba9e8110d761245315969b9e1882b3448
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075513"
---
# <a name="handle-advanced-hunting-errors"></a>Hantera avancerade sökfel

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Avancerad sökning visar fel som informerar om syntaxfel och när frågor kommer till fördefinierade [gränser.](advanced-hunting-limits.md) I tabellen nedan finns tips om hur du löser eller undviker fel. 

| Feltyp | Orsak | Lösning | Exempel på felmeddelanden |
|--|--|--|--|
| Syntaxfel | Frågan innehåller okända namn, inklusive referenser till icke-existenta operatorer, kolumner, funktioner eller tabeller. | Kontrollera att [referenserna till Kusto-operatorer och funktioner](https://docs.microsoft.com/azure/data-explorer/kusto/query/) är korrekta. I [schemat finns](advanced-hunting-schema-reference.md) rätt kolumner, funktioner och tabeller för avancerad sökning. Omge variabla strängar med citattecken så att de kan identifieras. När du skriver dina frågor kan du använda Komplettera automatiskt-förslag från IntelliSense. | `A recognition error occurred.` |
| Semantiska fel | Även om frågan använder giltiga operator-, kolumn-, funktions- eller tabellnamn finns det fel i strukturen och den resulterande logiken. I vissa fall identifieras den specifika operatorn som orsakade felet av avancerad sökning. | Sök efter fel i frågans struktur. Mer information [finns i kustodokumentationen.](https://docs.microsoft.com/azure/data-explorer/kusto/query/) När du skriver dina frågor kan du använda Komplettera automatiskt-förslag från IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Tidsgränser | En fråga kan endast köras inom en [begränsad tid innan den tidsinställning som används .](advanced-hunting-limits.md) Det här felet kan inträffa oftare när du kör komplexa frågor. | [Optimera frågan](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-begränsning | Frågor i samma klientorganisation har överskridit [cpu-resurserna som](advanced-hunting-limits.md) har tilldelats baserat på klientorganisationens storlek. | Tjänsten kontrollerar CPU-resursanvändningen var 15:e minut och varje dag och visar varningar efter att användningen överskrider 10 % av den tilldelade gränsen. Om användningen av tjänsten når 100 % blockeras frågor till efter nästa dagliga eller 15-minuterscykel. [Optimera dina frågor för att undvika att nå CPU-gränser](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Överskriden storleksgräns för resultat  | Den sammanlagda storleken på resultatuppsättningen för frågan har överskridit maxgränsen. Det här felet kan uppstå om resultatuppsättningen är så stor att trunkeringen vid gränsen på 10 000 poster inte kan minska den till en godtagbar storlek. Resultat som har flera kolumner med anpassningsbart innehåll är mer sannolikt att påverkas av det här felet. | [Optimera frågan](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Överflödig resursanvändning | Frågan har förbrukat alltför mycket resurser och har slutat slutföras. I vissa fall identifierar avancerad sökning den specifika operatorn som inte optimerades. | [Optimera frågan](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Okända fel | Frågan misslyckades på grund av en okänd orsak. | Försök att köra frågan igen. Kontakta Microsoft via portalen om frågor fortsätter att returnera okända fel. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Relaterade ämnen
- [Avancerade metodtips för sökning](advanced-hunting-best-practices.md)
- [Tjänstbegränsningar](advanced-hunting-limits.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
- [Översikt över Kusto Query-språk](https://docs.microsoft.com/azure/data-explorer/kusto/query/)