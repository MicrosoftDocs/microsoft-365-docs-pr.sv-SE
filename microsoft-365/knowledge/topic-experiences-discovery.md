---
title: Hantera identifiering av avsnitt i Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig att hantera identifiering av avsnitt i Microsoft 365.
ms.openlocfilehash: 035fb74f1989dc7ef5b7fcf8e9c6d59b63cf2b42
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667896"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a><span data-ttu-id="2c5e6-103">Hantera identifiering av avsnitt i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5e6-103">Manage topic discovery in Microsoft 365</span></span>

<span data-ttu-id="2c5e6-104">Du kan hantera identifierings inställningar för avsnitt i [administrations centret för Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2c5e6-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="2c5e6-105">Du måste vara global administratör eller SharePoint-administratör för att utföra dessa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="2c5e6-106">Så här öppnar du inställningar för hantering av ämnen:</span><span class="sxs-lookup"><span data-stu-id="2c5e6-106">To access topics management settings:</span></span>

1. <span data-ttu-id="2c5e6-107">I administrations centret för Microsoft 365 klickar du på **Inställningar** och sedan på **org Settings**.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="2c5e6-108">Klicka på **kunskaps nätverk** på fliken **tjänster** .</span><span class="sxs-lookup"><span data-stu-id="2c5e6-108">On the **Services** tab, click **Knowledge network**.</span></span>

    ![Koppla personer till kunskap](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="2c5e6-110">Välj fliken **identifiering av ämne** . I följande avsnitt finns information om de olika inställningarna.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![kunskap – nätverks inställningar](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="2c5e6-112">Välj SharePoint-rubriker</span><span class="sxs-lookup"><span data-stu-id="2c5e6-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="2c5e6-113">Du kan ändra de SharePoint-webbplatser i din organisation som ska crawlas för avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="2c5e6-114">Om du vill ta med eller utesluta en viss lista med webbplatser kan du använda följande. csv-mall:</span><span class="sxs-lookup"><span data-stu-id="2c5e6-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="2c5e6-115">Om du lägger till webbplatser med webbplats väljaren läggs de till i den befintliga listan över webbplatser som ska inkluderas eller exkluderas.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="2c5e6-116">Om du laddar upp en CSV-fil skrivs en befintlig lista över.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="2c5e6-117">Om du tidigare har inkluderat eller uteslutit vissa webbplatser kan du hämta listan som en CSV-fil, göra ändringar och ladda upp den nya listan.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="2c5e6-118">Välja webbplatser för identifiering av ämnen</span><span class="sxs-lookup"><span data-stu-id="2c5e6-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="2c5e6-119">På fliken **identifiering** , under **Välj SharePoint-ämnes källor**, väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="2c5e6-120">På sidan **Select SharePoint topic sources** väljer du vilka SharePoint-webbplatser som ska crawlas som källor för dina ämnen under identifiering.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="2c5e6-121">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="2c5e6-121">This includes:</span></span>
    - <span data-ttu-id="2c5e6-122">**Alla webbplatser**: alla SharePoint-webbplatser i din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="2c5e6-123">Här fångar du aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="2c5e6-124">**Alla, förutom markerade webbplatser**: Skriv namnen på de webbplatser du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="2c5e6-125">Du kan också ladda upp en lista med webbplatser som du inte vill ska ingå i sökningen.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="2c5e6-126">Webbplatser som skapats i framtiden kommer att inkluderas som källor för avsnitts identifiering.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="2c5e6-127">**Endast valda webbplatser**: Skriv in namnen på de webbplatser du vill ta med.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="2c5e6-128">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-128">You can also upload a list of sites.</span></span> <span data-ttu-id="2c5e6-129">Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="2c5e6-130">**Inga webbplatser**: ämnen skapas eller uppdateras inte automatiskt med SharePoint-innehåll.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="2c5e6-131">Befintliga avsnitt finns kvar i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-131">Existing topics remain in the topic center.</span></span>

    ![Skärm bild av användar gränssnittet för SharePoint-rubriker](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="2c5e6-133">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="2c5e6-134">Utelämna ämnen efter namn</span><span class="sxs-lookup"><span data-stu-id="2c5e6-134">Exclude topics by name</span></span>

<span data-ttu-id="2c5e6-135">Du kan utesluta ämnen från Upptäck genom att överföra en lista med en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="2c5e6-136">Om du tidigare har uteslutit ämnen kan du ladda ned. csv, göra ändringar och ladda upp den igen.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="2c5e6-137">På fliken **identifiering** , under **utelämna ämnen**, väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="2c5e6-138">Klicka på **utelämna ämnen efter namn**.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="2c5e6-139">Om du behöver skapa en lista kan du Hämta CSV-mallen och lägga till ämnen som du vill undanta (se *arbeta med CSV-mallen* nedan).</span><span class="sxs-lookup"><span data-stu-id="2c5e6-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="2c5e6-140">När filen är klar klickar du på **Bläddra** och laddar upp filen.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="2c5e6-141">Om det finns en befintlig lista kan du Hämta CSV-filen som innehåller listan.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="2c5e6-142">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-142">Click **Save**.</span></span>

    ![Skärm bild av användar gränssnittet undanta ämnen](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="2c5e6-144">Arbeta med CSV-mallen</span><span class="sxs-lookup"><span data-stu-id="2c5e6-144">Working with the .csv template</span></span>

<span data-ttu-id="2c5e6-145">Du kan kopiera CSV-mallen nedan:</span><span class="sxs-lookup"><span data-stu-id="2c5e6-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="2c5e6-146">I CSV-mallen anger du följande information om de avsnitt som du vill undanta:</span><span class="sxs-lookup"><span data-stu-id="2c5e6-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="2c5e6-147">**Namn**: Skriv namnet på det ämne som du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="2c5e6-148">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="2c5e6-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="2c5e6-149">Exakt träff: du kan ange exakt namn eller akronym (till exempel *contoso* eller *ATL*).</span><span class="sxs-lookup"><span data-stu-id="2c5e6-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="2c5e6-150">Ofullständig matchning: du kan exkludera alla ämnen som har ett visst ord i det.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="2c5e6-151">Till exempel kommer *bågen* att exkludera alla ämnen med ord *båge* i det, till exempel *båge cirkel*, *plasma båge svets* eller *tränings båge*. Observera att den inte utesluter ämnen där texten är inkluderad som en del av ett ord, till exempel *arkitekturen*.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="2c5e6-152">**Står för (valfritt)**: om du vill utesluta en akronym skriver du orden som förkortningen står för.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="2c5e6-153">**MatchType-exakt/delvis**: Skriv om det namn du angav är en *exakt* eller *delvis* matchnings typ.</span><span class="sxs-lookup"><span data-stu-id="2c5e6-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Uteslut avsnitt i en CSV-mall](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="2c5e6-155">Se även</span><span class="sxs-lookup"><span data-stu-id="2c5e6-155">See also</span></span>

[<span data-ttu-id="2c5e6-156">Hantera ämnets synlighet i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5e6-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="2c5e6-157">Hantera behörigheter för ämne i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5e6-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="2c5e6-158">Ändra namnet på ämnes centret i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5e6-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

