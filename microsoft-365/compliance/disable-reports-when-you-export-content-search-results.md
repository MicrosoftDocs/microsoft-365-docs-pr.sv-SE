---
title: Inaktivera rapporter när du exporterar innehållssökningsresultat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Redigera Windows-registret på den lokala datorn om du vill inaktivera rapporter när du exporterar resultatet av en innehållssökning från säkerhets- & kompatibilitetscentret.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161579"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="55e22-103">Inaktivera rapporter när du exporterar innehållssökningsresultat</span><span class="sxs-lookup"><span data-stu-id="55e22-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="55e22-104">När du använder verktyget för eDiscovery-export för att exportera resultatet av en innehållssökning i säkerhets- och efterlevnadscentret för & skapar och exporterar verktyget automatiskt två rapporter som innehåller ytterligare information om det exporterade innehållet.</span><span class="sxs-lookup"><span data-stu-id="55e22-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="55e22-105">De här rapporterna Results.csv filen och Manifest.xml (se avsnittet Vanliga frågor och svar om hur du inaktiverar [exportrapporter](#frequently-asked-questions-about-disabling-export-reports) i det här avsnittet för detaljerade beskrivningar av rapporterna).</span><span class="sxs-lookup"><span data-stu-id="55e22-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="55e22-106">Eftersom dessa filer kan vara mycket stora kan du snabba upp nedladdningstiden och spara diskutrymme genom att förhindra att filerna exporteras.</span><span class="sxs-lookup"><span data-stu-id="55e22-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="55e22-107">Det kan du göra genom att Windows i registret på datorn som du använder för att exportera sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="55e22-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="55e22-108">Om du vill ta med rapporterna vid ett senare tillfälle kan du redigera registerinställningen.</span><span class="sxs-lookup"><span data-stu-id="55e22-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="55e22-109">Skapa registerinställningar för att inaktivera exportrapporterna</span><span class="sxs-lookup"><span data-stu-id="55e22-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="55e22-110">Gör följande på den dator som du använder för att exportera resultatet en innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="55e22-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="55e22-111">Stäng verktyget eDiscovery Export om det är öppet.</span><span class="sxs-lookup"><span data-stu-id="55e22-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="55e22-112">Utför en eller båda av följande steg, beroende på vilken exportrapport du vill inaktivera.</span><span class="sxs-lookup"><span data-stu-id="55e22-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="55e22-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="55e22-113">**Results.csv**</span></span>
    
      <span data-ttu-id="55e22-114">Spara följande text i en Windows med hjälp av filnamnssuffixet REG. till exempel DisableResultsCsv.reg.</span><span class="sxs-lookup"><span data-stu-id="55e22-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="55e22-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="55e22-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="55e22-116">Spara följande text i en Windows med hjälp av filnamnssuffixet REG. till exempel DisableManifestXml.reg.</span><span class="sxs-lookup"><span data-stu-id="55e22-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="55e22-117">I Windows i Utforskaren klickar eller dubbelklickar du på REG-filen som du skapade i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="55e22-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="55e22-118">I fönstret User Access Control klickar du på **Ja** så att Registereditorn kan göra ändringen.</span><span class="sxs-lookup"><span data-stu-id="55e22-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="55e22-119">När du uppmanas att fortsätta klickar du på **Ja.**</span><span class="sxs-lookup"><span data-stu-id="55e22-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="55e22-120">Registereditorn visar ett meddelande om att inställningen har lagts till i registret.</span><span class="sxs-lookup"><span data-stu-id="55e22-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="55e22-121">Redigera registerinställningar för att återaktivera exportrapporterna</span><span class="sxs-lookup"><span data-stu-id="55e22-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="55e22-122">Om du inaktiverade Results.csv- och Manifest.xml-rapporterna genom att skapa REG-filerna i föregående procedur kan du redigera filerna och återaktivera rapporten så att den exporteras med sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="55e22-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="55e22-123">Gör på nytt följande på den dator som du använder för att exportera resultatet en innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="55e22-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="55e22-124">Stäng verktyget eDiscovery Export om det är öppet.</span><span class="sxs-lookup"><span data-stu-id="55e22-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="55e22-125">Redigera en eller båda .reg-redigeringsfilerna som du skapade i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="55e22-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="55e22-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="55e22-126">**Results.csv**</span></span>
    
        <span data-ttu-id="55e22-127">Öppna filen DisableResultsCsv.reg Anteckningar, ändra värdet till `False` `True` och spara sedan filen.</span><span class="sxs-lookup"><span data-stu-id="55e22-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="55e22-128">När du har redigerat filen ser den till exempel ut så här:</span><span class="sxs-lookup"><span data-stu-id="55e22-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="55e22-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="55e22-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="55e22-130">Öppna filen DisableManifestXml.reg i Anteckningar, ändra värdet till `False` `True` och spara sedan filen.</span><span class="sxs-lookup"><span data-stu-id="55e22-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="55e22-131">När du har redigerat filen ser den till exempel ut så här:</span><span class="sxs-lookup"><span data-stu-id="55e22-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="55e22-132">I Windows i Utforskaren klickar eller dubbelklickar du på en REG-fil som du redigerade i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="55e22-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="55e22-133">I fönstret User Access Control klickar du på **Ja** så att Registereditorn kan göra ändringen.</span><span class="sxs-lookup"><span data-stu-id="55e22-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="55e22-134">När du uppmanas att fortsätta klickar du på **Ja.**</span><span class="sxs-lookup"><span data-stu-id="55e22-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="55e22-135">Registereditorn visar ett meddelande om att inställningen har lagts till i registret.</span><span class="sxs-lookup"><span data-stu-id="55e22-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="55e22-136">Vanliga frågor och svar om hur du inaktiverar exportrapporter</span><span class="sxs-lookup"><span data-stu-id="55e22-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="55e22-137">**Vilka är Results.csv och Manifest.xml rapporter?**</span><span class="sxs-lookup"><span data-stu-id="55e22-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="55e22-138">Filen Results.csv och Manifest.xml innehåller ytterligare information om det innehåll som exporterades.</span><span class="sxs-lookup"><span data-stu-id="55e22-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="55e22-139">**Results.csv** Ett Excel som innehåller information om varje objekt som hämtas som sökresultat.</span><span class="sxs-lookup"><span data-stu-id="55e22-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="55e22-140">För e-post innehåller resultatloggen information om varje meddelande, inklusive:</span><span class="sxs-lookup"><span data-stu-id="55e22-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="55e22-141">Platsen för meddelandet i källpostlådan (inklusive om meddelandet finns i den primära postlådan eller arkivpostlådan).</span><span class="sxs-lookup"><span data-stu-id="55e22-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="55e22-142">Datumet då meddelandet skickades eller togs emot.</span><span class="sxs-lookup"><span data-stu-id="55e22-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="55e22-143">Ämnesraden från meddelandet.</span><span class="sxs-lookup"><span data-stu-id="55e22-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="55e22-144">Meddelandets avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="55e22-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="55e22-145">Om meddelandet är ett duplicerat meddelande om du har aktiverat avduplicering när du exporterar sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="55e22-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="55e22-146">Dubblettmeddelanden har ett värde i den överordnade **ItemId-kolumnen** som identifierar meddelandet som en dubblett.</span><span class="sxs-lookup"><span data-stu-id="55e22-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="55e22-147">Värdet i kolumnen **Överordnat ItemId** är detsamma som värdet i kolumnen **Item DocumentId** för meddelandet som exporterades.</span><span class="sxs-lookup"><span data-stu-id="55e22-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="55e22-148">För dokument SharePoint och OneDrive för företag innehåller resultatloggen information om varje dokument, inklusive:</span><span class="sxs-lookup"><span data-stu-id="55e22-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="55e22-149">URL-adressen för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="55e22-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="55e22-150">URL-adressen för webbplatssamlingen där dokumentet finns.</span><span class="sxs-lookup"><span data-stu-id="55e22-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="55e22-151">Datumet då dokumentet senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="55e22-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="55e22-152">Namnet på dokumentet (som finns i kolumnen Ämne i resultatloggen).</span><span class="sxs-lookup"><span data-stu-id="55e22-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="55e22-153">**Manifest.xml** En manifestfil (i XML-format) som innehåller information om varje objekt som ingår i sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="55e22-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="55e22-154">Informationen i den här rapporten är densamma som Results.csv, men den är i det format som anges av EDRM (Electronic Discovery Reference Model).</span><span class="sxs-lookup"><span data-stu-id="55e22-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="55e22-155">Mer information om EDRM finns i [https://www.edrm.net](https://www.edrm.net) .</span><span class="sxs-lookup"><span data-stu-id="55e22-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="55e22-156">**När bör jag inaktivera exporten av rapporterna?**</span><span class="sxs-lookup"><span data-stu-id="55e22-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="55e22-157">Det beror på dina specifika behov.</span><span class="sxs-lookup"><span data-stu-id="55e22-157">It depends on your specific needs.</span></span> <span data-ttu-id="55e22-158">Många organisationer behöver ingen ytterligare information om sökresultat och dessa rapporter behövs inte.</span><span class="sxs-lookup"><span data-stu-id="55e22-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="55e22-159">**Vilken dator måste jag göra detta på?**</span><span class="sxs-lookup"><span data-stu-id="55e22-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="55e22-160">Du måste ändra registerinställningen på alla lokala datorer där du kör verktyget för eDiscovery-export.</span><span class="sxs-lookup"><span data-stu-id="55e22-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="55e22-161">**Måste jag starta om datorn när jag har ändrat den här inställningen?**</span><span class="sxs-lookup"><span data-stu-id="55e22-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="55e22-162">Nej, du behöver inte starta om datorn.</span><span class="sxs-lookup"><span data-stu-id="55e22-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="55e22-163">Men om verktyget för eDiscovery-export körs måste du stänga det och starta om det när du har ändrat registerinställningen.</span><span class="sxs-lookup"><span data-stu-id="55e22-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="55e22-164">**Redigeras en befintlig registernyckel, eller skapas en ny nyckel?**</span><span class="sxs-lookup"><span data-stu-id="55e22-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="55e22-165">En ny registernyckel skapas första gången du kör REG-filen som du skapade i proceduren i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="55e22-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="55e22-166">Sedan redigeras inställningen varje gång du ändrar och kör .reg-redigeringsfilen på ny gång.</span><span class="sxs-lookup"><span data-stu-id="55e22-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
