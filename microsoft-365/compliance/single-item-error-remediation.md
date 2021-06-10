---
title: Felåtgärder för enskilt objekt
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
ms.assetid: ''
description: Du kan åtgärda ett bearbetningsfel i ett dokument i en granskningsuppsättning i Advanced eDiscovery utan att behöva följa processen för massfelåtgärd.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2021
ms.locfileid: "52161719"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="ad021-103">Åtgärd för enstaka objektfel i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ad021-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="ad021-104">Felreparation ger Advanced eDiscovery möjlighet att hantera dataproblem som hindrar Advanced eDiscovery att bearbeta innehållet på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="ad021-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="ad021-105">Till exempel kan inte lösenordsskyddade filer bearbetas eftersom filerna är låsta eller krypterade.</span><span class="sxs-lookup"><span data-stu-id="ad021-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="ad021-106">Tidigare kunde du bara massreklarera fel med hjälp av det [här arbetsflödet.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="ad021-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="ad021-107">Men ibland är det inte rimligt att åtgärda fel i flera filer när du är osäker på om någon av filerna svarar på det ärende du undersöker.</span><span class="sxs-lookup"><span data-stu-id="ad021-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="ad021-108">Det kanske inte heller är meningsfullt att åtgärda fel innan du har haft möjlighet att granska filens metadata (till exempel filplats eller vem som har åtkomst) för att hjälpa dig att fatta snabba beslut om tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="ad021-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="ad021-109">En ny  funktion som kallas åtgärd för enstaka objekt ger eDiscovery-hanterare möjlighet att visa metadata för filer med ett bearbetningsfel och vid behov åtgärda felet direkt i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="ad021-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="ad021-110">I artikeln beskrivs hur du identifierar, ignorerar och åtgärdar filer med bearbetningsfel i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="ad021-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="ad021-111">Identifiera dokument med fel</span><span class="sxs-lookup"><span data-stu-id="ad021-111">Identify documents with errors</span></span>

<span data-ttu-id="ad021-112">Dokument med bearbetningsfel i en granskningsuppsättning identifieras nu (med en banderoll).</span><span class="sxs-lookup"><span data-stu-id="ad021-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="ad021-113">Du kan åtgärda eller ignorera felet.</span><span class="sxs-lookup"><span data-stu-id="ad021-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="ad021-114">Följande skärmbild visar en banderoll med bearbetningsfel för ett Word-dokument i en granskningsuppsättning som är lösenordsskyddad.</span><span class="sxs-lookup"><span data-stu-id="ad021-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="ad021-115">Observera också att du kan visa filens metadata i dokument med bearbetningsfel.</span><span class="sxs-lookup"><span data-stu-id="ad021-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Banderoll visas för dokument med bearbetningsfel](../media/SIERimage1.png)

<span data-ttu-id="ad021-117">Du kan också söka efter dokument som har bearbetningsfel genom att använda **villkoret Bearbetningsstatus** när du frågar dokumenten i [en granskningsuppsättning.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="ad021-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Använda villkoret Bearbetningsstatus för att söka efter feldokument](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="ad021-119">Ignorera fel</span><span class="sxs-lookup"><span data-stu-id="ad021-119">Ignore errors</span></span>

<span data-ttu-id="ad021-120">Du kan ignorera ett bearbetningsfel genom att klicka på **Ignorera** i banderollen för bearbetningsfel.</span><span class="sxs-lookup"><span data-stu-id="ad021-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="ad021-121">När du ignorerar ett fel tas dokumentet bort från arbetsflödet [för massfelreparation.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="ad021-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="ad021-122">När ett fel ignoreras ändrar dokumentbanderollen färg och anger att bearbetningsfelet ignorerades.</span><span class="sxs-lookup"><span data-stu-id="ad021-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="ad021-123">Du kan när som helst återställa beslutet att ignorera felet genom att klicka på **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="ad021-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Klicka på Ignorera om du vill ignorera bearbetningsfelet](../media/SIERimage3.png)

