---
title: Lägga till icke-förfallna datakällor i ett Advanced eDiscovery fall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Du kan lägga till icke-tilläggsdatakällor till ett Advanced eDiscovery fall och placera ett hold i datakällan. Icke-försvöjda datakällor indexeras om, så allt innehåll som markerats som delvis indexerats om för att göra det helt och snabbt sökbart.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/31/2020
ms.locfileid: "52161709"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="0f3dd-104">Lägga till icke-förfallna datakällor i ett Advanced eDiscovery fall</span><span class="sxs-lookup"><span data-stu-id="0f3dd-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="0f3dd-105">I Advanced eDiscovery fall uppfyller den inte alltid dina behov att associera en Microsoft 365 datakälla med en vårdnadshavare i ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="0f3dd-106">Men du kanske fortfarande behöver koppla dessa data till ett ärende så att du kan söka i dem, lägga till dem i en granskningsuppsättning och analysera och granska dem.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="0f3dd-107">Funktionen i Advanced eDiscovery kallas *icke-förseningsdatakällor* och gör att du kan lägga till data i ett ärende utan att behöva koppla dem till en vårdnadshavare.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="0f3dd-108">Det gäller även samma Advanced eDiscovery för icke-sammanhängande data som är tillgängliga för data som är associerade med vårdnadshavare.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="0f3dd-109">Två av de mest användbara sakerna som du kan använda för icke-uppslagna data är att placera dem i förvaring och bearbeta dem med hjälp av [Avancerad indexering.](indexing-custodian-data.md)</span><span class="sxs-lookup"><span data-stu-id="0f3dd-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="0f3dd-110">Lägga till en datakälla som inte är i följd</span><span class="sxs-lookup"><span data-stu-id="0f3dd-110">Add a non-custodial data source</span></span>

<span data-ttu-id="0f3dd-111">Följ dessa steg för att lägga till och hantera icke-förfallna datakällor i Advanced eDiscovery fall.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="0f3dd-112">På **Advanced eDiscovery** klickar du på det ärende du vill lägga till data i.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="0f3dd-113">Klicka på **fliken Datakällor** och sedan på **Lägg till**  >  **datakälla Lägg till dataplatser.**</span><span class="sxs-lookup"><span data-stu-id="0f3dd-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="0f3dd-114">På den **utfällliga sidan Nya icke-tilläggsdataplatser** väljer du de datakällor som du vill lägga till för ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="0f3dd-115">Du kan lägga till flera postlådor och webbplatser genom att expandera **avsnitten SharePoint** eller **Exchange** och sedan klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Lägga SharePoint webbplatser och Exchange postlådor som icke-uppslagna datakällor](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="0f3dd-117">**SharePoint – klicka** på Redigera **för att** lägga till webbplatser.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="0f3dd-118">Välj en webbplats i listan eller så kan du söka efter en webbplats genom att skriva webbplatsadressen i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="0f3dd-119">Välj de webbplatser som du vill lägga till som icke-objektande datakällor och klicka på Lägg **till.**</span><span class="sxs-lookup"><span data-stu-id="0f3dd-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="0f3dd-120">**Exchange – klicka** på Redigera **för att** lägga till postlådor.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="0f3dd-121">Skriv ett namn eller alias (minst tre tecken) i sökrutan för postlådor eller distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="0f3dd-122">Markera de postlådor som du vill lägga till som icke-lika datakällor och klicka på Lägg **till.**</span><span class="sxs-lookup"><span data-stu-id="0f3dd-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0f3dd-123">Du kan använda **avsnitten SharePoint** och **Exchange** för att lägga till webbplatser och postlådor som är kopplade till en Grupp- eller Yammer-grupp som icke-sammanhängande datakällor.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="0f3dd-124">Du måste separat lägga till postlådan och webbplatsen som är kopplade till en grupp eller Yammer grupp.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="0f3dd-125">När du lägger till icke-tilläggsdatakällor kan du välja att placera dessa platser som förvaring eller inte.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="0f3dd-126">Markera eller avmarkera **kryssrutan Håll** ned bredvid datakällan om du vill markera den som väntande.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="0f3dd-127">Klicka **på** Lägg till längst ned på den utfällliga sidan Nya **icke-förfallna dataplatser** för att lägga till datakällor för ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="0f3dd-128">Varje icke-ljudande datakälla som du har lagt till visas på **sidan Datakällor.**</span><span class="sxs-lookup"><span data-stu-id="0f3dd-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="0f3dd-129">Icke-ljudande datakällor identifieras med **värdet för Dataplats** i **kolumnen Källtyp.**</span><span class="sxs-lookup"><span data-stu-id="0f3dd-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Icke-uppsövade datakällor på fliken Datakällor](../media/NonCustodialDataSources2.png)

<span data-ttu-id="0f3dd-131">När du lägger till icke-namngivna datakällor i ärendet skapas ett jobb med namnet  Indexera om *icke-förfallna data* och visas på fliken Jobb för ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="0f3dd-132">När jobbet har skapats indexeras indexeringsprocessen Avancerat i och datakällorna indexeras om.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="0f3dd-133">Hantera förvaring för datakällor som inte kan innehålla data som inte kan administreras</span><span class="sxs-lookup"><span data-stu-id="0f3dd-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="0f3dd-134">När du placerar ett ärende i en datakälla som inte är försend med ett dokument skapas automatiskt en princip för förvaring som innehåller de icke-dokumentade datakällorna för ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="0f3dd-135">När du placerar andra icke-uppsagd datakällor i förvaring läggs de till i den här principen för förvaring.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="0f3dd-136">Öppna Advanced eDiscovery och välj **fliken** Håll ned.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="0f3dd-137">Klicka **på NCDSHold- \<GUID\>**, där GUID-värdet är unikt för ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="0f3dd-138">På den utfällande sidan visas information och statistik om icke-direktförseliga datakällor som är i förvaring.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![På den utfällande sidan för icke-förfallna datakällor visas statistik](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="0f3dd-140">Klicka **på Redigera** förvaring för att visa de icke-dokumentade datakällor som har satts på is och utföra följande hanteringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="0f3dd-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="0f3dd-141">På sidan **Platser kan** du släppa en icke-ljudande datakälla genom att ta bort den från förvaringen.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="0f3dd-142">När en datakälla släpps tas inte den icke-förfallna datakällan bort från det aktuella ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="0f3dd-143">Det här tar bara bort det kvart som lades till i datakällan.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="0f3dd-144">På sidan **Fråga** kan du redigera förvaringen om du vill skapa ett frågebaserat förvarings nekat ärende som tillämpas på alla icke-förfallna datakällor.</span><span class="sxs-lookup"><span data-stu-id="0f3dd-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
