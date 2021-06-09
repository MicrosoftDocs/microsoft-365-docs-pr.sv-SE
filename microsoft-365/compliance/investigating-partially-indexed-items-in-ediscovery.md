---
title: Undersöker delvis indexerade objekt i eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du hanterar delvis indexerade objekt (kallas även icke indexerade objekt) från Exchange, SharePoint och OneDrive för företag inom organisationen.
ms.openlocfilehash: 539fd2687735a5ee14be543750becca8c6c3154c
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311474"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="9e3bd-103">Undersöker delvis indexerade objekt i eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9e3bd-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="9e3bd-104">En eDiscovery-sökning som du kör från efterlevnadscentret för Microsoft 365 inkluderar automatiskt delvis indexerade objekt i det uppskattade sökresultatet när du kör en sökning.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="9e3bd-105">Delvis indexerade objekt Exchange postlådeobjekt och dokument på SharePoint och OneDrive för företag-webbplatser som av någon anledning inte indexerats helt för sökning.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="9e3bd-106">De flesta e-postmeddelanden och webbplatsdokument indexeras korrekt eftersom de faller inom [indexeringsbegränsningarna för e-postmeddelanden.](limits-for-content-search.md#indexing-limits-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="9e3bd-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="9e3bd-107">Vissa objekt kan dock överskrida indexeringsgränserna och indexeras delvis.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="9e3bd-108">Här är andra orsaker till varför objekt inte kan indexeras för sökning och returneras som delvis indexerade objekt när du kör en eDiscovery-sökning:</span><span class="sxs-lookup"><span data-stu-id="9e3bd-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="9e3bd-109">E-postmeddelanden har en bifogad fil utan en giltig hanterare, t.ex. bildfiler. det här är den vanligaste orsaken till delvis indexerade e-postobjekt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="9e3bd-110">För många bifogade filer i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="9e3bd-111">En fil som bifogas i ett e-postmeddelande är för stor.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="9e3bd-112">Filtypen stöds för indexering men ett indexeringsfel uppstod för en viss fil.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="9e3bd-113">Även om innehållet varierar har de flesta organisationers kunder mindre än 1 % innehåll per volym och mindre än 12 % innehåll per storlek som är delvis indexerat.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="9e3bd-114">Orsaken till skillnaden mellan volym och storlek är att större filer har en högre sannolikhet för att innehåll som inte kan indexeras helt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="9e3bd-115">Varför ändras antalet delvis indexerade objekt för en sökning?</span><span class="sxs-lookup"><span data-stu-id="9e3bd-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="9e3bd-116">När du har kört en eDiscovery-sökning visas det totala antalet och storleken på delvis indexerade objekt på de platser som har sökts i sökresultatstatistiken som visas i den detaljerade statistiken för sökningen.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="9e3bd-117">Observera att dessa kallas  *icke indexerade objekt*  i sökstatistiken.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="9e3bd-118">Här är några saker som påverkar antalet delvis indexerade objekt som returneras i sökresultaten:</span><span class="sxs-lookup"><span data-stu-id="9e3bd-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="9e3bd-119">Om ett objekt är delvis indexerat och matchar sökfrågan inkluderas det i både antal (och storlek) för sökresultatobjekt och delvis indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="9e3bd-120">Men när resultatet av samma sökning exporteras inkluderas objektet endast i uppsättningen sökresultat. det tas inte med som ett delvis indexerat objekt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="9e3bd-121">Delvis indexerade objekt som finns SharePoint och OneDrive-webbplatser ingår inte i uppskattningen av delvis indexerade objekt som visas i den detaljerade statistiken för sökningen. </span><span class="sxs-lookup"><span data-stu-id="9e3bd-121">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="9e3bd-122">Delvis indexerade objekt kan emellertid exporteras när du exporterar resultatet av en eDiscovery-sökning.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-122">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="9e3bd-123">Om du till exempel bara söker på webbplatser blir det uppskattade antalet delvis indexerade objekt noll.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-123">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="9e3bd-124">Beräkna förhållandet mellan delvis indexerade element i organisationen</span><span class="sxs-lookup"><span data-stu-id="9e3bd-124">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="9e3bd-125">För att förstå hur exponering av delvis indexerade objekt visas i organisationen kan du köra en sökning efter allt innehåll i alla postlådor (med hjälp av en tom nyckelordsfråga).</span><span class="sxs-lookup"><span data-stu-id="9e3bd-125">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="9e3bd-126">I följande exempel finns det 1 629 904 (146,46 GB) helt indexerade objekt och 10 025 (10,27 GB) delvis indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-126">In the following example, there are 1,629,904 (146.46 GB) fully indexed items and 10,025 (10.27 GB) partially indexed items.</span></span>
  