<span data-ttu-id="ad021-125">Du kan också söka efter alla dokument som hade ett bearbetningsfel som ignorerades med hjälp av villkoret Ignorerad bearbetning när dokument i en *granskningsuppsättning* körs.</span><span class="sxs-lookup"><span data-stu-id="ad021-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Använd villkoret Ignorerade bearbetningsfel om du vill söka efter ignorerade feldokument](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="ad021-127">Åtgärda fel i ett dokument</span><span class="sxs-lookup"><span data-stu-id="ad021-127">Remediate a document with errors</span></span>

<span data-ttu-id="ad021-128">Ibland kan du behöva åtgärda ett bearbetningsfel i dokument (genom att ta bort ett lösenord, dekryptera en krypterad fil eller återställa ett skadat dokument) och sedan lägga till det åtgärdade dokumentet i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="ad021-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="ad021-129">På så sätt kan du granska och exportera feldokumentet tillsammans med de andra dokumenten i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="ad021-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="ad021-130">För att åtgärda ett enskilt dokument gör du så här:</span><span class="sxs-lookup"><span data-stu-id="ad021-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="ad021-131">Klicka **på Ladda** ned  >  **original** för att ladda ned en kopia av filen till en lokal dator.</span><span class="sxs-lookup"><span data-stu-id="ad021-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Ladda ned dokumentet med bearbetningsfelet](../media/SIERimage5.png)

2. <span data-ttu-id="ad021-133">Åtgärda felet i filen offline.</span><span class="sxs-lookup"><span data-stu-id="ad021-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="ad021-134">För krypterade filer, som skulle kräva dekrypteringsprogramvara, för att ta bort lösenordsskydd, antingen tillhandahålla lösenordet och spara filen eller använda en lösenordsruckare.</span><span class="sxs-lookup"><span data-stu-id="ad021-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="ad021-135">När du har åtgärdat filen går du till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="ad021-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="ad021-136">Markera filen med det åtgärdade bearbetningsfelet i granskningsuppsättningen och klicka sedan **på Åtgärd.**</span><span class="sxs-lookup"><span data-stu-id="ad021-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Klicka på Åtgärd i banderollen i dokumentet med bearbetningsfel](../media/SIERimage6.png)


4. <span data-ttu-id="ad021-138">Klicka **på** Bläddra , gå till platsen för den åtgärdade filen på den lokala datorn och markera sedan filen.</span><span class="sxs-lookup"><span data-stu-id="ad021-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Klicka på Bläddra och markera den åtgärdade filen på den lokala datorn](../media/SIERimage7.png)

    <span data-ttu-id="ad021-140">När du har valt den åtgärdade filen laddas den automatiskt upp till granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="ad021-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="ad021-141">Du kan spåra filens bearbetningsstatus.</span><span class="sxs-lookup"><span data-stu-id="ad021-141">You can track the processing status of the file.</span></span>

    ![Status för åtgärdsprocessen visas](../media/SIERimage8.png)

   <span data-ttu-id="ad021-143">När bearbetningen är klar kan du visa det åtgärdade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="ad021-143">After processing is completed, you can view the remediated document.</span></span>

    ![Du kan visa den åtgärdade filen i det ursprungliga formatet i granskningsuppsättningen](../media/SIERimage9.png)

<span data-ttu-id="ad021-145">Mer information om vad som händer när ett dokument åtgärdas finns i [Vad händer när filer åtgärdas.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)</span><span class="sxs-lookup"><span data-stu-id="ad021-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="ad021-146">Söka efter åtgärdade dokument</span><span class="sxs-lookup"><span data-stu-id="ad021-146">Search for remediated documents</span></span>

<span data-ttu-id="ad021-147">Du kan söka efter alla dokument i en granskningsuppsättning som har åtgärdats med hjälp av **villkoret Nyckelord** och ange följande egenskap:värdepar: **IsFromErrorRemediation:true.**</span><span class="sxs-lookup"><span data-stu-id="ad021-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="ad021-148">Den här egenskapen är också tillgänglig i inläsningsfilen för export när du exporterar dokument från en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="ad021-148">This property is also available in the export load file when you export documents from a review set.</span></span>
