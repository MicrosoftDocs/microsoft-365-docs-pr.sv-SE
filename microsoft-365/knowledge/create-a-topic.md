---
title: Skapa ett nytt ämne i Microsoft Viva-ämnen
description: Så här skapar du ett nytt ämne i Microsoft Viva-ämnen.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 7d1dc1af6e845ccfe2fb0e8f5701a2cd3018c308
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687537"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a>Skapa ett nytt ämne i Microsoft Viva-ämnen

I Viva-ämnen kan du skapa ett nytt ämne om ett ämne inte upptäcks genom indexering eller om AI-tekniken inte hittar tillräckligt med bevis för att det ska kunna etableras som ett ämne.

> [!Note] 
> Observera att information i ett ämne som har samlats av AI är säkerhets trimad [,](topic-experiences-security-trimming.md)men observera att ämnesbeskrivning och personinformation i ett manuellt skapat ämne visas för alla användare som har behörighet att visa ämnet. 


## <a name="requirements"></a>Krav

Om du vill skapa ett nytt ämne måste du:
- Ha en Viva Topics-licens.
- Har behörighet att [**Vem kan skapa eller redigera ämnen**](./topic-experiences-user-permissions.md). Knowledge admins can give users this permission in the Viva Topics topic permissions settings. 

> [!Note] 
> Användare som har behörighet att hantera ämnen i ämnescentret (knowledge managers) har redan behörighet att skapa och redigera ämnen.

## <a name="to-create-a-topic"></a>Skapa ett ämne

Du kan skapa ett nytt ämne från två platser:

- Startsidan för Topic Center: Alla licensierade användare med **Vem** kan skapa eller redigera ämnesbehörigheter (deltagare)  kan skapa ett nytt ämne från ämnescentret genom att välja Nytt-menyn och välja **Ämnessida.** 

    ![Nytt ämne från ämnescenter](../media/knowledge-management/new-topic.png)  

- Sidan Hantera ämnen: Alla licensierade användare som har **Vem** kan hantera behörighet för ämnen (kunskapshanterare) kan skapa ett nytt ämne från sidan Hantera ämnen i Ämnescenter genom att välja **Ny ämnessida.** 

    ![Nytt ämne från hantera ämnen](../media/knowledge-management/new-topic-topic-center.png)  

### <a name="to-create-a-new-topic"></a>Så här skapar du ett nytt ämne:

1. Välj alternativet för att skapa en ny ämnessida från menyfliksområdet på sidan Hantera ämnen.

2.  I avsnittet **Namnge det här** avsnittet skriver du namnet på det nya avsnittet.

    ![Ge det här avsnittet ett namn](../media/knowledge-management/k-new-topic-page.png)  

3. I **avsnittet Alternativa namn** skriver du alla andra namn som ämnet kan hänvisas till. 

    ![Alternativa namn](../media/knowledge-management/alt-names.png)  

4. Skriv **ett** par meningar som beskriver ämnet i avsnittet Beskrivning. 

    ![Beskrivning av ämnet](../media/knowledge-management/description.png)

4. I avsnittet **Fästa personer** kan du fästa en person för att visa att personen har en anslutning till ämnet (till exempel en ägare till en ansluten resurs). Börja med att skriva in  användarens namn eller e-postadress i rutan Lägg till en ny användare och välj sedan den användare du vill lägga till från sökresultatet. Du kan även "ta bort" dem genom att välja **ikonen Ta bort från** listan på användarkortet. Du kan också dra personen till en annan plats i listan.
 
    ![Fästa personer](../media/knowledge-management/pinned-people.png)

5. I avsnittet **Fästa filer och sidor kan** du lägga till eller "fästa" en fil SharePoint en webbplatssida som är kopplad till avsnittet.

   ![Fästa filer och sidor](../media/knowledge-management/pinned-files-and-pages.png)
 
    Om du vill lägga till en ny fil väljer du Lägg till **,** SharePoint webbplats från ofta besökta eller följda webbplatser och väljer sedan filen från webbplatsens dokumentbibliotek.

    Du kan också använda alternativet **Från en länk för** att lägga till en fil eller sida genom att ange URL-adressen. 

    > [!Note] 
    > Filer och sidor som du lägger till måste finnas inom samma Microsoft 365 klientorganisation. Om du vill lägga till en länk till en extern resurs i ämnet kan du lägga till den via ikonen för arbetsytan i steg 8.


6.  I **avsnittet Relaterade** webbplatser visas webbplatser som har information om ämnet. 

    ![Avsnittet Relaterade webbplatser](../media/knowledge-management/related-sites.png)

    Du kan lägga till  en relaterad webbplats genom att välja Lägg till och sedan söka efter webbplatsen eller välja den i listan med vanliga eller senaste webbplatser.
    
    ![Välj webbplats](../media/knowledge-management/sites.png)

7. I **avsnittet Relaterade** ämnen visas anslutningar som finns mellan olika ämnen. Du kan lägga till en anslutning till ett annat ämne genom att välja **knappen Anslut** för ett relaterat ämne, skriva namnet på det relaterade ämnet och välja det i sökresultatet. 

   ![Relaterade ämnen](../media/knowledge-management/related-topic.png)  

    Du kan sedan ge en beskrivning av hur ämnena är relaterade och välja **Uppdatera**.

   ![Beskrivning av relaterade ämnen](../media/knowledge-management/related-topics-update.png) 

   Det relaterade ämnet du har lagt till visas som ett anslutet ämne.

   ![Närliggande ämnen kopplade](../media/knowledge-management/related-topics-final.png) 

   Om du vill ta bort ett relaterat ämne markerar du det ämne du vill ta bort och väljer sedan **ikonen Ta bort** ämne.
 
   ![Ta bort relaterade ämnen](../media/knowledge-management/remove-related.png)  

   Välj sedan Ta **bort**.

   ![Bekräfta borttagning](../media/knowledge-management/remove-related-confirm.png) 

8. Du kan också lägga till statiska objekt på sidan (t.ex. text, bilder eller länkar) genom att välja ikonen för arbetsytan, som du hittar under den korta beskrivningen. Om du markerar den SharePoint verktygslådan där du kan välja objektet du vill lägga till på sidan.

   ![Canvas-ikon](../media/knowledge-management/webpart-library.png) 

9. Spara **ändringarna** genom att välja Publicera. 

När du har publicerat sidan visas ämnesnamnet, alternativt namn, beskrivning och fästa personer för alla licensierade användare som visar ämnet. Specifika filer, sidor och webbplatser visas bara på ämnessidan om användaren Office 365 behörighet till objektet. 



## <a name="see-also"></a>Se även



