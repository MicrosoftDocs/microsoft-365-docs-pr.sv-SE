---
title: Förhandsgranska resultaten från en eDiscovery-sökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Förhandsgranska ett exempel på resultaten från en innehållssökning eller en Core eDiscovery-sökning i Microsoft 365 Efterlevnadscenter.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538595"
---
# <a name="preview-ediscovery-search-results"></a><span data-ttu-id="bb029-103">Förhandsgranska eDiscovery-sökresultaten</span><span class="sxs-lookup"><span data-stu-id="bb029-103">Preview eDiscovery search results</span></span>

<span data-ttu-id="bb029-104">När du har kört en innehållssökning eller en sökning som är kopplad till ett Core eDiscovery-ärende kan du förhandsgranska ett exempel på resultaten från sökningen.</span><span class="sxs-lookup"><span data-stu-id="bb029-104">After you run a Content search or a search associated with a Core eDiscovery case, you can preview a sample of the results returned by the search.</span></span> <span data-ttu-id="bb029-105">Genom att förhandsgranska objekten som returneras av sökfrågan kan du avgöra om sökningen returnerar de resultat som du hoppades på eller om du behöver ändra sökfrågan och köra sökningen igen.</span><span class="sxs-lookup"><span data-stu-id="bb029-105">Previewing items returned by the search query can help you determine if the search is returning the results you hope for or if you need to change the search query and rerun the search.</span></span>

<span data-ttu-id="bb029-106">Så här gör du för att förhandsgranska resultaten som returneras av en sökning:</span><span class="sxs-lookup"><span data-stu-id="bb029-106">To preview a sample of results returned by a search:</span></span>

1. <span data-ttu-id="bb029-107">I Microsoft 365 Efterlevnadscenter går du till sidan Innehållssökning eller till ett Core eDiscovery-ärende.</span><span class="sxs-lookup"><span data-stu-id="bb029-107">In the Microsoft 365 compliance center, go to the Content search page or a Core eDiscovery case.</span></span>

2. <span data-ttu-id="bb029-108">Välj Sök för att visa den utfällbara sidan.</span><span class="sxs-lookup"><span data-stu-id="bb029-108">Select search to display the flyout page.</span></span>

3. <span data-ttu-id="bb029-109">Längst ned på den utfällbara sidan klickar du på **Granska exempel**.</span><span class="sxs-lookup"><span data-stu-id="bb029-109">On the bottom of the flyout page, click **Review sample**.</span></span>

   ![Klicka på Granska exempel på utfällbara sidan för att förhandsgranska resultat](../media/PreviewSearchResults1.png)

   <span data-ttu-id="bb029-111">En sida visas med ett exempel på sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="bb029-111">A page is displayed containing a sample of the search results.</span></span>

4. <span data-ttu-id="bb029-112">Välj ett objekt om du vill visa dess innehåll i läsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bb029-112">Select an item to view its contents in the reading pane.</span></span>

   ![Förhandsgranska objekt i läsfönstret](../media/PreviewSearchResults2.png)

   <span data-ttu-id="bb029-114">Observera att nyckelord från sökfrågan markeras när du förhandsgranskar objekt i föregående skärmbild.</span><span class="sxs-lookup"><span data-stu-id="bb029-114">In the previous screenshot, notice that keywords from the search query are highlighted when you preview items.</span></span>

## <a name="how-the-search-result-samples-are-selected"></a><span data-ttu-id="bb029-115">Hur exempel på sökresultat väljs</span><span class="sxs-lookup"><span data-stu-id="bb029-115">How the search result samples are selected</span></span>

<span data-ttu-id="bb029-116">Högst 1 000 slumpmässigt valda objekt är tillgängliga att förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="bb029-116">A maximum of 1,000 randomly selected items are available to preview.</span></span> <span data-ttu-id="bb029-117">Förutom att det finns slumpmässigt valda objekt som är tillgängliga för förhandsgranskning måste de också uppfylla följande villkor:</span><span class="sxs-lookup"><span data-stu-id="bb029-117">In addition to being randomly selected, items available for preview must also meet the following criteria:</span></span>

