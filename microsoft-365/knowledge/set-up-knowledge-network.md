---
title: 'Konfigurera kunskapshantering (förhandsversion) '
description: Så här ställer du in Knowledge Management.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: d4bc45bd1c88d4043df661972399dc6740dbed84
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540136"
---
# <a name="set-up-knowledge-management-preview"></a>Konfigurera kunskapshantering (förhandsversion)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

Du kan använda administrationscentret för Microsoft 365 för att konfigurera [Kunskapshantering](knowledge-management-overview.md). 

> [!Important]
> Det är viktigt att planera det bästa sättet att konfigurera och konfigurera Kunskapshantering i din miljö. Du måste till exempel ta hänsyn till följande:
- Vilka SharePoint-webbplatser du vill analysera för ämnen.
- Vilka användare du vill göra ämnen synliga för.
- Vilka användare du vill ge behörighet att hantera ämnen i ämnescentret.
- Vilka användare du vill ge behörighet att skapa eller redigera ämnen i ämnescentret.
- Vilket namn du vill ge ditt ämnescenter.

> [!Note]
> Det kan vara bra att skapa säkerhetsgrupper för att tilldela användarna de behörigheter som behövs för att visa ämnen, hantera ämnen och skapa och redigera ämnen.

En administratör kan också [göra ändringar i dina valda inställningar när som helst efter installationen](manage-knowledge-network.md) via knowledge management-inställningarna i Administrationscentret för Microsoft 365.

## <a name="requirements"></a>Krav 
Du måste ha behörighet för global administratör eller SharePoint-administratör för att kunna komma åt Microsoft 365-administrationscentret och konfigurera organisatoriska kunskapsuppgifter.

## <a name="set-up-your-knowledge-network"></a>Konfigurera kunskapsnätverket

När du konfigurerar kunskapsnätverket får du följande information:

- Ämnesidentifiering: Välja ämneskällor och ämnen som ska uteslutas från identifiering.
- Ämnessynlighet: Välja vem som kan visa ämnen som högdagrar, på sök- och ämnessidor.
- Ämnesbehörigheter: Välja vem som kan skapa, redigera och hantera ämnen.
- Ämnescenter: Skapa ditt ämnescenter.
- Granska: Kontrollera och tillämpa inställningarna.

Så här konfigurerar du kunskapsnätverket:

1. I administrationscentret för Microsoft 365 (admin.microsoft.com) väljer du **Installationsprogrammet**och visar sedan avsnittet **Organisationskunskap.**
2. Klicka på Anslut personer **till kunskap**i avsnittet **Organisationskunskap.**<br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. På sidan **Anslut personer till kunskap** klickar du på Kom **igång** för att gå igenom installationsprocessen.<br/>

    ![Komma igång](../media/content-understanding/k-get-started.png) </br>

4. På sidan **Välj hur kunskapsnätverket kan hitta ämnen** konfigurerar du ämnesidentifiering. I avsnittet **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som ska genomsökas som källor för dina ämnen under identifieringen. Detta inkluderar:</br>
    a. **Alla webbplatser:** Alla SharePoint-webbplatser i din klientorganisation. Detta fångar nuvarande och framtida webbplatser.</br>
    b. **Alla, utom valda platser:** Skriv namnen på de webbplatser som du vill utesluta.  Du kan också ladda upp en lista över webbplatser som du vill välja bort från identifiering. Webbplatser som skapas i framtiden kommer att inkluderas som källor för ämnesidentifiering. </br>
    c. **Endast valda platser:** Skriv namnen på de platser som du vill inkludera. Du kan också ladda upp en lista över webbplatser. Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för ämnesidentifiering. </br>

    ![Välj hur du hittar ämnen](../media/content-understanding/ksetup1.png) </br>
   
5. I avsnittet **Uteslut efter namn** kan du välja att ta med namn på ämnen som du inte vill ska finnas i de identifierade resultaten. Använd den här inställningen om du vill förhindra att känsliga ämnen inkluderas som en del av kunskapsnätverket. Dina alternativ inkluderar:</br>
    a. **Uteslut inte några ämnen** </br>
    b. **Uteslut ämne som innehåller dessa termer**: Om du har ämnen som du inte vill visa för användare som en del av kunskapsnätverket.
   - Ladda ner den medföljande mallen.
   - Ange de ämnesnamn som du vill utesluta. Du måste ange matchningstypen som exakt eller partiell. Exakt matchning innebär att ämnen som passar den exakta termen utesluts. Partiell matchning är strängare och innebär att ämnen som innehåller termen utesluts. Om du till exempel anger *Doc* som ämnesnamn utesluts *Doc-sammansättning* medan *Docker* inte gör det. Ämnesnamn är skiftlägesokänsliga.  
        - Välj om du  **+**   vill importera den färdiga CSV-filen. Välj sedan **Ladda upp**. Du ser en grön bock om filen har bearbetats. Välj **Nästa**.</br>


6. På sidan **Vem kan se ämnen och var de kan se dem** konfigurerar du ämnessynlighet. I inställningen **Vem kan se ämnen i kunskapsnätverket** väljer du vem som ska ha tillgång till ämnesinformation, till exempel markerade ämnen, ämneskort, ämnessvar i sök- och ämnessidor. Du kan välja:</br>
    a. **Alla i organisationen**</br>
    b. **Endast markerade personer eller säkerhetsgrupper**</br>
    c. **Ingen**</br>

    ![Vem kan se ämnen](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskapshanteringslicenser som tilldelats dem kan visa ämnen. 

7. På sidan **Behörigheter för ämneshantering** väljer du vem som ska kunna skapa, redigera eller hantera ämnen. I avsnittet **Vem kan skapa och redigera ämnen** kan du välja:</br>
    a. **Alla i organisationen**</br>
    b. **Endast markerade personer eller säkerhetsgrupper**</br>
8. I avsnittet **Vem kan hantera ämnen** kan du välja:</br>
    a. **Alla i organisationen**</br>
    b. **Utvalda personer eller säkerhetsgrupper**</br>

    ![Behörigheter för ämneshantering](../media/content-understanding/ksetup3.png) </br>

    Välj **Nästa**.</br>
9. På sidan **Skapa ämnescenter** kan du skapa en webbplats för ämnescenter där ämnessidor kan visas och ämnen kan hanteras.  Skriv ett namn på ämnescentret i **rutan Ämnescenter.** Du kan också skriva en kort beskrivning i rutan **Webbplatsbeskrivning.** </br>

Välj **Nästa**.</br>

   ![Skapa kunskapscenter](../media/content-understanding/ksetup4.png) </br> 

10. På sidan **Granska och avsluta** kan du titta på den valda inställningen och välja att göra ändringar. Om du är nöjd med dina val väljer du **Aktivera**.

    ![Avsluta och granska](../media/content-understanding/ksetup5.png) </br> 

11. Sidan **Kunskapsnätverk som aktiveras** visas och bekräftar att systemet nu kommer att börja analysera dina valda webbplatser för ämnen och skapa knowledge center-webbplatsen. Välj **Klar**.</br>

    ![Aktiverat](../media/content-understanding/ksetup6.png) </br> 

12. Du kommer tillbaka till din **Anslut personer till kunskapssidan.** På den här sidan kan du välja **Hantera** om du vill göra ändringar i konfigurationsinställningarna. 

    ![Inställningar tillämpas](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> Efter installationen kan en administratör [göra ändringar i dina valda inställningar för kunskapshantering](manage-knowledge-network.md) när som helst genom att gå tillbaka till den här sidan.


## <a name="see-also"></a>Se även



  






