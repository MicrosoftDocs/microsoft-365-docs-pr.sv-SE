---
title: Åtgärda fel vid bearbetning av data
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
description: Lär dig hur du använder felreparation för att korrigera dataproblem i Advanced eDiscovery som kan förhindra korrekt bearbetning av innehåll.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2067831a85e3b3a506917fac5b93acfa0b174db
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161936"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="18d66-103">Åtgärda fel vid bearbetning av data</span><span class="sxs-lookup"><span data-stu-id="18d66-103">Error remediation when processing data</span></span>

<span data-ttu-id="18d66-104">Felreparation gör att eDiscovery-administratörer kan hantera dataproblem som Advanced eDiscovery att bearbeta innehållet på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="18d66-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="18d66-105">Till exempel kan inte lösenordsskyddade filer bearbetas eftersom filerna är låsta eller krypterade.</span><span class="sxs-lookup"><span data-stu-id="18d66-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="18d66-106">Med hjälp av felreparation kan eDiscovery-administratörer ladda ned filer med sådana fel, ta bort lösenordsskyddet och sedan ladda upp de åtgärdade filerna.</span><span class="sxs-lookup"><span data-stu-id="18d66-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="18d66-107">Använd följande arbetsflöde för att åtgärda filer med fel i Advanced eDiscovery fall.</span><span class="sxs-lookup"><span data-stu-id="18d66-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="18d66-108">Skapa en session för felreparation för att åtgärda filer med bearbetningsfel</span><span class="sxs-lookup"><span data-stu-id="18d66-108">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="18d66-109">Om åtgärdsguiden är stängd när som helst under följande procedur kan du återgå till  felreparationssessionen på  fliken Bearbetning genom att välja Åtgärder i den nedrullningsmenyn Visa. </span><span class="sxs-lookup"><span data-stu-id="18d66-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="18d66-110">På fliken **Bearbetning** i Advanced eDiscovery fallet väljer du Fel  i den nedrullningsmenyn Visa och väljer sedan  en **granskningsuppsättning** eller hela ärendet i listrutan Omfattning.</span><span class="sxs-lookup"><span data-stu-id="18d66-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="18d66-111">I det här avsnittet visas alla fel från ärendet eller felet från en viss granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="18d66-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![Felreparation](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="18d66-113">Markera de fel du vill åtgärda genom att klicka på alternativknappen bredvid feltypen eller filtypen.</span><span class="sxs-lookup"><span data-stu-id="18d66-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="18d66-114">I följande exempel åtgärdar vi en lösenordsskyddad fil.</span><span class="sxs-lookup"><span data-stu-id="18d66-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="18d66-115">Klicka **på Ny felreparation**.</span><span class="sxs-lookup"><span data-stu-id="18d66-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="18d66-116">Arbetsflödet för felreparation börjar med en förberedelsefas där filerna med fel kopieras till en Plats som tillhandahålls av Microsoft Azure Storage så att du kan ladda ned dem till din lokala dator för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="18d66-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Förbereda felreparation](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="18d66-118">När förberedelsen är klar klickar du på **Nästa: Ladda ned filer för** att fortsätta med nedladdningen.</span><span class="sxs-lookup"><span data-stu-id="18d66-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Ladda ned filer](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="18d66-120">Om du vill ladda ned filer anger **du målsökvägen för nedladdning**.</span><span class="sxs-lookup"><span data-stu-id="18d66-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="18d66-121">Det här är en sökväg till den överordnade mappen på den lokala datorn dit filen ska laddas ned.</span><span class="sxs-lookup"><span data-stu-id="18d66-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="18d66-122">Standardsökvägen, %USERPROFILE%\Downloads\errors, pekar på den inloggade användarens hämtade mapp.</span><span class="sxs-lookup"><span data-stu-id="18d66-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="18d66-123">Du kan ändra den här sökvägen om du vill.</span><span class="sxs-lookup"><span data-stu-id="18d66-123">You can change this path if desired.</span></span> <span data-ttu-id="18d66-124">Om du ändrar den rekommenderar vi att du använder en lokal filsökväg för bästa prestanda.</span><span class="sxs-lookup"><span data-stu-id="18d66-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="18d66-125">Använd inte en fjärrnätverkssökväg.</span><span class="sxs-lookup"><span data-stu-id="18d66-125">Don't use a remote network path.</span></span> <span data-ttu-id="18d66-126">Du kan till exempel använda sökvägen **C:\Remediation.**</span><span class="sxs-lookup"><span data-stu-id="18d66-126">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="18d66-127">Sökvägen till den överordnade mappen läggs automatiskt till i AzCopy-kommandot (som värdet för **parametern /Dest).**</span><span class="sxs-lookup"><span data-stu-id="18d66-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="18d66-128">Kopiera det fördefinierade kommandot genom att klicka **på Kopiera till Urklipp.**</span><span class="sxs-lookup"><span data-stu-id="18d66-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="18d66-129">Öppna ett Windows Kommandotolk, klistra in kommandot AzCopy och tryck sedan på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="18d66-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![Förbereda för felreparation](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="18d66-131">Du måste använda AzCopy v8.1 om du vill använda kommandot som finns på **sidan Ladda ned** filer.</span><span class="sxs-lookup"><span data-stu-id="18d66-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="18d66-132">Du måste också använda AzCopy v8.1 för att ladda upp filerna i steg 10.</span><span class="sxs-lookup"><span data-stu-id="18d66-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="18d66-133">Information om hur du installerar den här versionen av AzCopy finns i Överföra data med [AzCopy v8.1 på Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="18d66-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="18d66-134">Om det angivna AzCopy-kommandot misslyckas kan du [gå till Felsöka AzCopy i Advanced eDiscovery.](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="18d66-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="18d66-135">De valda filerna laddas ned till den plats som du angav i steg 5.</span><span class="sxs-lookup"><span data-stu-id="18d66-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="18d66-136">I den överordnade mappen (till exempel **C:\Remediation)** skapas automatiskt följande undermappsstruktur:</span><span class="sxs-lookup"><span data-stu-id="18d66-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="18d66-137">*Undermapp 1* namnges med ID för ärendet eller granskningsuppsättningen, beroende på omfattningen som du valde i steg 1.</span><span class="sxs-lookup"><span data-stu-id="18d66-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="18d66-138">*Undermapp 2 namnges* med fil-ID för den nedladdade filen</span><span class="sxs-lookup"><span data-stu-id="18d66-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="18d66-139">Den nedladdade filen finns i *undermapp 2 och* har även namnet fil-ID.</span><span class="sxs-lookup"><span data-stu-id="18d66-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="18d66-140">Här är ett exempel på mappsökvägen och det felfilnamn som skapas när objekt hämtas till den överordnade **mappen C:\Remediation:**</span><span class="sxs-lookup"><span data-stu-id="18d66-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="18d66-141">Om flera filer laddas ned laddas var och en ned till en undermapp som namnges med fil-ID.</span><span class="sxs-lookup"><span data-stu-id="18d66-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="18d66-142">När du laddar upp filer i steg 9 och steg 10 måste de åtgärdade filerna ha samma filnamn och finnas i samma undermappsstruktur.</span><span class="sxs-lookup"><span data-stu-id="18d66-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="18d66-143">Undermappen och filnamnen används för att associera den åtgärdade filen med den ursprungliga felfilen.</span><span class="sxs-lookup"><span data-stu-id="18d66-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="18d66-144">Om mappstrukturen eller filnamnen ändras får du följande felmeddelande: `Cannot apply Error Remediation to the current Workingset` .</span><span class="sxs-lookup"><span data-stu-id="18d66-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="18d66-145">För att förhindra problem rekommenderar vi att du sparar de åtgärdade filerna i samma överordnade mapp och undermappsstruktur.</span><span class="sxs-lookup"><span data-stu-id="18d66-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="18d66-146">När du har laddat ned filerna kan du åtgärda dem med ett lämpligt verktyg.</span><span class="sxs-lookup"><span data-stu-id="18d66-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="18d66-147">För lösenordsskyddade filer finns det flera verktyg för återställning av lösenord som du kan använda.</span><span class="sxs-lookup"><span data-stu-id="18d66-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="18d66-148">Om du har lösenorden till filerna kan du öppna dem och ta bort lösenordsskyddet.</span><span class="sxs-lookup"><span data-stu-id="18d66-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="18d66-149">Återgå till Advanced eDiscovery och felreparationsguiden och klicka sedan på **Nästa: Upload filer**.</span><span class="sxs-lookup"><span data-stu-id="18d66-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="18d66-150">Nu flyttas du till nästa sida där du kan ladda upp filerna.</span><span class="sxs-lookup"><span data-stu-id="18d66-150">This moves to the next page where you can now upload the files.</span></span>

    ![Upload Filer](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="18d66-152">Ange den överordnade mapp där de åtgärdade filerna finns i **textrutan Sökväg till** plats för filer.</span><span class="sxs-lookup"><span data-stu-id="18d66-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="18d66-153">Den överordnade mappen måste ha samma undermappsstruktur som skapades när du laddade ned filerna.</span><span class="sxs-lookup"><span data-stu-id="18d66-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="18d66-154">Sökvägen till den överordnade mappen läggs automatiskt till i AzCopy-kommandot (som värdet på **parametern /Source).**</span><span class="sxs-lookup"><span data-stu-id="18d66-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="18d66-155">Kopiera det fördefinierade kommandot genom att klicka **på Kopiera till Urklipp.**</span><span class="sxs-lookup"><span data-stu-id="18d66-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="18d66-156">Öppna ett Windows Kommandotolk, klistra in kommandot AzCopy och tryck sedan på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="18d66-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="18d66-157">ladda upp filerna.</span><span class="sxs-lookup"><span data-stu-id="18d66-157">upload the files.</span></span>

    ![Resultat av lyckad uppladdning av åtgärdade filer i Azcopy](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="18d66-159">När du har kört kommandot AzCopy klickar du på **Nästa: Bearbeta filer**.</span><span class="sxs-lookup"><span data-stu-id="18d66-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="18d66-160">När bearbetningen är klar kan du gå till granskningsuppsättningen och visa de åtgärdade filerna.</span><span class="sxs-lookup"><span data-stu-id="18d66-160">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="18d66-161">Åtgärdar fel i behållarfiler</span><span class="sxs-lookup"><span data-stu-id="18d66-161">Remediating errors in container files</span></span>

<span data-ttu-id="18d66-162">I situationer när innehållet i en behållarfil (till exempel en .zip-fil) inte kan extraheras av Advanced eDiscovery kan behållarna laddas ned och innehållet expanderas till samma mapp där den ursprungliga behållaren finns.</span><span class="sxs-lookup"><span data-stu-id="18d66-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="18d66-163">De utökade filerna tilldelas den överordnade behållaren som om den ursprungligen expanderades av Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="18d66-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="18d66-164">Processen fungerar enligt beskrivningen ovan, med undantag för att ladda upp en enda fil som ersättningsfil.</span><span class="sxs-lookup"><span data-stu-id="18d66-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="18d66-165">Inkludera inte den ursprungliga behållarfilen när du laddar upp åtgärdade filer.</span><span class="sxs-lookup"><span data-stu-id="18d66-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="18d66-166">Åtgärda fel genom att ladda upp den extraherade texten</span><span class="sxs-lookup"><span data-stu-id="18d66-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="18d66-167">Ibland går det inte att åtgärda så att filen får det ursprungliga format som Advanced eDiscovery kan tolka.</span><span class="sxs-lookup"><span data-stu-id="18d66-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="18d66-168">Men du kan ersätta den ursprungliga filen med en textfil som innehåller originaltexten i den ursprungliga filen (i en process som kallas *textöverlägg*).</span><span class="sxs-lookup"><span data-stu-id="18d66-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="18d66-169">Det gör du genom att följa stegen som beskrivs i den här artikeln men i stället för att åtgärda den ursprungliga filen i det ursprungliga formatet skapar du en textfil som innehåller den extraherade texten från den ursprungliga filen och laddar sedan upp textfilen med det ursprungliga filnamnet som lagts till med ett .txt-suffix.</span><span class="sxs-lookup"><span data-stu-id="18d66-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="18d66-170">Du kan till exempel ladda ned en fil vid felreparation med filnamnet 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span><span class="sxs-lookup"><span data-stu-id="18d66-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="18d66-171">Du öppnar filen i det ursprungliga programmet, kopierar texten och klistrar sedan in den i en ny fil med namnet 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span><span class="sxs-lookup"><span data-stu-id="18d66-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="18d66-172">När du gör det måste du ta bort den ursprungliga filen i det ursprungliga formatet från platsen för den åtgärdade filen på den lokala datorn innan du laddar upp den åtgärdade textfilen till Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="18d66-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="18d66-173">Vad händer när filer åtgärdas?</span><span class="sxs-lookup"><span data-stu-id="18d66-173">What happens when files are remediated</span></span>

<span data-ttu-id="18d66-174">När åtgärdade filer överförs bevaras de ursprungliga metadata, förutom följande fält:</span><span class="sxs-lookup"><span data-stu-id="18d66-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="18d66-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="18d66-175">ExtractedTextSize</span></span>
- <span data-ttu-id="18d66-176">HasText</span><span class="sxs-lookup"><span data-stu-id="18d66-176">HasText</span></span>
- <span data-ttu-id="18d66-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="18d66-177">IsErrorRemediate</span></span>
- <span data-ttu-id="18d66-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="18d66-178">LoadId</span></span>
- <span data-ttu-id="18d66-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="18d66-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="18d66-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="18d66-180">ProcessingStatus</span></span>
- <span data-ttu-id="18d66-181">Text</span><span class="sxs-lookup"><span data-stu-id="18d66-181">Text</span></span>
- <span data-ttu-id="18d66-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="18d66-182">WordCount</span></span>
- <span data-ttu-id="18d66-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="18d66-183">WorkingsetId</span></span>

<span data-ttu-id="18d66-184">En definition av alla metadatafält i Advanced eDiscovery finns i [Dokumentmetadatafält](document-metadata-fields-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="18d66-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields-in-advanced-ediscovery.md).</span></span>