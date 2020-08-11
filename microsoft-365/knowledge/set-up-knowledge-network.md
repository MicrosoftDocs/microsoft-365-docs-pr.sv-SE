---
title: 'Konfigurera kunskaps hantering (för hands version) '
description: Så här konfigurerar du kunskaps hantering.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612554"
---
# <a name="set-up-knowledge-management-preview"></a>Konfigurera kunskaps hantering (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Du kan använda administrations centret för Microsoft 365 för att ställa in och konfigurera [kunskaps hantering](knowledge-management-overview.md). 

> [!Important]
> Det är viktigt att planera det bästa sättet att ställa in och konfigurera kunskaps hantering i din miljö. Till exempel måste du tänka på följande:
- Vilka SharePoint-webbplatser som du vill analysera för avsnitt.
- Vilka användare du vill göra ämnen synliga för.
- Vilka användare som du vill ge behörighet att hantera ämnen i ämnes centret.
- Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnes centret.
- Vilket namn du vill ge ditt ämnes Center.

> [!Note]
> Det kan vara praktiskt att skapa säkerhets grupper för att ge användarna de behörigheter som krävs för att Visa ämnen, hantera ämne och skapa och redigera ämnen.

En administratör kan också [göra ändringar i dina valda inställningar när som helst efter installationen](manage-knowledge-network.md) via kunskaps hanterings inställningarna i Microsoft 365 Admin Center.

## <a name="requirements"></a>Krav 
Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och ställa in organisationens kunskaps uppgifter.

## <a name="set-up-your-knowledge-network"></a>Konfigurera kunskaps nätverk

Genom att konfigurera kunskaps nätverket får du hjälp med följande:

- Avsnitts identifiering: välja ämnen och ämnen som ska undantas från identifieringen.
- Ämnets synlighet: välja vilka som får Visa ämnen som högdagrar, på sidan Sök och ämnen.
- Behörigheter för ämne: välja vem som kan skapa, redigera och hantera ämnen.
- Ämnes Center: skapa ett ämnes Center.
- Granska: kontrol lera och tillämpa dina inställningar.

Så här konfigurerar du ditt kunskaps nätverk:

1. I administrations centret för Microsoft 365 (admin.microsoft.com) väljer du **Konfigurera**och sedan Visa avsnittet **organisations** information.
2. I avsnittet **organisationsinformation** klickar du på **Anslut personer till kunskap**.<br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. På sidan **Anslut personer till kunskap** klickar du på **komma igång** för att vägleda dig genom installations processen.<br/>

    ![Komma igång](../media/content-understanding/k-get-started.png) </br>

4. På sidan **Välj hur kunskaps nätverket kan hitta ämnes** sidor konfigurerar du identifiering av avsnitt. Välj vilka SharePoint-webbplatser som ska crawlas som källor för dina ämnen under identifiering i avsnittet Välj avsnitts **källor för SharePoint** . Detta inkluderar:</br>
    a. **Alla webbplatser**: alla SharePoint-webbplatser i din klient organisation. Här fångar du aktuella och framtida webbplatser.</br>
    b. **Alla, förutom markerade webbplatser**: Skriv namnen på de webbplatser du vill undanta.  Du kan också ladda upp en lista med webbplatser som du inte vill ska ingå i sökningen. Webbplatser som skapats i framtiden tas med i källor för avsnitts identifiering. </br>
    c. **Endast valda webbplatser**: Skriv in namnen på de webbplatser du vill ta med. Du kan också ladda upp en lista med webbplatser. Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen. </br>

    ![Välj hur du vill hitta ämnen](../media/content-understanding/ksetup1.png) </br>
   
5. I avsnittet **undanta ämnen efter namn** kan du välja att inkludera namn på ämnen som du inte vill ska finnas med i resultatet. Använd den här inställningen för att förhindra att känsliga ämnen tas med i kunskaps nätet. Alternativen är:</br>
    a. **Utelämna inte ämnen** </br>
    b. **Utelämna ämnen som innehåller följande villkor**: om du har ämnen som du inte vill visa för användarna som en del av kunskaps nätet.
   -Ladda ner den medföljande mallen.
   -Ange ämnen som du vill undanta. Du måste ange matchnings typen som exakt eller delvis. Exakt matchning innebär att ämnen som uppfyller den exakta termen utesluts. Delvis träff är striktare och innebär att ämnen som innehåller termen utesluts. Om du till exempel anger *doc* som ämnes namn utesluts *dokument sammansättning* när *docknings stationen* inte gör det. Ämnes namn är Skift läges känsliga.  
        -Välj  **+**   för att importera den färdiga CSV-filen. Välj sedan **Ladda upp**. En grön bock markering visas om filen har bearbetats. Välj **Nästa**.</br>


6. På sidan **vem kan se ämnen och var de kan se dem** ser du avsnitts visning. I listan **vilka kan se ämnen i kunskaps nätverkets** inställning väljer du vilka som ska ha åtkomst till ämnen, till exempel markerade ämnen, ämnes kort, ämnes svar i sökningar och avsnitts sidor. Du kan välja:</br>
    a. **Alla i organisationen**</br>
    b. **Endast valda personer eller säkerhets grupper**</br>
    c. **Ingen**</br>

    ![Vilka som kan se ämnen](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskaps hanterings licenser tilldelade till dem kan visa ämnen. 

7. På sidan **behörigheter för hantering av ämnen** kan du välja vem som ska kunna skapa, redigera och hantera ämnen. I avsnittet **vilka som kan skapa och redigera ämnen** kan du välja:</br>
    a. **Alla i organisationen**</br>
    b. **Endast valda personer eller säkerhets grupper**</br>
8. I avsnittet **vilka kan hantera ämnen** kan du välja:</br>
    a. **Alla i organisationen**</br>
    b. **Markerade personer eller säkerhets grupper**</br>

    ![Behörigheter för hantering av ämnen](../media/content-understanding/ksetup3.png) </br>

    Välj **Nästa**.</br>
9. På sidan **skapa ämnes Center** kan du skapa en ämnes Center-webbplats där du kan visa ämnes sidor och ämnen kan hanteras.  Skriv ett namn på ämnes centret i rutan **namn på ämnes Center** . Du kan också skriva en kort beskrivning i rutan **Beskrivning** . </br>

Välj **Nästa**.</br>

   ![Skapa kunskaps Center](../media/content-understanding/ksetup4.png) </br> 

10. På sidan **Granska och slutför** kan du titta på den valda inställningen och välja att göra ändringar. Om du är nöjd med dina val väljer du **Aktivera**.

    ![Slutför och granska](../media/content-understanding/ksetup5.png) </br> 

11. Sidan **kunskaps nätverk aktive rad** visar och bekräftar att systemet kommer att börja analysera dina valda webbplatser för att få hjälp med ämnen och att skapa kunskaps Center webbplatsen. Välj **klar**.</br>

    ![Rad](../media/content-understanding/ksetup6.png) </br> 

12. Du kommer att återföras till sidan **Koppla personer till kunskap** . Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar. 

    ![Inställningar tillämpas](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> När installationen är slutförd kan administratören [ändra dina valda kunskaps hanterings inställningar](manage-knowledge-network.md) när som helst genom att gå tillbaka till den här sidan.


## <a name="see-also"></a>Se även



  






