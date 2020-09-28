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
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="99d94-103">Konfigurera SharePoint-Syntex</span><span class="sxs-lookup"><span data-stu-id="99d94-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="99d94-104">Administratörer kan använda administrations centret för Microsoft 365 för att konfigurera och Microsoft SharePoint-Syntex.</span><span class="sxs-lookup"><span data-stu-id="99d94-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="99d94-105">Tänk på följande innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="99d94-105">Consider the following before you start:</span></span>

- <span data-ttu-id="99d94-106">Vilka SharePoint-webbplatser aktiverar du formulär bearbetning?</span><span class="sxs-lookup"><span data-stu-id="99d94-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="99d94-107">Alla, vissa eller utvalda webbplatser?</span><span class="sxs-lookup"><span data-stu-id="99d94-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="99d94-108">Vad heter du för innehålls Center och vem är den primära webbplats administratören?</span><span class="sxs-lookup"><span data-stu-id="99d94-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="99d94-109">Du kan ändra inställningarna efter den första installationen i Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="99d94-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="99d94-110">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="99d94-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="99d94-111">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="99d94-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="99d94-112">Innan du konfigurerar dig bör du planera för det bästa sättet att konfigurera och konfigurera innehålls förståelse i din miljö.</span><span class="sxs-lookup"><span data-stu-id="99d94-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="99d94-113">Du måste till exempel tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="99d94-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="99d94-114">SharePoint-webbplatserna som du vill aktivera bearbetning av formulär för – alla, vissa eller markerade webbplatser</span><span class="sxs-lookup"><span data-stu-id="99d94-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="99d94-115">Ditt innehålls Center och namnet på den primära webbplats administratören</span><span class="sxs-lookup"><span data-stu-id="99d94-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="99d94-116">Krav</span><span class="sxs-lookup"><span data-stu-id="99d94-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="99d94-117">Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och ställa in innehålls förståelse.</span><span class="sxs-lookup"><span data-stu-id="99d94-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="99d94-118">Som administratör kan du också göra ändringar i dina valda inställningar när som helst efter installationen och i alla inställningar för innehålls förståelse i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99d94-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="99d94-119">Så här konfigurerar du SharePoint-Syntex</span><span class="sxs-lookup"><span data-stu-id="99d94-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="99d94-120">I administrations centret för Microsoft 365 väljer du **Konfigurera**och sedan avsnittet **organisations** information.</span><span class="sxs-lookup"><span data-stu-id="99d94-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="99d94-121">I avsnittet **organisationsinformation** väljer du **Automatisera innehålls förståelse**.</span><span class="sxs-lookup"><span data-stu-id="99d94-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Sidan för information om organisationens kunskap](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="99d94-123">Gå igenom konfigurationen genom att klicka på **komma igång** på sidan **Automatisera SharePoint-Syntex** .</span><span class="sxs-lookup"><span data-stu-id="99d94-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Starta installationen](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="99d94-125">På sidan Aktivera bild taggning väljer du om du vill tillåta [bild märkning](image-tagging.md).</span><span class="sxs-lookup"><span data-stu-id="99d94-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Skärm bild av alternativ för bild markeringar](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="99d94-127">På sidan **Konfigurera formulär bearbetning** kan du välja om du vill låta användare kunna använda AI-verktyget för att skapa formulär bearbetnings modeller i specifika SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="99d94-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="99d94-128">Ett meny alternativ är tillgängligt i menyfliksområdet dokument bibliotek för att **skapa en formulär bearbetnings modell** i SharePoint-dokumentbibliotek där den är aktive rad.</span><span class="sxs-lookup"><span data-stu-id="99d94-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="99d94-129">För **vilka SharePoint-bibliotek bör visa alternativ för att skapa en modell för formulär bearbetning**kan du välja:</span><span class="sxs-lookup"><span data-stu-id="99d94-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="99d94-130">**Alla SharePoint-bibliotek** som gör det tillgängligt för alla SharePoint-bibliotek i organisationen.</span><span class="sxs-lookup"><span data-stu-id="99d94-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="99d94-131">**Endast bibliotek på valda webbplatser**och välj de webbplatser som du vill göra tillgänglig för.</span><span class="sxs-lookup"><span data-stu-id="99d94-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![Konfigurera formulär bearbetning](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="99d94-133">Om du aktiverar den här inställningen i ett SharePoint-dokumentbibliotek påverkar det inte befintliga modeller som tillämpas på biblioteket eller möjligheten att tillämpa dokument förståelse på ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="99d94-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="99d94-134">På sidan **skapa innehålls Center** kan du skapa en SharePoint-webbplats för innehålls Center där användarna kan skapa och hantera dokument förståelse modeller.</span><span class="sxs-lookup"><span data-stu-id="99d94-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="99d94-135">a.</span><span class="sxs-lookup"><span data-stu-id="99d94-135">a.</span></span> <span data-ttu-id="99d94-136">För **webbplats namn**anger du det namn som du vill ge innehålls Center webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="99d94-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="99d94-137">b.</span><span class="sxs-lookup"><span data-stu-id="99d94-137">b.</span></span> <span data-ttu-id="99d94-138">**Webbplats adressen** visar URL-adressen för webbplatsen, baserat på vad du har valt för webbplats namnet.</span><span class="sxs-lookup"><span data-stu-id="99d94-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="99d94-139">Om du vill ändra det klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="99d94-139">If you want to change it, click **Edit**.</span></span></br>

      ![Skapa innehålls Center](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="99d94-141">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="99d94-141">Select **Next**.</span></span>

7. <span data-ttu-id="99d94-142">På sidan **Granska och slutför** kan du titta på den valda inställningen och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="99d94-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="99d94-143">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="99d94-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="99d94-144">På bekräftelse sidan klickar du på **klar**.</span><span class="sxs-lookup"><span data-stu-id="99d94-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="99d94-145">Du kommer att återföras till sidan **Automatisera innehålls förståelse** .</span><span class="sxs-lookup"><span data-stu-id="99d94-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="99d94-146">Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar.</span><span class="sxs-lookup"><span data-stu-id="99d94-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="99d94-147">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="99d94-147">Assign licenses</span></span>

<span data-ttu-id="99d94-148">När du har konfigurerat en SharePoint-Syntex måste du tilldela licenser för de användare som ska använda formulär bearbetning och dokument förstå funktioner.</span><span class="sxs-lookup"><span data-stu-id="99d94-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="99d94-149">Så här tilldelar du licenser:</span><span class="sxs-lookup"><span data-stu-id="99d94-149">To assign licenses:</span></span>

1. <span data-ttu-id="99d94-150">Klicka på **aktiva användare**under **användare**i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99d94-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="99d94-151">Välj de användare som du vill licensiera och klicka på **Hantera produkt licenser**.</span><span class="sxs-lookup"><span data-stu-id="99d94-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="99d94-152">Välj **tilldela mer**.</span><span class="sxs-lookup"><span data-stu-id="99d94-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="99d94-153">Välj **intelligent Content Services**.</span><span class="sxs-lookup"><span data-stu-id="99d94-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="99d94-154">Under **program**kontrollerar du att **gemensam data tjänst för intelligenta innehålls tjänster** och **intelligenta innehålls tjänster** är markerade.</span><span class="sxs-lookup"><span data-stu-id="99d94-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![SharePoint Syntex-licenser i administrations centret för Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="99d94-156">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="99d94-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="99d94-157">Krediteringar för AI-byggare</span><span class="sxs-lookup"><span data-stu-id="99d94-157">AI Builder credits</span></span>

<span data-ttu-id="99d94-158">Om du har 300 eller fler SharePoint Syntex-licenser för SharePoint Syntex i organisationen tilldelas du 1 000 000 AI Builder-kredit.</span><span class="sxs-lookup"><span data-stu-id="99d94-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="99d94-159">Om du har färre än 300 licenser måste du köpa AI Builder-kredit för att kunna använda formulär bearbetning.</span><span class="sxs-lookup"><span data-stu-id="99d94-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="99d94-160">Du kan uppskatta vilken AI Builder-kapacitet som passar dig med [AI Builder-kalkylatorn](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="99d94-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

1. <span data-ttu-id="99d94-161">Gå till [administrations centret för Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) för att kontrol lera kredit och användning.</span><span class="sxs-lookup"><span data-stu-id="99d94-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99d94-162">Aktivera den här inställningen i ett SharePoint-dokumentbibliotek påverkar inte befintliga modeller som tillämpas på biblioteket eller möjligheten att tillämpa dokument förståelse på ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="99d94-162">Enable this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
2. <span data-ttu-id="99d94-163">På sidan **skapa innehålls Center** kan du skapa en SharePoint-webbplats för innehålls Center där användare kan skapa och hantera dokument förståelse modeller.</span><span class="sxs-lookup"><span data-stu-id="99d94-163">From the **Create Content Center** page, you can create a SharePoint content center site for which users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="99d94-164">a.</span><span class="sxs-lookup"><span data-stu-id="99d94-164">a.</span></span> <span data-ttu-id="99d94-165">För **webbplats namn**anger du det namn du vill använda för innehålls Center webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="99d94-165">For **Site name**, type the name you want for the content center site.</span></span></br>
    <span data-ttu-id="99d94-166">b.</span><span class="sxs-lookup"><span data-stu-id="99d94-166">b.</span></span> <span data-ttu-id="99d94-167">Webb **adressen** för din webbplats visas, baserat på webbplats namnet.</span><span class="sxs-lookup"><span data-stu-id="99d94-167">The **Site address** shows the URL for your site, based on the site name.</span></span></br>

    > [!NOTE] 
    > <span data-ttu-id="99d94-168">Du kan välja ett språk som stöds, innehålls förstå modeller kan bara skapas för engelska.</span><span class="sxs-lookup"><span data-stu-id="99d94-168">While you can select any supported language, content understanding models can only be created for English.</span></span></br>

      ![Skapa innehålls Center](../media/content-understanding/admin-cu-create-cc.png)</br>

3. <span data-ttu-id="99d94-170">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="99d94-170">Select **Next**.</span></span>

4. <span data-ttu-id="99d94-171">På sidan **Slutför och granska** tittar du på den valda inställningen och väljer att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="99d94-171">On the **Finish and review** page, look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="99d94-172">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="99d94-172">If you are satisfied with your selections, select **Activate**.</span></span>

5. <span data-ttu-id="99d94-173">Sidan **innehålls användning aktive rad** visas och bekräftar att systemet har lagt till dina inställningar för formulär bearbetning och skapat innehålls Center webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="99d94-173">The **Content understanding activated** page displays, confirming the system added your form processing preferences and created the Content Center site.</span></span> <span data-ttu-id="99d94-174">Välj **klar**.</span><span class="sxs-lookup"><span data-stu-id="99d94-174">Select **Done**.</span></span>

6. <span data-ttu-id="99d94-175">Du kommer att återföras till sidan **Automatisera innehålls förståelse** .</span><span class="sxs-lookup"><span data-stu-id="99d94-175">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="99d94-176">Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar.</span><span class="sxs-lookup"><span data-stu-id="99d94-176">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="99d94-177">Se även</span><span class="sxs-lookup"><span data-stu-id="99d94-177">See also</span></span>

[<span data-ttu-id="99d94-178">Översikt över formulär bearbetnings modellen</span><span class="sxs-lookup"><span data-stu-id="99d94-178">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="99d94-179">Steg-för-steg: hur du skapar en modell för dokument förståelse (video)</span><span class="sxs-lookup"><span data-stu-id="99d94-179">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

