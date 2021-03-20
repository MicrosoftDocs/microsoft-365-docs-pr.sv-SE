---
title: 'Ämnesidentifiering och läroplan för Microsoft Viva-ämnen  '
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
ms.openlocfilehash: 2f4c726849d438738f3c0d432daab53ee27b19ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917434"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Identifiering och säkring av Microsoft Viva-ämnen 

Viva Ämnen ordnar information och kunskaper i din Microsoft 365-miljö. Vi har all erfarenhet av att läsa igenom dokument och webbplatssidor där vi stöter på termer som vi inte är vana vid. Många gånger stannar vi vad vi gör för att ägna tid åt att söka efter mer information.

Viva Topics använder Microsoft Graph och AI för att **identifiera ämnen** i organisationen.  Ett ämne är en fras eller term som har en särskild betydelse för organisationen och har relaterade resurser som kan hjälpa andra att förstå vad det är och hitta mer information om det. Det finns många olika typer av ämnen som är viktiga för din organisation. Till en början kan du identifiera följande typer av ämnen:
- Project
- Händelse
- Organisation
- Plats
- Produkt
- Kreativt arbete
- Studiefält

AI identifierar personer och innehåll som är kopplat till ämnet, och om tillräckligt många upptäcks blir det ett föreslaget ämne. Du identifierar följande egenskaper och visar dem på en **ämnessida:**
- Alternativa namn och/eller förkortningar.
- En kort beskrivning om ämnet.
- Personer som kan vara kunniga om ämnet.
- Filer, sidor och webbplatser som är relaterade till ämnet.

Egenskaperna identifieras från filerna och sidorna som är en del av bevisen för att identifiera ämnet. Alternativa namn och förkortningar kommer från dessa filer och sidor. Den korta beskrivningen kommer från dessa filer och sidor, eller från Internet via Wikipedia. Källfilen, sidan eller Wikipedia-artikeln refereras tillsammans med de föreslagna egenskaperna. Personer föreslås utifrån deras aktiva bidrag (till exempel redigeringar) i filerna och sidorna. En referens till beloppet för en viss person ger en ledtråd till varför personen har identifierats. Filer, sidor och webbplatser rangordnas utifrån om de är centrala för ämnet, oavsett om de kan ge en översikt eller introduktion till ämnet. 

Det är inte alla ämnen som du bör ha nytta av i din organisation. Den kanske inte har identifierat något av rätt alternativa namn, beskrivningar, lämpliga personer eller innehåll. Möjligheten att lägga till ämnen som inte har identifierats, hålla föreslagna ämnen och särskilt viktiga för att förbättra kvaliteten på ämnen som kan upptäckas i organisationen.

När kontexten är lämplig föreslår Viva Ämnen att följande ämnen markeras på alla sidor på moderna SharePoint-webbplatser i klientorganisationen. En sidförfattare kan också referera till avsnittet direkt på sidan för den moderna SharePoint-webbplatsen. När en användare är nyfiken på att få mer information om  ett ämne kan de välja det markerade avsnittet för att visa ett kort med en kort ämnessammanfattning som ger en kort beskrivning. Och om de vill veta mer kan de välja länken **Ämnesinformation** i sammanfattningen för att öppna sidan med detaljerad information.

![Höjdpunkter Topic](../media/knowledge-management/saturn.png) </br>

Dessutom kan användare hitta ämnen via Microsoft Search.

## <a name="topic-curation-and-feedback"></a>Ämnes curation och feedback

Viva Topics tar gärna del av en person som vill förbättra kvaliteten på dina ämnen. Även om AI först identifierar och föreslår ämnen är det manuellt gjorda redigeringar av innehåll från deltagare, manuellt tillagda ämnen, bekräftelse från användare av AI-upptäckta egenskaper och innehåll och feedback på användbara ämnen allt viktigt.

- Ämnen kan granskas av **kunskapschefer** i organisationen. Knowledge Manager kan granska ämnen som de har behörighet att se. På sidan Hantera ämnen i ämnescentret kan de välja att bekräfta AI-genererade ämnen ("föreslagna ämnen") som giltiga, avvisa ämnen för att förhindra att innehållet visas som ett ämne, skapa ämnen som inte identifierats av AI eller identifiera ämnen som kan dra nytta av några redigeringar av ämnesexperter för att vara mer användbara eller korrekta. Mer information finns i [Hantera ämnen i Ämnescenter.](manage-topics.md)

- Du kan tilldela *behörigheten Skapa och* redigera ämnen till en av dina licensierade användare så att de kan göra ändringar i befintliga ämnen eller skapa nya ämnen. På så sätt kan användare med kunskap om avsnittet uppdatera ämnessidan direkt för att göra korrigeringar eller lägga till ytterligare information. De kan också lägga till nya ämnen som AI inte kunde identifiera. Om det finns tillräckligt med information om dessa manuellt tillagda ämnen, och AI kan identifiera den här typen av ämne, kan ytterligare förslag från AI förbättra dessa manuellt tillagda ämnen. Människor och AI kan hålla kunskap rätt med tiden och inte ha den här på en person. Mer information finns i [Skapa ett nytt ämne](./create-a-topic.md) och Redigera ett [ämne.](./edit-a-topic.md)

- Även användare som bara har läsbehörighet till ämne (ämnes läsare) kommer att uppmanas att kontrollera hur användbara vissa ämnen är. Feedbackfrågor ställs på kortet **Ämnessammanfattning** för att förbättra värdet på ämnet och dess information. Frågor om kvaliteten och användbarheten för AI-förslagen presenteras för användarna ett i taget. Frågor som ingår:</br>

    1. Om det var användbart att identifiera ämnet på SharePoint-sidan. Det finns en möjlighet att ta bort markeringen om den inte är korrekt eller användbar. Om tillräckligt många personer anger att ett ämne inte identifieras korrekt på en viss sida kommer den här markeringen så småningom att tas bort för alla användare. 

    2. Om det föreslagna ämnet är värdefullt för organisationen. Om tillräckligt många personer anger att det föreslagna ämnet är värdefullt bekräftas ämnet automatiskt. Om det föreslagna ämnet inte är värdefullt avvisas ämnet automatiskt. Knowledge Manager kan observera den här aktiviteten i vyn Hantera ämnen.

    3. Om personer och resursförslag är användbara.

    4. På startsidan för Ämnescenter kan du se de ämnen i organisationen som du har en anslutning till. Du kan välja att själv stanna kvar i ämnet eller ta bort dig själv. Den här feedbacken återspeglas för alla som upptäcker det här avsnittet. Se [Översikt över ämnescenter](./topic-center-overview.md) för mer information på startsidan för ämnescentret.

Även om människor redigerar söker AI kontinuerligt efter mer information om ämnen och söker efter mänsklig verifiering. Om AI till exempel tror att du är en person som ska finnas med som expert på ett ämne, kommer den att be dig att bekräfta detta. 


## <a name="see-also"></a>Se även