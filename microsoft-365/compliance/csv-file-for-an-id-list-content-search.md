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
description: Använd CSV-filer från en befintlig innehållssökning för att skapa en sökning i en ID-lista som returnerar specifika e-postmeddelanden.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161581"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="fa364-103">Förbereda en CSV-fil för en ID-lista Innehållssökning</span><span class="sxs-lookup"><span data-stu-id="fa364-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="fa364-104">Du kan söka efter specifika e-postmeddelanden och andra postlådeobjekt med hjälp av en lista Exchange-ID.</span><span class="sxs-lookup"><span data-stu-id="fa364-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="fa364-105">Om du vill skapa en sökning med ID-listor (som kallas för riktad sökning) skickar du en CSV-fil (kommaavgränsade värden) som identifierar de specifika postlådeobjekten att söka efter.</span><span class="sxs-lookup"><span data-stu-id="fa364-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="fa364-106">För den här CSV-filen använder du **Results.csv-filen** eller **Oindexerade Items.csv-filen** som tas med när du exporterar sökresultatet eller exporterar en innehållsökningsrapport från och befintlig innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="fa364-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="fa364-107">Sedan redigerar du en av dessa filer för att ange de specifika objekten som ska sökas efter, och skapar sedan en ny sökning i ID-listan och skickar CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="fa364-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="fa364-108">Här är en snabb överblick över processen för att skapa en sökning i en ID-lista.</span><span class="sxs-lookup"><span data-stu-id="fa364-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="fa364-109">Skapa och kör en ny eller guidad innehållssökning i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="fa364-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="fa364-110">Exportera innehållssökningsresultaten eller exportera rapporten för innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="fa364-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="fa364-111">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="fa364-111">For more information, see:</span></span>

    - [<span data-ttu-id="fa364-112">Exportera resultat för innehållssökning</span><span class="sxs-lookup"><span data-stu-id="fa364-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="fa364-113">Exportera en rapport för innehållssökning</span><span class="sxs-lookup"><span data-stu-id="fa364-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="fa364-114">Redigera **Results.csv** eller Icke indexerade objekt **Items.csv** och identifiera de specifika postlådeobjekt som du vill ska ingå i sökningen i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="fa364-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="fa364-115">Läs [anvisningarna för](#prepare-the-csv-file-for-an-id-list-search) att förbereda en CSV-fil för sökning i EN ID-lista.</span><span class="sxs-lookup"><span data-stu-id="fa364-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="fa364-116">Skapa en ny sökning i ID-listan (se [instruktionerna](#create-an-id-list-search)) och skicka CSV-filen som du förberett.</span><span class="sxs-lookup"><span data-stu-id="fa364-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="fa364-117">Sökningen som skapas söker bara efter de objekt som har markerats i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="fa364-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="fa364-118">Sökningar i ID-listor stöds endast för postlådeobjekt.</span><span class="sxs-lookup"><span data-stu-id="fa364-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="fa364-119">Det går inte att söka efter SharePoint och OneDrive dokument i en sökning i en ID-lista.</span><span class="sxs-lookup"><span data-stu-id="fa364-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="fa364-120">**Varför skapa en sökning i en ID-lista?**</span><span class="sxs-lookup"><span data-stu-id="fa364-120">**Why create an ID list search?**</span></span> <span data-ttu-id="fa364-121">Om du inte kan avgöra om ett objekt svarar på en eDiscovery-begäran baserat på metadata i **Results.csv-** eller **Oindexerade Items.csv-filer** kan du använda en ID-lista för att söka efter, förhandsgranska och exportera objektet för att avgöra om det svarar på det ärende som du undersöker.</span><span class="sxs-lookup"><span data-stu-id="fa364-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="fa364-122">Sökningar i ID-listor används oftast för att söka efter och returnera en viss uppsättning icke indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="fa364-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="fa364-123">Förbereda CSV-filen för sökning i ID-lista</span><span class="sxs-lookup"><span data-stu-id="fa364-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="fa364-124">När du exporterat sökresultatet eller rapporten för en innehållssökning kan du utföra följande steg för att förbereda CSV-filen för sökning i en ID-lista.</span><span class="sxs-lookup"><span data-stu-id="fa364-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="fa364-125">Den här CSV-filen identifierar alla objekt i sökningen i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="fa364-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="fa364-126">Observera att du kan använda en CSV-fil från en sökning som inkluderade SharePoint webbplatser  och OneDrive-konton, men du kan bara välja postlådeobjekt för sökning med en ID-lista.</span><span class="sxs-lookup"><span data-stu-id="fa364-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="fa364-127">Om du väljer ett dokument i SharePoint eller OneDrive misslyckas CSV-filen när du skapar en sökning i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="fa364-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="fa364-128">Öppna **Results.csv** eller **icke indexerade Items.csv** i Excel.</span><span class="sxs-lookup"><span data-stu-id="fa364-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="fa364-129">I kolumnen **Markerad** skriver du **Ja** i cellen som motsvarar objektet du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="fa364-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="fa364-130">Upprepa det här steget för alla objekt som du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="fa364-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa364-131">När du öppnar CSV-filen i Excel ändras dataformatet för kolumnen **Dokument-ID** till **Allmänt.**</span><span class="sxs-lookup"><span data-stu-id="fa364-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="fa364-132">Det leder till att dokument-ID:t för ett objekt visas i vetenskaplig notation.</span><span class="sxs-lookup"><span data-stu-id="fa364-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="fa364-133">Exempel: Dokument-ID för "481037338205" visas som "4,81037E+11" Du måste utföra nästa steg för att  ändra dataformatet i kolumnen **Dokument-ID** till Tal för att återställa rätt format för dokument-ID.</span><span class="sxs-lookup"><span data-stu-id="fa364-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="fa364-134">Om du inte gör det kommer sökningen i ID-listan som använder CSV-filen att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="fa364-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="fa364-135">Högerklicka på hela kolumnen **Dokument-ID** och välj **Formatera celler.**</span><span class="sxs-lookup"><span data-stu-id="fa364-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="fa364-136">Klicka på **Tal** i rutan **Kategori.**</span><span class="sxs-lookup"><span data-stu-id="fa364-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="fa364-137">Ändra antalet decimaler till **0** och klicka sedan på **OK för** att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="fa364-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="fa364-138">Observera att värdena i kolumnen Dokument-ID ändras till tal.</span><span class="sxs-lookup"><span data-stu-id="fa364-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="fa364-139">Här är ett exempel på en CSV-fil som kan skickas för innehållssökning i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="fa364-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![Exempel på en CSV-fil för en sökning med riktat innehåll](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="fa364-141">Spara CSV-filen eller **använd Spara som** för att spara filen med ett annat filnamn.</span><span class="sxs-lookup"><span data-stu-id="fa364-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="fa364-142">Se till att spara filen i CSV-format i båda fallen.</span><span class="sxs-lookup"><span data-stu-id="fa364-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="fa364-143">Skapa en sökning i en ID-lista</span><span class="sxs-lookup"><span data-stu-id="fa364-143">Create an ID list search</span></span>

<span data-ttu-id="fa364-144">Nästa steg är att skapa en ny ID-lista Innehållssökning och skicka CSV-filen som du förberett i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="fa364-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa364-145">Du bör skapa en sökning i ID-listan högst 2 dagar efter att du exporterat resultatet eller rapporten från en innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="fa364-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="fa364-146">Om sökresultatet eller rapporten som exporterades för mer än två dagar sedan bör du exportera om sökresultatet eller rapporten för att generera uppdaterade CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="fa364-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="fa364-147">Sedan kan du förbereda en av de uppdaterade CSV-filerna och använda den för att skapa en sökning i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="fa364-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="fa364-148">Gå till Sök & i **Säkerhets- och** \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="fa364-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="fa364-149">På sidan **Sök** klickar du på pilen bredvid Lägg ![ till-ikonen ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Ny sökning** och klickar sedan på Sök efter **ID-lista**.</span><span class="sxs-lookup"><span data-stu-id="fa364-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![Klicka på Sök efter ID-lista i listrutan Ny sökning](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="fa364-151">På den **utfällbara** menyn Sök efter ID ger du sökningen  ett namn (och beskriver den om det). Klicka sedan på Bläddra och välj CSV-filen som du förberedde i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="fa364-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="fa364-152">Microsoft 365 försöker verifiera CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="fa364-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="fa364-153">Om verifieringen inte lyckas visas ett felmeddelande som kan hjälpa dig att felsöka verifieringsfelen.</span><span class="sxs-lookup"><span data-stu-id="fa364-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="fa364-154">CSV-filen måste valideras för att du ska kunna skapa en sökning i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="fa364-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="fa364-155">När CSV-filen har verifierats klickar du på **Sök för** att skapa sökningen i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="fa364-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="fa364-156">Här är ett exempel på det uppskattade sökresultatet och frågan som genereras för sökning med ID-listor.</span><span class="sxs-lookup"><span data-stu-id="fa364-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![Sökfråga för en riktad innehållssökning i informationsfönstret](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="fa364-158">Observera att det uppskattade antalet objekt som visas i statistik för ID-sökningen ska matcha antalet objekt som du valde i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="fa364-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="fa364-159">Förhandsgranska eller exportera de objekt som returneras av sökningen i ID-listan.</span><span class="sxs-lookup"><span data-stu-id="fa364-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="fa364-160">Om du flyttar en postlåda efter att ha skapat en sökning i ID-listan returnerar frågan för sökningen inte de angivna objekten.</span><span class="sxs-lookup"><span data-stu-id="fa364-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="fa364-161">Det beror på att egenskapen **DocumentId** för postlådeobjekt ändras när en postlåda flyttas.</span><span class="sxs-lookup"><span data-stu-id="fa364-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="fa364-162">I den sällsynta instansen när en postlåda flyttas när du har skapat en sökning i en ID-lista ska du skapa en ny innehållssökning (eller uppdatera sökresultaten för den befintliga innehållssökningen) och sedan exportera sökresultatet eller rapporten för att generera uppdaterade CSV-filer som kan användas för att skapa en ny ID-lista.</span><span class="sxs-lookup"><span data-stu-id="fa364-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
