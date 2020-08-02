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
# <a name="set-up-content-understanding-preview"></a><span data-ttu-id="2372c-103">Konfigurera innehållsförståelse (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="2372c-103">Set up content understanding (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="2372c-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="2372c-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="2372c-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="2372c-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="2372c-106">Administratörer kan använda Microsoft 365-administrationscentret för att konfigurera innehållsbeståelse.</span><span class="sxs-lookup"><span data-stu-id="2372c-106">Admins can use the Microsoft 365 admin center to set up and configure content understanding.</span></span> 

<span data-ttu-id="2372c-107">Innan du konfigurerar, se till att planera för det bästa sättet att ställa in och konfigurera innehållsförståelse i din miljö.</span><span class="sxs-lookup"><span data-stu-id="2372c-107">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="2372c-108">Du måste till exempel ta hänsyn till följande:</span><span class="sxs-lookup"><span data-stu-id="2372c-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="2372c-109">Vilka SharePoint-webbplatser aktiverar du formulärbearbetning?</span><span class="sxs-lookup"><span data-stu-id="2372c-109">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="2372c-110">Alla av dem, vissa, eller välj webbplatser?</span><span class="sxs-lookup"><span data-stu-id="2372c-110">All of them, some, or select sites?</span></span>
- <span data-ttu-id="2372c-111">Namnet på ditt innehållscenter och vem är den primära webbplatsadministratören?</span><span class="sxs-lookup"><span data-stu-id="2372c-111">Name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="2372c-112">En administratör kan också göra ändringar i dina valda inställningar när som helst efter installationen genom hanteringsinställningarna för innehålls förståelse i microsoft 365-administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="2372c-112">An admin can also make changes to your selected settings anytime after setup through the content understanding management settings in the Microsoft 365 admin center.</span></span>


## <a name="requirements"></a><span data-ttu-id="2372c-113">Krav</span><span class="sxs-lookup"><span data-stu-id="2372c-113">Requirements</span></span> 
<span data-ttu-id="2372c-114">Du måste ha behörigheten Global Admin eller SharePoint för att kunna komma åt Microsoft 365-administrationscentret och konfigurera innehållsförståelse.</span><span class="sxs-lookup"><span data-stu-id="2372c-114">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>


## <a name="to-set-up-content-understanding"></a><span data-ttu-id="2372c-115">Så här ställer du in innehållsöverensning</span><span class="sxs-lookup"><span data-stu-id="2372c-115">To set up content understanding</span></span>

