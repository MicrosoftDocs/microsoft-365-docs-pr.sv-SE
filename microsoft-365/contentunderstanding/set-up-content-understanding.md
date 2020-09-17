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
# <a name="set-up-content-understanding-preview"></a><span data-ttu-id="9ef83-103">Konfigurera innehålls förståelse (för hands version)</span><span class="sxs-lookup"><span data-stu-id="9ef83-103">Set up content understanding (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="9ef83-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="9ef83-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="9ef83-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="9ef83-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="9ef83-106">Administratörer kan använda Microsoft 365 Admin Center för att konfigurera och konfigurera innehålls förståelse.</span><span class="sxs-lookup"><span data-stu-id="9ef83-106">Admins can use the Microsoft 365 admin center to set up and configure content understanding.</span></span> 

<span data-ttu-id="9ef83-107">Innan du konfigurerar dig bör du planera för det bästa sättet att konfigurera och konfigurera innehålls förståelse i din miljö.</span><span class="sxs-lookup"><span data-stu-id="9ef83-107">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="9ef83-108">Till exempel måste du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="9ef83-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="9ef83-109">Vilka SharePoint-webbplatser aktiverar du formulär bearbetning?</span><span class="sxs-lookup"><span data-stu-id="9ef83-109">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="9ef83-110">Alla, vissa eller utvalda webbplatser?</span><span class="sxs-lookup"><span data-stu-id="9ef83-110">All of them, some, or select sites?</span></span>
- <span data-ttu-id="9ef83-111">Namn på innehålls Center och vem är den primära webbplats administratören?</span><span class="sxs-lookup"><span data-stu-id="9ef83-111">Name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="9ef83-112">En administratör kan också göra ändringar i dina valda inställningar när som helst efter installationen via konfigurations inställningarna för innehålls förståelse i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ef83-112">An admin can also make changes to your selected settings anytime after setup through the content understanding management settings in the Microsoft 365 admin center.</span></span>


## <a name="requirements"></a><span data-ttu-id="9ef83-113">Krav</span><span class="sxs-lookup"><span data-stu-id="9ef83-113">Requirements</span></span> 
<span data-ttu-id="9ef83-114">Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och ställa in innehålls förståelse.</span><span class="sxs-lookup"><span data-stu-id="9ef83-114">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>


## <a name="to-set-up-content-understanding"></a><span data-ttu-id="9ef83-115">Konfigurera innehålls förståelse</span><span class="sxs-lookup"><span data-stu-id="9ef83-115">To set up content understanding</span></span>

