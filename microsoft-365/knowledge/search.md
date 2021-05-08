---
title: Använda Microsoft Search för att hitta ämnen i Microsoft Viva-ämnen
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Lär dig hur du kan söka efter ämnen i Microsoft Viva.
ms.openlocfilehash: 15b42c9d3689a73c865be53bb29f298fcbf896bd
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281048"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Använda Microsoft Search för att hitta ämnen i Microsoft Viva-ämnen

Viva Topics-användare kan hitta ämnen genom viktiga ämnen på sina SharePoint-webbplatser, men de kan också hitta dem via Microsoft Search. 

## <a name="topic-answer"></a>Ämnessvar

När du söker efter ett visst ämne i Microsoft Search (till exempel "Saturnus"), visas resultatet i förslagsformatet Svar om ett ämne finns och hittas.

Ämnessvaret visas:
- Ämnesnamn
- Alternativa namn: Alternativa namn eller förkortningar för avsnittet.
- Definition: Beskrivning av ämnet som tillhandahålls av AI eller manuellt läggs till av en person.
- Föreslagna eller fästa personer: Personer som föreslås av AI eller är fästa vid ämnet av en person
- Föreslagna eller fästa resurser: Filer, sidor eller webbplatser som antingen föreslås av AI eller är fästa i ämnet av en person. 

   ![Ämne i sökning](../media/knowledge-management/search-topic-answer.png) 

Ämnessidan kan visas i sökresultatet även om ämnessvarskortet inte visas.

Sökresultaten i Word och PowerPoint också visa ämnessvaret när ett hittas.


## <a name="acronyms"></a>Förkortningar

I Viva Ämnen kan du manuellt redigera ett ämne för att ta med en förkortning för det som ett <b>alternativt namn.</b> Det gör att en användare som söker efter bara ämnets förkortning kan hitta ämnessvaret via Microsoft Search.

[Acronym Answers](/microsoftsearch/manage-acronyms) är en funktion som tillhandahålls genom Microsoft Search och hanteras separat från Viva Topics.

## <a name="bookmarks-and-topics"></a>Bokmärken och ämnen

[Bokmärken](/microsoftsearch/manage-bookmarks) är en Microsoft Search-funktion som hjälper användare att snabbt hitta viktiga webbplatser och verktyg med bara en sökning (till exempel ett resebokningsverktyg på en extern webbplats utanför Microsoft 365-klientorganisationen). De skapas av sökadministratörer i Microsoft 365 administrationscenter. 

För användare som söker information om att boka en resa för arbete:

- Om en del användare känner till reseverktygets namn (till exempel "Samtidiga") är det enklare att skapa ett bokmärke för att gå direkt till den externa webbplatsen.
- För användare som ofta söker efter "resor" kan du skapa ett ämne på "Resor" som innehåller den information de förväntar sig. Det kan vara bra att lägga till en länk till den externa samtidiga webbplatsen i beskrivningen av avsnittet. Om länken istället är till en intern resebokningswebbplats hos Microsoft 365 kan du lägga till den i "Fästa resurser".
 
### <a name="search-results-priority"></a>Prioritet för sökresultat 
 
När en användare söker efter en term som "resor" visas sökresultaten i följande prioritet i Microsoft Search
1. Publicerade eller bekräftade ämnen 
2. Bokmärken
3. Föreslagna ämnen
