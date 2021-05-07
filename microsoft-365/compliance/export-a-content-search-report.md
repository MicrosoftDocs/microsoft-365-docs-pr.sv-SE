---
title: Exportera en rapport för innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: I stället för att exportera de faktiska resultaten av en innehållssökning i säkerhets- & kompatibilitetscentret i Office 365 kan du exportera en sökresultatrapport. Rapporten innehåller en sammanfattning av sökresultaten och ett dokument med detaljerad information om varje objekt som ska exporteras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "52162659"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="1eb2a-104">Exportera en rapport för innehållssökning</span><span class="sxs-lookup"><span data-stu-id="1eb2a-104">Export a Content Search report</span></span>

<span data-ttu-id="1eb2a-105">I stället för att exportera hela uppsättningen sökresultat från en innehållssökning i efterlevnadscentret för säkerhet i & (och från en innehållssökning som är kopplad till ett eDiscovery-ärende) kan du exportera samma rapporter som genereras när du exporterar sökresultat.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="1eb2a-106">När du exporterar en rapport laddas den ned till en mapp med samma namn som Innehållssökning, men som läggs till i *_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="1eb2a-107">Om innehållssökningen till exempel heter  *ContosoCase0815* laddas rapporten ned till en mapp med namnet *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="1eb2a-108">En lista över dokument som ingår i rapporten finns i [Vad ingår i rapporten.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="1eb2a-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="1eb2a-109">Tilldela roller och kontrollera systemkrav</span><span class="sxs-lookup"><span data-stu-id="1eb2a-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="1eb2a-110">Om du vill exportera en rapport för innehållssökning måste du ha tilldelats rollen Efterlevnadssökning i säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="1eb2a-111">Den här rollen tilldelas som standard till de inbyggda rollgrupperna eDiscovery Manager och Organisationshantering.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="1eb2a-112">Mer information finns i Tilldela [eDiscovery-behörigheter.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="1eb2a-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="1eb2a-113">När du exporterar en rapport lagras data tillfälligt i ett unikt Azure Storage i Microsoft-molnet innan de laddas ned till din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="1eb2a-114">Se till att din organisation kan ansluta till slutpunkten i Azure, som är **\* .blob.core.windows.net** (jokertecknet representerar en unik identifierare för exporten).</span><span class="sxs-lookup"><span data-stu-id="1eb2a-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="1eb2a-115">Sökresultatdata tas bort från området Azure Storage två veckor efter att den har skapats.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span>

- <span data-ttu-id="1eb2a-116">Datorn du använder för att exportera sökresultaten måste uppfylla följande systemkrav:</span><span class="sxs-lookup"><span data-stu-id="1eb2a-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="1eb2a-117">Senaste versionen av Windows (32-bitars eller 64-bitars)</span><span class="sxs-lookup"><span data-stu-id="1eb2a-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="1eb2a-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="1eb2a-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="1eb2a-119">Du måste använda någon av följande webbläsare som stöds för att köra eDiscovery Export Tool<sup>1:</sup></span><span class="sxs-lookup"><span data-stu-id="1eb2a-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="1eb2a-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1eb2a-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="1eb2a-121">ELLER</span><span class="sxs-lookup"><span data-stu-id="1eb2a-121">OR</span></span>

  - <span data-ttu-id="1eb2a-122">Microsoft Internet Explorer 10 och senare versioner</span><span class="sxs-lookup"><span data-stu-id="1eb2a-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="1eb2a-123"><sup>1</sup> Microsoft tillverkar inte tillägg eller tillägg från tredje part för ClickOnce tilläggsprogram.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="1eb2a-124">Export av sökresultat med en webbläsare som inte stöds med tillägg eller tillägg från tredje part stöds inte.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="1eb2a-125"><sup>2</sup> På grund av de senaste ändringarna Microsoft Edge är ClickOnce inte längre aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="1eb2a-126">Anvisningar om hur du aktiverar ClickOnce i Edge finns i [Använda verktyget för eDiscovery-export i Microsoft Edge.](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="1eb2a-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="1eb2a-127">Om den uppskattade totala storleken på resultatet som returneras av en innehållssökning överskrider 2 TB misslyckas exporten av rapporten.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="1eb2a-128">Om du vill exportera rapporten försöker du begränsa omfattningen och köra sökningen igen så att den uppskattade storleken på resultatet är mindre än 2 TB.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="1eb2a-129">När du exporterar innehållsökningsrapporter räknas antalet exporter som körs samtidigt och det maximala antalet exporter som en enskild användare kan köra.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="1eb2a-130">Mer information om exportgränser finns i [Exportera resultat för innehållssökning.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="1eb2a-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="1eb2a-131">Generera och ladda ned en rapport för innehållssökning</span><span class="sxs-lookup"><span data-stu-id="1eb2a-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="1eb2a-132">Stegen för att skapa och ladda ned en rapport för innehållssökning liknar att faktiskt exportera sökresultat.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="1eb2a-133">Steg 1: Generera rapporten för export</span><span class="sxs-lookup"><span data-stu-id="1eb2a-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="1eb2a-134">Det första steget är att förbereda rapporten för nedladdning till datorn som exporteras.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="1eb2a-135">När du rapporten överförs rapportdokumenten till ett Azure Storage i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="1eb2a-136">Gå till [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="1eb2a-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="1eb2a-137">Logga in med ditt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="1eb2a-138">I den vänstra rutan i säkerhets- & Säkerhets- och efterlevnadscenter klickar du **på Sök** \> **efter innehållsökning**.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="1eb2a-139">Välj **en sökning på** sidan Innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="1eb2a-140">Klicka på Generera rapport under **Exportera rapport till en dator** i **informationsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="1eb2a-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1eb2a-141">Om resultatet för en sökning är äldre än 7 dagar uppmanas du att uppdatera sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="1eb2a-142">Om det händer avbryter du  exporten, klickar på Uppdatera sökresultat i informationsfönstret för den valda sökningen och startar rapportexporten igen när resultatet har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="1eb2a-143">Välj **något av följande** alternativ under **Inkludera följande objekt från sökningen** på sidan Exportera en rapport:</span><span class="sxs-lookup"><span data-stu-id="1eb2a-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="1eb2a-144">Exportera endast indexerade objekt</span><span class="sxs-lookup"><span data-stu-id="1eb2a-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="1eb2a-145">Exportera indexerade och icke indexerade objekt</span><span class="sxs-lookup"><span data-stu-id="1eb2a-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="1eb2a-146">Exportera endast icke indexerade objekt</span><span class="sxs-lookup"><span data-stu-id="1eb2a-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="1eb2a-147">Mer information om icke indexerade objekt finns i [Delvis indexerade objekt i Innehållssökning](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="1eb2a-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="1eb2a-148">Välj att ta med sökstatistik för alla versioner SharePoint dokument.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="1eb2a-149">Det här alternativet visas bara om innehållskällorna för sökningen omfattar SharePoint eller OneDrive för företag webbplatser.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="1eb2a-150">Klicka **på Generera rapport**.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="1eb2a-151">Sökresultatrapporten förbereds för nedladdning, vilket innebär att rapportdokumenten laddas upp till Azure Storage i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="1eb2a-152">När rapporten är klar för nedladdning visas **länken Ladda** ned rapport under Exportera rapport till **en dator** i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1eb2a-153">Du kan också exportera en rapport för en innehållssökning som är kopplad till ett e-dataidentifieringsfall.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="1eb2a-154">Det gör du genom att gå **till eDiscovery** \> **eDiscovery**, markera ett ärende och klicka på **Redigera** ![ redigera-ikonen ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="1eb2a-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="1eb2a-155">På sidan **Sökningar** väljer du en sökning och klickar sedan på **exportera** ![ sökresultatikonen ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Exportera en rapport.**</span><span class="sxs-lookup"><span data-stu-id="1eb2a-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="1eb2a-156">Steg 2: Ladda ned rapporten</span><span class="sxs-lookup"><span data-stu-id="1eb2a-156">Step 2: Download the report</span></span>

<span data-ttu-id="1eb2a-157">Nästa steg är att ladda ned rapporten från Azure Storage området till din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="1eb2a-158">Klicka på Ladda ned rapport under Exportera rapport till en dator **i** informationsfönstret för sökningen som du genererade **rapporten för.**</span><span class="sxs-lookup"><span data-stu-id="1eb2a-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="1eb2a-159">Sidan **Ladda** ned rapport visas och innehåller följande information om den rapport som laddas ned till datorn.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="1eb2a-160">Antalet objekt som kommer att laddas ned.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="1eb2a-161">Den uppskattade totala storleken på de objekt som kommer att laddas ned.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="1eb2a-162">Om indexerade eller icke indexerade produkter exporteras.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="1eb2a-163">Icke indexerade objekt är objekt som har ett känt format, är krypterade eller inte indexeras av andra orsaker.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="1eb2a-164">Om versioner SharePoint dokument hämtas.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="1eb2a-165">Status för rapportexportprocessen.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-165">The status of the report export process.</span></span> <span data-ttu-id="1eb2a-166">Du kan börja ladda ned rapporten även om förberedelsen av rapporten inte är slutförd.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="1eb2a-167">Klicka på Kopiera till **Urklipp under Exportnyckel.** </span><span class="sxs-lookup"><span data-stu-id="1eb2a-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="1eb2a-168">Du använder den här nyckeln i steg 5 för att ladda ned rapporten.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1eb2a-169">Eftersom vem som helst kan installera och starta verktyget för eDiscovery-export och sedan använda den här nyckeln för att ladda ned sökrapporten, bör du vidta vissa försiktighetsåtgärder för att skydda den här nyckeln på samma sätt som du skyddar lösenord eller annan säkerhetsrelaterad information.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="1eb2a-170">Klicka **på Ladda ned rapport.**</span><span class="sxs-lookup"><span data-stu-id="1eb2a-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="1eb2a-171">Om du uppmanas att installera **eDiscovery-exportverktyget klickar** du på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="1eb2a-172">I **eDiscovery-exportverktyget** klistrar du in exportnyckeln som du kopierade i steg 2 i lämplig ruta.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="1eb2a-173">Klicka **på** Bläddra för att ange den plats där du vill ladda ned rapporten.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="1eb2a-174">Klicka **på Start** för att ladda ned sökresultatet till datorn.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="1eb2a-175">I **verktyget eDiscovery Export** visas statusinformation om exporten, inklusive en uppskattning av antalet (och storleken) av de återstående objekten som ska laddas ned.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="1eb2a-176">När exporten är klar kan du komma åt filerna på den plats där de laddades ned.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1eb2a-177">Du kan ladda ned rapporten för en innehållssökning som är kopplad till ett e-dataidentifieringsfall.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="1eb2a-178">Det gör du genom att gå **till eDiscovery** \> **eDiscovery**, markera ett ärende och klicka på **Redigera** ![ redigera-ikonen ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="1eb2a-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="1eb2a-179">På sidan **Exporter** väljer du en rapportexport och klickar sedan **på Ladda ned** rapport i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="1eb2a-180">Vad som ingår i rapporten</span><span class="sxs-lookup"><span data-stu-id="1eb2a-180">What's included in the report</span></span>

<span data-ttu-id="1eb2a-181">När du skapar och exporterar en rapport om resultatet av en innehållssökning laddas följande dokument ned:</span><span class="sxs-lookup"><span data-stu-id="1eb2a-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="1eb2a-182">**Sammanfattning av export:** Ett Excel som innehåller en sammanfattning av exporten.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="1eb2a-183">Det omfattar information som antal innehållskällor som har sökts, antalet sökresultat från varje innehållsplats, det uppskattade antalet objekt, det faktiska antalet objekt som skulle exporteras och den uppskattade och faktiska storleken på de objekt som skulle exporteras.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1eb2a-184">Om du tar med icke indexerade objekt när du exporterar rapporten inkluderas antalet icke indexerade objekt i det totala antalet uppskattade sökresultat och det totala antalet nedladdade sökresultat (om du skulle exportera sökresultaten) som visas i rapporten Exportsammanfattning.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="1eb2a-185">Med andra ord är det totala antalet objekt som hämtas lika med det totala antalet uppskattade resultat och det totala antalet icke indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="1eb2a-186">**Manifest:** En manifestfil (i XML-format) som innehåller information om varje objekt som ingår i sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="1eb2a-187">**Resultat:** Ett Excel som innehåller en rad med information om varje indexerat objekt som skulle exporteras med sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="1eb2a-188">För e-post innehåller resultatloggen information om varje meddelande, inklusive:</span><span class="sxs-lookup"><span data-stu-id="1eb2a-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="1eb2a-189">Platsen för meddelandet i källpostlådan (inklusive om meddelandet finns i den primära postlådan eller arkivpostlådan).</span><span class="sxs-lookup"><span data-stu-id="1eb2a-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="1eb2a-190">Datumet då meddelandet skickades eller togs emot.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="1eb2a-191">Ämnesraden från meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="1eb2a-192">Meddelandets avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="1eb2a-193">För dokument från SharePoint och OneDrive för företag innehåller resultatloggen information om varje dokument, inklusive:</span><span class="sxs-lookup"><span data-stu-id="1eb2a-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="1eb2a-194">URL-adressen för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="1eb2a-195">URL-adressen för webbplatssamlingen där dokumentet finns.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="1eb2a-196">Datumet då dokumentet senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="1eb2a-197">Namnet på dokumentet (som finns i kolumnen Ämne i resultatloggen).</span><span class="sxs-lookup"><span data-stu-id="1eb2a-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1eb2a-198">Antalet rader i  resultatrapporten ska vara lika med det totala antalet sökresultat minus det totala antalet objekt som visas i rapporten Icke **indexerade** objekt.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="1eb2a-199">**Icke indexerade objekt:** Ett Excel dokument som innehåller information om icke indexerade objekt som ingår i sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="1eb2a-200">Om du inte tar med icke indexerade objekt när du skapar sökresultatrapporten kommer den här rapporten fortfarande att laddas ned, men den är tom.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
