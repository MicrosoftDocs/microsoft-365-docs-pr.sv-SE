---
title: Översikt över Microsoft Viva-ämnen
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan; lauris
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
ms.openlocfilehash: 785fddb7c951bb6f7c170971f0af4eb7ac8f9a83
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984910"
---
# <a name="microsoft-viva-topics-overview"></a>Översikt över Microsoft Viva-ämnen 

Viva Topics använder Microsoft AI-teknik, Microsoft 365, Microsoft Graph, Search och andra komponenter och tjänster för att ge användarna kunskap i de Microsoft 365-appar de använder varje dag, med början på moderna SharePoint-sidor, Microsoft Search och sökning i Word, PowerPoint, Outlook och Excel.

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

<br/>

Viva Topics hjälper till att lösa ett viktigt affärsproblem i många företag – att tillhandahålla information till användare när de behöver det. Till exempel behöver nya medarbetare snabbt lära sig mycket ny information, och stöter på termer som de inte vet något om när de läser igenom företagsinformation. För att lära sig mer kan användaren behöva ge sig av från vad de gör och ägna värdefull tid åt att söka efter information, till exempel information om vad termen är, vem i organisationen som är ämnesexpert och kanske webbplatser och dokument som är relaterade till termen.

Viva Topics använder AI för att automatiskt söka efter och identifiera *ämnen* i organisationen. Här sammanställs information om dem, till exempel en kort beskrivning, personer som arbetar med ämnet samt webbplatser, filer och sidor som är relaterade till det. En kunskapshanterare eller deltagare kan välja att uppdatera ämnesinformationen efter behov. Ämnena är tillgängliga för användarna, vilket innebär att för alla förekomster av ämnet som visas på en modern SharePoint-webbplats i nyheter och sidor markeras texten. Användarna kan välja ett ämne för att få mer information via ämnesinformationen. Ämnen finns också i SharePoint Search.

## <a name="how-topics-are-displayed-to-users"></a>Hur ämnen visas för användare

Ämnen visas för användare via:

