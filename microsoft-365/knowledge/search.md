---
title: Använda Microsoft Search till att hitta ämnen i Microsoft Viva-ämnen
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
ms.openlocfilehash: 484d2477f7e4dbef096a4b8a2d30095708c6cc3f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50108316"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Använda Microsoft Search till att hitta ämnen i Microsoft Viva-ämnen

Viva Topics-användare kan hitta ämnen genom viktiga ämnen på Sina SharePoint-webbplatser, men de kan också hitta dem via Microsoft Search. 

## <a name="topic-answer"></a>Ämnessvar

När du söker efter ett visst ämne i Microsoft Search (till exempel "Saturnus"), visas resultatet i formatet Svarsförslag om ett ämne finns och hittas.

Ämnessvaret visas:
- Ämnesnamn
- Alternativa namn: Alternativa namn eller förkortningar för ämnet.
- Definition: Beskrivning av ämnet som tillhandahålls av AI eller som lagts till manuellt av en person.
- Föreslagna eller fästa personer: Personer som föreslås av AI eller är fästa vid ämnet av en person
- Föreslagna eller fästa resurser: Filer, sidor eller webbplatser som antingen föreslås av AI eller är fästa i ämnet av en person. 

   ![Ämne i sökning](../media/knowledge-management/search-topic-answer.png) 

Ämnessidan kan visas i sökresultatet även om ämnessvarskortet inte visas.


## <a name="acronyms"></a>Förkortningar

I Viva-ämnen kan du manuellt redigera ett ämne så att en förkortning för det tas med som ett <b>alternativt namn.</b> På så sätt kan en användare som söker efter endast ämnets förkortning hitta ämnessvaret via Microsoft Search.

[Akronym Answers](https://docs.microsoft.com/microsoftsearch/manage-acronyms) är en funktion som tillhandahålls genom Microsoft Search och hanteras separat från Viva Topics.

## <a name="bookmarks-and-topics"></a>Bokmärken och ämnen

[Bokmärken](https://docs.microsoft.com/microsoftsearch/manage-bookmarks) är en Microsoft Search-funktion som hjälper användare att snabbt hitta viktiga webbplatser och verktyg med bara en sökning (till exempel ett resebokningsverktyg på en extern webbplats utanför Microsoft 365-klientorganisationen). De skapas av sökadministratörer i administrationscentret för Microsoft 365. 

För användare som letar efter information om att boka en arbetsresa:

- Om vissa användare känner till reseverktygets namn (till exempel "Samtidiga") är det enklare att skapa ett bokmärke för att gå direkt till den externa webbplatsen.
- För användare som ofta söker efter "resor" skapar du ett ämne på "Resa" som innehåller den information de förväntar sig att se. Det kan vara bra att lägga till en länk till den externa samtidiga webbplatsen i beskrivningen av avsnittet. Om länken istället är till en intern resebokningswebbplats hos Microsoft 365-klientorganisationen kan du lägga till den i "Fästa resurser".
 
### <a name="search-results-priority"></a>Prioritet för sökresultat 
 
När en användare söker efter en term som "resa" visas sökresultat i användarens sökupplevelse med följande prioritet i Microsoft Search
1. Publicerade eller bekräftade ämnen 
2. Bokmärken
3. Föreslagna ämnen 



