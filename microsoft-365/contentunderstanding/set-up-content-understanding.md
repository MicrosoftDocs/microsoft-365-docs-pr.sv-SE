---
title: 'Konfigurera innehållsförståelse (förhandsgranskning) '
description: Så här ställer du in Project Cortex.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fca80e45dfa45ee5da9521854c6eebfbd87d8859
ms.sourcegitcommit: 91c82a79962387205c4dd4dd8d61322b79fed55f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46539914"
---
# <a name="set-up-content-understanding-preview"></a>Konfigurera innehållsförståelse (förhandsgranskning)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

Administratörer kan använda Microsoft 365-administrationscentret för att konfigurera innehållsbeståelse. 

Innan du konfigurerar, se till att planera för det bästa sättet att ställa in och konfigurera innehållsförståelse i din miljö. Du måste till exempel ta hänsyn till följande:
- Vilka SharePoint-webbplatser aktiverar du formulärbearbetning? Alla av dem, vissa, eller välj webbplatser?
- Namnet på ditt innehållscenter och vem är den primära webbplatsadministratören?

En administratör kan också göra ändringar i dina valda inställningar när som helst efter installationen genom hanteringsinställningarna för innehålls förståelse i microsoft 365-administrationscentret.


## <a name="requirements"></a>Krav 
Du måste ha behörigheten Global Admin eller SharePoint för att kunna komma åt Microsoft 365-administrationscentret och konfigurera innehållsförståelse.


## <a name="to-set-up-content-understanding"></a>Så här ställer du in innehållsöverensning

1. I administrationscentret för Microsoft 365 väljer du **Installationsprogrammet**och visar sedan avsnittet **Organisationskunskap.**
2. I avsnittet **Organisatorisk kunskap** väljer du **Automatisera innehållsöverensning**.<br/>

    ![Inställningssida för organisationskunskap](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. På sidan **Automatisera innehållsöverenskommelsen** klickar du på **Kom igång** för att gå igenom installationsprocessen.<br/>

    ![Börja installationen](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. På sidan **Konfigurera formulärbearbetning** kan du välja om du vill att användarna ska kunna använda AI Builder för att skapa formulärbearbetningsmodeller i specifika SharePoint-dokumentbibliotek. Ett menyalternativ är tillgängligt i menyfliksområdet för dokumentbiblioteket för att **skapa en formulärbearbetningsmodell** i SharePoint-dokumentbibliotek där den är aktiverad.
 
     För **vilka SharePoint-bibliotek ska visa alternativet för att skapa en formulärbearbetningsmodell**kan du välja:</br>
    - **Alla SharePoint-bibliotek** för att göra det tillgängligt för alla SharePoint-bibliotek i din klientorganisation.</br>
    - **Endast bibliotek på valda platser**och välj sedan de platser där du vill göra det tillgängligt.</br>
    - **Inga SharePoint-bibliotek** om du för närvarande inte vill göra det tillgängligt för några webbplatser (du kan ändra detta efter installationen).
</br>

   ![Konfigurera formulärbearbetning](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > Om du aktiverar den här inställningen i ett SharePoint-dokumentbibliotek påverkas inte befintliga modeller som tillämpas på biblioteket eller möjligheten att tillämpa dokumentöverenstagande modeller i ett bibliotek. 

    
5. På sidan **Skapa innehållscenter** kan du skapa en SharePoint-webbplats för innehållscenter där användarna kan skapa och hantera dokumentöverenstagande modeller. </br>
    a. För **Webbplatsnamn**skriver du det namn som du vill ge webbplatsen för innehållscentret.</br>
    b. **Webbplatsadressen** visar webbadressen för din webbplats, baserat på vad du valde för webbplatsnamnet.</br>

    > [!Note] 
    > Du kan välja ett språk som stöds, observera att innehållsöverenseringsmodeller endast kan skapas för engelska.</br>

      ![Skapa innehållscenter](../media/content-understanding/admin-cu-create-cc.png)</br>


    Välj **Nästa**.
6. På sidan **Slutför och granska** kan du titta på den valda inställningen och välja att göra ändringar. Om du är nöjd med dina val väljer du **Aktivera**.



7. Sidan **Innehållsförståelse aktiverad** visas, vilket bekräftar att systemet har lagt till dina inställningar för formulärbearbetning och skapat Content Center-webbplatsen. Välj **Klar**.

8. Du kommer tillbaka till sidan För att **förstå automatisera innehåll.** På den här sidan kan du välja **Hantera** om du vill göra ändringar i konfigurationsinställningarna. 

## <a name="see-also"></a>Se även



  






