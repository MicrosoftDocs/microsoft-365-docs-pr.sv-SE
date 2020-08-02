---
title: 'Hantera kunskapshanteringsnätverket(Förhandsgranska) '
description: Så här ställer du in Knowledge Management.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540124"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="4899f-103">Hantera ditt kunskapshanteringsnätverk (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4899f-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4899f-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="4899f-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4899f-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="4899f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="4899f-106">När du [har konfigurerat kunskapshantering](set-up-knowledge-network.md)kan en administratör när som helst efteråt göra justeringar i konfigurationsinställningarna via administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4899f-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="4899f-107">Du kan till exempel behöva justera inställningarna för något av följande:</span><span class="sxs-lookup"><span data-stu-id="4899f-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="4899f-108">Lägg till nya SharePoint-källor i mina ämnen.</span><span class="sxs-lookup"><span data-stu-id="4899f-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="4899f-109">Ändra vilka användare som ska ha åtkomst till ämnen.</span><span class="sxs-lookup"><span data-stu-id="4899f-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="4899f-110">Ändra vilka användare som har behörighet att utföra uppgifter i ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="4899f-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="4899f-111">Ändra namnet på ditt ämnescenter</span><span class="sxs-lookup"><span data-stu-id="4899f-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="4899f-112">Krav</span><span class="sxs-lookup"><span data-stu-id="4899f-112">Requirements</span></span> 
<span data-ttu-id="4899f-113">Du måste ha behörigheten Global admin eller SharePoint för att kunna komma åt Microsoft 365-administrationscentret och hantera organisatoriska kunskapsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="4899f-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="4899f-114">Så här kommer du åt kunskapshanteringsinställningarna:</span><span class="sxs-lookup"><span data-stu-id="4899f-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="4899f-115">I administrationscentret för Microsoft 365 väljer du **Installationsprogrammet**och visar sedan avsnittet **Organisationskunskap.**</span><span class="sxs-lookup"><span data-stu-id="4899f-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="4899f-116">Klicka på Anslut personer **till kunskap**i avsnittet **Organisationskunskap.**</span><span class="sxs-lookup"><span data-stu-id="4899f-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="4899f-118">På sidan **Anslut personer till kunskap** väljer du **Hantera** för att öppna fönstret Inställningar **för kunskapsnätverk.**</span><span class="sxs-lookup"><span data-stu-id="4899f-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![inställningar för kunskapsnätverk](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="4899f-120">Ändra hur kunskapsnätverket kan hitta ämnen</span><span class="sxs-lookup"><span data-stu-id="4899f-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="4899f-121">Välj fliken **Ämnesidentifiering** om du vill uppdatera dina alternativ för SharePoint-ämneskällor.</span><span class="sxs-lookup"><span data-stu-id="4899f-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="4899f-122">Med den här inställningen kan du välja de SharePoint-platser i din klientorganisation som ska genomsökas och brytas för ämnen.</span><span class="sxs-lookup"><span data-stu-id="4899f-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="4899f-123">Välj **Redigera**under **Välj SharePoint-ämneskällor**på fliken **Ämnesidentifiering** .</span><span class="sxs-lookup"><span data-stu-id="4899f-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="4899f-124">På sidan **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som ska genomsökas som källor för dina ämnen under identifieringen.</span><span class="sxs-lookup"><span data-stu-id="4899f-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="4899f-125">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="4899f-125">This includes:</span></span></br>
    <span data-ttu-id="4899f-126">a.</span><span class="sxs-lookup"><span data-stu-id="4899f-126">a.</span></span> <span data-ttu-id="4899f-127">**Alla webbplatser:** Alla SharePoint-webbplatser i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4899f-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="4899f-128">Detta fångar nuvarande och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="4899f-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="4899f-129">b.</span><span class="sxs-lookup"><span data-stu-id="4899f-129">b.</span></span> <span data-ttu-id="4899f-130">**Alla, utom valda platser:** Skriv namnen på de webbplatser som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="4899f-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="4899f-131">Du kan också ladda upp en lista över webbplatser som du vill välja bort från identifiering.</span><span class="sxs-lookup"><span data-stu-id="4899f-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="4899f-132">Webbplatser som skapas i framtiden kommer att inkluderas som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="4899f-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="4899f-133">c.</span><span class="sxs-lookup"><span data-stu-id="4899f-133">c.</span></span> <span data-ttu-id="4899f-134">**Endast valda platser:** Skriv namnen på de platser som du vill inkludera.</span><span class="sxs-lookup"><span data-stu-id="4899f-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="4899f-135">Du kan också ladda upp en lista över webbplatser.</span><span class="sxs-lookup"><span data-stu-id="4899f-135">You can also upload a list of sites.</span></span> <span data-ttu-id="4899f-136">Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="4899f-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Välj hur du hittar ämnen](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="4899f-138">Om du har ett antal webbplatser som du vill utesluta (om du väljer **Alla, utom valda webbplatser)** eller inkluderar (om du har valt **Endast valda webbplatser)** kan du välja att ladda upp en CSV-fil med webbplatsnamn och webbadresser.</span><span class="sxs-lookup"><span data-stu-id="4899f-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="4899f-139">Du kan välja **Hämta webbplatsmall .csv** om du vill använda CSV-mallfilen.</span><span class="sxs-lookup"><span data-stu-id="4899f-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="4899f-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4899f-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="4899f-141">Ändra vem som kan se ämnen i organisationen</span><span class="sxs-lookup"><span data-stu-id="4899f-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="4899f-142">Välj fliken **Ämnesidentifiering** om du vill uppdatera vem i organisationen som kan se upptäckta ämnen i sökresultaten och när ämnen markeras i innehåll som SharePoint-sidor.</span><span class="sxs-lookup"><span data-stu-id="4899f-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="4899f-143">Välj **Redigera**under **Vem kan se ämnen i kunskapsnätverket**på fliken **Ämnesidentifiering** .</span><span class="sxs-lookup"><span data-stu-id="4899f-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="4899f-144">På sidan Vem kan se ämnen på sidan **kunskapsnätverk** väljer du vem som ska ha tillgång till ämnesinformation, till exempel markerade ämnen, ämneskort, ämnessvar i sök- och ämnessidor.</span><span class="sxs-lookup"><span data-stu-id="4899f-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="4899f-145">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="4899f-145">You can select:</span></span></br>
    <span data-ttu-id="4899f-146">a.</span><span class="sxs-lookup"><span data-stu-id="4899f-146">a.</span></span> <span data-ttu-id="4899f-147">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="4899f-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="4899f-148">b.</span><span class="sxs-lookup"><span data-stu-id="4899f-148">b.</span></span> <span data-ttu-id="4899f-149">**Endast markerade personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="4899f-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="4899f-150">c.</span><span class="sxs-lookup"><span data-stu-id="4899f-150">c.</span></span> <span data-ttu-id="4899f-151">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="4899f-151">**No one**</span></span></br>

    ![Vem kan se ämnen](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="4899f-153">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4899f-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="4899f-154">Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskapshanteringslicenser som tilldelats dem kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="4899f-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="4899f-155">Ändra vem som har behörighet att utföra uppgifter i ämnescentret</span><span class="sxs-lookup"><span data-stu-id="4899f-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="4899f-156">Välj fliken **Ämnesbehörigheter** om du vill uppdatera vem som har behörighet att göra följande på ämnescentrets sida:</span><span class="sxs-lookup"><span data-stu-id="4899f-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="4899f-157">Vilka användare kan skapa och redigera ämnen: Skapa nya ämnen som inte hittades under identifieringen eller redigera befintlig information om ämnessidan.</span><span class="sxs-lookup"><span data-stu-id="4899f-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="4899f-158">Vilka användare kan hantera ämnen: Bekräfta eller avvisa identifierade ämnen.</span><span class="sxs-lookup"><span data-stu-id="4899f-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="4899f-159">Så här uppdaterar du vem som har behörighet att skapa och redigera ämnen:</span><span class="sxs-lookup"><span data-stu-id="4899f-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="4899f-160">Välj **Redigera**under Vem **kan skapa och redigera ämnen**på fliken **Ämnesbehörigheter** .</span><span class="sxs-lookup"><span data-stu-id="4899f-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="4899f-161">På sidan **Vem kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="4899f-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="4899f-162">a.</span><span class="sxs-lookup"><span data-stu-id="4899f-162">a.</span></span> <span data-ttu-id="4899f-163">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="4899f-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="4899f-164">b.</span><span class="sxs-lookup"><span data-stu-id="4899f-164">b.</span></span> <span data-ttu-id="4899f-165">**Endast markerade personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="4899f-165">**Only selected people or security groups**</span></span></br>

    ![Skapa och redigera ämnen](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="4899f-167">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4899f-167">Select **Save**.</span></span></br>

<span data-ttu-id="4899f-168">Så här uppdaterar du vem som har behörighet att hantera ämnen:</span><span class="sxs-lookup"><span data-stu-id="4899f-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="4899f-169">Välj **Redigera**under Vem **kan hantera ämnen**på fliken **Ämnesbehörigheter.**</span><span class="sxs-lookup"><span data-stu-id="4899f-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="4899f-170">På sidan **Vem kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="4899f-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="4899f-171">a.</span><span class="sxs-lookup"><span data-stu-id="4899f-171">a.</span></span> <span data-ttu-id="4899f-172">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="4899f-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="4899f-173">b.</span><span class="sxs-lookup"><span data-stu-id="4899f-173">b.</span></span> <span data-ttu-id="4899f-174">**Utvalda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="4899f-174">**Selected people or security groups**</span></span></br>

    ![Hantera ämnen](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="4899f-176">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4899f-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="4899f-177">Uppdatera namn på ämnescenter</span><span class="sxs-lookup"><span data-stu-id="4899f-177">Update your topic center name</span></span>

<span data-ttu-id="4899f-178">Välj fliken **Ämnescenter** om du vill uppdatera namnet på ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="4899f-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="4899f-179">Välj **Redigera**under **Namnet Ämnescenter**på fliken **Ämnescenter** .</span><span class="sxs-lookup"><span data-stu-id="4899f-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="4899f-180">Skriv det nya namnet för ämnescentret i **namnrutan För ämnescenter** på **namnsidan** Redigera ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="4899f-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="4899f-181">Välj **Spara**</span><span class="sxs-lookup"><span data-stu-id="4899f-181">Select **Save**</span></span>

    ![Redigera namn på ämnescenter](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="4899f-183">Se även</span><span class="sxs-lookup"><span data-stu-id="4899f-183">See also</span></span>



  






