---
title: Översikt över Microsoft Viva-ämnen
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Översikt över Viva Topics.
ms.openlocfilehash: 91442ba12b3d5df1d9934022751f4bc381cd40e8
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453975"
---
# <a name="microsoft-viva-topics-overview"></a>Översikt över Microsoft Viva-ämnen 

Viva Topics använder Microsoft AI-teknik, Microsoft 365, Microsoft Graph, Search och andra komponenter och tjänster för att föra kunskap till användarna i Microsoft 365-appar som de använder varje dag. De börjar med moderna SharePoint-sidor och Microsoft Search.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Med Viva Topics kan du hantera ett viktigt affärsproblem i många företag – där användarna får tillgång till informationen när de behöver den. Till exempel behöver nya medarbetare snabbt lära sig mycket ny information, och stöter på termer som de inte vet något om när de läser igenom företagsinformation. För att lära sig mer kan användaren behöva ge sig av från vad de gör och ägna värdefull tid åt att söka efter information, till exempel information om vad termen är, vem i organisationen som är ämnesexpert och kanske webbplatser och dokument som är relaterade till termen.

Viva Topics använder AI för att automatiskt söka efter och identifiera **ämnen** i organisationen. Här sammanställs information om dem, till exempel en kort beskrivning, personer som arbetar med ämnet samt webbplatser, filer och sidor som är relaterade till det. En kunskapshanterare eller deltagare kan välja att uppdatera ämnesinformationen efter behov. Ämnena är tillgängliga för användarna, vilket innebär att för alla förekomster av ämnet som visas på en modern SharePoint-webbplats i nyheter och sidor markeras texten. Användarna kan välja ett ämne för att få mer information via ämnesinformationen. Ämnen finns också i SharePoint Search.


## <a name="how-topics-are-displayed-to-users"></a>Hur ämnen visas för användare

