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
description: 'Skapa snabblänkar till e-post, dokument, appar, SharePoint-webbplatser, externa webbplatser och andra resurser genom att lägga till anpassade paneler i startprogrammet. '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926240"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="1f093-103">Lägga till anpassade paneler i startprogrammet</span><span class="sxs-lookup"><span data-stu-id="1f093-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1f093-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="1f093-104">The admin center is changing.</span></span> <span data-ttu-id="1f093-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="1f093-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1f093-106">I Microsoft 365 kan du snabbt och enkelt komma åt e-post, kalendrar, dokument och appar med hjälp av startprogrammet[(läs mer).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="1f093-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="1f093-107">Det här är appar som du får med Microsoft 365 samt anpassade appar som du lägger till från [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) eller [Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="1f093-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="1f093-p103">Du kan lägga till egna paneler i startprogrammet som pekar på SharePoint-webbplatser, externa webbplatser, äldre program och mycket mer. De anpassade panelerna visas under **Alla** appar i startprogrammet, men du kan fästa dem under **Start**-appar och instruera användarna att göra samma sak. Det här gör det enkelt att hitta de webbplatser, program och resurser som ni behöver i arbetet. I exemplet nedan används en egen panel som heter "Contoso-portalen" för att nå ett företags SharePoint-intranätwebbplats.</span><span class="sxs-lookup"><span data-stu-id="1f093-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Startprogrammet](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="1f093-113">Lägga till en anpassad panel i startprogrammet</span><span class="sxs-lookup"><span data-stu-id="1f093-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="1f093-114">Logga in på administrationscentret som global administratör, gå till  >  **Inställningar för organisationens** inställningar och välj fliken **Organisationsprofil.**</span><span class="sxs-lookup"><span data-stu-id="1f093-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="1f093-115">Välj Anpassade **startprogrammets** paneler på fliken **Organisationsprofil.**</span><span class="sxs-lookup"><span data-stu-id="1f093-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="1f093-116">Välj **Lägg till en anpassad panel.**</span><span class="sxs-lookup"><span data-stu-id="1f093-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="1f093-117">Ange ett **Panelnamn** för den nya panelen.</span><span class="sxs-lookup"><span data-stu-id="1f093-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="1f093-118">Namnet visas sedan i panelen.</span><span class="sxs-lookup"><span data-stu-id="1f093-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="1f093-119">Ange en **URL till webbplatsen** för panelen.</span><span class="sxs-lookup"><span data-stu-id="1f093-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="1f093-120">Det är här du vill att användarna ska gå när de väljer panelen i startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="1f093-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="1f093-121">Använd HTTPS i URL:en.</span><span class="sxs-lookup"><span data-stu-id="1f093-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="1f093-122">Tips: Om du skapar en panel för en SharePoint-webbplats går du till webbplatsen, kopierar webbadressen och klistrar in den här.</span><span class="sxs-lookup"><span data-stu-id="1f093-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="1f093-123">URL-adressen till standardgruppwebbplatsen ser ut så här: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="1f093-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="1f093-124">Ange en **URL för bilden** för panelen.</span><span class="sxs-lookup"><span data-stu-id="1f093-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="1f093-125">Bilden visas på sidan Mina program och i startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="1f093-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="1f093-126">TIPS: Bilden ska vara 60 x 60 bildpunkter och vara tillgänglig för alla i organisationen utan autentisering.</span><span class="sxs-lookup"><span data-stu-id="1f093-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="1f093-127">Ange en **beskrivning** för panelen.</span><span class="sxs-lookup"><span data-stu-id="1f093-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="1f093-128">Detta visas när du markerar panelen på sidan Mina program och väljer **Programinformation.**</span><span class="sxs-lookup"><span data-stu-id="1f093-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="1f093-129">Välj **Spara ändringar** för att skapa den anpassade panelen.</span><span class="sxs-lookup"><span data-stu-id="1f093-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="1f093-130">Den anpassade panelen visas nu i startprogrammet på fliken **Alla** för dig och dina användare.</span><span class="sxs-lookup"><span data-stu-id="1f093-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="1f093-131">Höja panelen till startprogrammet</span><span class="sxs-lookup"><span data-stu-id="1f093-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="1f093-132">Välj ikonen för startprogrammet och välj **Alla appar.**</span><span class="sxs-lookup"><span data-stu-id="1f093-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="1f093-133">Leta reda på den nya panelen för appen, välj ellipsen och välj **Fäst i startprogrammet.**</span><span class="sxs-lookup"><span data-stu-id="1f093-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="1f093-134">Om du inte ser länken till den anpassade panelen du skapade i föregående steg bör du kontrollera att du har tilldelats en Exchange Online-postlåda och att du loggat in till postlådan minst en gång.</span><span class="sxs-lookup"><span data-stu-id="1f093-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="1f093-135">De här stegen krävs för anpassade paneler i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f093-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1f093-136">Både du och användarna måste utföra de här åtgärderna när ni vill att anpassade paneler från Mina program-sidan ska fästas i startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="1f093-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="1f093-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="1f093-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="1f093-138">Gå till organisationsprofilfliken **Inställningar** för inställningar  >    >  **i** </a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1f093-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="1f093-139">Välj **Redigera bredvid** Lägg till anpassade paneler för **din organisation** på sidan **Organisationsprofil.**</span><span class="sxs-lookup"><span data-stu-id="1f093-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="1f093-140">Uppdatera **panelnamnet**, **URL:en**, **beskrivningen** och **bild-URL:en** för den anpassade brickan (se den [Lägga till en anpassad panel i startprogrammet](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="1f093-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="1f093-141">Välj **Uppdatera** \> **stäng.**</span><span class="sxs-lookup"><span data-stu-id="1f093-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="1f093-142">Om du vill ta bort en anpassad panel markerar **du panelen i** fönstret Anpassade paneler och väljer Ta bort **panel** Ta  >  **bort.**</span><span class="sxs-lookup"><span data-stu-id="1f093-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="1f093-143">Hur går jag vidare?</span><span class="sxs-lookup"><span data-stu-id="1f093-143">What's next?</span></span>

<span data-ttu-id="1f093-144">Förutom att lägga till paneler i startprogrammet kan du lägga till startprogrammets paneler i navigeringsfältet[(läs mer).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="1f093-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="1f093-145">Om du vill anpassa utseendet och känslan i Microsoft 365 så att den matchar organisationens varumärke kan du gå till Anpassa [Microsoft 365-temat.](../setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="1f093-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