- [Ämnen markerade](topic-experiences-overview.md#sharepoint-highlights) på SharePoint sidor
- Ämnessvar [i sökresultat](topic-experiences-overview.md#search-results)
- Söka i [Office-program](topic-experiences-overview.md#office-application-search)
- [Startsida för](topic-experiences-overview.md#topic-center) Ämnescenter

### <a name="sharepoint-highlights"></a>SharePoint över viktiga händelser

När ett ämne omnämns i innehåll på nyheter och sidor i SharePoint markeras det. Du kan öppna ämnessammanfattningen från markeringen. Öppna ämnesinformationen från sammanfattningens rubrik om du vill se hela ämnessidan. Det omnämnda avsnittet kan identifieras automatiskt eller ha refererats direkt av sidans författare. 

   ![Skärmbild som visar viktiga ämnen.](../media/knowledge-management/saturn.png) 

### <a name="search-results"></a>Sökresultat

Du kan [](search.md#topic-answer) se ett ämnessvar i sökresultat när du söker från startsidan för SharePoint, söker på Office.com eller söker från en SharePoint-webbplats efter att du har ändrat sökomfattningen så att den omfattar hela organisationen. Ämnessvaret visas i ämnet i resultatlistan och ger dig en kort uppsättning information om det ämnet. 

   ![Skärmbild som visar sökresultatet för en SharePoint webbplatssökning.](../media/knowledge-management/site-search-results.png) 

### <a name="office-application-search"></a>Office programsökning

När du använder Sök i Office-appar som Word, PowerPoint, Outlook eller Excel – antingen via sökrutan eller genom att välja Sök i snabbmenyn – visas ämnessvar i sökresultaten. 

   ![Skärmbild som visar sökning i Word via sökrutan.](../media/knowledge-management/word-search-2.png)

   ![Skärmbild som visar sökning i Word via snabbmenyn Sök.](../media/knowledge-management/word-search-1.png)

### <a name="topic-center"></a>Ämnescenter

Användarna kan se ämnen i organisationen som de har en anslutning till på [startsidan för ämnescentret.](topic-center-overview.md#home-page)

## <a name="knowledge-indexing"></a>Kunskapsindexering

Viva Topics använder Microsoft AI-teknik för att identifiera *ämnen* i Microsoft 365-miljön.

Ett ämne är en fras eller term som är organisatoriskt signifikativ eller viktig. Den har en specifik betydelse för organisationen och har relaterade resurser som kan hjälpa andra att förstå vad den är och hitta mer information om den. Det finns många olika typer av ämnen som är viktiga för din organisation. Till en början fokuserar Microsoft AI-tekniken på följande typer:

- Project
- Händelse
- Organisation
- Plats
- Produkt
- Kreativt arbete
- Studiefält

När ett ämne identifieras och AI bestämmer att det innehåller tillräckligt med information för att vara ett föreslaget ämne, visas informationen som hämtades via ämnesindexering på en *ämnessida*, till exempel:

- Alternativa namn och förkortningar.
- En kort beskrivning om ämnet.
- Personer som kan vara kunniga om ämnet.
- Filer, sidor och webbplatser som är relaterade till ämnet.

Dina kunskapsadministratörer kan välja att crawla alla SharePoint-webbplatser i klientorganisationen för ämnen eller att bara välja vissa.

Mer information finns i avsnittet [Ämnesidentifiering och läroplan.](./topic-experiences-discovery-curation.md)

## <a name="roles"></a>Roller

När du använder Viva Topics i Microsoft 365-miljön har användarna följande roller:

- Ämnesanvändare: Användare som kan se ämnen markerade på moderna SharePoint-webbplatser som de har minst *Läsa* åtkomst till och i Microsoft Search. De kan markera ämneshöjdpunkter om du vill se information om ämnet på ämnessidorna. Ämnesanvändare kan ge feedback om hur användbart ett ämne är för dem.

- Deltagare: Användare som har behörighet att redigera befintliga ämnen eller skapa nya. Kunskapsadministratörer tilldelar behörighet som deltagare till användare via inställningarna för Viva Topics i Administrationscenter för Microsoft 365. Observera att du även kan välja att ge alla som tittar på ämnet behörighet att redigera och skapa ämnen så att alla kan bidra till ämnen som de ser.

- Kunskapshanterare: Användare som vägleder ämnen genom ämnets livscykel. Knowledge managers use the Manage topics page in the topic center to confirm AI-suggested topics, remove topics that are no longer relevant, as edit **existing topics** or create new ones, and are the only users who have access to it. Kunskapsadministratörer tilldelar behörighet som kunskapshanterare till användare via inställningarna för Viva Topics i Administrationscenter för Microsoft 365. 

- Kunskapsadministratörer: Administratörer ställer in Viva-ämnen och hanterar det via administratörskontrollerna i Administrationscenter för Microsoft 365. En global Microsoft 365- eller SharePoint-administratör kan för närvarande fungera som kunskapsadministratör.

Mer information finns i [Viva Topics-roller.](topic-experiences-roles.md)

## <a name="topic-management"></a>Ämneshantering

Ämneshanteringen utförs **på sidan** Hantera ämnen i organisationens *ämnescenter.* Ämnescentret skapas under installationen och fungerar som ditt kunskapscenter för din organisation. 

Alla licensierade användare kan se ämnen som de är anslutna  till i ämnescentret, men endast användare med behörigheten Hantera ämnen (knowledge managers) kan visa och använda **sidan Hantera** ämnen.

Kunskapshanterare kan:

- Bekräfta eller ta bort ämnen som har upptäckts i klientorganisationen.
- Skapa nya ämnen manuellt efter behov (om till exempel inte tillräckligt med information tillhandahölls för att den ska upptäckas via AI).
- Redigera befintliga ämnessidor.

Mer information finns i [Hantera ämnen i ämnescentret.](manage-topics.md)  

## <a name="admin-controls"></a>Administratörskontroller

Administratörskontroller i Administrationscenter för Microsoft 365 du kan hantera Viva Ämnen. De gör det möjligt för en global Microsoft 365- eller SharePoint-administratör att:

- Kontrollera vilka användare i organisationen som får se ämnen på moderna sidor i SharePoint eller i SharePoint-sökresultat.
- Kontrollera vilka SharePoint-webbplatser som ska crawlas för att identifiera ämnen.
- Undanta specifika ämnen från att hittas.
- Styra vilka användare som kan hantera ämnen i temacenter.
- Kontrollera vilka användare som kan skapa och redigera ämnen.
- Kontrollera vilka användare som kan visa ämnen.

Mer information om administratörskontroller finns i [Tilldela användarbehörigheter](./plan-topic-experiences.md#user-permissions), [hantera synlighet för ämnen](./topic-experiences-knowledge-rules.md)och hantera identifiering av [ämnen.](./topic-experiences-discovery.md)

## <a name="topic-curation--feedback"></a>Ämneshantering och feedback

AI kommer kontinuerligt att arbeta med att ge förslag för att förbättra dina ämnen när ändringar sker i din miljö. 

Användare med behörighet att redigera eller skapa ämnen kan uppdatera ämnessidor direkt om de vill göra korrigeringar eller lägga till ytterligare information. De kan också lägga till nya ämnen som AI inte kunde identifiera. Om det finns tillräckligt med information om dessa manuellt tillagda ämnen, och AI kan identifiera den här typen av ämne, kan ytterligare förslag från AI förbättra dessa manuellt tillagda ämnen.

Användare som du tillåter åtkomst till för att se ämnen i sitt dagliga arbete kan bli tillfrågade om ämnet var användbart för dem. Systemet ser på svaren och använder dem för att förbättra markering av ämnet, och hjälpa dig att avgöra vad som visas i ämnessammanfattningar och i ämnesinformation.

Mer information finns i avsnittet [Ämnesidentifiering och läroplan.](./topic-experiences-discovery-curation.md)

## <a name="see-also"></a>Se även

[Använda Microsoft Search för att hitta ämnen i Viva-ämnen](./search.md)