1. <span data-ttu-id="9ef83-116">I administrations centret för Microsoft 365 väljer du **Konfigurera**och sedan avsnittet **organisations** information.</span><span class="sxs-lookup"><span data-stu-id="9ef83-116">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>
2. <span data-ttu-id="9ef83-117">I avsnittet **organisationsinformation** väljer du **Automatisera innehålls förståelse**.</span><span class="sxs-lookup"><span data-stu-id="9ef83-117">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Sidan för information om organisationens kunskap](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="9ef83-119">På sidan **Automatisera innehålls förståelse** klickar du på **komma igång** för att vägleda dig genom installations processen.</span><span class="sxs-lookup"><span data-stu-id="9ef83-119">On the **Automate content understanding** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Starta installationen](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. <span data-ttu-id="9ef83-121">På sidan **Konfigurera formulär bearbetning** kan du välja om du vill låta användare kunna använda AI-verktyget för att skapa formulär bearbetnings modeller i specifika SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="9ef83-121">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="9ef83-122">Ett meny alternativ är tillgängligt i menyfliksområdet dokument bibliotek för att **skapa en formulär bearbetnings modell** i SharePoint-dokumentbibliotek där den är aktive rad.</span><span class="sxs-lookup"><span data-stu-id="9ef83-122">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="9ef83-123">För **vilka SharePoint-bibliotek bör visa alternativ för att skapa en modell för formulär bearbetning**kan du välja:</span><span class="sxs-lookup"><span data-stu-id="9ef83-123">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
    - <span data-ttu-id="9ef83-124">**Alla SharePoint-bibliotek** som gör det tillgängligt för alla SharePoint-bibliotek i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="9ef83-124">**All SharePoint libraries** to make it available to all SharePoint libraries in your tenant.</span></span></br>
    - <span data-ttu-id="9ef83-125">**Endast bibliotek på valda webbplatser**och välj de webbplatser som du vill göra tillgänglig för.</span><span class="sxs-lookup"><span data-stu-id="9ef83-125">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>
    - <span data-ttu-id="9ef83-126">**Inga SharePoint-bibliotek** om du inte vill göra det tillgängligt för några webbplatser (du kan ändra det efter installationen).</span><span class="sxs-lookup"><span data-stu-id="9ef83-126">**No SharePoint libraries** if you currently don't want to make it available to any sites (you can change this after setup).</span></span>
</br>

   <span data-ttu-id="9ef83-127">![Konfigurera formulär bearbetning](../media/content-understanding/admin-configforms.png)
</span><span class="sxs-lookup"><span data-stu-id="9ef83-127">![Configure form processing](../media/content-understanding/admin-configforms.png)
</span></span></br>

   > [!Note]
   > <span data-ttu-id="9ef83-128">Om du aktiverar den här inställningen i ett SharePoint-dokumentbibliotek påverkar det inte befintliga modeller som tillämpas på biblioteket eller möjligheten att tillämpa dokument förståelse på ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="9ef83-128">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 

    
5. <span data-ttu-id="9ef83-129">På sidan **skapa innehålls Center** kan du skapa en SharePoint-webbplats för innehålls Center där användarna kan skapa och hantera dokument förståelse modeller.</span><span class="sxs-lookup"><span data-stu-id="9ef83-129">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="9ef83-130">a.</span><span class="sxs-lookup"><span data-stu-id="9ef83-130">a.</span></span> <span data-ttu-id="9ef83-131">För **webbplats namn**anger du det namn som du vill ge innehålls Center webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9ef83-131">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="9ef83-132">b.</span><span class="sxs-lookup"><span data-stu-id="9ef83-132">b.</span></span> <span data-ttu-id="9ef83-133">**Webbplats adressen** visar URL-adressen för webbplatsen, baserat på vad du har valt för webbplats namnet.</span><span class="sxs-lookup"><span data-stu-id="9ef83-133">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span></br>

    > [!Note] 
    > <span data-ttu-id="9ef83-134">Du kan välja ett språk som stöds, men du kan bara skapa innehålls förstå modeller för engelska.</span><span class="sxs-lookup"><span data-stu-id="9ef83-134">While you can select any supported language, note that content understanding models can only be created for English.</span></span></br>

      ![Skapa innehålls Center](../media/content-understanding/admin-cu-create-cc.png)</br>


    <span data-ttu-id="9ef83-136">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9ef83-136">Select **Next**.</span></span>
6. <span data-ttu-id="9ef83-137">På sidan **Slutför och granska** kan du titta på den valda inställningen och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="9ef83-137">On the **Finish and review** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="9ef83-138">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="9ef83-138">If you are satisfied with your selections, select **Activate**.</span></span>



7. <span data-ttu-id="9ef83-139">Sidan **innehålls förståelse** visas och bekräftar att systemet har lagt till dina inställningar för formulär bearbetning och skapar innehålls Center webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9ef83-139">The **Content understanding activated** page will display, confirming that the system has added your form processing preferences and creating the Content Center site.</span></span> <span data-ttu-id="9ef83-140">Välj **klar**.</span><span class="sxs-lookup"><span data-stu-id="9ef83-140">Select **Done**.</span></span>

8. <span data-ttu-id="9ef83-141">Du kommer att återföras till sidan **Automatisera innehålls förståelse** .</span><span class="sxs-lookup"><span data-stu-id="9ef83-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="9ef83-142">Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar.</span><span class="sxs-lookup"><span data-stu-id="9ef83-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="9ef83-143">Se även</span><span class="sxs-lookup"><span data-stu-id="9ef83-143">See also</span></span>



  






