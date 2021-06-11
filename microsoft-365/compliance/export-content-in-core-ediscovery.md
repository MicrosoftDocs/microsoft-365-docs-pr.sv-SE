---
title: Exportera och ladda ned innehåll från en bas-eDiscovery-fråga
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Här beskrivs hur du exporterar och laddar ned innehåll från en bas-e-dataidentifieringsfall i Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310862"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="a7637-103">Exportera innehåll från en bas-e-dataidentifieringsfall</span><span class="sxs-lookup"><span data-stu-id="a7637-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="a7637-104">När en sökning som är kopplad till ett Bas-eDiscovery-ärende har körts kan du exportera sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="a7637-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="a7637-105">När du exporterar sökresultat hämtas postlådeobjekt i PST-filer eller som enskilda meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a7637-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="a7637-106">När du exporterar innehåll SharePoint och OneDrive för företag exporteras kopior av ursprungliga Office och andra dokument.</span><span class="sxs-lookup"><span data-stu-id="a7637-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="a7637-107">En Results.csv fil som innehåller information om alla objekt som exporteras och en manifestfil (i XML-format) som innehåller information om varje sökresultat exporteras också.</span><span class="sxs-lookup"><span data-stu-id="a7637-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="a7637-108">Exportera sökresultat</span><span class="sxs-lookup"><span data-stu-id="a7637-108">Export search results</span></span>

1. <span data-ttu-id="a7637-109">Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och logga in med inloggningsuppgifterna för användarkontot som har tilldelats lämpliga eDiscovery-behörigheter.</span><span class="sxs-lookup"><span data-stu-id="a7637-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="a7637-110">I det vänstra navigeringsfönstret i Microsoft 365 kompatibilitetscenter klickar du på Visa alla **och** sedan på **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="a7637-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="a7637-111">På sidan **Bas-eDiscovery** klickar du på namnet på det ärende som du vill skapa ett sådant ärende i.</span><span class="sxs-lookup"><span data-stu-id="a7637-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="a7637-112">På **startsidan för** ärendet klickar du på **fliken** Sökningar.</span><span class="sxs-lookup"><span data-stu-id="a7637-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="a7637-113">På menyn **Åtgärder** längst ned på den utfällade sidan klickar du på **Exportera resultat.**</span><span class="sxs-lookup"><span data-stu-id="a7637-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![Alternativet Exportera resultat på menyn Åtgärder](../media/ActionMenuExportResults.png)

   <span data-ttu-id="a7637-115">Arbetsflödet för att exportera resultatet av en sökning som är kopplad till ett basfall för eDiscovery är detsamma som att exportera sökresultatet för en sökning på sidan **Innehållssökning.**</span><span class="sxs-lookup"><span data-stu-id="a7637-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="a7637-116">Stegvisa instruktioner finns i Exportera [sökresultat för innehåll.](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="a7637-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a7637-117">När du exporterar sökresultat kan du välja att aktivera avduplicering så att bara en kopia av ett e-postmeddelande exporteras, även om flera förekomster av samma meddelande kan ha hittats i postlådorna som har sökts.</span><span class="sxs-lookup"><span data-stu-id="a7637-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="a7637-118">Mer information om avduplicering och hur dubbletter identifieras finns i [Avduplicering i eDiscovery-sökresultat.](de-duplication-in-ediscovery-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="a7637-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="a7637-119">När du startar exporten förbereds sökresultaten för nedladdning, vilket innebär att de överförs till en Microsoft-tillhandahållen Azure Storage plats i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="a7637-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="a7637-120">Klicka på **fliken** Exporter för att visa listan med exportjobb.</span><span class="sxs-lookup"><span data-stu-id="a7637-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![Exportera jobb på fliken Exportera i Bas-eDiscovery-fall](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="a7637-122">Du kanske måste klicka på **Uppdatera** för att uppdatera listan med exportjobb så att den visar det exportjobb du har skapat.</span><span class="sxs-lookup"><span data-stu-id="a7637-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="a7637-123">Exportjobb har samma namn som motsvarande sökning **_Export** lagts till i söknamnet.</span><span class="sxs-lookup"><span data-stu-id="a7637-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="a7637-124">Klicka på exportjobbet du skapade för att visa statusinformation på den utfällade sidan.</span><span class="sxs-lookup"><span data-stu-id="a7637-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="a7637-125">Den här informationen omfattar den procentandel av artiklar som har överförts till Azure Storage plats.</span><span class="sxs-lookup"><span data-stu-id="a7637-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="a7637-126">När alla objekt har överförts klickar du på **Ladda ned resultat** för att ladda ned sökresultatet till den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="a7637-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="a7637-127">Mer information om hur du laddar ned sökresultat finns i Steg 2 i [Exportera sökresultat för innehåll](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="a7637-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="a7637-128">Mer information om hur du exporterar sökningar från ett ärende</span><span class="sxs-lookup"><span data-stu-id="a7637-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="a7637-129">Mer information om exportfiler som ingår när du exporterar sökresultat finns i [Exportera en rapport för innehållssökning.](export-a-content-search-report.md#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="a7637-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="a7637-130">Om du startar om exporten påverkas inte sökresultaten som hämtas om du ändrar frågorna för de sökningar som utgör exportjobbet.</span><span class="sxs-lookup"><span data-stu-id="a7637-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="a7637-131">När du startar om en export körs samma kombinerade sökjobb som startades när exportjobbet skapades igen.</span><span class="sxs-lookup"><span data-stu-id="a7637-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="a7637-132">Om du startar om en export kommer sökresultaten som kopieras till den Azure Storage plats att skriva över de tidigare resultaten.</span><span class="sxs-lookup"><span data-stu-id="a7637-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="a7637-133">Tidigare resultat som kopierades går inte att hämta.</span><span class="sxs-lookup"><span data-stu-id="a7637-133">The previous results that were copied won't be available to be downloaded.</span></span>
