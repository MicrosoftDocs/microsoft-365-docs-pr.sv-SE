---
title: Konfigurera SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Konfigurera innehållstolkning i Project Cortex
ms.openlocfilehash: 6078b41f8911301d343925c5bf895e881abddffe
ms.sourcegitcommit: 88c2461b14cd16f74979f4bcd0a9ad18e4422cb3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469727"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="2691c-103">Konfigurera SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="2691c-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="2691c-104">Administratörer kan använda Administrationscenter för Microsoft 365 för att konfigurera [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="2691c-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="2691c-105">Tänk på följande innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="2691c-105">Consider the following before you start:</span></span>

- <span data-ttu-id="2691c-106">På vilka SharePoint-webbplatser kommer du aktivera formulärbearbetning?</span><span class="sxs-lookup"><span data-stu-id="2691c-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="2691c-107">Alla, vissa eller utvalda webbplatser?</span><span class="sxs-lookup"><span data-stu-id="2691c-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="2691c-108">Vad heter ditt standard innehållscenter?</span><span class="sxs-lookup"><span data-stu-id="2691c-108">What will you name of your default content center?</span></span>

<span data-ttu-id="2691c-109">Du kan ändra inställningarna efter den första konfigurationen i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2691c-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="2691c-110">Innan konfigurationen ser du till att planera för det bästa sättet att ställa in och konfigurera innehållstolkning i din miljö.</span><span class="sxs-lookup"><span data-stu-id="2691c-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="2691c-111">Till exempel behöver du överväga om följande namn av:</span><span class="sxs-lookup"><span data-stu-id="2691c-111">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="2691c-112">De SharePoint-webbplatser som du vill aktivera formulärbearbetning för – alla, vissa eller utvalda webbplatser</span><span class="sxs-lookup"><span data-stu-id="2691c-112">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="2691c-113">Ditt innehållscenter och namnet på den primära webbplatsadministratören</span><span class="sxs-lookup"><span data-stu-id="2691c-113">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="2691c-114">Krav</span><span class="sxs-lookup"><span data-stu-id="2691c-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="2691c-115">Du måste ha behörighet som global administratör eller SharePoint-administratör för att kunna komma åt Administrationscenter för Microsoft 365 och konfigurera innehållstolkning.</span><span class="sxs-lookup"><span data-stu-id="2691c-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="2691c-116">Som administratör kan du också göra ändringar i dina valda inställningar när som helst efter konfigurationen och under inställningarna för hantering av innehållstolkning i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2691c-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="2691c-117">Att konfigurera SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="2691c-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="2691c-118">I Administrationscenter för Microsoft 365 välj **Konfiguration** och se sedan **Filer och innehåll** sektionen.</span><span class="sxs-lookup"><span data-stu-id="2691c-118">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="2691c-119">I **Filer och innehåll** sektionen välj **Automatisera innehållstolkning**.</span><span class="sxs-lookup"><span data-stu-id="2691c-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="2691c-120">På sidan **Automatisera innehållstolkning** klickar du på **Komma igång** för att gå igenom konfigurationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2691c-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2691c-121">![Starta konfiguration](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="2691c-121">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="2691c-122">På sidan **Konfigurera formulärbearbetning** kan du välja om du vill tillåta att användare kan skapa modeller för formulärbearbetning i vissa dokumentbibliotek i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2691c-122">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="2691c-123">Ett menyalternativ kommer att vara tillgängligt i menyfliksområdet för dokumentbiblioteket för att **Skapa en modell för formulärbearbetning** i dokumentbibliotek i SharePoint där den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="2691c-123">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="2691c-124">För **vilka SharePoint-bibliotek som ska visa alternativ för att skapa modell för formulärbearbetning** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="2691c-124">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="2691c-125">**Alla SharePoint-bibliotek** för att göra det tillgängligt för alla SharePoint-bibliotek i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2691c-125">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="2691c-126">**Bara bibliotek på utvalda webbplatser** och välj sedan de webbplatser där du vill göra det tillgängligt eller ladda upp en lista med upp till 50 webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2691c-126">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="2691c-127">**Inga SharePoint-bibliotek** om du inte vill att det ska vara tillgängligt för några webbplatser (du kan ändra det när konfigurationen är slutförd).</span><span class="sxs-lookup"><span data-stu-id="2691c-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2691c-128">![Konfigurera formulärbearbetning](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="2691c-128">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="2691c-129">Att ta bort en webbplats efter att den har inkluderats påverkar inte befintliga modeller som används i biblioteken på webbplatsen eller möjligheten att använda modeller för dokumenttolkning på ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="2691c-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="2691c-130">På sidan **Skapa innehållscenter** kan du skapa en SharePoint-webbplats för innehållscenter där dina användare kan skapa och hantera modeller för dokumenttolkning.</span><span class="sxs-lookup"><span data-stu-id="2691c-130">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="2691c-131">För **Webbplatsnamn**skriver du namnet som du vill använda på webbplatsen för innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="2691c-131">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="2691c-132">**Webbplatsens adress** kommer att visa URL:en för din webbplats baserat på vad du valde som webbplatsnamn.</span><span class="sxs-lookup"><span data-stu-id="2691c-132">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="2691c-133">Om du vill ändra det klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="2691c-133">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="2691c-134">![Skapa innehållscenter](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="2691c-134">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="2691c-135">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2691c-135">Select **Next**.</span></span>

6. <span data-ttu-id="2691c-136">På sidan **Granska och slutför** kan du titta på vald inställning och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="2691c-136">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2691c-137">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="2691c-137">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="2691c-138">På bekräftelsesidan klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="2691c-138">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="2691c-139">Du kommer tillbaka till sidan **Automatisera innehållstolkning**.</span><span class="sxs-lookup"><span data-stu-id="2691c-139">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="2691c-140">På den här sidan kan du välja **Hantera** om du vill göra ändringar i dina konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="2691c-140">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="2691c-141">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="2691c-141">Assign licenses</span></span>

<span data-ttu-id="2691c-142">När du har konfigurerat en SharePoint Syntex måste du tilldela licenser för de användare som kommer att använda SharePoint Syntex-funktioner.</span><span class="sxs-lookup"><span data-stu-id="2691c-142">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="2691c-143">För att tilldela licenser:</span><span class="sxs-lookup"><span data-stu-id="2691c-143">To assign licenses:</span></span>

1. <span data-ttu-id="2691c-144">I Administrationscenter för Microsoft 365 klickar du på **Användare** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="2691c-144">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="2691c-145">Välj de användare som du vill licensiera och klicka på **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="2691c-145">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="2691c-146">Välj **Tilldela fler**.</span><span class="sxs-lookup"><span data-stu-id="2691c-146">Select **Assign more**.</span></span>

4. <span data-ttu-id="2691c-147">Välj **Intelligenta innehållstjänster**.</span><span class="sxs-lookup"><span data-stu-id="2691c-147">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="2691c-148">Under **Appar**ser du till att **Gemensam datatjänst för Intelligenta innehållstjänster** och **Intelligenta innehållstjänster** båda är markerade.</span><span class="sxs-lookup"><span data-stu-id="2691c-148">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2691c-149">![SharePoint Syntex licenser i Administrationscenter för Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="2691c-149">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="2691c-150">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="2691c-150">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="2691c-151">AI Builder-krediter</span><span class="sxs-lookup"><span data-stu-id="2691c-151">AI Builder credits</span></span>

<span data-ttu-id="2691c-152">Om du har 300 eller fler SharePoint Syntex-licenser för SharePoint Syntex i din organisation allokeras en miljon AI Builder-krediter.</span><span class="sxs-lookup"><span data-stu-id="2691c-152">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="2691c-153">Om du har färre än 300 licenser måste du köpa AI Builder-krediter för att kunna använda formulärbearbetning.</span><span class="sxs-lookup"><span data-stu-id="2691c-153">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="2691c-154">Du kan beräkna den AI Builder-kapacitet som passar dig bäst med [Kalkylatorn för AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="2691c-154">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="2691c-155">Gå till [Administrationscenter för Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) om du vill kontrollera krediterna och användningen.</span><span class="sxs-lookup"><span data-stu-id="2691c-155">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="2691c-156">Se även</span><span class="sxs-lookup"><span data-stu-id="2691c-156">See also</span></span>

[<span data-ttu-id="2691c-157">Översikt över modellen för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="2691c-157">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="2691c-158">Steg för steg: Hur du skapar en modell för dokumenttolkning (video)</span><span class="sxs-lookup"><span data-stu-id="2691c-158">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

