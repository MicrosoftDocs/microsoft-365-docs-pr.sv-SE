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
- m365initiative-topics
localization_priority: None
description: Översikt över Viva-ämnen.
ms.openlocfilehash: f45e0f7c6090d4584526aa9c2abb5ec98213d635
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107651"
---
# <a name="microsoft-viva-topics-overview"></a>Översikt över Microsoft Viva-ämnen 

Viva Topics använder Microsoft AI-teknik, Microsoft 365, Microsoft Graph, Search och andra komponenter och tjänster för att ge dina användare kunskap i Microsoft 365-appar de använder varje dag, med början på moderna SharePoint-sidor och Microsoft Search.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Viva Topics hjälper till att lösa viktiga affärsproblem i många företag – att tillhandahålla information till användare när de behöver det. Nya medarbetare behöver till exempel lära sig mycket ny information snabbt och stöter på termer som de inte vet någonting om när de läser igenom företagets information. Om du vill veta mer kan användaren behöva gå ifrån vad de gör och ägna värdefull tid åt att söka efter information, till exempel information om vad termen är, vem i organisationen som är ämnesexpert, och kanske webbplatser och dokument som är relaterade till termen.

Viva Topics använder AI för att automatiskt söka efter och identifiera **ämnen** i organisationen. Den sammanställer information om dem, till exempel en kort beskrivning, personer som arbetar med ämnet och webbplatser, filer och sidor som är relaterade till den. En knowledge manager eller deltagare kan välja att uppdatera ämnesinformationen efter behov. Ämnena är tillgängliga för användarna, vilket innebär att texten markeras för alla förekomster av ämnet som visas på en modern SharePoint-webbplats i nyheter och sidor. Användarna kan välja att markera avsnittet för att få mer information via ämnesinformationen. Ämnen finns också i SharePoint Search.


## <a name="how-topics-are-displayed-to-users"></a>Hur ämnen visas för användare

