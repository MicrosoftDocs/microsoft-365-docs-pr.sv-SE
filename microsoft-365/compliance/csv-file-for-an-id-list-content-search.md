---
title: Förbereda en CSV-fil för en ID-lista Innehållssökning
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Använd en CSV-fil från en befintlig innehållssökning om du vill skapa en sökning i en ID-lista som returnerar specifika e-postobjekt.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311558"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="5ff66-103">Förbereda en CSV-fil för en ID-lista Innehållssökning</span><span class="sxs-lookup"><span data-stu-id="5ff66-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="5ff66-104">Du kan söka efter specifika e-postmeddelanden och andra postlådeobjekt med hjälp av en lista Exchange-ID.</span><span class="sxs-lookup"><span data-stu-id="5ff66-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="5ff66-105">Om du vill skapa en sökning med en ID-lista skickar du en fil med kommaavgränsade värden (CSV) som identifierar de specifika postlådeobjekt som du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="5ff66-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="5ff66-106">För den här CSV-filen använder du **Results.csv-filen** eller icke indexerade **Items.csv-filen** som tas med när du exporterar sökresultatet för innehåll eller exporterar en innehållssökningsrapport från en befintlig innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="5ff66-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="5ff66-107">Sedan redigerar du en av dessa filer för att ange specifika objekt att söka efter, skapa en ny sökning i ID-listan och skicka CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="5ff66-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="5ff66-108">**Varför skapa en sökning i en ID-lista?**</span><span class="sxs-lookup"><span data-stu-id="5ff66-108">**Why create an ID list search?**</span></span> <span data-ttu-id="5ff66-109">Om du inte kan avgöra om ett objekt svarar på en eDiscovery-begäran baserat på metadata i **Results.csv-** eller **Oindexerade Items.csv-filer** kan du använda en ID-lista för att söka efter, förhandsgranska och exportera objektet för att avgöra om det svarar på det ärende som du undersöker.</span><span class="sxs-lookup"><span data-stu-id="5ff66-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="5ff66-110">Sökningar i ID-listor används oftast för att söka efter och returnera en viss uppsättning icke indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="5ff66-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="5ff66-111">Här är en snabb överblick över processen för att skapa en sökning i en ID-lista.</span><span class="sxs-lookup"><span data-stu-id="5ff66-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="5ff66-112">Skapa och kör en ny sökning i Microsoft 365 kompatibilitetscenter.</span><span class="sxs-lookup"><span data-stu-id="5ff66-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="5ff66-113">Exportera sökresultaten eller rapporten för innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="5ff66-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="5ff66-114">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="5ff66-114">For more information, see:</span></span>

    - [<span data-ttu-id="5ff66-115">Exportera resultat av innehållssökning</span><span class="sxs-lookup"><span data-stu-id="5ff66-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="5ff66-116">Exportera en innehållssökningsrapport</span><span class="sxs-lookup"><span data-stu-id="5ff66-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="5ff66-117">Redigera filen **Results.csv** icke **indexerade eItems.csvpostlådor** och identifiera de specifika postlådeobjekt som ska ingå i sökningen i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="5ff66-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="5ff66-118">Läs [anvisningarna för](#prepare-the-csv-file-for-an-id-list-search) att förbereda en CSV-fil för sökning i EN ID-lista.</span><span class="sxs-lookup"><span data-stu-id="5ff66-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="5ff66-119">Skapa en ny sökning i ID-listan (se [instruktionerna](#create-an-id-list-search)) och skicka CSV-filen som du förberett.</span><span class="sxs-lookup"><span data-stu-id="5ff66-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="5ff66-120">Sökningen som skapas söker bara efter de objekt som har markerats i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="5ff66-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="5ff66-121">Sökningar i ID-listor stöds endast för postlådeobjekt.</span><span class="sxs-lookup"><span data-stu-id="5ff66-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="5ff66-122">Det går inte att söka efter SharePoint och OneDrive dokument i en sökning i en ID-lista.</span><span class="sxs-lookup"><span data-stu-id="5ff66-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="5ff66-123">Förbereda CSV-filen för sökning i ID-lista</span><span class="sxs-lookup"><span data-stu-id="5ff66-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="5ff66-124">När du exporterat sökresultatet eller rapporten för en sökning utför du följande steg för att förbereda CSV-filen för en sökning i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="5ff66-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="5ff66-125">Den här CSV-filen identifierar alla objekt i sökningen i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="5ff66-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="5ff66-126">Du kan använda en CSV-fil från en sökning som inkluderade SharePoint-webbplatser och OneDrive-konton, men du kan bara välja postlådeobjekt för sökning i en ID-lista.</span><span class="sxs-lookup"><span data-stu-id="5ff66-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="5ff66-127">Om du väljer ett dokument i SharePoint eller OneDrive misslyckas CSV-filen när du skapar en sökning i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="5ff66-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="5ff66-128">Öppna **Results.csv** eller **icke indexerade Items.csv** i Excel.</span><span class="sxs-lookup"><span data-stu-id="5ff66-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="5ff66-129">I kolumnen **Markerad** skriver du **Ja** i cellen som motsvarar objektet du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="5ff66-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="5ff66-130">Upprepa det här steget för alla objekt som du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="5ff66-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5ff66-131">När du öppnar CSV-filen i Excel kan dataformatet för kolumnen **Dokument-ID** ha ändrats till **Allmänt.**</span><span class="sxs-lookup"><span data-stu-id="5ff66-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="5ff66-132">Det leder till att dokument-ID:t för ett objekt visas i vetenskaplig notation.</span><span class="sxs-lookup"><span data-stu-id="5ff66-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="5ff66-133">Dokument-ID för "481037338205" visas till exempel som "4,81037E+11".</span><span class="sxs-lookup"><span data-stu-id="5ff66-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="5ff66-134">Om det händer måste du utföra nästa steg för att ändra  dataformatet i kolumnen **Dokument-ID** till Tal för att återställa rätt format för dokument-ID.</span><span class="sxs-lookup"><span data-stu-id="5ff66-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="5ff66-135">Om du inte gör det kommer sökningen i ID-listan som använder CSV-filen att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="5ff66-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="5ff66-136">Högerklicka på hela kolumnen **Dokument-ID** och välj **Formatera celler.**</span><span class="sxs-lookup"><span data-stu-id="5ff66-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="5ff66-137">Klicka på **Tal** i rutan **Kategori.**</span><span class="sxs-lookup"><span data-stu-id="5ff66-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="5ff66-138">Ändra antalet decimaler till **0** och klicka sedan på **OK för** att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="5ff66-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="5ff66-139">Observera att värdena i kolumnen Dokument-ID ändras till tal.</span><span class="sxs-lookup"><span data-stu-id="5ff66-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="5ff66-140">Här är ett exempel på en CSV-fil som kan skickas för innehållssökning med ID-listor.</span><span class="sxs-lookup"><span data-stu-id="5ff66-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![Exempel på en CSV-fil för en sökning med riktat innehåll](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="5ff66-142">Spara CSV-filen eller **använd Spara som** för att spara filen med ett annat filnamn.</span><span class="sxs-lookup"><span data-stu-id="5ff66-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="5ff66-143">Se till att spara filen i CSV-format i båda fallen.</span><span class="sxs-lookup"><span data-stu-id="5ff66-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="5ff66-144">Skapa en sökning i en ID-lista</span><span class="sxs-lookup"><span data-stu-id="5ff66-144">Create an ID list search</span></span>

<span data-ttu-id="5ff66-145">Nästa steg är att skapa en ny sökning i ID-listan och skicka CSV-filen som du förberett i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="5ff66-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ff66-146">Du bör skapa en sökning i ID-listan högst 2 dagar efter att du exporterat sökresultatet eller rapporten.</span><span class="sxs-lookup"><span data-stu-id="5ff66-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="5ff66-147">Om sökresultatet eller rapporten som exporterades för mer än två dagar sedan bör du exportera om sökresultatet eller rapporten för att generera uppdaterade CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="5ff66-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="5ff66-148">Sedan kan du förbereda en av de uppdaterade CSV-filerna och använda den för att skapa en sökning i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="5ff66-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="5ff66-149">Gå till <https://compliance.microsoft.com> och logga in.</span><span class="sxs-lookup"><span data-stu-id="5ff66-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="5ff66-150">I det vänstra navigeringsfönstret i Microsoft 365 Efterlevnadscenter klickar du på **Visa alla** och sedan på **Innehållssökning**.</span><span class="sxs-lookup"><span data-stu-id="5ff66-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="5ff66-151">Klicka på **Sök efter** ID-lista på **sidan Innehållssökning.**</span><span class="sxs-lookup"><span data-stu-id="5ff66-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="5ff66-152">På den **utfällbara** menyn Sök efter ID ger du sökningen  ett namn (och beskriver den om det). Klicka sedan på Bläddra och välj CSV-filen som du förberedde i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="5ff66-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="5ff66-153">Microsoft 365 försöker verifiera CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="5ff66-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="5ff66-154">Om verifieringen inte lyckas visas ett felmeddelande som kan hjälpa dig att felsöka verifieringsfelen.</span><span class="sxs-lookup"><span data-stu-id="5ff66-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="5ff66-155">CSV-filen måste valideras för att du ska kunna skapa en sökning i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="5ff66-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="5ff66-156">När CSV-filen har verifierats klickar du på **Sök för** att skapa sökningen i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="5ff66-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="5ff66-157">Här är ett exempel på den utfällade sidan från en sökning i ID-listan som visar den fråga som genereras och det uppskattade antalet sökresultat.</span><span class="sxs-lookup"><span data-stu-id="5ff66-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![Sökfråga för sökning i ID-lista](../media/SearchIDListFlyout.png)

    <span data-ttu-id="5ff66-159">Det uppskattade antalet objekt som visas i statistik för ID-sökningen ska matcha antalet objekt som du valde i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="5ff66-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="5ff66-160">Förhandsgranska eller exportera de objekt som returneras av sökningen i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="5ff66-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="5ff66-161">Mer information</span><span class="sxs-lookup"><span data-stu-id="5ff66-161">More information</span></span>

<span data-ttu-id="5ff66-162">Om du flyttar en postlåda efter att ha skapat en sökning i ID-listan returnerar frågan för sökningen inte de angivna objekten.</span><span class="sxs-lookup"><span data-stu-id="5ff66-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="5ff66-163">Det beror på att egenskapen **DocumentId** för postlådeobjekt ändras när en postlåda flyttas.</span><span class="sxs-lookup"><span data-stu-id="5ff66-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="5ff66-164">I den sällsynta instansen när en postlåda flyttas när du har skapat en sökning i en ID-lista bör du skapa en ny innehållssökning (eller uppdatera sökresultatet för en befintlig sökning) och sedan exportera sökresultatet eller rapporten för att generera uppdaterade CSV-filer som kan användas för att skapa en ny ID-lista.</span><span class="sxs-lookup"><span data-stu-id="5ff66-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
