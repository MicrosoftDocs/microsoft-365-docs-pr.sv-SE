---
title: Hantera fel i avancerad jakt för Microsoft Threat Protection
description: Problem som visas vid användning av avancerad jakt
keywords: Avancerad jakt, Hot jakt, cyberterrorism Threat stöldskydd, Microsoft Threat Protection, Microsoft 365, MTP, m365, Sök, fråga, telemetri, schema, kusto, tids gräns, resurser, fel, okänt fel, gränser, kvot, parameter, tilldelning
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 8b9c46e312d28c7a08efbfa74f96dc33b90fee0a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636899"
---
# <a name="handle-advanced-hunting-errors"></a>Hantera avancerade jakt fel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


I Advanced jakt visas fel för att informera om syntaxfel och när frågor trycker på [fördefinierade kvoter och användnings parametrar](advanced-hunting-limits.md). Se tabellen nedan för tips om hur du kan lösa eller undvika fel.

| Feltypen | Orsak | Lösning | Exempel på fel meddelanden |
|--|--|--|--|
| Syntaxfel | Frågan innehåller okända namn, inklusive referenser till icke-befintliga operatorer, kolumner, funktioner eller tabeller. | Se till att referenser till [Kusto operatörer och funktioner](https://docs.microsoft.com/azure/data-explorer/kusto/query/) är korrekta. Kontrol lera [schemat](advanced-hunting-schema-tables.md) för de korrekta, avancerade kolumnerna, funktionerna och tabellerna. Omge variabel strängar med citat tecken så att de känns igen. Använd Autoavsluta-förslagen från IntelliSense när du skriver dina frågor. | `A recognition error occurred.` |
| Semantiska fel | När frågan använder giltiga Operator-, kolumn-, funktions-eller tabell namn finns det fel i dess struktur och resulterande logik. I vissa fall identifierar Advanced jakt den specifika operatören som orsakade felet. | Kontrol lera om det finns fel i strukturen i frågan. Se [Kusto dokumentation](https://docs.microsoft.com/azure/data-explorer/kusto/query/) för vägledning. Använd Autoavsluta-förslagen från IntelliSense när du skriver dina frågor. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Gränser | En fråga kan bara köras inom en [begränsad period innan tids gränsen för timeout](advanced-hunting-limits.md). Det här felet kan inträffa oftare när komplexa frågor körs. | [Optimera frågan](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-begränsning | Frågor i samma klient organisation har överskridit de [CPU-resurser](advanced-hunting-limits.md) som har tilldelats baserat på innehavarens storlek. | Tjänsten kontrollerar CPU-resursanvändningen var 15: e minut och dagligen och visar varningar efter användnings område överskrider 10% av den tilldelade kvoten. Om du har till gång till 100% använder tjänsten frågor fram till efter nästa dagliga eller 15-minuters cykel. [Optimera dina frågor för att undvika att använda processor kvoter](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Gränsen för resultat storlek har överskridits  | Den sammansatta storleken för frågeresultatet har överskridit maximal storlek. Det här felet kan uppstå om resultat uppsättningen är så stor att trunkering vid 10 000-Record Limit inte kan minska den till en acceptabel storlek. Resultat som har flera kolumner med innehåll av större storlek är sannolikt att det här felet påverkas. | [Optimera frågan](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Orimlig resursförbrukning | Frågan har förbrukat alltför många resurser och har stoppats. I vissa fall identifierar Advanced jakt den specifika operatören som inte optimerats. | [Optimera frågan](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Okända fel | Frågan misslyckades på grund av ett okänt fel. | Prova att köra frågan igen. Kontakta Microsoft via portalen om frågor fortsätter att returnera okända fel. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Relaterade ämnen
- [Avancerade råd om att få råd](advanced-hunting-best-practices.md)
- [Kvoter och användnings parametrar](advanced-hunting-limits.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Kusto Query-översikt](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