När ett ämne omnämns i innehåll på nyheter och sidor i SharePoint markeras det. Du kan öppna ämnessammanfattningen från markeringen. Öppna ämnesinformationen från sammanfattningens rubrik. Det omnämnda ämnet kan identifieras automatiskt eller ha lagts till på sidan med en direkt referens till ämnet av sidans författare. 

   ![Höjdpunkter Topic](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Kunskapsindexering

Viva Topics använder Microsoft AI-teknik för att identifiera **ämnen** i Microsoft 365-miljön.

Ett ämne är en fras eller term som är organisatoriskt signifikativ eller viktig. Den har en specifik betydelse för organisationen och har relaterade resurser som kan hjälpa andra att förstå vad den är och hitta mer information om den. Det finns många olika typer av ämnen som är viktiga för din organisation. Till en början fokuserar Microsoft AI-tekniken på följande typer:
- Project
- Händelse
- Organisation
- Plats
- Produkt
- Kreativt arbete
- Studiefält


När ett ämne identifieras och AI bestämmer att det innehåller tillräckligt med information för att vara ett föreslaget ämne, visas informationen som hämtades via ämnesindexering på en **ämnessida**, till exempel:

- Alternativa namn och förkortningar.
- En kort beskrivning om ämnet.
- Personer som kan vara kunniga om ämnet.
- Filer, sidor och webbplatser som är relaterade till ämnet.

Dina kunskapsadministratörer kan välja att crawla alla SharePoint-webbplatser i klientorganisationen för ämnen eller att bara välja vissa.

Se [Identifiering och säkring av ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation) för mer information

## <a name="roles"></a>Roller

När du använder Viva Topics i Microsoft 365-miljön har användarna följande roller:

- Ämnesanvändare: Användare som kan se ämnen markerade på moderna SharePoint-webbplatser som de har minst *Läsa* åtkomst till och i Microsoft Search. De kan markera ämneshöjdpunkter om du vill se information om ämnet på ämnessidorna. Ämnesanvändare kan ge feedback om hur användbart ett ämne är för dem.

- Deltagare: Användare som har behörighet att redigera befintliga ämnen eller skapa nya. Kunskapsadministratörer tilldelar behörighet som deltagare till användare via inställningarna för Viva Topics i Administrationscenter för Microsoft 365. Observera att du även kan välja att ge alla som tittar på ämnet behörighet att redigera och skapa ämnen så att alla kan bidra till ämnen som de ser.

- Kunskapshanterare: Användare som vägleder ämnen genom ämnets livscykel. Kunskapshanterare använder sidan **Hantera Topics** i Temacenter för att bekräfta AI-föreslagna ämnen, ta bort ämnen som inte längre är relevanta och redigera befintliga ämnen eller skapa nya och är de enda användarna som har åtkomst till dem. Kunskapsadministratörer tilldelar behörighet som kunskapshanterare till användare via inställningarna för Viva Topics i Administrationscenter för Microsoft 365. 

- Kunskapsadministratörer: Kunskapsadministratörer har ställt in Viva Topics och hanterar dem via administratörskontrollerna i Administrationscenter för Microsoft 365. En global Microsoft 365- eller SharePoint-administratör kan för närvarande fungera som kunskapsadministratör.

Se [roller för Viva Topics](topic-experiences-roles.md) för mer information.

## <a name="topic-management"></a>Ämneshantering

Ämneshanteringen görs på sidan **Hantera ämnen** på organisationens webbplats **temacenter**. Temacenter skapas under installationen och fungerar som kunskapscenter för organisationen. 

Alla licensierade användare kan se ämnen som de är anslutna till i temacenter, men endast användare med behörigheten *Hantera ämnen* (kunskapshanterare) kan visa och använda sidan Hantera ämnen.

Kunskapshanterare kan:

- Bekräfta eller ta bort ämnen som har upptäckts i klientorganisationen.
- Skapa nya ämnen manuellt efter behov (om till exempel inte tillräckligt med information tillhandahölls för att den ska upptäckas via AI).
- Redigera befintliga ämnessidor.</br>

Se [Hantera ämnen i temacenter](manage-topics.md) för mer information.  


## <a name="admin-controls"></a>Administratörskontroller

Med administratörskontroller i Administrationscenter för Microsoft 365 kan du hantera ditt kunskapsnätverk. De gör det möjligt för en global Microsoft 365- eller SharePoint-administratör att:

- Kontrollera vilka användare i organisationen som får se ämnen på moderna sidor i SharePoint eller i SharePoint-sökresultat.
- Kontrollera vilka SharePoint-webbplatser som ska crawlas för att identifiera ämnen.
- Undanta specifika ämnen från att hittas.
- Styra vilka användare som kan hantera ämnen i temacenter.
- Kontrollera vilka användare som kan skapa och redigera ämnen.
- Kontrollera vilka användare som kan visa ämnen.

Se [tilldela användarbehörigheter](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions), [hantera synlighet för ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)och [hantera identifiering av ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) för mer information om administratörskontroller.

## <a name="topic-curation--feedback"></a>Ämneshantering och feedback

AI kommer kontinuerligt att arbeta med att ge förslag för att förbättra dina ämnen när ändringar sker i din miljö. 

Användare med behörighet att redigera eller skapa ämnen kan uppdatera ämnessidor direkt om de vill göra korrigeringar eller lägga till ytterligare information. De kan också lägga till nya ämnen som AI inte kunde identifiera. Om det finns tillräckligt med information om dessa manuellt tillagda ämnen, och AI kan identifiera den här typen av ämne, kan ytterligare förslag från AI förbättra dessa manuellt tillagda ämnen 

Användare som du tillåter åtkomst till för att se ämnen i sitt dagliga arbete kan bli tillfrågade om ämnet var användbart för dem. Systemet ser på svaren och använder dem för att förbättra markering av ämnet, och hjälpa dig att avgöra vad som visas i ämnessammanfattningar och i ämnesinformation.

Dessutom kan användare med rätt behörighet tagga objekt, till exempel Yammer-konversationer som är relevanta för ett ämne, och lägga till dem i ett visst ämne. 

Se [Identifiering och säkring av ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation) för mer information


## <a name="see-also"></a>Se även