När ett ämne nämns i innehåll på nyheter och sidor i SharePoint visas det markerat. Du kan öppna ämnessammanfattningen från överstrykningen. Öppna ämnesinformationen från rubriken på sammanfattningen. Det omnämnda ämnet kan identifieras automatiskt eller ha lagts till på sidan med en direkt referens till avsnittet av sidförfattaren. 

   ![Viktiga ämnen](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Kunskapsindexering

Viva Topics använder Microsoft AI-teknik för att identifiera **ämnen** i Din Microsoft 365-miljö.

Ett ämne är en fras eller term som är signifikant eller viktig i organisationen. Den har en särskild betydelse för organisationen och har relaterade resurser som kan hjälpa andra att förstå vad det är och hitta mer information om det. Det finns många olika typer av ämnen som är viktiga för din organisation. I början fokuserar Microsoft AI-tekniken på följande typer:
- Project
- Händelse
- Organisation
- Plats
- Produkt
- Kreativt arbete
- Studiefält


När ett ämne identifieras och AI avgör att det har tillräckligt  med information för att det ska vara ett föreslaget ämne, visar en ämnessida den information som har samlats genom ämnesindexeringen, till exempel:

- Alternativa namn och förkortningar.
- En kort beskrivning av ämnet.
- Personer som kanske känner till ämnet.
- Filer, sidor och webbplatser som är relaterade till ämnet.

Dina kunskapsadministratörer kan välja att crawla alla SharePoint-webbplatser i klientorganisationen efter ämnen eller bara välja vissa.

Se [identifiering och curation av ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)

## <a name="roles"></a>Roller

När du använder Viva Topics i Microsoft 365-miljön har användarna följande roller:

- Ämnes läsare: Användare som kan se viktiga ämnen på  moderna SharePoint-webbplatser som de har minst läsbehörighet till och i Microsoft Search. De kan välja ämnes fokuspunkter för att se ämnesinformation på ämnessidor. Ämnes läsare kan ge feedback om hur användbart ett ämne är för dem.

- Deltagare: Användare som har behörighet att redigera befintliga ämnen eller skapa nya. Kunskapsadministratörer tilldelar deltagarbehörigheter till användare via inställningarna för Viva Topics i administrationscentret för Microsoft 365. Observera att du även kan ge alla som visar ämnen behörighet att redigera och skapa ämnen så att alla kan bidra till ämnen som de ser.

- Knowledge managers: Users who guide topics through the topic lifecycle. Knowledge managers use the Manage Topics page in the Topic center to confirm AI-suggested topics, remove topics that are no longer relevant, as as **edit existing** topics or create new ones, and are the only users who have access to it. Kunskapsadministratörer tilldelar användare behörighet som knowledge manager via administratörsinställningarna för Viva Topics i administrationscentret för Microsoft 365. 

- Kunskapsadministratörer: Kunskapsadministratörer ställer in Viva-ämnen och hanterar det via administratörskontrollerna i administrationscentret för Microsoft 365. För närvarande kan en global Microsoft 365- eller SharePoint-administratör fungera som kunskapsadministratör.

Mer information [finns i Rollerna i Viva-ämnen.](topic-experiences-roles.md)

## <a name="topic-management"></a>Ämneshantering

Ämneshanteringen utförs **på sidan Hantera** ämnen i organisationens **ämnescenter.** Ämnescentret skapas under installationen och fungerar som ditt kunskapscenter för din organisation. 

Alla licensierade användare kan se ämnen som de är anslutna  till i ämnescentret, men endast användare med behörigheten Hantera ämnen (knowledge managers) kan visa och använda sidan Hantera ämnen.

Kunskapschefer kan:

- Bekräfta eller ta bort ämnen som identifierats i klientorganisationen.
- Skapa nya ämnen manuellt efter behov (om till exempel inte tillräckligt med information har tillhandahållits för att den ska upptäckas via AI).
- Redigera befintliga ämnessidor.</br>

Mer information [finns i Hantera ämnen i ämnescentret.](manage-topics.md)  


## <a name="admin-controls"></a>Administratörskontroller

Med administratörskontroller i administrationscentret för Microsoft 365 kan du hantera ditt kunskapsnätverk. De gör det möjligt för en global Microsoft 365- eller SharePoint-administratör att:

- Styr vilka användare i organisationen som får se ämnen på moderna SharePoint-sidor eller i SharePoint-sökresultat.
- Styr vilka SharePoint-webbplatser som crawlas för att identifiera ämnen.
- Undanta vissa ämnen från att hittas.
- Styr vilka användare som kan hantera ämnen i ämnescentret.
- Styr vilka användare som kan skapa och redigera ämnen.
- Styr vilka användare som kan visa ämnen.

Se [tilldela användarbehörigheter,](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions) [hantera synlighet för ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)och hantera identifiering av [ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) för mer information om administratörskontroller.

## <a name="topic-curation--feedback"></a>Ämnes curation & feedback

AI arbetar kontinuerligt med att ge förslag för att förbättra dina ämnen när ändringar sker i din miljö. 

Användare med behörighet att redigera eller skapa ämnen kan uppdatera ämnessidor direkt om de vill göra korrigeringar eller lägga till ytterligare information. De kan också lägga till nya ämnen som AI inte kunde identifiera. Om det finns tillräckligt med information om dessa manuellt tillagda ämnen och AI kan identifiera den här typen av ämne kan ytterligare förslag från AI förbättra dessa manuellt tillagda ämnen 

Användare som du tillåter åtkomst till för att se ämnen i sitt dagliga arbete kan bli tillfrågade om ämnet var användbart för dem. Systemet tittar på de här svaren och använder dem för att förbättra ämnets markering och hjälper till att avgöra vad som visas i ämnessammanfattningar och i ämnesinformation.

Användare med rätt behörighet kan dessutom tagga objekt som Yammer konversation som är relevant för ett ämne och lägga till dem i ett visst ämne. 

Se [identifiering och curation av ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)


## <a name="see-also"></a>Se även

