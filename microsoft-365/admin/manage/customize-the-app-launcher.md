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
description: Skapa snabblänkar till e-post, dokument, appar, SharePoint webbplatser, externa webbplatser och andra resurser genom att lägga till anpassade paneler i startprogrammet.
ms.openlocfilehash: 47f871d66f180225e877a521ef159fc745960507
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623779"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="3d121-103">Lägga till anpassade paneler i startprogrammet</span><span class="sxs-lookup"><span data-stu-id="3d121-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="3d121-104">I Microsoft 365 kan du snabbt och enkelt komma åt e-post, kalendrar, dokument och appar med hjälp av startprogrammet[(läs mer).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="3d121-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="3d121-105">Det här är appar som Microsoft 365 och anpassade appar som du lägger till [från SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) eller Azure [AD.](/previous-versions/office/office-365-api/)</span><span class="sxs-lookup"><span data-stu-id="3d121-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="3d121-p102">Du kan lägga till egna paneler i startprogrammet som pekar på SharePoint-webbplatser, externa webbplatser, äldre program och mycket mer. De anpassade panelerna visas under **Alla** appar i startprogrammet, men du kan fästa dem under **Start**-appar och instruera användarna att göra samma sak. Det här gör det enkelt att hitta de webbplatser, program och resurser som ni behöver i arbetet. I exemplet nedan används en egen panel som heter "Contoso-portalen" för att nå ett företags SharePoint-intranätwebbplats.</span><span class="sxs-lookup"><span data-stu-id="3d121-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Startprogrammet](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="3d121-111">Lägga till en anpassad panel i startprogrammet</span><span class="sxs-lookup"><span data-stu-id="3d121-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="3d121-112">Logga in som global administratör i administrationscentret, gå **Inställningar**  >  **organisationen Inställningar** och välj fliken **Organisationsprofil.**</span><span class="sxs-lookup"><span data-stu-id="3d121-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="3d121-113">På fliken **Organisationsprofil** väljer du Anpassade **startprogrammets paneler**.</span><span class="sxs-lookup"><span data-stu-id="3d121-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="3d121-114">Välj **Lägg till en anpassad panel**.</span><span class="sxs-lookup"><span data-stu-id="3d121-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="3d121-p103">Ange ett **Panelnamn** för den nya panelen. Namnet visas sedan i panelen.</span><span class="sxs-lookup"><span data-stu-id="3d121-p103">Enter a **Tile name** for the new tile. The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="3d121-117">Ange en **URL till webbplatsen** för panelen.</span><span class="sxs-lookup"><span data-stu-id="3d121-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="3d121-118">Det är här du vill att användarna ska gå när de väljer panelen i startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="3d121-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="3d121-119">Använd HTTPS i URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="3d121-119">Use HTTPS in the URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="3d121-120">Om du vill skapa en panel för en SharePoint-webbplats: gå till webbplatsen, kopiera webbadressen och klistra in den här.</span><span class="sxs-lookup"><span data-stu-id="3d121-120">If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="3d121-121">URL-adressen till standardgruppwebbplatsen ser ut så här: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="3d121-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="3d121-122">Ange en **URL för bilden** för panelen.</span><span class="sxs-lookup"><span data-stu-id="3d121-122">Enter a **URL of the image** for the tile.</span></span> <span data-ttu-id="3d121-123">Bilden visas på sidan Mina program och i startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="3d121-123">The image appears on the My apps page and app launcher.</span></span>

    > [!TIP]
    > <span data-ttu-id="3d121-124">Bilden ska vara 60 x 60 bildpunkter och vara tillgänglig för alla i organisationen utan autentisering.</span><span class="sxs-lookup"><span data-stu-id="3d121-124">The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="3d121-125">Ange en **beskrivning** för panelen.</span><span class="sxs-lookup"><span data-stu-id="3d121-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="3d121-126">Detta visas när du väljer panelen på sidan Mina program och väljer **Programinformation**.</span><span class="sxs-lookup"><span data-stu-id="3d121-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="3d121-127">Välj **Spara ändringar för** att skapa den anpassade panelen.</span><span class="sxs-lookup"><span data-stu-id="3d121-127">Select **Save changes** to create the custom tile.</span></span> 
    
    <span data-ttu-id="3d121-128">Den anpassade panelen visas nu i startprogrammet på fliken **Alla** för dig och dina användare.</span><span class="sxs-lookup"><span data-stu-id="3d121-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="3d121-129">Om du inte ser länken till den anpassade panelen du skapade i föregående steg bör du kontrollera att du har tilldelats en Exchange Online-postlåda och att du loggat in till postlådan minst en gång.</span><span class="sxs-lookup"><span data-stu-id="3d121-129">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="3d121-130">Dessa steg krävs för anpassade paneler i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d121-130">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="3d121-131">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="3d121-131">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="3d121-132">I administrationscentret går du till fliken **Inställningar**  >  **Organisationsprofil Inställningar**  >  **Organisationsprofil.**</span><span class="sxs-lookup"><span data-stu-id="3d121-132">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="3d121-133">På sidan **Organisationsprofil** bredvid Lägg till   **anpassade paneler för din organisation väljer** du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="3d121-133">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="3d121-134">Uppdatera **panelnamnet**, **URL:en**, **beskrivningen** och **bild-URL:en** för den anpassade brickan (se den [Lägga till en anpassad panel i startprogrammet](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="3d121-134">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="3d121-135">Välj **Uppdatera** \> **stäng.**</span><span class="sxs-lookup"><span data-stu-id="3d121-135">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="3d121-136">Om du vill ta bort en anpassad panel väljer **du panelen i** fönstret Anpassade paneler och väljer Ta bort panel **Ta**  >  **bort.**</span><span class="sxs-lookup"><span data-stu-id="3d121-136">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="3d121-137">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3d121-137">Next steps</span></span>

<span data-ttu-id="3d121-138">Förutom att lägga till paneler i startprogrammet kan du lägga till startprogrammets paneler i navigeringsfältet[(läs mer).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="3d121-138">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="3d121-139">Om du vill anpassa utseendet och känslan Microsoft 365 som matchar organisationens varumärke kan du gå till [Anpassa Microsoft 365 temat](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="3d121-139">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="3d121-140">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="3d121-140">Related content</span></span>

<span data-ttu-id="3d121-141">[Fästa appar i användarnas startprogram](pin-apps-to-app-launcher.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="3d121-141">[Pin apps to your users' app launcher](pin-apps-to-app-launcher.md) (article)</span></span>\
<span data-ttu-id="3d121-142">[Uppgradera dina Microsoft 365 för företag-användare till den senaste Office klienten](../setup/upgrade-users-to-latest-office-client.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="3d121-142">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>\
<span data-ttu-id="3d121-143">[Hantera tillägg i administrationscentret](../manage/manage-addins-in-the-admin-center.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="3d121-143">[Manage add-ins in the admin center](../manage/manage-addins-in-the-admin-center.md) (article)</span></span>
