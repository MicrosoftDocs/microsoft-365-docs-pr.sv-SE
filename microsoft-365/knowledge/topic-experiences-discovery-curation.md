---
title: 'Ämnesidentifiering och läroplan för Microsoft Viva Topics  '
description: Översikt över hur ämnen upptäcks.
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 036dbc4029cc7e8308ad295ccd8b45dc3879a6f8
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453963"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Identifiering och säkring av Microsoft Viva-ämnen 

Viva Topics ordnar information efter kunskap i Microsoft 365-miljön. Vi har alla erfarenhet av att läsa igenom dokument och webbplatssidor där vi stöter på termer som vi inte är bekant med. Många gånger slutar vi göra det vi gör för att ägna tid åt att söka efter mer information.

Viva Topics använder Microsoft Graph och AI för att identifiera **ämnen** i organisationen.  Ett ämne är en fras eller term som har en särskild betydelse för organisationen och som har relaterade resurser som kan hjälpa andra att förstå vad det är och hitta mer information om det. Det finns många olika typer av ämnen som är viktiga för din organisation. Till en början kan du identifiera följande typer av ämnen:
- Project
- Händelse
- Organisation
- Plats
- Produkt
- Kreativt arbete
- Studiefält

AI identifierar personer och innehåll som är kopplat till ämnet och om tillräckligt mycket upptäcks blir det ett föreslaget ämne. Du identifierar följande egenskaper och visar dem på en **ämnessida:**
- Alternativa namn och/eller förkortningar.
- En kort beskrivning av ämnet.
- Personer som kanske känner till ämnet.
- Filer, sidor och webbplatser som är relaterade till ämnet.

Egenskaperna identifieras från filerna och sidorna som är en del av beviset för att identifiera ämnet. Alternativa namn och förkortningar kommer från dessa filer och sidor. Den korta beskrivningen kommer från dessa filer och sidor eller från Internet via Wikipedia. Källfilen, sidan eller Wikipedia-artikeln refereras till tillsammans med de föreslagna egenskaperna. Personer föreslås utifrån deras aktiva bidrag (till exempel ändringar) i filer och sidor. En referens till beloppet för en viss person ger en ledtråd till varför personen har identifierats. Filer, sidor och webbplatser rangordnas utifrån om de är centrala för ämnet, oavsett om de kan ge en översikt eller introduktion till ämnet. 

Alla ämnen kommer inte att vara användbara för din organisation. Den kanske inte har identifierat något av de rätta alternativa namnen, beskrivningarna, rätt personer eller innehåll. Så möjligheten att lägga till ämnen som inte identifieras, behålla föreslagna ämnen och ämnen är avgörande för att förbättra kvaliteten på ämnen som kan upptäckas i organisationen.

När kontexten är lämplig föreslår Viva Topics att dessa ämnen markeras på alla moderna SharePoint-webbplatssidor i klientorganisationen. En sidförfattare kan också referera till avsnittet direkt på sidan för modern SharePoint-webbplats. När en användare är nyfiken på att få mer information om  ett ämne kan de välja det markerade avsnittet för att visa ett kort för ämnessammanfattning som ger en kort beskrivning. Och om de vill veta mer kan de välja en länk **för** ämnesinformation i sammanfattningen för att öppna den detaljerade ämnessidan.

![Viktiga ämnen](../media/knowledge-management/saturn.png) </br>

Dessutom kan användare också hitta ämnen via Microsoft Search.

## <a name="topic-curation-and-feedback"></a>Ämnes curation och feedback

Viva Topics tar gärna del av ditt bidrag till att förbättra kvaliteten på dina ämnen. Medan AI först identifierar och föreslår ämnen är det viktigt att manuellt redigera innehåll från deltagare, manuellt lägga till ämnen, bekräfta från användare för AI-identifierade egenskaper och innehåll och att ge feedback på användbarheten för ämnen.

- Ämnen kan granskas av **kunskapsansvariga** i organisationen. Kunskapshanteraren kan granska ämnen som de har behörighet att se. På sidan Hantera ämnen i Ämnescenter kan de välja att bekräfta AI-genererade ämnen ("föreslagna ämnen") som giltiga, avvisa ämnen för att förhindra att innehållet visas som ett ämne, skapa ämnen som inte identifierats av AI eller identifiera ämnen som kan dra nytta av några redigeringar av ämnesexperter för att vara mer användbara eller korrekta. Mer information finns i [Hantera ämnen i Ämnescenter.](manage-topics.md)

- Du kan tilldela *behörigheten Skapa och* redigera ämnen till alla dina licensierade användare så att de kan göra ändringar i befintliga ämnen eller skapa nya ämnen. På så sätt kan användare som är kunniga om ämnet uppdatera ämnessidan direkt för att göra korrigeringar eller lägga till ytterligare information. De kan också lägga till nya ämnen som AI inte kunde identifiera. Om det finns tillräckligt med information om dessa manuellt tillagda ämnen, och AI kan identifiera den här typen av ämne, kan ytterligare förslag från AI förbättra dessa manuellt tillagda ämnen. Människor och AI kan tillsammans hålla kunskap rätt med tiden och inte ha detta på en enda person. Mer information finns i Skapa [ett nytt ämne](https://docs.microsoft.com/microsoft-365/knowledge/create-a-topic) och Redigera ett [ämne.](https://docs.microsoft.com/microsoft-365/knowledge/edit-a-topic)

- Även användare som bara har läsbehörighet till ämnen (ämnesvisare) uppmanas att kontrollera hur användbara vissa ämnen är. Feedbackfrågor ställs på **sammanfattningskortet Ämne** för att förbättra ämnets värde och information. Frågor om kvaliteten och användbarheten i AI-förslagen presenteras för användarna en i taget. Frågor omfattar:</br>

    1. Om det var användbart att identifiera ämnet på SharePoint-sidan. Det finns en möjlighet att ta bort markeringen om den inte är korrekt eller användbar. Om tillräckligt många personer anger att ett ämne inte identifieras korrekt på en viss sida kommer den här markeringen så småningom att tas bort för alla användare. 

    2. Om det föreslagna ämnet är värdefullt för organisationen. Om tillräckligt många anger att det föreslagna ämnet är värdefullt bekräftas ämnet automatiskt. Om det föreslagna ämnet inte är värdefullt avvisas ämnet automatiskt. Knowledge Manager kan observera den här aktiviteten i vyn Hantera ämnen.

    3. Om personer och resursförslag är användbara.

    4. På startsidan för Ämnescenter kan du se de ämnen i organisationen som du har en anslutning till. Du kan välja att själv stå kvar i listan över ämnet eller ta bort dig själv. Den här feedbacken återspeglas för alla som upptäcker det här avsnittet. Se [översikten över Ämnescenter](https://docs.microsoft.com/microsoft-365/knowledge/topic-center-overview) för mer information på startsidan för ämnescentret.

Även när människor redigerar söker AI kontinuerligt efter mer information om ämnen och söker efter verifiering av människor. Om AI till exempel tror att du är en person som bör finnas med som expert på ett ämne, får du bekräfta detta. 


## <a name="see-also"></a>Se även
