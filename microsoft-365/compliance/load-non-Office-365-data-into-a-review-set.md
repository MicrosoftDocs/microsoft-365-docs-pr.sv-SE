---
title: Läsa in data som Microsoft 365 i en granskningsuppsättning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig hur du importerar icke-Microsoft 365 data till en granskningsuppsättning för analys i Advanced eDiscovery fall.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161849"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="45708-103">Läsa in data som Microsoft 365 i en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="45708-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="45708-104">Alla dokument som du behöver analysera i Advanced eDiscovery finns inte i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45708-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="45708-105">Med funktionen för Microsoft 365 dataimport i Advanced eDiscovery kan du ladda upp dokument som inte finns i Microsoft 365 till en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="45708-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="45708-106">Den här artikeln visar hur du för in icke-Microsoft 365 dokument till Advanced eDiscovery för analys.</span><span class="sxs-lookup"><span data-stu-id="45708-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="45708-107">Krav för att överföra innehåll som inte Office 365 innehåll</span><span class="sxs-lookup"><span data-stu-id="45708-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="45708-108">Om du använder funktionen för uppladdning Microsoft 365 som beskrivs i den här artikeln krävs att du har följande:</span><span class="sxs-lookup"><span data-stu-id="45708-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="45708-109">Alla medarbetare som du vill associera icke-Microsoft 365 måste tilldelas rätt licens.</span><span class="sxs-lookup"><span data-stu-id="45708-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="45708-110">Mer information finns i [Komma igång med Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span><span class="sxs-lookup"><span data-stu-id="45708-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="45708-111">Ett befintligt Advanced eDiscovery ärende.</span><span class="sxs-lookup"><span data-stu-id="45708-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="45708-112">Dokumentföretag måste läggas till i ärendet innan du kan överföra och associera icke-Microsoft 365 data med dem.</span><span class="sxs-lookup"><span data-stu-id="45708-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="45708-113">Icke-Microsoft 365-data måste vara en filtyp som stöds av Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="45708-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="45708-114">Mer information finns i [Filtyper som stöds i Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="45708-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="45708-115">Alla filer som laddas upp till en granskningsuppsättning måste finnas i mappar, där varje mapp är associerad med en särskild person.</span><span class="sxs-lookup"><span data-stu-id="45708-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="45708-116">Namnen för de här mapparna måste ha följande namnformat: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="45708-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="45708-117">Den alias@domainname måste vara användarens alias Microsoft 365 och domän.</span><span class="sxs-lookup"><span data-stu-id="45708-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="45708-118">Du kan samla alla alias@domainname i en rotmapp.</span><span class="sxs-lookup"><span data-stu-id="45708-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="45708-119">Rotmappen kan endast innehålla alias@domainname mappar.</span><span class="sxs-lookup"><span data-stu-id="45708-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="45708-120">Lösa filer i rotmappen stöds inte.</span><span class="sxs-lookup"><span data-stu-id="45708-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="45708-121">Mappstrukturen för de icke-Microsoft 365 data som du vill ladda upp liknar följande exempel:</span><span class="sxs-lookup"><span data-stu-id="45708-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="45708-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="45708-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="45708-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="45708-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="45708-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="45708-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="45708-125">Där abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, och staci.gonzalez@contoso.com är i det fallet SMTP-adresserna till biblioteksadresserna.</span><span class="sxs-lookup"><span data-stu-id="45708-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Mappstruktur för Microsoft 365 datauppladdning](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="45708-127">Ett konto som har tilldelats rollgruppen för eDiscovery-hanteraren (och lagts till som eDiscovery-administratör).</span><span class="sxs-lookup"><span data-stu-id="45708-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="45708-128">Verktyget AzCopy v8.1 är installerat på en dator som har tillgång till den Microsoft 365 andra innehållsmappstrukturen.</span><span class="sxs-lookup"><span data-stu-id="45708-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="45708-129">Information om hur du installerar AzCopy finns i [Överföra data med AzCopy v8.1 på Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="45708-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="45708-130">Installera AzCopy på standardplatsen, d.v.s. **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="45708-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="45708-131">Du måste använda AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="45708-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="45708-132">Andra versioner av AzCopy kanske inte fungerar vid inläsning av Microsoft 365-data i Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="45708-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="45708-133">Upload icke-Microsoft 365 innehåll i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="45708-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="45708-134">Som eDiscovery Manager eller eDiscovery-administratör öppnar du Advanced eDiscovery och går till den händelse som icke-Microsoft 365-data laddas upp till.</span><span class="sxs-lookup"><span data-stu-id="45708-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="45708-135">Klicka **på Granska uppsättningar** och välj sedan granskningsuppsättningen för att ladda upp de Microsoft 365 data till.</span><span class="sxs-lookup"><span data-stu-id="45708-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="45708-136">Om du inte har någon granskningsuppsättning kan du skapa en.</span><span class="sxs-lookup"><span data-stu-id="45708-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="45708-137">I granskningsuppsättningen klickar du på Hantera **granskningsuppsättning** och sedan på Visa uppladdningar på **panelen Microsoft 365 data.** </span><span class="sxs-lookup"><span data-stu-id="45708-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="45708-138">Klicka **Upload filer för** att starta dataimportguiden.</span><span class="sxs-lookup"><span data-stu-id="45708-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Upload filer](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="45708-140">Det första steget i guiden förbereder en säker plats från Microsoft som Azure Storage att ladda upp filerna till.</span><span class="sxs-lookup"><span data-stu-id="45708-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="45708-141">När förberedelsen är klar **blir knappen Upload filer** aktiv.</span><span class="sxs-lookup"><span data-stu-id="45708-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Import för Microsoft 365: Förbereda](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="45708-143">Klicka **på Nästa: Upload filer**.</span><span class="sxs-lookup"><span data-stu-id="45708-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="45708-144">På **Upload filer** gör du följande:</span><span class="sxs-lookup"><span data-stu-id="45708-144">On the **Upload files** page, do the following:</span></span>

   ![Icke-Microsoft 365: Upload filer](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="45708-146">a.</span><span class="sxs-lookup"><span data-stu-id="45708-146">a.</span></span> <span data-ttu-id="45708-147">I rutan **Sökväg till platsen för** filer verifierar du eller anger platsen för rotmappen där du har lagrat de Microsoft 365 data du vill ladda upp.</span><span class="sxs-lookup"><span data-stu-id="45708-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="45708-148">Exempel: För platsen för de exempelfiler som visas i avsnittet Innan du börjar skriver du **%USERPROFILE\Nedladdningar\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="45708-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="45708-149">När du har rätt plats ser du till att AzCopy-kommandot som visas i rutan under sökvägen uppdateras korrekt.</span><span class="sxs-lookup"><span data-stu-id="45708-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="45708-150">b.</span><span class="sxs-lookup"><span data-stu-id="45708-150">b.</span></span> <span data-ttu-id="45708-151">Klicka **på Kopiera till Urklipp** för att kopiera kommandot som visas i rutan.</span><span class="sxs-lookup"><span data-stu-id="45708-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="45708-152">Starta en Windows kommandotolk, klistra in kommandot som du kopierade  i föregående steg och tryck sedan på Retur för att starta kommandot AzCopy.</span><span class="sxs-lookup"><span data-stu-id="45708-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="45708-153">När du startar kommandot laddas filerna som Microsoft 365 upp till den plats Azure Storage förbereddes i steg 4.</span><span class="sxs-lookup"><span data-stu-id="45708-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Import utan Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="45708-155">Som tidigare nämnts måste du använda AzCopy v8.1 för att kunna använda kommandot som finns på **sidan Upload filer.**</span><span class="sxs-lookup"><span data-stu-id="45708-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="45708-156">Om det angivna AzCopy-kommandot misslyckas kan du [gå till Felsöka AzCopy i Advanced eDiscovery.](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="45708-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="45708-157">Gå tillbaka till säkerhets- & säkerhets- och efterlevnadscentret och **klicka på Nästa: Bearbeta** filer i guiden.</span><span class="sxs-lookup"><span data-stu-id="45708-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="45708-158">Detta initierar bearbetning, text extrahering och indexering av de Microsoft 365 filer som laddats upp till Azure Storage platsen.</span><span class="sxs-lookup"><span data-stu-id="45708-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="45708-159">Spåra förloppet för bearbetningen av filerna på  sidan **Processfiler** eller på fliken Jobb genom att visa ett jobb med namnet Lägga till **Microsoft 365-data i en uppsättning med granskare.**</span><span class="sxs-lookup"><span data-stu-id="45708-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="45708-160">När jobbet är klart blir de nya filerna tillgängliga i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="45708-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Import utan Microsoft 365: Bearbeta filer](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="45708-162">När bearbetningen är klar kan du stänga guiden.</span><span class="sxs-lookup"><span data-stu-id="45708-162">After the processing is finished, you can close the wizard.</span></span>