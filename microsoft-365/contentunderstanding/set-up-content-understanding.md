---
title: 'Konfigurera innehålls förståelse (för hands version) '
description: Så här konfigurerar du Project cortex.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 05696f99e59cbd51ba004f6007311b4b6af4a839
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950042"
---
# <a name="set-up-content-understanding-preview"></a>Konfigurera innehålls förståelse (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Administratörer kan använda Microsoft 365 Admin Center för att konfigurera och konfigurera innehålls förståelse. 

Innan du konfigurerar dig bör du planera för det bästa sättet att konfigurera och konfigurera innehålls förståelse i din miljö. Till exempel måste du tänka på följande:
- Vilka SharePoint-webbplatser aktiverar du formulär bearbetning? Alla, vissa eller utvalda webbplatser?
- Namn på innehålls Center och vem är den primära webbplats administratören?

En administratör kan också göra ändringar i dina valda inställningar när som helst efter installationen via konfigurations inställningarna för innehålls förståelse i administrations centret för Microsoft 365.


## <a name="requirements"></a>Krav 
Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och ställa in innehålls förståelse.


## <a name="to-set-up-content-understanding"></a>Konfigurera innehålls förståelse

1. I administrations centret för Microsoft 365 väljer du **Konfigurera**och sedan avsnittet **organisations** information.
2. I avsnittet **organisationsinformation** väljer du **Automatisera innehålls förståelse**.<br/>

    ![Sidan för information om organisationens kunskap](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. På sidan **Automatisera innehålls förståelse** klickar du på **komma igång** för att vägleda dig genom installations processen.<br/>

    ![Starta installationen](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. På sidan **Konfigurera formulär bearbetning** kan du välja om du vill låta användare kunna använda AI-verktyget för att skapa formulär bearbetnings modeller i specifika SharePoint-dokumentbibliotek. Ett meny alternativ är tillgängligt i menyfliksområdet dokument bibliotek för att **skapa en formulär bearbetnings modell** i SharePoint-dokumentbibliotek där den är aktive rad.
 
     För **vilka SharePoint-bibliotek bör visa alternativ för att skapa en modell för formulär bearbetning**kan du välja:</br>
    - **Alla SharePoint-bibliotek** som gör det tillgängligt för alla SharePoint-bibliotek i klient organisationen.</br>
    - **Endast bibliotek på valda webbplatser**och välj de webbplatser som du vill göra tillgänglig för.</br>
    - **Inga SharePoint-bibliotek** om du inte vill göra det tillgängligt för några webbplatser (du kan ändra det efter installationen).
</br>

   ![Konfigurera formulär bearbetning](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > Om du aktiverar den här inställningen i ett SharePoint-dokumentbibliotek påverkar det inte befintliga modeller som tillämpas på biblioteket eller möjligheten att tillämpa dokument förståelse på ett bibliotek. 

    
5. På sidan **skapa innehålls Center** kan du skapa en SharePoint-webbplats för innehålls Center där användarna kan skapa och hantera dokument förståelse modeller. </br>
    a. För **webbplats namn**anger du det namn som du vill ge innehålls Center webbplatsen.</br>
    b. **Webbplats adressen** visar URL-adressen för webbplatsen, baserat på vad du har valt för webbplats namnet.</br>

    > [!Note] 
    > Du kan välja ett språk som stöds, men du kan bara skapa innehålls förstå modeller för engelska.</br>

      ![Skapa innehålls Center](../media/content-understanding/admin-cu-create-cc.png)</br>


    Välj **Nästa**.
6. På sidan **Slutför och granska** kan du titta på den valda inställningen och välja att göra ändringar. Om du är nöjd med dina val väljer du **Aktivera**.



7. Sidan **innehålls förståelse** visas och bekräftar att systemet har lagt till dina inställningar för formulär bearbetning och skapar innehålls Center webbplatsen. Välj **klar**.

8. Du kommer att återföras till sidan **Automatisera innehålls förståelse** . Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar. 

## <a name="see-also"></a>Se även



  






