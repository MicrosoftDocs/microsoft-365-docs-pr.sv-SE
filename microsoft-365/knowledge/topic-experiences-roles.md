---
title: Avsnitt som får roller (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig mer om användar roller i avsnittet.
ms.openlocfilehash: b649ea81d8e5b036e9332e9c87b67a951b5905a7
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975699"
---
# <a name="topic-experiences-roles-preview"></a>Avsnitt som får roller (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Läs mer om Project Cortex](https://aka.ms/projectcortex).


När du använder avsnitts upplevelser i din Microsoft 365-miljö kan användarna ha följande roller:
-   Visnings program
-   Ämnes deltagare
-   Kunskaps chef
-   Kunskaps administratör

## <a name="topic-viewer"></a>Visnings program

Avsnitts läsare är användare i organisationen som kan visa markerade ämnen i sin moderna SharePoint-webbplats och i SharePoint-sökning. De kan välja avsnitt för att visa mer information om dem på en ämnes sida. 

För avsnitts markeringar och deras ämnes sidor som ska visas för ett ämnes visnings program måste användaren:
-   [Tilldelas en licens för ämne](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) i Microsoft 365-administratören.
-   Får synlighet för avsnitt. Detta görs av kunskaps administratören på sidan Inställningar i administrations centret för Microsoft 365.


## <a name="topic-contributors"></a>Ämnes deltagare

Ämnes deltagare är användare i din organisation som inte bara har behörighet som visnings program, men som också kan redigera ett befintligt ämne eller skapa ett nytt ämne. De har en viktig roll i att manuellt "Visa" informationen på en ämnes sida (både AI eller manuellt angiven) för att säkerställa dess kvalitet.

Användare som har behörigheten ämne kan se en **redigerings** knapp som visas på ämnes sidor, vilket gör att de kan uppdatera och publicera ett ämne.

En ämnes deltagare kan också skapa och publicera ett nytt ämne genom sin ämnes Center-webbplats.

För att kunna skapa och redigera ett ämne måste användaren:

-   [Tilldelas en licens för ämne](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) i Microsoft 365-administratören.
-   [Få behörighet att skapa och redigera ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center). Detta görs av kunskaps administratören på sidan Inställningar i administrations centret för Microsoft 365.

## <a name="knowledge-managers"></a>Kunskaps chefer

Kunskaps chefer är användare som hanterar ämnen i din organisation.  Avsnitts hantering sker via sidan Hantera ämnen i ämnes centret och är endast synlig för kunskaps cheferna.

På sidan Hantera ämnen kan en kunskaps chef göra följande:
-   Visa alla AI-förslag.
-   Granska ämnen för att kontrol lera att de är giltiga.
-   Ta bort ämnen som du inte vill ska synas för användarna.


Dessutom kan en kunskaps chef redigera befintliga ämnen eller skapa nya.

För att kunna hantera ämnen måste användaren:
-   [Tilldelas en licens för ämne](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) i Microsoft 365-administratören.
-   [Få behörighet att hantera ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)). Detta görs av kunskaps administratören på sidan Inställningar i administrations centret för Microsoft 365.

Användare som har en bra överblick över ditt företag kan vara bra för rollen som kunskaps chef. Sådana personer kanske inte bara har kunskapen för att veta om ämnena är giltiga eller inte, men kan också vara kända personer inom företaget som är relaterade till ämnena.


## <a name="knowledge-admins"></a>Kunskaps administratörer

Kunskaps administratörer är administratörer som konfigurerar och konfigurerar ämnen i din Microsoft 365-miljö. De hanterar också inställningarna för avsnitts upplevelser när installationen är klar. För kunskaps administratörs rollen måste du ha en Microsoft 365 global-eller SharePoint-administratör eftersom konfiguration och hantering sker i administrations centret för Microsoft 365.
Under installationen kan kunskaps administratörer konfigurera ämnen för att göra följande:

-   Välj vilka SharePoint-webbplatser som ska crawlas för avsnitt.
-   Välj vilka licensierade användare som ska kunna se ämnen (avsnitts läsare).
-   Välj vilka ämnen som ska undantas från att identifieras.
-   Välj vilka licensierade användare som ska kunna skapa och redigera ämnen (ämnes deltagare).
-   Välj vilka licensierade användare som ska kunna hantera ämnen (kunskaps administratörer).
-   Ge ämnes Center ett namn.

Kunskaps cheferna måste kunna koordineras av alla som har flera olika ämnen i organisationen för att kunna konfigurera den. Om det till exempel finns känslig information i ett nytt projekt måste kunskaps ledaren bli informerad så att de kan se till att SharePoint-webbplatsen inte crawlas för ämnen eller att vissa ämnes namn måste uteslutas.


## <a name="see-also"></a>Se även

