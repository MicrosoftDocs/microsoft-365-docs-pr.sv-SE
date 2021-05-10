---
title: Ämnescenteröversikt i Microsoft Viva-ämnen
description: Läs mer om Ämnescenter i Microsoft Viva-ämnen.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ROBOTS: ''
localization_priority: None
ms.openlocfilehash: bdb49af4ac43976a1ad734e507902781d63c5670
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301794"
---
# <a name="topic-center-overview-in-microsoft-viva-topics"></a>Ämnescenteröversikt i Microsoft Viva-ämnen

I Microsoft Viva Topics är ämnescentret en modern SharePoint som fungerar som kunskapscentrum för organisationen. Den skapas under installationen [av Viva Topics](set-up-topic-experiences.md) i Microsoft 365 administrationscenter.

I ämnescentret finns en  standardhemsida med webbdelen Ämnen där alla licensierade användare kan se ämnen som de har en anslutning till. 

Alla licensierade användare som kan visa ämnen har tillgång till ämnescentret, men knowledge managers kan också hantera ämnen via **sidan Hantera** ämnen. Fliken **Hantera ämnen** visas bara för användare som har behörigheten Hantera ämnen. 

## <a name="where-is-my-topic-center"></a>Var finns mitt ämnescenter?

Ämnescentret skapas under installationen av Viva Topics. När installationen är klar kan administratören hitta URL-adressen på sidan [För hantering av ämnescenter.](./topic-experiences-administration.md#to-access-topics-management-settings)


1. I Microsoft 365 väljer du Först **Inställningar** och sedan **Organisationsinställningar.**
2. Välj **Ämnesupplevelser** på **fliken Tjänster.**

    ![Anslut att få kunskap](../media/admin-org-knowledge-options-completed.png) </br>

3. Välj fliken **Ämnescenter.** Under **Webbplatsadress** finns en länk till ämnescentret.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-center.png) </br>



## <a name="home-page"></a>Startsida

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LAhZ]  

</br>


På startsidan för ämnescentret kan du se de ämnen i organisationen som du har en anslutning till.

- Föreslagna anslutningar – Du ser ämnen listade under **Vi har listat dig om dessa ämnen. Blev det rätt?** Det här är ämnen där din koppling till ämnet har föreslagits via AI. Du kan till exempel vara författare till en relaterad fil eller webbplats. Du uppmanas att bekräfta att du bör vara listad som en relaterad person för ämnet.

   ![Föreslagna anslutningar](../media/knowledge-management/my-topics.png) </br>
 
- Bekräftade anslutningar – Det här är ämnen där du är fäst på ämnessidan eller om du har bekräftat en föreslagen anslutning till avsnittet. Ämnen flyttas från det föreslagna avsnittet till bekräftad när du bekräftar en föreslagen anslutning.
 
   ![Bekräftade ämnen](../media/knowledge-management/my-topics-confirmed.png) </br>

När en användare bekräftar sin anslutning till ett ämne kan användaren göra ändringar på ämnessidan för att curate anslutningen. De kan till exempel ge mer information om anslutningen till ämnet.


## <a name="manage-topics-page"></a>Sidan Hantera ämnen

För att kunna arbeta **i avsnittet** Hantera ämnen i ämnescentret måste du ha den behörighet för Hantera ämne som krävs för knowledge manager-rollen. Administratören kan tilldela de här [](set-up-topic-experiences.md)behörigheterna till användare under [kunskapshanteringskonfigurationen,](topic-experiences-knowledge-rules.md) eller så kan nya användare läggas till efteråt av en administratör via Microsoft 365 administrationscentret.

På sidan Hantera ämnen visar instrumentpanelen ämne alla ämnen som du har åtkomst till och som identifierats från dina angivna källplatser. Varje ämne kommer att visa det datum då ämnet upptäcktes. En användare som har tilldelats behörigheten Hantera ämnen kan granska de ofirmerade ämnena och välja att:
- Bekräfta ämnet: Anger för användare att ett AI-föreslaget ämne har validerats av en mänsklig man. 
- Publicera ämnet: Redigera ämnesinformationen för att förbättra kvaliteten på det ämne som ursprungligen identifierades och markerar avsnittet för alla användare som har åtkomst till ämnen. 
- Ta bort ämnet: Gör att ämnet inte kan upptäckts för slutanvändare. Avsnittet flyttas till fliken **Borttaget** och kan bekräftas senare om det behövs. 

> [!Note] 
> Mer [information om ämnenhantering](manage-topics.md) finns i Hantera ämnen på sidan Hantera ämnen.

## <a name="create-or-edit-a-topic"></a>Skapa eller redigera ett ämne

Om du har behörigheten Skapa och redigera ämnen kan du:

- [Redigera befintliga ämnen:](edit-a-topic.md)Du kan göra ändringar i befintliga ämnessidor som skapats genom identifiering.
- [Skapa nya ämnen:](create-a-topic.md)Du kan skapa nya ämnen för ämnen som inte hittades genom upptäckten eller om AI-verktygen inte hittade tillräckligt många bevis för att skapa ett ämne.


## <a name="see-also"></a>Se även

[Hantera ämnen i ämnes centret](manage-topics.md)

