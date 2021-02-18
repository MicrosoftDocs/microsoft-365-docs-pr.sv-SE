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
- m365initiative-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: fbdd0e9b75e92d8080d9aaf43a2d1eaa8baacbc3
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279404"
---
# <a name="create-a-new-topic"></a>Skapa ett nytt ämne 

I Viva Topics kan du skapa ett nytt ämne om ett ämne inte upptäcks genom indexering eller om AI-tekniken inte hittar tillräckligt med bevis för att etablera det som ett ämne.

> [!Note] 
> Observera att informationen i ett ämne [](topic-experiences-security-trimming.md)som har samlats av AI är säkerhets trimad, men observera att ämnesbeskrivningen och personinformationen i ett manuellt skapat ämne är synlig för alla användare som har behörighet att visa ämnet. 


## <a name="requirements"></a>Krav

Om du vill skapa ett nytt ämne måste du:
- Ha en Viva Topics-licens.
- Ha behörighet till [**vem som kan skapa eller redigera ämnen.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) Knowledge admins can give users this permission in the Viva Topics topic permissions settings. 

> [!Note] 
> Användare som har behörighet att hantera ämnen i ämnescentret (knowledge managers) har redan behörighet att skapa och redigera ämnen.

## <a name="to-create-a-topic"></a>Så här skapar du ett ämne

Du kan skapa ett nytt ämne från två platser:

- Startsidan för Ämnescenter: Alla  licensierade användare med behörigheten Vem kan skapa eller redigera ämnen (deltagare) kan skapa ett nytt ämne från ämnescentret genom att välja menyn Nytt och sedan välja <b>sidan Ämne.</b> <b></b></br> 

    ![Nytt ämne från ämnescenter](../media/knowledge-management/new-topic.png) </br> 

- Sidan Hantera ämnen: Alla licensierade användare som har behörigheten Vem kan hantera ämnen (knowledge managers) kan skapa ett nytt ämne från sidan Hantera ämnen i Ämnescenter genom att välja <b>Sidan Nytt ämne.</b> </br> 

    ![Nytt ämne från att hantera ämnen](../media/knowledge-management/new-topic-topic-center.png) </br> 

### <a name="to-create-a-new-topic"></a>Så här skapar du ett nytt ämne:

1. I avsnittet **Namnge det här** avsnittet skriver du namnet på det nya avsnittet.

    ![Ge det här avsnittet ett namn](../media/knowledge-management/k-new-topic-page.png) </br> 


2. I avsnittet <b>Alternativa namn</b> skriver du andra namn som ämnet kan hänvisas till. 

    ![Alternativa namn](../media/knowledge-management/alt-names.png) </br> 
3. Skriv <b>några</b> meningar som beskriver ämnet i avsnittet Beskrivning. 

    ![Beskrivning av ämnet](../media/knowledge-management/description.png)</br>

4. I avsnittet <b>Fästa personer kan</b> du fästa en person för att visa personen som ämnesexpert i ämnet. Börja med att skriva in <b></b> användarens namn eller e-postadress i rutan lägg till en ny användare och välj sedan den användare du vill lägga till i sökresultatet. Du kan även "ta bort" dem genom att välja ikonen Ta bort <b>från listan</b> på användarkortet. Du kan också dra personen för att ändra ordningen som listan med personer visas.
 
    ![Fästa personer](../media/knowledge-management/pinned-people.png)</br>


5. I avsnittet <b>Fästa filer och sidor kan</b> du lägga till eller "fästa" en fil eller en SharePoint-webbplatssida som är kopplad till ämnet.

   ![Fästa filer och sidor](../media/knowledge-management/pinned-files-and-pages.png)</br>
 
    Om du vill lägga till en ny fil väljer du Lägg <b>till,</b>väljer SharePoint-webbplatsen från ofta besökta eller följda webbplatser och väljer sedan filen från webbplatsens dokumentbibliotek.

    Du kan också använda alternativet <b>Från en länk för</b> att lägga till en fil eller sida genom att ange URL-adressen. 

    > [!Note] 
    > Filer och sidor som du lägger till måste finnas inom samma Microsoft 365-klientorganisation. Om du vill lägga till en länk till en extern resurs i ämnet kan du lägga till den via arbetsytans ikon i steg 8.


6.  I <b>avsnittet Relaterade</b> webbplatser visas webbplatser som har information om ämnet. 

    ![Avsnittet Relaterade webbplatser](../media/knowledge-management/related-sites.png)</br>

    Du kan lägga till en relaterad webbplats genom att välja <b>Lägg</b> till och sedan antingen söka efter webbplatsen eller välja den i listan med ofta besökta eller senaste webbplatser.</br>
    
    ![Välj webbplats](../media/knowledge-management/sites.png)</br>

7. I <b>avsnittet Relaterade</b> ämnen visas kopplingar som finns mellan olika ämnen. Du kan lägga till en anslutning <b></b> till ett annat ämne genom att välja knappen Anslut till ett relaterat ämne, skriva namnet på det relaterade ämnet och välja det i sökresultatet. 

   ![Relaterade ämnen](../media/knowledge-management/related-topic.png)</br>  

    Du kan sedan ge en beskrivning av hur ämnena är relaterade och välja <b>Uppdatera.</b></br>

   ![Beskrivning av närliggande ämnen](../media/knowledge-management/related-topics-update.png)</br> 

   Det relaterade ämnet som du lagt till visas som ett anslutet ämne.

   ![Närliggande ämnen](../media/knowledge-management/related-topics-final.png)</br> 

   Om du vill ta bort ett relaterat ämne väljer du det ämne du vill ta bort och sedan ikonen <b>Ta bort</b> ämne.</br>
 
   ![Ta bort relaterat ämne](../media/knowledge-management/remove-related.png)</br>  

   Välj sedan <b>Ta bort.</b></br>

   ![Bekräfta borttagning](../media/knowledge-management/remove-related-confirm.png)</br> 
     
 


8. Du kan också lägga till statiska objekt på sidan (t.ex. text, bilder eller länkar) genom att välja ikonen för arbetsytan, som du hittar under den korta beskrivningen. När du markerar den öppnas SharePoint-verktygslådan där du kan välja objektet du vill lägga till på sidan.

   ![Canvas-ikon](../media/knowledge-management/webpart-library.png)</br> 


9. Välj **Publicera** för att spara ändringarna. 

När du har publicerat sidan visas ämnesnamn, alternativt namn, beskrivning och fästa personer för alla licensierade användare som visar ämnet. Specifika filer, sidor och webbplatser visas bara på ämnessidan om visningsprogrammet har Office 365-behörighet till objektet. 



## <a name="see-also"></a>Se även



  






