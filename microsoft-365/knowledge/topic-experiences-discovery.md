---
title: Hantera identifiering av ämnen i Microsoft Viva-ämnen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Lär dig hur du administrerar ämnesidentifiering i Microsoft Viva-ämnen.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107771"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="d2a8f-103">Hantera identifiering av ämnen i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="d2a8f-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="d2a8f-104">Du kan hantera inställningar för identifiering av ämnen i administrationscentret för [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d2a8f-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="d2a8f-105">Du måste vara global administratör eller SharePoint-administratör för att kunna utföra de här uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="d2a8f-106">Så här kommer du åt inställningar för hantering av ämnen:</span><span class="sxs-lookup"><span data-stu-id="d2a8f-106">To access topics management settings:</span></span>

1. <span data-ttu-id="d2a8f-107">Klicka på Inställningar och sedan Organisationsinställningar i **administrationscentret** **för** Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="d2a8f-108">Klicka på **Ämnesupplevelser** på **fliken Tjänster.**</span><span class="sxs-lookup"><span data-stu-id="d2a8f-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Koppla samman personer med kunskap](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="d2a8f-110">Välj fliken **Ämnesidentifiering.** I följande avsnitt finns information om de olika inställningarna.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="d2a8f-112">Välj SharePoint-ämneskällor</span><span class="sxs-lookup"><span data-stu-id="d2a8f-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="d2a8f-113">Du kan ändra vilka SharePoint-webbplatser i organisationen som ska crawlas för ämnen.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="d2a8f-114">Om du vill ta med eller utesluta en viss lista med webbplatser kan du använda följande CSV-mall:</span><span class="sxs-lookup"><span data-stu-id="d2a8f-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="d2a8f-115">Om du lägger till webbplatser med hjälp av webbplatsväljaren läggs de till i den befintliga listan med webbplatser som ska inkluderas eller undantas.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="d2a8f-116">Om du laddar upp en CSV-fil kommer den att skriva över alla befintliga listor.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="d2a8f-117">Om du tidigare har tagit med eller uteslutit specifika webbplatser kan du ladda ned listan som en CSV-fil, göra ändringar och ladda upp den nya listan.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="d2a8f-118">Välja webbplatser för ämnesidentifiering</span><span class="sxs-lookup"><span data-stu-id="d2a8f-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="d2a8f-119">Välj Redigera **under Välj** SharePoint-ämneskällor **på fliken** Ämnesidentifiering. </span><span class="sxs-lookup"><span data-stu-id="d2a8f-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="d2a8f-120">På sidan **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som ska crawlas som källor för ämnen under identifieringen.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="d2a8f-121">Det omfattar:</span><span class="sxs-lookup"><span data-stu-id="d2a8f-121">This includes:</span></span>
    - <span data-ttu-id="d2a8f-122">**Alla webbplatser**: Alla SharePoint-webbplatser i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="d2a8f-123">Detta fångar aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="d2a8f-124">**Alla, förutom valda webbplatser:** Skriv namnen på de webbplatser som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="d2a8f-125">Du kan också ladda upp en lista över webbplatser som du vill avanmäla från identifiering.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="d2a8f-126">Webbplatser som skapas i framtiden kommer att ingå som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="d2a8f-127">**Endast valda webbplatser:** Skriv namnen på de webbplatser som du vill ska ingå.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="d2a8f-128">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-128">You can also upload a list of sites.</span></span> <span data-ttu-id="d2a8f-129">Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="d2a8f-130">**Inga webbplatser:** Ämnen genereras eller uppdateras inte automatiskt med SharePoint-innehåll.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="d2a8f-131">Befintliga ämnen finns kvar i ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-131">Existing topics remain in the topic center.</span></span>

    ![Skärmbild av användargränssnittet för SharePoint-ämneskällor](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="d2a8f-133">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="d2a8f-134">Utesluta ämnen efter namn</span><span class="sxs-lookup"><span data-stu-id="d2a8f-134">Exclude topics by name</span></span>

<span data-ttu-id="d2a8f-135">Du kan utesluta ämnen från identifiering genom att ladda upp en lista med hjälp av en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="d2a8f-136">Om du tidigare har uteslutit ämnen kan du ladda ned CSV-filen, göra ändringar och ladda upp den igen.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="d2a8f-137">Välj Redigera **under Exkludera ämnen** på fliken Ämnesidentifiering. </span><span class="sxs-lookup"><span data-stu-id="d2a8f-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="d2a8f-138">Klicka **på Exkludera ämnen efter namn.**</span><span class="sxs-lookup"><span data-stu-id="d2a8f-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="d2a8f-139">Om du behöver skapa en lista laddar du ned CSV-mallen och lägger till de ämnen du vill utesluta (se Arbeta med *CSV-mallen* nedan).</span><span class="sxs-lookup"><span data-stu-id="d2a8f-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="d2a8f-140">När filen är klar klickar du på **Bläddra** och laddar upp filen.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="d2a8f-141">Om det finns en befintlig lista kan du ladda ned CSV-filen som innehåller listan.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="d2a8f-142">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-142">Click **Save**.</span></span>

    ![Skärmbild av användargränssnittet för uteslutning av ämnen](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="d2a8f-144">Arbeta med CSV-mallen</span><span class="sxs-lookup"><span data-stu-id="d2a8f-144">Working with the .csv template</span></span>

<span data-ttu-id="d2a8f-145">Du kan kopiera CSV-mallen nedan:</span><span class="sxs-lookup"><span data-stu-id="d2a8f-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="d2a8f-146">I CSV-mallen anger du följande information om de ämnen du vill utesluta:</span><span class="sxs-lookup"><span data-stu-id="d2a8f-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="d2a8f-147">**Namn:** Skriv namnet på det ämne som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="d2a8f-148">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="d2a8f-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="d2a8f-149">Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL).*</span><span class="sxs-lookup"><span data-stu-id="d2a8f-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="d2a8f-150">Delvis matchning: Du kan utesluta alla ämnen som innehåller ett visst ord.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="d2a8f-151">En båge *utesluter* till exempel  alla ämnen där ordet båge finns, t.ex. arcuscirkel, arcus-arcus- eller *utbildningsbåge.*  Observera att den inte exkluderar ämnen där texten ingår som en del av ett ord, till exempel *arkitektur.*</span><span class="sxs-lookup"><span data-stu-id="d2a8f-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="d2a8f-152">**Står för (valfritt)**: Om du vill utesluta en förkortning skriver du orden som förkortningen står för.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="d2a8f-153">**MatchType-Exact/Partial:** Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.</span><span class="sxs-lookup"><span data-stu-id="d2a8f-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Utesluta ämnen i CSV-mall](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="d2a8f-155">Se även</span><span class="sxs-lookup"><span data-stu-id="d2a8f-155">See also</span></span>

[<span data-ttu-id="d2a8f-156">Hantera synlighet för ämnen i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d2a8f-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="d2a8f-157">Hantera ämnesbehörigheter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d2a8f-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="d2a8f-158">Ändra namnet på ämnescentret i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d2a8f-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
