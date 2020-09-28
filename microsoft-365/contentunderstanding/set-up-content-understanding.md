---
title: Konfigurera SharePoint-Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Konfigurera innehålls förståelse i Project cortex
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294890"
---
# <a name="set-up-sharepoint-syntex"></a>Konfigurera SharePoint-Syntex

Administratörer kan använda administrations centret för Microsoft 365 för att konfigurera och Microsoft SharePoint-Syntex. 

Tänk på följande innan du börjar:

- Vilka SharePoint-webbplatser aktiverar du formulär bearbetning? Alla, vissa eller utvalda webbplatser?
- Vad heter du för innehålls Center och vem är den primära webbplats administratören?

Du kan ändra inställningarna efter den första installationen i Microsoft 365 Admin Center.

Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Innan du konfigurerar dig bör du planera för det bästa sättet att konfigurera och konfigurera innehålls förståelse i din miljö. Du måste till exempel tänka på följande:

- SharePoint-webbplatserna som du vill aktivera bearbetning av formulär för – alla, vissa eller markerade webbplatser
- Ditt innehålls Center och namnet på den primära webbplats administratören

## <a name="requirements"></a>Krav 

> [!NOTE]
> Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och ställa in innehålls förståelse.

Som administratör kan du också göra ändringar i dina valda inställningar när som helst efter installationen och i alla inställningar för innehålls förståelse i administrations centret för Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Så här konfigurerar du SharePoint-Syntex

1. I administrations centret för Microsoft 365 väljer du **Konfigurera**och sedan avsnittet **organisations** information.

2. I avsnittet **organisationsinformation** väljer du **Automatisera innehålls förståelse**.<br/>

    ![Sidan för information om organisationens kunskap](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. Gå igenom konfigurationen genom att klicka på **komma igång** på sidan **Automatisera SharePoint-Syntex** .<br/>

    ![Starta installationen](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. På sidan Aktivera bild taggning väljer du om du vill tillåta [bild märkning](image-tagging.md).

    ![Skärm bild av alternativ för bild markeringar](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. På sidan **Konfigurera formulär bearbetning** kan du välja om du vill låta användare kunna använda AI-verktyget för att skapa formulär bearbetnings modeller i specifika SharePoint-dokumentbibliotek. Ett meny alternativ är tillgängligt i menyfliksområdet dokument bibliotek för att **skapa en formulär bearbetnings modell** i SharePoint-dokumentbibliotek där den är aktive rad.
 
     För **vilka SharePoint-bibliotek bör visa alternativ för att skapa en modell för formulär bearbetning**kan du välja:</br>
      - **Alla SharePoint-bibliotek** som gör det tillgängligt för alla SharePoint-bibliotek i organisationen.</br>
      - **Endast bibliotek på valda webbplatser**och välj de webbplatser som du vill göra tillgänglig för.</br>

   ![Konfigurera formulär bearbetning](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Om du aktiverar den här inställningen i ett SharePoint-dokumentbibliotek påverkar det inte befintliga modeller som tillämpas på biblioteket eller möjligheten att tillämpa dokument förståelse på ett bibliotek. 
    
6. På sidan **skapa innehålls Center** kan du skapa en SharePoint-webbplats för innehålls Center där användarna kan skapa och hantera dokument förståelse modeller. </br>
    a. För **webbplats namn**anger du det namn som du vill ge innehålls Center webbplatsen.</br>
    b. **Webbplats adressen** visar URL-adressen för webbplatsen, baserat på vad du har valt för webbplats namnet. Om du vill ändra det klickar du på **Redigera**.</br>

      ![Skapa innehålls Center](../media/content-understanding/admin-cu-create-cc.png)</br>

    Välj **Nästa**.

7. På sidan **Granska och slutför** kan du titta på den valda inställningen och välja att göra ändringar. Om du är nöjd med dina val väljer du **Aktivera**.

8. På bekräftelse sidan klickar du på **klar**.

9. Du kommer att återföras till sidan **Automatisera innehålls förståelse** . Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar. 

## <a name="assign-licenses"></a>Tilldela licenser

När du har konfigurerat en SharePoint-Syntex måste du tilldela licenser för de användare som ska använda formulär bearbetning och dokument förstå funktioner.

Så här tilldelar du licenser:

1. Klicka på **aktiva användare**under **användare**i administrations centret för Microsoft 365.

2. Välj de användare som du vill licensiera och klicka på **Hantera produkt licenser**.

3. Välj **tilldela mer**.

4. Välj **intelligent Content Services**. Under **program**kontrollerar du att **gemensam data tjänst för intelligenta innehålls tjänster** och **intelligenta innehålls tjänster** är markerade.

    ![SharePoint Syntex-licenser i administrations centret för Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Klicka på **Spara ändringar**.

## <a name="ai-builder-credits"></a>Krediteringar för AI-byggare

Om du har 300 eller fler SharePoint Syntex-licenser för SharePoint Syntex i organisationen tilldelas du 1 000 000 AI Builder-kredit. Om du har färre än 300 licenser måste du köpa AI Builder-kredit för att kunna använda formulär bearbetning.

Du kan uppskatta vilken AI Builder-kapacitet som passar dig med [AI Builder-kalkylatorn](https://powerapps.microsoft.com/ai-builder-calculator).

1. Gå till [administrations centret för Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) för att kontrol lera kredit och användning.

    > [!NOTE]
    > Aktivera den här inställningen i ett SharePoint-dokumentbibliotek påverkar inte befintliga modeller som tillämpas på biblioteket eller möjligheten att tillämpa dokument förståelse på ett bibliotek. 
    
2. På sidan **skapa innehålls Center** kan du skapa en SharePoint-webbplats för innehålls Center där användare kan skapa och hantera dokument förståelse modeller. </br>
    a. För **webbplats namn**anger du det namn du vill använda för innehålls Center webbplatsen.</br>
    b. Webb **adressen** för din webbplats visas, baserat på webbplats namnet.</br>

    > [!NOTE] 
    > Du kan välja ett språk som stöds, innehålls förstå modeller kan bara skapas för engelska.</br>

      ![Skapa innehålls Center](../media/content-understanding/admin-cu-create-cc.png)</br>

3. Välj **Nästa**.

4. På sidan **Slutför och granska** tittar du på den valda inställningen och väljer att göra ändringar. Om du är nöjd med dina val väljer du **Aktivera**.

5. Sidan **innehålls användning aktive rad** visas och bekräftar att systemet har lagt till dina inställningar för formulär bearbetning och skapat innehålls Center webbplatsen. Välj **klar**.

6. Du kommer att återföras till sidan **Automatisera innehålls förståelse** . Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar. 

## <a name="see-also"></a>Se även

[Översikt över formulär bearbetnings modellen](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Steg-för-steg: hur du skapar en modell för dokument förståelse (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