1. <span data-ttu-id="2372c-116">I administrationscentret för Microsoft 365 väljer du **Installationsprogrammet**och visar sedan avsnittet **Organisationskunskap.**</span><span class="sxs-lookup"><span data-stu-id="2372c-116">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>
2. <span data-ttu-id="2372c-117">I avsnittet **Organisatorisk kunskap** väljer du **Automatisera innehållsöverensning**.</span><span class="sxs-lookup"><span data-stu-id="2372c-117">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Inställningssida för organisationskunskap](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="2372c-119">På sidan **Automatisera innehållsöverenskommelsen** klickar du på **Kom igång** för att gå igenom installationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2372c-119">On the **Automate content understanding** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Börja installationen](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. <span data-ttu-id="2372c-121">På sidan **Konfigurera formulärbearbetning** kan du välja om du vill att användarna ska kunna använda AI Builder för att skapa formulärbearbetningsmodeller i specifika SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="2372c-121">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="2372c-122">Ett menyalternativ är tillgängligt i menyfliksområdet för dokumentbiblioteket för att **skapa en formulärbearbetningsmodell** i SharePoint-dokumentbibliotek där den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="2372c-122">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="2372c-123">För **vilka SharePoint-bibliotek ska visa alternativet för att skapa en formulärbearbetningsmodell**kan du välja:</span><span class="sxs-lookup"><span data-stu-id="2372c-123">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
    - <span data-ttu-id="2372c-124">**Alla SharePoint-bibliotek** för att göra det tillgängligt för alla SharePoint-bibliotek i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="2372c-124">**All SharePoint libraries** to make it available to all SharePoint libraries in your tenant.</span></span></br>
    - <span data-ttu-id="2372c-125">**Endast bibliotek på valda platser**och välj sedan de platser där du vill göra det tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="2372c-125">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>
    - <span data-ttu-id="2372c-126">**Inga SharePoint-bibliotek** om du för närvarande inte vill göra det tillgängligt för några webbplatser (du kan ändra detta efter installationen).</span><span class="sxs-lookup"><span data-stu-id="2372c-126">**No SharePoint libraries** if you currently don't want to make it available to any sites (you can change this after setup).</span></span>
</br>

   <span data-ttu-id="2372c-127">![Konfigurera formulärbearbetning](../media/content-understanding/admin-configforms.png)
</span><span class="sxs-lookup"><span data-stu-id="2372c-127">![Configure form processing](../media/content-understanding/admin-configforms.png)
</span></span></br>

   > [!Note]
   > <span data-ttu-id="2372c-128">Om du aktiverar den här inställningen i ett SharePoint-dokumentbibliotek påverkas inte befintliga modeller som tillämpas på biblioteket eller möjligheten att tillämpa dokumentöverenstagande modeller i ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="2372c-128">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 

    
5. <span data-ttu-id="2372c-129">På sidan **Skapa innehållscenter** kan du skapa en SharePoint-webbplats för innehållscenter där användarna kan skapa och hantera dokumentöverenstagande modeller.</span><span class="sxs-lookup"><span data-stu-id="2372c-129">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="2372c-130">a.</span><span class="sxs-lookup"><span data-stu-id="2372c-130">a.</span></span> <span data-ttu-id="2372c-131">För **Webbplatsnamn**skriver du det namn som du vill ge webbplatsen för innehållscentret.</span><span class="sxs-lookup"><span data-stu-id="2372c-131">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="2372c-132">b.</span><span class="sxs-lookup"><span data-stu-id="2372c-132">b.</span></span> <span data-ttu-id="2372c-133">**Webbplatsadressen** visar webbadressen för din webbplats, baserat på vad du valde för webbplatsnamnet.</span><span class="sxs-lookup"><span data-stu-id="2372c-133">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span></br>

    > [!Note] 
    > <span data-ttu-id="2372c-134">Du kan välja ett språk som stöds, observera att innehållsöverenseringsmodeller endast kan skapas för engelska.</span><span class="sxs-lookup"><span data-stu-id="2372c-134">While you can select any supported language, note that content understanding models can only be created for English.</span></span></br>

      ![Skapa innehållscenter](../media/content-understanding/admin-cu-create-cc.png)</br>


    <span data-ttu-id="2372c-136">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2372c-136">Select **Next**.</span></span>
6. <span data-ttu-id="2372c-137">På sidan **Slutför och granska** kan du titta på den valda inställningen och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="2372c-137">On the **Finish and review** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2372c-138">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="2372c-138">If you are satisfied with your selections, select **Activate**.</span></span>



7. <span data-ttu-id="2372c-139">Sidan **Innehållsförståelse aktiverad** visas, vilket bekräftar att systemet har lagt till dina inställningar för formulärbearbetning och skapat Content Center-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2372c-139">The **Content understanding activated** page will display, confirming that the system has added your form processing preferences and creating the Content Center site.</span></span> <span data-ttu-id="2372c-140">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="2372c-140">Select **Done**.</span></span>

8. <span data-ttu-id="2372c-141">Du kommer tillbaka till sidan För att **förstå automatisera innehåll.**</span><span class="sxs-lookup"><span data-stu-id="2372c-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="2372c-142">På den här sidan kan du välja **Hantera** om du vill göra ändringar i konfigurationsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="2372c-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2372c-143">Se även</span><span class="sxs-lookup"><span data-stu-id="2372c-143">See also</span></span>



  






