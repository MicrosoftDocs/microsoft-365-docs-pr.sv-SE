---
title: Skapa sökfrågor i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Använd nyckelord och villkor för att begränsa sökningens omfattning när du söker efter data med hjälp av Advanced eDiscovery i Microsoft 365.
ms.openlocfilehash: e0df319257776d3995a4b8e37781d7b5dad54d82
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2021
ms.locfileid: "52161841"
---
# <a name="build-search-queries-for-collections-in-advanced-ediscovery"></a>Skapa sökfrågor för samlingar i Advanced eDiscovery

När du konfigurerar sökfrågan när du skapar en samling i ett Advanced eDiscovery-ärende kan du använda nyckelord för att hitta specifikt innehåll och villkor för att begränsa sökningens omfattning för att returnera de objekt som är mest relevanta för den juridiska undersökningen. [](collections-overview.md)

![Använda nyckelord och villkor för att begränsa resultatet av en sökning](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Nyckelordssökningar

Skriv en nyckelordsfråga **i rutan** Nyckelord i sökfrågan. Du kan ange nyckelord, egenskaper för e-postmeddelanden, till exempel datum för skickade och mottagna meddelanden, eller dokumentegenskaper, t.ex. filnamn eller det datum då ett dokument senast ändrades. Du kan använda mer komplexa frågor som innehåller booleska operatorer som **AND**, **OR**, **NOT**, och **NEAR**. Du kan också söka efter känslig information (t.ex. personnummer) i dokument i SharePoint och OneDrive (inte i e-postmeddelanden), eller söka efter dokument som har delats externt. Om du lämnar **rutan Nyckelord** tom visas allt innehåll på de angivna innehållsplatserna i sökresultatet.

## <a name="keyword-list"></a>Nyckelordslista

Alternativt kan du markera kryssrutan Visa **nyckelordslista och** skriva ett nyckelord eller en nyckelordsfras på varje rad. Nyckelorden på varje rad är sammankopplade med en logisk operator (som representeras som *c:er* i sökfrågesyntaxen) som liknar den **ELLER-operatorn** i sökfrågan som skapas. Det innebär att objekt som innehåller ett nyckelord på valfri rad finns i sökresultaten. Du kan lägga till upp till 180 rader i nyckelordslistan Advanced eDiscovery i sökfrågor.

![Använd nyckelordslistan för att få statistik för varje nyckelord i frågan](../media/KeywordListSearch.png)

Varför ska jag använda nyckelordslistan? Du kan få statistik som visar hur många objekt som matchar varje nyckelord i nyckelordslistan. Det kan hjälpa dig att snabbt identifiera de nyckelord som är mest (och minst) effektiva. Du kan också använda en nyckelordsfras (inom parentes) i en rad i listan med nyckelord. Mer information om sökstatistik finns i [Sökstatistik](search-statistics-in-advanced-ediscovery.md).

## <a name="conditions"></a>Villkor

Du kan lägga till sökvillkor för att begränsa omfattningen av en sökning och returnera en mer förfinad uppsättning resultat. Varje villkor lägger till en sats i sökfrågan som skapas och körs när du startar sökningen. Ett villkor är logiskt kopplat till nyckelordsfrågan som anges i nyckelordsrutan av en logisk operator (som representeras som *c:c* i sökfrågesyntaxen) som fungerar ungefär som operatorn **OCH.** Det innebär att objekt måste uppfylla både nyckelordsfrågan och ett eller flera villkor som ska tas med i sökresultatet. Det är så du begränsar resultatet med hjälp av villkor. En lista och en beskrivning av de villkor som du kan använda i en sökfråga finns i avsnittet "Sökvillkor" i [Nyckelordsfrågor och sökvillkor.](keyword-queries-and-search-conditions.md#search-conditions)