![Exempel på sökstatistik som visar delvis indexerade objekt](../media/PartiallyIndexedItemsTest.png)
  
<span data-ttu-id="9e3bd-128">Du kan bestämma hur många procent av delvis indexerade element är med hjälp av följande beräkningar.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-128">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="9e3bd-129">**Så här beräknar du förhållandet mellan delvis indexerade element i organisationen:**</span><span class="sxs-lookup"><span data-stu-id="9e3bd-129">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

<span data-ttu-id="9e3bd-130">Med hjälp av sökresultaten från föregående exempel indexeras 0,62 % av alla postlådor delvis.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-130">By using the search results from the previous example, 0.62% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="9e3bd-131">**Så här beräknar du procentandelen av storleken på delvis indexerade objekt i organisationen:**</span><span class="sxs-lookup"><span data-stu-id="9e3bd-131">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 MB) x 100 = 7.0%`

<span data-ttu-id="9e3bd-132">I exemplet ovan kommer alltså 7 % av den totala storleken på postlådeobjekt från delvis indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-132">So in the previous example, 7% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="9e3bd-133">Som tidigare nämnts har de flesta organisationers kunder mindre än 1 % innehåll per volym och mindre än 12 % innehåll i storlek som är delvis indexerat.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-133">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="9e3bd-134">Arbeta med delvis indexerade objekt</span><span class="sxs-lookup"><span data-stu-id="9e3bd-134">Working with partially indexed items</span></span>

<span data-ttu-id="9e3bd-135">Om du behöver undersöka delvisa objekt för att verifiera att de [](export-a-content-search-report.md) inte innehåller relevant information kan du exportera en innehållsökningsrapport som innehåller information om delvis indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-135">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="9e3bd-136">När du exporterar en rapport för innehållssökning måste du välja ett exportalternativ som innehåller delvis indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-136">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![Välj det andra eller tredje alternativet för att exportera delvis indexerade objekt](../media/PartiallyIndexedItemsExportOptions.png)
  