- <span data-ttu-id="bb029-118">Högst 100 objekt från en enskild innehållsplats (en postlåda eller en webbplats) kan förhandsgranskas.</span><span class="sxs-lookup"><span data-stu-id="bb029-118">A maximum of 100 items from a single content location (a mailbox or a site) can be previewed.</span></span> <span data-ttu-id="bb029-119">Det innebär att det kan finnas färre än 1 000 objekt tillgängliga för förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="bb029-119">This means that it's possible that less than 1,000 items might be available for preview.</span></span> <span data-ttu-id="bb029-120">Om du till exempel söker i fyra postlådor och sökningen returnerar 1 500 uppskattade objekt kommer bara 400 att vara tillgängliga för förhandsgranskning eftersom bara 100 objekt från varje postlåda kan förhandsgranskas.</span><span class="sxs-lookup"><span data-stu-id="bb029-120">For example, if you search four mailboxes and the search returns 1,500 estimated items, only 400 will be available for preview because only 100 items from each mailbox can be previewed.</span></span>

- <span data-ttu-id="bb029-121">För postlådeobjekt är endast e-postmeddelanden tillgängliga att förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="bb029-121">For mailbox items, only email messages are available to preview.</span></span> <span data-ttu-id="bb029-122">Objekt som uppgifter, kalenderobjekt och kontakter kan inte förhandsgranskas.</span><span class="sxs-lookup"><span data-stu-id="bb029-122">Items like tasks, calendar items, and contacts can't be previewed.</span></span>

- <span data-ttu-id="bb029-123">För webbplatsobjekt är endast dokument tillgängliga att förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="bb029-123">For site items, only documents are available to preview.</span></span> <span data-ttu-id="bb029-124">Det går inte att förhandsgranska objekt som mappar, listor eller bifogade filer i listor.</span><span class="sxs-lookup"><span data-stu-id="bb029-124">Items like folders, lists, or list attachments can't be previewed.</span></span>

## <a name="file-types-supported-when-previewing-search-results"></a><span data-ttu-id="bb029-125">Filtyper som stöds vid förhandsgranskning av sökresultaten</span><span class="sxs-lookup"><span data-stu-id="bb029-125">File types supported when previewing search results</span></span>

<span data-ttu-id="bb029-126">Du kan förhandsgranska de filtyper som stöds i förhandsgranskningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bb029-126">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="bb029-127">Om filtypen inte stöds måste du ladda ned en kopia av filen till den lokala datorn (klicka på **Ladda ned originalobjektet**).</span><span class="sxs-lookup"><span data-stu-id="bb029-127">If a file type isn't supported, you have to download a copy of the file to your local computer (by clicking **Download original item**).</span></span> <span data-ttu-id="bb029-128">För ASPX-webbsidor ingår URL-adressen för sidan, men du kanske inte har behörighet att komma åt sidan.</span><span class="sxs-lookup"><span data-stu-id="bb029-128">For .aspx Web pages, the URL for the page is included though you may not have permissions to access the page.</span></span> <span data-ttu-id="bb029-129">Icke indexerade objekt inte är tillgängliga för förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="bb029-129">Unindexed items aren't available for previewing.</span></span>

<span data-ttu-id="bb029-130">Följande filtyper stöds och kan förhandsgranskas i sökresultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="bb029-130">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="bb029-131">.txt, .html, .mhtml</span><span class="sxs-lookup"><span data-stu-id="bb029-131">.txt, .html, .mhtml</span></span>

- <span data-ttu-id="bb029-132">.eml</span><span class="sxs-lookup"><span data-stu-id="bb029-132">.eml</span></span>

- <span data-ttu-id="bb029-133">.doc, .docx, .docm</span><span class="sxs-lookup"><span data-stu-id="bb029-133">.doc, .docx, .docm</span></span>

- <span data-ttu-id="bb029-134">.pptm, .pptx</span><span class="sxs-lookup"><span data-stu-id="bb029-134">.pptm, .pptx</span></span>

- <span data-ttu-id="bb029-135">.pdf</span><span class="sxs-lookup"><span data-stu-id="bb029-135">.pdf</span></span>

<span data-ttu-id="bb029-136">Följande filbehållartyper stöds också.</span><span class="sxs-lookup"><span data-stu-id="bb029-136">Also, the following file container types are supported.</span></span> <span data-ttu-id="bb029-137">Du kan visa listan med filer i behållaren i förhandsgranskningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bb029-137">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="bb029-138">.zip</span><span class="sxs-lookup"><span data-stu-id="bb029-138">.zip</span></span>

- <span data-ttu-id="bb029-139">.gzip</span><span class="sxs-lookup"><span data-stu-id="bb029-139">.gzip</span></span>