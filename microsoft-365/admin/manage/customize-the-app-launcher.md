---
title: Lägga till anpassade paneler i startprogrammet
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Skapa snabblänkar till e-post, dokument, program, SharePoint-webbplatser, externa webbplatser och andra resurser genom att lägga till anpassade paneler i startprogrammet. '
ms.openlocfilehash: cc4edbfadc5c9555e04d04de8f7368dd86aa9974
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915440"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Lägga till anpassade paneler i startprogrammet

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

I Microsoft 365 kan du snabbt och enkelt komma åt e-post, kalendrar, dokument och appar med hjälp av startprogrammet[(läs mer).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) Det här är appar som du får med Microsoft 365 samt anpassade appar som du lägger till från [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) eller [Azure AD.](/previous-versions/office/office-365-api/)
  
Du kan lägga till egna paneler i startprogrammet som pekar på SharePoint-webbplatser, externa webbplatser, äldre program och mycket mer. De anpassade panelerna visas under **Alla** appar i startprogrammet, men du kan fästa dem under **Start**-appar och instruera användarna att göra samma sak. Det här gör det enkelt att hitta de webbplatser, program och resurser som ni behöver i arbetet. I exemplet nedan används en egen panel som heter "Contoso-portalen" för att nå ett företags SharePoint-intranätwebbplats. 
  
![Startprogrammet](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Lägga till en anpassad panel i startprogrammet

1. Logga in som global administratör i administrationscentret, gå till **Inställningar**  >  **Organisationsinställningar** och välj **fliken Organisationsprofil.**
    
2. På fliken **Organisationsprofil** väljer du Anpassade **startprogrammets paneler**.
  
3. Välj **Lägg till en anpassad panel**. 
  
4. Ange ett **Panelnamn** för den nya panelen. Namnet visas sedan i panelen. 
    
5. Ange en **URL till webbplatsen** för panelen. Det är här du vill att användarna ska gå när de väljer panelen i startprogrammet. Använd HTTPS i URL-adressen.<br/>TIPS: Om du skapar en panel för en SharePoint-webbplats går du till webbplatsen, kopierar webbadressen och klistrar in den här. URL-adressen till standardgruppwebbplatsen ser ut så här: `https://<company_name>.sharepoint.com` 
  
6. Ange en **URL för bilden** för panelen. Bilden visas på sidan Mina program och i startprogrammet.<br/>TIPS: Bilden ska vara 60 x 60 bildpunkter och vara tillgänglig för alla i organisationen utan autentisering.

7. Ange en **beskrivning** för panelen. Detta visas när du väljer panelen på sidan Mina program och väljer **Programinformation**. 
  
8. Välj **Spara ändringar för** att skapa den anpassade panelen. 
    
Den anpassade panelen visas nu i startprogrammet på fliken **Alla** för dig och dina användare. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. I administrationscentret går du till fliken  >  **Organisationsprofil i Inställningar**  >  **för** </a> organisationsinställningar.
    
2. På sidan **Organisationsprofil** bredvid Lägg till   **anpassade paneler för din organisation väljer** du **Redigera**.

3. Uppdatera **panelnamnet**, **URL:en**, **beskrivningen** och **bild-URL:en** för den anpassade brickan (se den [Lägga till en anpassad panel i startprogrammet](#add-a-custom-tile-to-the-app-launcher)).
    
4. Välj **Uppdatera** \> **stäng.** 
    
Om du vill ta bort en anpassad panel väljer **du panelen i** fönstret Anpassade paneler och väljer Ta bort panel **Ta**  >  **bort.** 
  
## <a name="whats-next"></a>Hur går jag vidare?

Förutom att lägga till paneler i startprogrammet kan du lägga till startprogrammets paneler i navigeringsfältet[(läs mer).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) Om du vill anpassa utseendet och känslan i Microsoft 365 så att den matchar organisationens varumärke kan du gå till Anpassa [Microsoft 365-temat](../setup/customize-your-organization-theme.md).
