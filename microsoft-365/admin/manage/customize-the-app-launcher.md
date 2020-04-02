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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Skapa snabblänkar till din e-post, dokument, appar, SharePoint-webbplatser, externa webbplatser och andra resurser genom att lägga till anpassade paneler i startprogrammet. '
ms.openlocfilehash: e52bad5cdd1809e8aa0d97c681b69daa5143d3fd
ms.sourcegitcommit: 4b73f070747a66874c03fdf670ffdf16f736585a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43103081"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="6a3b1-103">Lägga till anpassade paneler i startprogrammet</span><span class="sxs-lookup"><span data-stu-id="6a3b1-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="6a3b1-p101">I Office 365 kan du snabbt och enkelt öppna e-post, kalendrar, dokument och program med hjälp av Office 365-startprogrammet ([läs mer](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Dessa är program som du får i Office 365 samt de anpassade program som du lägger till via [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) eller [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="6a3b1-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="6a3b1-p102">Du kan lägga till egna paneler i startprogrammet som pekar på SharePoint-webbplatser, externa webbplatser, äldre program och mycket mer. De anpassade panelerna visas under **Alla** appar i startprogrammet, men du kan fästa dem under **Start**-appar och instruera användarna att göra samma sak. Det här gör det enkelt att hitta de webbplatser, program och resurser som ni behöver i arbetet. I exemplet nedan används en egen panel som heter "Contoso-portalen" för att nå ett företags SharePoint-intranätwebbplats.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Startprogrammet för Office 365](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="6a3b1-111">Lägga till en anpassad panel i startprogrammet</span><span class="sxs-lookup"><span data-stu-id="6a3b1-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="6a3b1-112">Gå till fliken Inställningar och välj **organisationsprofil** **i** **administrationscentret.** > </span><span class="sxs-lookup"><span data-stu-id="6a3b1-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="6a3b1-113">På fliken **Organisationsprofil** väljer du **Anpassade startpaneler**för startprogram .</span><span class="sxs-lookup"><span data-stu-id="6a3b1-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="6a3b1-114">Välj **Lägg till en anpassad panel**.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="6a3b1-115">Ange ett **Panelnamn** för den nya panelen.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="6a3b1-116">Namnet visas sedan i panelen.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="6a3b1-117">Ange en **webbadress till panelen.**</span><span class="sxs-lookup"><span data-stu-id="6a3b1-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="6a3b1-118">Det här är den plats där du vill att användarna ska gå när de väljer panelen i startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="6a3b1-119">Använd HTTPS i URL:en.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="6a3b1-120">Om du skapar en panel för en SharePoint-webbplats navigerar du till den webbplatsen, kopierar webbadressen och klistrar in den här.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="6a3b1-121">Webbadressen till standardgruppwebbplatsen ser ut så här:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="6a3b1-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="6a3b1-122">Ange en **URL till bilden** för panelen.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="6a3b1-123">Bilden visas på sidan Mina program och i startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="6a3b1-124">TIPS: Bilden ska vara 60x60 pixlar och vara tillgänglig för alla i organisationen utan att behöva autentisering.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="6a3b1-125">Ange en **beskrivning** för panelen.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="6a3b1-126">Du ser detta när du väljer panelen på sidan Mina appar och väljer **Appinformation**.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="6a3b1-127">Välj **Spara ändringar** om du vill skapa den anpassade panelen.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="6a3b1-128">Den anpassade panelen visas nu i startprogrammet på fliken **Alla** för dig och dina användare.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="6a3b1-129">Befordra panelen till Startprogrammet</span><span class="sxs-lookup"><span data-stu-id="6a3b1-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="6a3b1-130">Välj ikonen för startprogrammet och välj **Alla appar**.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="6a3b1-131">Leta reda på den nya panelen för din app, välj ellipsen och välj **Fäst för startprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="6a3b1-p108">Om du inte ser länken till den anpassade panelen du skapade i föregående steg bör du kontrollera att du har tilldelats en Exchange Online-postlåda och att du loggat in till postlådan minst en gång. De här stegen krävs för anpassade paneler i Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6a3b1-134">Både du och användarna måste utföra de här åtgärderna när ni vill att anpassade paneler från Mina program-sidan ska fästas i startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="6a3b1-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="6a3b1-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="6a3b1-136">Gå till**Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">fliken Organisationsprofilinställningar</a> i **administrationscentret.** > </span><span class="sxs-lookup"><span data-stu-id="6a3b1-136">In the admin center, go to the **Settings** > **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> tab.</span></span>
    
2. <span data-ttu-id="6a3b1-137">Välj **Redigera**bredvid **Lägg till anpassade paneler för din organisation**på sidan **Organisationsprofil.**</span><span class="sxs-lookup"><span data-stu-id="6a3b1-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="6a3b1-138">Uppdatera **panelnamnet**, **URL:en**, **beskrivningen** och **bild-URL:en** för den anpassade brickan (se den [Lägga till en anpassad panel i startprogrammet](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="6a3b1-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="6a3b1-139">Välj **Uppdatera** \> **stäng**.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="6a3b1-140">Om du vill ta bort en anpassad panel markerar du panelen i fönstret **Anpassade paneler** och väljer **Ta bort panel** > **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="6a3b1-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="6a3b1-141">Hur går jag vidare?</span><span class="sxs-lookup"><span data-stu-id="6a3b1-141">What's next?</span></span>

<span data-ttu-id="6a3b1-p109">Förutom att lägga till paneler i startprogrammet kan du lägga till startprogramspanelerna i Office 365-navigeringsfältet ([läs mer](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Information om hur du anpassar utformningen av Office 365 så att den matchar organisationens varumärke finns i [Anpassa Office 365-temat](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="6a3b1-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

