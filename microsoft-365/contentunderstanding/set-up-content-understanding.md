---
title: Konfigurera SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Konfigurera innehållstolkning i Project Cortex
ms.openlocfilehash: 7589003505aafb480872b14a09c383cfbe0dff40
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683559"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="02e7a-103">Konfigurera SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="02e7a-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="02e7a-104">Administratörer kan använda Administrationscenter för Microsoft 365 för att konfigurera [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="02e7a-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="02e7a-105">Tänk på följande innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="02e7a-105">Consider the following before you start:</span></span>

- <span data-ttu-id="02e7a-106">På vilka SharePoint-webbplatser kommer du aktivera formulärbearbetning?</span><span class="sxs-lookup"><span data-stu-id="02e7a-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="02e7a-107">Alla, vissa eller utvalda webbplatser?</span><span class="sxs-lookup"><span data-stu-id="02e7a-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="02e7a-108">Vad heter ditt standard innehållscenter?</span><span class="sxs-lookup"><span data-stu-id="02e7a-108">What will you name your default content center?</span></span>

<span data-ttu-id="02e7a-109">Du kan ändra inställningarna efter den första konfigurationen i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02e7a-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="02e7a-p102">Innan konfigurationen ser du till att planera för det bästa sättet att ställa in och konfigurera innehållstolkning i din miljö. Till exempel behöver du fatta följande beslut:</span><span class="sxs-lookup"><span data-stu-id="02e7a-p102">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="02e7a-112">De SharePoint-webbplatser där du vill aktivera formulärbearbetning för – alla, vissa eller utvalda webbplatser</span><span class="sxs-lookup"><span data-stu-id="02e7a-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="02e7a-113">Namn och administratörer för innehållscentret</span><span class="sxs-lookup"><span data-stu-id="02e7a-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="02e7a-114">Krav</span><span class="sxs-lookup"><span data-stu-id="02e7a-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="02e7a-115">Du måste ha behörighet som global administratör eller SharePoint-administratör för att kunna komma åt Administrationscenter för Microsoft 365 och konfigurera SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="02e7a-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="02e7a-116">Som administratör kan du också göra ändringar i dina valda inställningar när som helst efter konfigurationen och under inställningarna för hantering av innehållstolkning i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02e7a-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

<span data-ttu-id="02e7a-117">Om du planerar att använda en anpassad Power Platform-miljö måste du [installera *AI Builder för Project Cortex* -appen i den här miljön](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) och [tilldela AI Builder-krediter](/power-platform/admin/capacity-add-on) till den innan du kan skapa formulärbearbetningsmodeller.</span><span class="sxs-lookup"><span data-stu-id="02e7a-117">If you plan to use a custom Power Platform environment, you must [install the *AI Builder for Project Cortex* app in this environment](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) and [allocate AI Builder credits](/power-platform/admin/capacity-add-on) to it before you can create form processing models.</span></span>

### <a name="licensing"></a><span data-ttu-id="02e7a-118">Licensiering</span><span class="sxs-lookup"><span data-stu-id="02e7a-118">Licensing</span></span>

<span data-ttu-id="02e7a-119">Om du vill använda SharePoint Syntex måste organisationen ha en prenumeration på SharePoint Syntex och varje användare måste ha följande licenser tilldelade:</span><span class="sxs-lookup"><span data-stu-id="02e7a-119">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="02e7a-120">SharePoint-Syntex</span><span class="sxs-lookup"><span data-stu-id="02e7a-120">SharePoint Syntex</span></span>
- <span data-ttu-id="02e7a-121">SharePoint Syntex – SPO-typ</span><span class="sxs-lookup"><span data-stu-id="02e7a-121">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="02e7a-122">Vanliga datatjänster för SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="02e7a-122">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="02e7a-123">Om du avbryter SharePoint Syntex-prenumerationen vid ett framtida datum (eller om utvärderingsversionen går ut) kan användarna inte längre skapa eller köra dokumenttolkning eller bearbeta formulärmodeller och mallen för innehållscenter är inte längre tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="02e7a-123">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="02e7a-124">Dessutom kommer inte längre rapporter för termlagring, SKOS-taxonomiimport och push-fil av innehållstyp att vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="02e7a-124">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="02e7a-125">Inget innehåll tas bort och webbplatsbehörigheterna ändras inte.</span><span class="sxs-lookup"><span data-stu-id="02e7a-125">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="02e7a-126">AI Builder-krediter</span><span class="sxs-lookup"><span data-stu-id="02e7a-126">AI Builder credits</span></span>

<span data-ttu-id="02e7a-127">Om du har 300 eller fler SharePoint Syntex-licenser för SharePoint Syntex i din organisation allokeras en miljon AI Builder-krediter.</span><span class="sxs-lookup"><span data-stu-id="02e7a-127">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="02e7a-128">Om du har färre än 300 licenser måste du köpa AI Builder-krediter för att kunna använda formulärbearbetning.</span><span class="sxs-lookup"><span data-stu-id="02e7a-128">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="02e7a-129">Du kan beräkna den AI Builder-kapacitet som passar dig bäst med [Kalkylatorn för AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="02e7a-129">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="02e7a-130">Om du planerar att använda en anpassad Power Platform-miljö måste du [tilldela krediter till den miljö](/power-platform/admin/capacity-add-on).</span><span class="sxs-lookup"><span data-stu-id="02e7a-130">If you plan to use a custom Power Platform environment, you must [allocate credits to that environment](/power-platform/admin/capacity-add-on).</span></span>

<span data-ttu-id="02e7a-131">Gå till [Administrationscenter för Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) om du vill kontrollera dina krediter och användning.</span><span class="sxs-lookup"><span data-stu-id="02e7a-131">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="02e7a-132">Att konfigurera SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="02e7a-132">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="02e7a-133">I Administrationscenter för Microsoft 365 välj **Konfiguration** och se sedan **Filer och innehåll** sektionen.</span><span class="sxs-lookup"><span data-stu-id="02e7a-133">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="02e7a-134">I **Filer och innehåll** sektionen välj **Automatisera innehållstolkning**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-134">In the **Files and content** section, select **Automate content understanding**.</span></span> <span data-ttu-id="02e7a-135">Observera att din aktuella AI Builder-kredittillgänglighet visas i avsnittet **I korthet**. </span><span class="sxs-lookup"><span data-stu-id="02e7a-135">Note that your current AI Builder credit availability is shown in the **At a glance** section.</span></span><br/>

3. <span data-ttu-id="02e7a-136">På sidan **Automatisera innehållstolkning** klickar du på **Komma igång** för att gå igenom konfigurationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="02e7a-136">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span> <br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="02e7a-137">![Starta konfiguration](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="02e7a-137">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="02e7a-138">På sidan **Konfigurera formulärbearbetning** kan du välja om du vill tillåta att användare kan skapa modeller för formulärbearbetning i vissa dokumentbibliotek i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="02e7a-138">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="02e7a-139">Ett menyalternativ kommer att vara tillgängligt i menyfliksområdet för dokumentbiblioteket för att **Skapa en modell för formulärbearbetning** i dokumentbibliotek i SharePoint där den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="02e7a-139">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="02e7a-140">För **vilka SharePoint-bibliotek som ska visa alternativ för att skapa modell för formulärbearbetning** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="02e7a-140">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="02e7a-141">**Bibliotek på alla SharePoint-webbplatser** för att göra det tillgängligt för alla SharePoint-bibliotek i organisationen.</span><span class="sxs-lookup"><span data-stu-id="02e7a-141">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="02e7a-142">**Bibliotek på utvalda SharePoint-webbplatser** och välj sedan de webbplatser där du vill göra det tillgängligt eller ladda upp en lista med upp till 50 webbplatser.</span><span class="sxs-lookup"><span data-stu-id="02e7a-142">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="02e7a-143">**Inga SharePoint-bibliotek** om du inte vill att det ska vara tillgängligt för några webbplatser (du kan ändra det när konfigurationen är slutförd).</span><span class="sxs-lookup"><span data-stu-id="02e7a-143">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="02e7a-144">![Konfigurera webbplatsalternativ för formulärbearbetning](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="02e7a-144">![Configure form processing site options](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="02e7a-145">Att ta bort en webbplats efter att den har inkluderats påverkar inte befintliga modeller som används i biblioteken på webbplatsen eller möjligheten att använda modeller för dokumenttolkning på ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="02e7a-145">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
    <span data-ttu-id="02e7a-146">Om du har konfigurerat flera Power Platform-miljöer kan du välja vilken du vill använda för formulärbearbetning.</span><span class="sxs-lookup"><span data-stu-id="02e7a-146">If you have multiple Power Platform environments configured, you can choose which one you want to use with for form processing.</span></span> <span data-ttu-id="02e7a-147">(Det här alternativet visas inte om du bara har en miljö.)</span><span class="sxs-lookup"><span data-stu-id="02e7a-147">(This option will not appear if you only have one environment.)</span></span>

    ![Konfigurera alternativ för formulärbearbetning i Power Platform](../media/content-understanding/setup-power-platform-env.png)

    <span data-ttu-id="02e7a-149">För **Power Platform-miljö** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="02e7a-149">For **Power Platform environment**, you can select:</span></span>
    - <span data-ttu-id="02e7a-150">**Använd standardmiljön** för att använda din standardmiljö för Power Platform.</span><span class="sxs-lookup"><span data-stu-id="02e7a-150">**Use the default environment** to use your default Power Platform environment.</span></span>
    - <span data-ttu-id="02e7a-151">**Använd en anpassad miljö** för att använda en anpassad miljö.</span><span class="sxs-lookup"><span data-stu-id="02e7a-151">**Use a custom environment** to use a custom environment.</span></span> <span data-ttu-id="02e7a-152">Välj den miljö du vill använda från listan.</span><span class="sxs-lookup"><span data-stu-id="02e7a-152">Choose the environment that you want to use from the list.</span></span> <span data-ttu-id="02e7a-153">([Se kraven för en anpassad miljö](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).</span><span class="sxs-lookup"><span data-stu-id="02e7a-153">([See the requirements for a custom environment](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).</span></span>

    <span data-ttu-id="02e7a-154">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-154">Click **Next**.</span></span>

5. <span data-ttu-id="02e7a-155">På sidan **Skapa innehållscenter** kan du skapa en SharePoint-webbplats för innehållscenter där dina användare kan skapa och hantera modeller för dokumenttolkning.</span><span class="sxs-lookup"><span data-stu-id="02e7a-155">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="02e7a-156">För **Webbplatsnamn** skriver du namnet som du vill använda på webbplatsen för innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="02e7a-156">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="02e7a-157">**Webbplatsens adress** kommer att visa URL:en för din webbplats baserat på vad du valde som webbplatsnamn.</span><span class="sxs-lookup"><span data-stu-id="02e7a-157">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="02e7a-158">Om du vill ändra det klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-158">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="02e7a-159">![Skapa innehållscenter](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="02e7a-159">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="02e7a-160">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-160">Select **Next**.</span></span>

6. <span data-ttu-id="02e7a-161">På sidan **Granska och slutför** kan du titta på vald inställning och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="02e7a-161">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="02e7a-162">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-162">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="02e7a-163">På bekräftelsesidan klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-163">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="02e7a-164">Du kommer tillbaka till sidan **Automatisera innehållstolkning**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-164">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="02e7a-165">På den här sidan kan du välja **Hantera** om du vill göra ändringar i dina konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="02e7a-165">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="02e7a-166">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="02e7a-166">Assign licenses</span></span>

<span data-ttu-id="02e7a-167">När du har konfigurerat en SharePoint Syntex måste du tilldela licenser för de användare som kommer att använda SharePoint Syntex-funktioner.</span><span class="sxs-lookup"><span data-stu-id="02e7a-167">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="02e7a-168">För att tilldela licenser:</span><span class="sxs-lookup"><span data-stu-id="02e7a-168">To assign licenses:</span></span>

1. <span data-ttu-id="02e7a-169">I Administrationscenter för Microsoft 365 klickar du på **Användare** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-169">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="02e7a-170">Välj de användare som du vill licensiera och klicka på **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-170">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="02e7a-171">Välj **Appar** på den nedrullningsbar menyn.</span><span class="sxs-lookup"><span data-stu-id="02e7a-171">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="02e7a-172">Välj **Visa appar för SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-172">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="02e7a-173">Under **Appar** kontrollerar du att **Common Data Service for SharePoint Syntex**, **SharePoint Syntex** och **SharePoint Syntex – SPO-typ** är alla markerade.</span><span class="sxs-lookup"><span data-stu-id="02e7a-173">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="02e7a-174">![SharePoint Syntex-licenser i Administrationscentret för Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="02e7a-174">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="02e7a-175">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="02e7a-175">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="02e7a-176">Se även</span><span class="sxs-lookup"><span data-stu-id="02e7a-176">See also</span></span>

[<span data-ttu-id="02e7a-177">Översikt över modellen för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="02e7a-177">Overview of the form processing model</span></span>](/ai-builder/form-processing-model-overview)

[<span data-ttu-id="02e7a-178">Steg för steg: Hur du skapar en modell för dokumenttolkning (video)</span><span class="sxs-lookup"><span data-stu-id="02e7a-178">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

[<span data-ttu-id="02e7a-179">Skapa och hantera miljöer i administrationscentret för Power Platform</span><span class="sxs-lookup"><span data-stu-id="02e7a-179">Create and manage environments in the Power Platform admin center</span></span>](/power-platform/admin/create-environment)
