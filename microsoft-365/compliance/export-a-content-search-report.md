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
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311579"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="3c874-104">Exportera en innehållssökningsrapport</span><span class="sxs-lookup"><span data-stu-id="3c874-104">Export a Content search report</span></span>

<span data-ttu-id="3c874-105">I stället för att exportera hela uppsättningen sökresultat från en innehållssökning i efterlevnadscentret för Microsoft 365 (eller från en sökning som är kopplad till ett Bas-eDiscovery-ärende) kan du exportera samma rapporter som skapas när du exporterar de faktiska sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="3c874-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="3c874-106">När du exporterar en rapport laddas rapportfilerna ned till en mapp på den lokala datorn som har samma namn som Innehållssökning, men som läggs till i *_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="3c874-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="3c874-107">Om innehållssökningen till exempel heter  *ContosoCase0815* laddas rapporten ned till en mapp med namnet *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="3c874-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="3c874-108">En lista över dokument som ingår i rapporten finns i [Vad ingår i rapporten.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="3c874-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="3c874-109">Innan du exporterar en sökrapport</span><span class="sxs-lookup"><span data-stu-id="3c874-109">Before you export a search report</span></span>

- <span data-ttu-id="3c874-110">Om du vill exportera en sökrapport måste du ha rollen Efterlevnadssökning i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="3c874-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="3c874-111">Den här rollen tilldelas som standard till de inbyggda rollgrupperna eDiscovery Manager och Organisationshantering.</span><span class="sxs-lookup"><span data-stu-id="3c874-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="3c874-112">Mer information finns i [Tilldela eDiscovery-behörigheter](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3c874-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="3c874-113">När du exporterar en rapport lagras data tillfälligt på en Azure Storage plats i Microsoft Cloud innan de laddas ned till din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="3c874-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="3c874-114">Se till att din organisation kan ansluta till slutpunkten i Azure, som är **\* .blob.core.windows.net** (jokertecknet representerar en unik identifierare för exporten).</span><span class="sxs-lookup"><span data-stu-id="3c874-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="3c874-115">Sökresultatdata tas bort från e-Azure Storage två veckor efter att den har skapats.</span><span class="sxs-lookup"><span data-stu-id="3c874-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="3c874-116">Datorn du använder för att exportera sökresultaten måste uppfylla följande systemkrav:</span><span class="sxs-lookup"><span data-stu-id="3c874-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="3c874-117">Senaste versionen av Windows (32-bitars eller 64-bitars)</span><span class="sxs-lookup"><span data-stu-id="3c874-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="3c874-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="3c874-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="3c874-119">Du måste använda någon av följande webbläsare som stöds för att köra eDiscovery Export Tool<sup>1:</sup></span><span class="sxs-lookup"><span data-stu-id="3c874-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="3c874-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c874-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="3c874-121">ELLER</span><span class="sxs-lookup"><span data-stu-id="3c874-121">OR</span></span>

  - <span data-ttu-id="3c874-122">Microsoft Internet Explorer 10 och senare versioner</span><span class="sxs-lookup"><span data-stu-id="3c874-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="3c874-123"><sup>1</sup> Microsoft tillverkar inte tillägg eller tillägg från tredje part för ClickOnce tilläggsprogram.</span><span class="sxs-lookup"><span data-stu-id="3c874-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="3c874-124">Export av sökresultat med en webbläsare som inte stöds med tillägg eller tillägg från tredje part stöds inte.</span><span class="sxs-lookup"><span data-stu-id="3c874-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="3c874-125"><sup>2</sup> På grund av de senaste ändringarna Microsoft Edge är ClickOnce inte längre aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="3c874-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="3c874-126">Anvisningar om hur du aktiverar ClickOnce i Edge finns i [Använda verktyget för eDiscovery-export i Microsoft Edge.](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="3c874-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="3c874-127">Om den uppskattade totala storleken på resultatet som returneras av sökningen överskrider 2 TB misslyckas exporten av rapporterna.</span><span class="sxs-lookup"><span data-stu-id="3c874-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="3c874-128">Om du vill exportera rapporterna försöker du begränsa omfattningen och köra sökningen igen så att den uppskattade storleken på resultatet är mindre än 2 TB.</span><span class="sxs-lookup"><span data-stu-id="3c874-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="3c874-129">Om resultatet av en sökning är äldre än 7 dagar och du skickar ett exportrapportjobb visas ett felmeddelande som uppmanar dig att köra sökningen igen för att uppdatera sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="3c874-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="3c874-130">I så fall avbryter du exporten, kör sökningen igen och startar exporten igen.</span><span class="sxs-lookup"><span data-stu-id="3c874-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="3c874-131">Vid export av sökrapporter räknas antalet exporter som körs samtidigt och det maximala antalet exporter som en enskild användare kan köra.</span><span class="sxs-lookup"><span data-stu-id="3c874-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="3c874-132">Mer information om exportgränser finns i [Exportera sökresultat för innehåll.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="3c874-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="3c874-133">Steg 1: Generera rapporten för export</span><span class="sxs-lookup"><span data-stu-id="3c874-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="3c874-134">Det första steget är att förbereda rapporten för nedladdning till datorn som exporteras.</span><span class="sxs-lookup"><span data-stu-id="3c874-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="3c874-135">När du exporterar rapporten laddas rapportdokumenten upp till ett Azure Storage område i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="3c874-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="3c874-136">Välj Microsoft 365 innehållssökning som du vill exportera rapporten från i kompatibilitetscentret.</span><span class="sxs-lookup"><span data-stu-id="3c874-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="3c874-137">På menyn **Åtgärder** längst ned på sökmenyn klickar du på **Exportera rapport.**</span><span class="sxs-lookup"><span data-stu-id="3c874-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![Alternativet Exportera rapport på menyn Åtgärder](../media/ActionMenuExportReport.png)

   <span data-ttu-id="3c874-139">Den **utfällna** sidan Exportera rapport visas.</span><span class="sxs-lookup"><span data-stu-id="3c874-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="3c874-140">Vilka alternativ som finns för att exportera information om sökningen beror på om sökresultaten finns i postlådor eller på webbplatserna eller en kombination av båda.</span><span class="sxs-lookup"><span data-stu-id="3c874-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="3c874-141">Välj **något av** följande alternativ under Utdataalternativ:</span><span class="sxs-lookup"><span data-stu-id="3c874-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![Exportera utdataalternativ](../media/ExportOutputOptions.png)

    - <span data-ttu-id="3c874-143">Alla objekt, förutom sådana som har **okänt format,** krypteras eller inte indexeras av andra orsaker.</span><span class="sxs-lookup"><span data-stu-id="3c874-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="3c874-144">Det här alternativet exporterar bara information om indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="3c874-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="3c874-145">**Alla objekt, även sådana som har okänt format,** krypteras eller indexeras inte av andra orsaker.</span><span class="sxs-lookup"><span data-stu-id="3c874-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="3c874-146">Med det här alternativet exporteras information om indexerade och icke indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="3c874-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="3c874-147">**Endast objekt som har ett okänt format, är krypterade eller inte indexeras av andra orsaker.**</span><span class="sxs-lookup"><span data-stu-id="3c874-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="3c874-148">Med det här alternativet exporteras bara information om icke indexerade element.</span><span class="sxs-lookup"><span data-stu-id="3c874-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="3c874-149">Konfigurera **alternativet Aktivera avduplicering för Exchange innehåll.**</span><span class="sxs-lookup"><span data-stu-id="3c874-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="3c874-150">Om du väljer det här alternativet inkluderas antalet dubblettmeddelanden (före avduplicering och efter avduplicering) i sammanfattningsrapporten för export.</span><span class="sxs-lookup"><span data-stu-id="3c874-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="3c874-151">Dessutom inkluderas bara en kopia av ett meddelande i manifest.xml filen.</span><span class="sxs-lookup"><span data-stu-id="3c874-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="3c874-152">Men rapporten med exportresultat innehåller en rad för varje kopia av ett duplicerat meddelande så att du kan identifiera postlådorna som innehåller en kopia av det duplicerade meddelandet.</span><span class="sxs-lookup"><span data-stu-id="3c874-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="3c874-153">Mer information om de exporterade rapporterna finns i [Vad ingår i rapporten](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="3c874-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="3c874-154">Om du inte markerar det här alternativet innehåller exporten rapporter information om alla meddelanden som returneras av sökningen, inklusive dubbletter.</span><span class="sxs-lookup"><span data-stu-id="3c874-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="3c874-155">Mer information om avduplicering och hur dubbletter identifieras finns i [Avduplicering i eDiscovery-sökresultat.](de-duplication-in-ediscovery-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="3c874-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="3c874-156">Klicka **på Generera rapport**.</span><span class="sxs-lookup"><span data-stu-id="3c874-156">Click **Generate report**.</span></span>

   <span data-ttu-id="3c874-157">Sökrapporterna förbereds för nedladdning, vilket innebär att rapportdokumenten laddas upp till en Azure Storage plats i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="3c874-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="3c874-158">Det kan ta flera minuter.</span><span class="sxs-lookup"><span data-stu-id="3c874-158">This may take several minutes.</span></span>

<span data-ttu-id="3c874-159">Instruktioner för hur du laddar ned de exporterade sökrapporterna finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3c874-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="3c874-160">Steg 2: Ladda ned rapporten</span><span class="sxs-lookup"><span data-stu-id="3c874-160">Step 2: Download the report</span></span>

<span data-ttu-id="3c874-161">Nästa steg är att ladda ned rapporten från Azure Storage området till din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="3c874-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="3c874-162">På sidan **Innehållssökning** i kompatibilitetscentret för Microsoft 365 väljer du **fliken Exporter**</span><span class="sxs-lookup"><span data-stu-id="3c874-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="3c874-163">Du kanske måste klicka på **Uppdatera** för att uppdatera listan med exportjobb så att den visar det exportjobb du har skapat.</span><span class="sxs-lookup"><span data-stu-id="3c874-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="3c874-164">Exportera rapportjobb har samma namn som motsvarande sökning **_ReportsOnly** lagts till i söknamnet.</span><span class="sxs-lookup"><span data-stu-id="3c874-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="3c874-165">Välj det exportjobb som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="3c874-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="3c874-166">Klicka på **Kopiera till** Urklipp under **Exportera-tangenten** på den **utfällade sidan Exportera rapport.**</span><span class="sxs-lookup"><span data-stu-id="3c874-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="3c874-167">Du använder den här nyckeln i steg 6 för att ladda ned sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="3c874-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="3c874-168">Eftersom vem som helst kan installera och starta verktyget för eDiscovery-export och sedan använda den här nyckeln för att ladda ned sökrapporten, bör du vidta vissa försiktighetsåtgärder för att skydda den här nyckeln på samma sätt som du skyddar lösenord eller annan säkerhetsrelaterad information.</span><span class="sxs-lookup"><span data-stu-id="3c874-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="3c874-169">Klicka på Ladda ned resultat längst upp på den **utfällsbara sidan.**</span><span class="sxs-lookup"><span data-stu-id="3c874-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="3c874-170">Om du uppmanas att installera **eDiscovery-exportverktyget klickar** du på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="3c874-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="3c874-171">I **eDiscovery-exportverktyget** gör du följande:</span><span class="sxs-lookup"><span data-stu-id="3c874-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![eDiscovery-exportverktyget](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="3c874-173">Klistra in exportnyckeln som du kopierade i steg 3 i lämplig ruta.</span><span class="sxs-lookup"><span data-stu-id="3c874-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="3c874-174">Klicka **på** Bläddra för att ange den plats där du vill ladda ned sökrapportfilerna.</span><span class="sxs-lookup"><span data-stu-id="3c874-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="3c874-175">Klicka **på Start** för att ladda ned sökresultatet till datorn.</span><span class="sxs-lookup"><span data-stu-id="3c874-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="3c874-176">I **verktyget eDiscovery Export** visas statusinformation om exporten, inklusive en uppskattning av antalet (och storleken) av de återstående objekten som ska laddas ned.</span><span class="sxs-lookup"><span data-stu-id="3c874-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="3c874-177">När exporten är klar kan du komma åt filerna på den plats där de laddades ned.</span><span class="sxs-lookup"><span data-stu-id="3c874-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="3c874-178">Vad som ingår i rapporten</span><span class="sxs-lookup"><span data-stu-id="3c874-178">What's included in the report</span></span>

<span data-ttu-id="3c874-179">När du skapar och exporterar en rapport om resultatet av en innehållssökning laddas följande dokument ned:</span><span class="sxs-lookup"><span data-stu-id="3c874-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="3c874-180">**Exportsammanfattning:** Ett Excel som innehåller en sammanfattning av exporten.</span><span class="sxs-lookup"><span data-stu-id="3c874-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="3c874-181">Det omfattar information som antal innehållskällor som har sökts, antalet sökresultat från varje innehållsplats, det uppskattade antalet objekt, det faktiska antalet objekt som skulle exporteras och den uppskattade och faktiska storleken på de objekt som skulle exporteras.</span><span class="sxs-lookup"><span data-stu-id="3c874-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="3c874-182">Om du tar med icke indexerade objekt när du exporterar rapporten inkluderas antalet icke indexerade objekt i det totala antalet uppskattade sökresultat och det totala antalet nedladdade sökresultat (om du skulle exportera sökresultaten) som visas i sammanfattningsrapporten för export.</span><span class="sxs-lookup"><span data-stu-id="3c874-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="3c874-183">Med andra ord är det totala antalet objekt som hämtas lika med det totala antalet uppskattade resultat och det totala antalet icke indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="3c874-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="3c874-184">**Manifest:** En manifestfil (i XML-format) som innehåller information om varje objekt som ingår i sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="3c874-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="3c874-185">Om du har aktiverat alternativet för avduplicering inkluderas inte dubblettmeddelanden i manifestfilen.</span><span class="sxs-lookup"><span data-stu-id="3c874-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="3c874-186">**Resultat:** Ett Excel som innehåller en rad med information om varje indexerat objekt som skulle exporteras med sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="3c874-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="3c874-187">För e-post innehåller resultatloggen information om varje meddelande, inklusive:</span><span class="sxs-lookup"><span data-stu-id="3c874-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="3c874-188">Platsen för meddelandet i källpostlådan (inklusive om meddelandet finns i den primära postlådan eller arkivpostlådan).</span><span class="sxs-lookup"><span data-stu-id="3c874-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="3c874-189">Datumet då meddelandet skickades eller togs emot.</span><span class="sxs-lookup"><span data-stu-id="3c874-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="3c874-190">Ämnesraden från meddelandet.</span><span class="sxs-lookup"><span data-stu-id="3c874-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="3c874-191">Meddelandets avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="3c874-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="3c874-192">För dokument från SharePoint och OneDrive för företag innehåller resultatloggen information om varje dokument, inklusive:</span><span class="sxs-lookup"><span data-stu-id="3c874-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="3c874-193">URL-adressen för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="3c874-193">The URL for the document.</span></span>

  - <span data-ttu-id="3c874-194">URL-adressen för webbplatssamlingen där dokumentet finns.</span><span class="sxs-lookup"><span data-stu-id="3c874-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="3c874-195">Datumet då dokumentet senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="3c874-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="3c874-196">Namnet på dokumentet (som finns i kolumnen Ämne i resultatloggen).</span><span class="sxs-lookup"><span data-stu-id="3c874-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="3c874-197">Antalet rader i  resultatrapporten ska vara lika med det totala antalet sökresultat minus det totala antalet objekt som visas i rapporten Icke **indexerade** objekt.</span><span class="sxs-lookup"><span data-stu-id="3c874-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="3c874-198">**Trace.log:** En spårningslogg som innehåller detaljerad loggningsinformation om exporten och som kan hjälpa dig att upptäcka problem under exporten.</span><span class="sxs-lookup"><span data-stu-id="3c874-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="3c874-199">Om du öppnar ett ärende hos Microsoft Support om ett problem som rör export av sökrapporter kan du bli ombedd att ange den här spårningsloggen.</span><span class="sxs-lookup"><span data-stu-id="3c874-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="3c874-200">**Icke indexerade objekt:** Ett Excel dokument som innehåller information om icke indexerade objekt som ingår i sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="3c874-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="3c874-201">Om du inte tar med icke indexerade objekt när du skapar sökresultatrapporten kommer den här rapporten fortfarande att laddas ned, men den är tom.</span><span class="sxs-lookup"><span data-stu-id="3c874-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
