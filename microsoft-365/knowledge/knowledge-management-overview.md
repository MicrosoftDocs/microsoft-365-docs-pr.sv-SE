---
title: Översikt över kunskapshantering (förhandsgranskning)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Översikt över kunskapshanteringen i Project Cortex.
ms.openlocfilehash: 99b0d0ece9ef8271666b1978db7947f3e3f2a4e8
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540086"
---
# <a name="knowledge-management-0verview-preview"></a>Kunskapshantering 0verview (Förhandsgranska)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex) 

Kunskapshantering använder Microsoft AI-teknik, Microsoft 365, Delve, Sök och andra komponenter och tjänster för att skapa ett kunskapsnätverk i din Microsoft 365-miljö. 

   ![Flöde av kunskapshantering](../media/content-understanding/knowledge-management-flowchart.png) </br> 

Målet är att leverera information till användarna i appar som de använder varje dag, till exempel Outlook, Teams och SharePoint.

Användarna ser till exempel okända termer i sina e-postmeddelanden, SharePoint-webbplatser eller i Teams-konversationer som de vill veta mer om. Kunskapshantering använder AI för att automatiskt söka efter och identifiera dessa **ämnen**och sammanställer information om dem, till exempel en kort beskrivning, ämnesexperter i ämnet och webbplatser, filer och sidor som är relaterade till det. Du kan välja att uppdatera ämnesinformationen efter behov. Du kan sedan göra ämnena tillgängliga för användarna, vilket innebär att texten markeras för varje förekomst av ämnet som visas i appar som Outlook, Teams och SharePoint. Användare kan välja att välja ämne för att lära sig mer om det genom ämnesinformationen.


## <a name="topic-discovery"></a>Upptäckt av ämne

Knowledge Management använder Microsoft AI-teknik för att söka efter **ämnen** i din Office 365-miljö.

Ett ämne är en fras eller term som är organisatoriskt betydelsefull eller viktig. Den har en specifik betydelse för organisationen, och har resurser relaterade till den som kan hjälpa människor att förstå vad det är och hitta mer information om det.

När ett ämne upptäcks skapas en **ämnessida** som innehåller information som har samlats in genom ämnesidentifiering, till exempel:

- En kort beskrivning av ämnet.
- Användare som kan vara kunniga om ämnet.
- Filer, sidor och webbplatser som är relaterade till ämnet.


## <a name="topic-management"></a>Ämneshantering

Ämneshantering görs i organisationens **ämnescenter**. Ämnescentrets webbplats skapas under installationen och fungerar som ditt kunskapscentrum för din organisation. Den innehåller en lista över alla ämnen som upptäcktes i din miljö, liksom alla ämnessidor som har skapats för dessa ämnen. 

Användare som får rätt behörighet kan göra följande i ämnescentret:

- Bekräfta eller avvisa ämnen som upptäcktes i din klientorganisation.
- Skapa nya ämnen manuellt efter behov (till exempel om det inte fanns tillräckligt med information för att det ska upptäckas via AI).
- Redigera befintliga ämnessidor.</br>

Mer information [finns i Arbeta med ämne i ämnescentret.](work-with-topics.md)  


## <a name="admin-controls"></a>Administratörskontroller

Med administratörskontroller i administrationscentret för Microsoft 365 kan du hantera kunskapsnätverket. De gör det möjligt för en Microsoft 365 global eller SharePoint-administratör att:

- Kontrollera vilka användare i organisationen som får se ämnen i sina klientappar eller i SharePoint-sökresultat.
- Kontrollera vilka SharePoint-webbplatser som ska genomsökas för att söka efter ämnen.
- Konfigurera ämnesidentifiering för att utesluta specifika termer som du inte vill ska vara ett ämne.
- Styr vilka användare som kan bekräfta eller avvisa ämnen i ämnescentret.
- Styr vilka användare som kan skapa och redigera ämnen i ämnescentret.

Mer information [finns i Hantera kunskapsnätverket.](manage-knowledge-network.md) 

## <a name="topic-curation"></a>Ämneshärdning

AI kommer kontinuerligt att arbeta för att ge dig förslag för att förbättra dina ämnen när förändringar sker i din miljö.

Användare som du tillåter åtkomst till att se ämnen i sitt dagliga arbete får komma med förslag för att förbättra dem. Om en användare till exempel visar ämnessidan och ser information som är felaktig eller behöver läggas till, kan de med en länk på ämnessidan skicka en begäran om att uppdatera informationen.

Dessutom kan användare med rätt behörighet tagga objekt som Teams-konversation som är relevanta för ett ämne och lägga till dem i ett visst ämne.




## <a name="see-also"></a>Se även
[Ställ in kunskapshantering](set-up-knowledge-network.md)</br>
[Översikt över ämnescenter](topic-center-overview.md)