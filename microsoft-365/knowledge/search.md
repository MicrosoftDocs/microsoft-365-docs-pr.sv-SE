---
title: Använda Microsoft Search för att hitta ämnen i Microsoft Viva-ämnen
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Lär dig hur du kan söka efter ämnen i Microsoft Viva.
ms.openlocfilehash: a60d1e04c67eb42573bb566a5667f35227def2ad
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287263"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Använda Microsoft Search för att hitta ämnen i Microsoft Viva-ämnen

Viva Topics-användare kan hitta ämnen genom viktiga ämnen på sina SharePoint-webbplatser, men de kan också hitta dem via Microsoft Search. 

## <a name="topic-answer"></a>Ämnessvar

När du söker efter ett visst ämne från startsidan i SharePoint, på Office.com eller från en SharePoint-webbplats som har omfattningen begränsad till din organisation, visas resultatet i formatet ämnessvarsförslag om ett ämne finns och hittas.

Ämnessvaret visas:

- Ämnesnamn
- Alternativa namn: Alternativa namn eller förkortningar för avsnittet.
- Definition: Beskrivning av ämnet som tillhandahålls av AI eller manuellt läggs till av en person.
- Föreslagna eller fästa personer: Personer som föreslås av AI eller är fästa vid ämnet av en person
- Föreslagna eller fästa resurser: Filer, sidor eller webbplatser som antingen föreslås av AI eller är fästa i ämnet av en person. 

   ![Ämne i sökning](../media/knowledge-management/search-topic-answer.png) 

Ämnessidan kan visas i sökresultatet även om ämnessvarskortet inte visas.

Sökresultaten i Word, PowerPoint, Outlook och Excel visar också ämnessvaret när ett hittas.

## <a name="acronyms"></a>Förkortningar

I Viva Ämnen kan du manuellt redigera ett ämne för att ta med en förkortning för det som ett *alternativt namn.* Det gör att en användare som söker efter bara ämnets förkortning kan hitta ämnessvaret via Microsoft Search.

[Acronym Answers](/microsoftsearch/manage-acronyms) är en funktion som tillhandahålls Microsoft Search även hanteras separat från Viva Topics.

## <a name="bookmarks-and-topics"></a>Bokmärken och ämnen

[Bokmärken](/microsoftsearch/manage-bookmarks) är en Microsoft Search funktion som hjälper användare att snabbt hitta viktiga webbplatser och verktyg med bara en sökning (till exempel ett resebokningsverktyg på en extern webbplats utanför deras Microsoft 365-klientorganisation). De skapas av sökadministratörer i Administrationscenter för Microsoft 365. 

För användare som söker information om att boka en resa för arbete:

- Om en del användare känner till reseverktygets namn (till exempel "Samtidiga") är det enklare att skapa ett bokmärke för att gå direkt till den externa webbplatsen.

- För användare som ofta söker efter "resor" kan du skapa ett ämne på "Resor" som innehåller den information de förväntar sig. Det kan vara bra att lägga till en länk till den externa samtidiga webbplatsen i beskrivningen av avsnittet. Om länken istället är till en intern resebokningswebbplats hos Microsoft 365 kan du lägga till den i "Fästa resurser".
 
### <a name="search-results-priority"></a>Prioritet för sökresultat 

När en användare söker efter en term som "resa" i användarens sökupplevelse visas ett bokmärke i stället för ett ämne, om ett bokmärke är tillgängligt.

## <a name="see-also"></a>Se även

[Översikt över Viva-ämnen](topic-experiences-overview.md)
