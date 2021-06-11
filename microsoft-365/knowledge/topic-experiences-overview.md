---
title: Översikt över Microsoft Viva-ämnen
ms.author: chucked
author: chuckedmonson
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
ms.openlocfilehash: ecd090036f35a3cfdaffe532c800244c8174183b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302130"
---
# <a name="microsoft-viva-topics-overview"></a>Översikt över Microsoft Viva-ämnen 

Viva Topics använder Microsoft AI-teknik, Microsoft 365, Microsoft Graph, Search och andra komponenter och tjänster för att ge användarna kunskaper i Microsoft 365-appar de använder varje dag, med början på moderna SharePoint-sidor, Microsoft Search och sökning i Word, PowerPoint, Outlook och Excel.

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

<br/>

Med Viva Topics kan du hantera ett viktigt affärsproblem i många företag – där användarna får tillgång till informationen när de behöver den. Till exempel behöver nya medarbetare snabbt lära sig mycket ny information, och stöter på termer som de inte vet något om när de läser igenom företagsinformation. För att lära sig mer kan användaren behöva ge sig av från vad de gör och ägna värdefull tid åt att söka efter information, till exempel information om vad termen är, vem i organisationen som är ämnesexpert och kanske webbplatser och dokument som är relaterade till termen.

Viva Topics använder AI för att automatiskt söka efter och identifiera **ämnen** i organisationen. Här sammanställs information om dem, till exempel en kort beskrivning, personer som arbetar med ämnet samt webbplatser, filer och sidor som är relaterade till det. En kunskapshanterare eller deltagare kan välja att uppdatera ämnesinformationen efter behov. Ämnena är tillgängliga för användarna, vilket innebär att för alla förekomster av ämnet som visas på en modern SharePoint-webbplats i nyheter och sidor markeras texten. Användarna kan välja ett ämne för att få mer information via ämnesinformationen. Ämnen finns också i SharePoint Search.


## <a name="how-topics-are-displayed-to-users"></a>Hur ämnen visas för användare

När ett ämne omnämns i innehåll på nyheter och sidor i SharePoint markeras det. Du kan öppna ämnessammanfattningen från markeringen. Öppna ämnesinformationen från sammanfattningens rubrik. Det omnämnda ämnet kan identifieras automatiskt eller ha lagts till på sidan med en direkt referens till ämnet av sidans författare. 

   ![Höjdpunkter Topic](../media/knowledge-management/saturn.png) 

När du använder Sökning i Word, PowerPoint, Outlook eller Excel, antingen via sökrutan  eller genom att välja Sök i snabbmenyn, kan resultatet som visas också visa en ämnessammanfattning.

   ![Skärmbild som visar sökning i Word via sökrutan.](../media/knowledge-management/word-search-2.png)

   ![Skärmbild som visar sökning i Word via snabbmenyn Sök.](../media/knowledge-management/word-search-1.png)

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

Se [Ämnesidentifiering och curation](./topic-experiences-discovery-curation.md).

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
- Redigera befintliga ämnessidor.<br/>

Se [Hantera ämnen i temacenter](manage-topics.md) för mer information.  


## <a name="admin-controls"></a>Administratörskontroller

Med administratörskontroller i Microsoft 365 kan du hantera Viva Topics. De gör det möjligt för en global Microsoft 365- eller SharePoint-administratör att:

- Kontrollera vilka användare i organisationen som får se ämnen på moderna sidor i SharePoint eller i SharePoint-sökresultat.
- Kontrollera vilka SharePoint-webbplatser som ska crawlas för att identifiera ämnen.
- Undanta specifika ämnen från att hittas.
- Styra vilka användare som kan hantera ämnen i temacenter.
- Kontrollera vilka användare som kan skapa och redigera ämnen.
- Kontrollera vilka användare som kan visa ämnen.

Se [tilldela användarbehörigheter](./plan-topic-experiences.md#user-permissions), [hantera synlighet för ämnen](./topic-experiences-knowledge-rules.md)och [hantera identifiering av ämnen](./topic-experiences-discovery.md) för mer information om administratörskontroller.

## <a name="topic-curation--feedback"></a>Ämneshantering och feedback

AI kommer kontinuerligt att arbeta med att ge förslag för att förbättra dina ämnen när ändringar sker i din miljö. 

Användare med behörighet att redigera eller skapa ämnen kan uppdatera ämnessidor direkt om de vill göra korrigeringar eller lägga till ytterligare information. De kan också lägga till nya ämnen som AI inte kunde identifiera. Om det finns tillräckligt med information om dessa manuellt tillagda ämnen, och AI kan identifiera den här typen av ämne, kan ytterligare förslag från AI förbättra dessa manuellt tillagda ämnen 

Användare som du tillåter åtkomst till för att se ämnen i sitt dagliga arbete kan bli tillfrågade om ämnet var användbart för dem. Systemet ser på svaren och använder dem för att förbättra markering av ämnet, och hjälpa dig att avgöra vad som visas i ämnessammanfattningar och i ämnesinformation.

Dessutom kan användare med rätt behörighet tagga objekt, till exempel Yammer-konversationer som är relevanta för ett ämne, och lägga till dem i ett visst ämne. 

Se [Ämnesidentifiering och curation](./topic-experiences-discovery-curation.md).

<!--
## See also
-->