<span data-ttu-id="9e3bd-138">När du exporterar eDiscovery-sökresultat eller en sökrapport med något av följande alternativ innehåller exporten en rapport med namnet Icke indexerade Items.csv.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-138">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="9e3bd-139">Den här rapporten innehåller de flesta av samma information ResultsLog.csv filen. Men icke indexerade objekt Items.csv också två fält som är relaterade till delvis indexerade element: **Feltaggar** och **Felegenskaper.**</span><span class="sxs-lookup"><span data-stu-id="9e3bd-139">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="9e3bd-140">De här fälten innehåller information om indexeringsfelet för varje delvis indexerat objekt.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-140">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="9e3bd-141">Genom att använda informationen i de här två fälten kan du avgöra om indexeringsfelet för en viss undersökning ska påverkas.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-141">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="9e3bd-142">Om så är möjligt kan du utföra en riktad sökning och hämta och exportera specifika e-postmeddelanden och SharePoint- eller OneDrive-dokument så att du kan undersöka dem för att avgöra om de är relevanta för din undersökning.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-142">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="9e3bd-143">Stegvisa anvisningar finns i Förbereda en [CSV-fil för en riktad sökning i Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="9e3bd-143">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9e3bd-144">Den icke indexerade Items.csv innehåller även fält med **namnet Feltyp** **och Felmeddelande.**</span><span class="sxs-lookup"><span data-stu-id="9e3bd-144">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="9e3bd-145">Det här är äldre fält som innehåller information som liknar informationen i fälten **Feltaggar** och **Felegenskaper,** men med mindre detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-145">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="9e3bd-146">Du kan bortse från dessa tidigare fält.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-146">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="9e3bd-147">Fel som rör delvis indexerade objekt</span><span class="sxs-lookup"><span data-stu-id="9e3bd-147">Errors related to partially indexed items</span></span>

<span data-ttu-id="9e3bd-148">Feltaggar består av två delar med information, felet och filtypen.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-148">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="9e3bd-149">I det här felet/filtypspar:</span><span class="sxs-lookup"><span data-stu-id="9e3bd-149">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="9e3bd-150">`parseroutputsize` är felet och `xls` är filtypen för filen som felet inträffade i.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-150">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="9e3bd-151">I fall där filtypen inte kunde identifieras eller filtypen inte kunde identifieras för felet visas värdet i stället för `noformat` filtypen.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-151">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="9e3bd-152">Nedan följer en lista över indexeringsfel och en beskrivning av den möjliga orsaken till felet.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-152">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="9e3bd-153">Feltagg</span><span class="sxs-lookup"><span data-stu-id="9e3bd-153">Error tag</span></span> | <span data-ttu-id="9e3bd-154">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9e3bd-154">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="9e3bd-155">Ett e-postmeddelande hade för många bifogade filer och vissa av dem hanterade inte.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-155">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="9e3bd-156">Innehållshämtare och dokument tolkade för många nivåer av bifogade filer kapslade i andra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-156">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="9e3bd-157">Vissa av de här bifogade filerna har inte bearbetats.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-157">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="9e3bd-158">En bifogad fil misslyckades med avkodningen eftersom den var RMS-skyddad.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-158">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="9e3bd-159">En fil som bifogats i ett e-postmeddelande var för stor och kunde inte bearbetas.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-159">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="9e3bd-160">När det bearbetade e-postmeddelandet skrevs till indexet var en av de indexbara egenskaperna för stor och trunkerades.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-160">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="9e3bd-161">De trunkerade egenskaperna visas i fältet Felegenskaper.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-161">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="9e3bd-162">Ett e-postmeddelande innehöll text som inte kunde bearbetas som giltig Unicode.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-162">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="9e3bd-163">Indexeringen för det här objektet kan vara ofullständig.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-163">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="9e3bd-164">Innehållet i bifogade filer eller e-postmeddelanden krypteras och Microsoft 365 det inte gick att avkoda innehållet.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-164">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="9e3bd-165">Ett okänt fel uppstod vid tolkning.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-165">An unknown error occurred during parsing.</span></span> <span data-ttu-id="9e3bd-166">Det här beror vanligtvis på en programfel eller en tjänstkrasch.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-166">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="9e3bd-167">En bifogad fil var för stor för att parsern skulle kunna hantera och tolkning av den bifogade filen skedde inte eller slutfördes inte.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-167">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="9e3bd-168">En bifogad fil var felaktig och kunde inte hanteras av parsern.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-168">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="9e3bd-169">Resultatet kan bero på gamla filformat, filer som skapats med inkompatibla program eller virus som utger sig för att vara något annat än påstådda.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-169">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="9e3bd-170">Utdata från tolkning av en bifogad fil var för stor och behövde trunkeras.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-170">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="9e3bd-171">En bifogad fil hade en filtyp Microsoft 365 kunde inte identifiera.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-171">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="9e3bd-172">En bifogad fil hade en filtyp Office 365 kunde identifiera, men det går inte att tolka den filtypen.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-172">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="9e3bd-173">Värdet för en e-postegenskap i Exchange Store var för stort för att kunna hämtas och meddelandet kunde inte bearbetas.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-173">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="9e3bd-174">Det här händer vanligtvis bara med brödtexten i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-174">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="9e3bd-175">Det gick inte att avkoda ett RMS-skyddat meddelande för innehållshämtare.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-175">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="9e3bd-176">För många ord identifierades i dokumentet vid indexering.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-176">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="9e3bd-177">Bearbetningen av egenskapen upphörde när gränsen når gränsen och egenskapen trunkeras.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-177">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="9e3bd-178">Felfält beskriver vilka fält som påverkas av bearbetningsfelet som visas i fältet Feltaggar.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-178">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="9e3bd-179">Om du söker efter en egenskap som eller , påverkas inte resultatet av sökningen om du fel  `subject`  `participants` i brödtexten i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-179">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="9e3bd-180">Det kan vara användbart när du ska avgöra exakt vilka delvis indexerade objekt som du kan behöva undersöka ytterligare.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-180">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="9e3bd-181">Använda ett PowerShell-skript för att avgöra exponering av organisationen för delvis indexerade e-postobjekt</span><span class="sxs-lookup"><span data-stu-id="9e3bd-181">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="9e3bd-182">Följande steg visar hur du kör ett PowerShell-skript som söker efter alla objekt i alla Exchange-postlådor och sedan genererar en rapport om organisationens kvot för delvis indexerade e-postobjekt (efter antal och storlek) och visar antalet objekt (och deras filtyp) för varje indexeringsfel som uppstår.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-182">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="9e3bd-183">Använd feltaggsbeskrivningarna i föregående avsnitt för att identifiera indexeringsfelet.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-183">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="9e3bd-184">Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="9e3bd-184">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "**************************************************"
     " " 
     # Create a search with Error Tags Refinders enabled
     Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
     New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
     Start-ComplianceSearch "RefinerTest"
     # Loop while search is in progress
     do{
         Write-host "Waiting for search to complete..."
         Start-Sleep -s 5
         $complianceSearch = Get-ComplianceSearch "RefinerTest"
     }while ($complianceSearch.Status -ne 'Completed')
     $refiners = $complianceSearch.Refiners | ConvertFrom-Json
     $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
     $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
     $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
     " "
     "===== Partially indexed items ====="
     "         Total          Ratio"
     "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
     "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
     " "
     Write-Host ===== Reasons for partially indexed items =====
     foreach($errorTagProperty in $errorTagProperties)
     {
         $name = $refiners.Entries.($errorTagProperty.Name).Name
         $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
         $frag = $name.Split("{_}")
         $errorTag = $frag[0]
         $fileType = $frag[1]
         if ($errorTag -ne $lastErrorTag)
         {
             $errorTag
         }
         "    " + $fileType + " => " + $count
         $lastErrorTag = $errorTag
     }
   ```

2. <span data-ttu-id="9e3bd-185">[Ansluta till Säkerhets- och efterlevnadscenter i PowerShell](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e3bd-185">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="9e3bd-186">Gå till & i Security & Compliance Center, gå till mappen där du sparade skriptet i steg 1 och kör sedan skriptet. till exempel:</span><span class="sxs-lookup"><span data-stu-id="9e3bd-186">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="9e3bd-187">Här är ett exempel för den utdata som returneras av skriptet.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-187">Here's an example fo the output returned by the script.</span></span>
  
![Exempel på utdata från skript som genererar en rapport om exponering av delvis indexerade e-postobjekt i organisationen](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="9e3bd-189">Observera följande:</span><span class="sxs-lookup"><span data-stu-id="9e3bd-189">Note the following:</span></span>
>  
> - <span data-ttu-id="9e3bd-190">Det totala antalet och storleken på e-postobjekt och organisationens andel av delvis indexerade e-postobjekt (antal och storlek).</span><span class="sxs-lookup"><span data-stu-id="9e3bd-190">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="9e3bd-191">En lista med feltaggar och motsvarande filtyper för vilka felet uppstod.</span><span class="sxs-lookup"><span data-stu-id="9e3bd-191">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e3bd-192">Se även</span><span class="sxs-lookup"><span data-stu-id="9e3bd-192">See also</span></span>

[<span data-ttu-id="9e3bd-193">Delvis indexerade objekt i eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9e3bd-193">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)