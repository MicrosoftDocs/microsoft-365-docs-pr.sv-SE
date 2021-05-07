---
title: Exportera dokument till organisationens Azure Storage konto
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
ms.custom: seo-marvel-mar2020
description: Exportera dokument i en granskning som är inställd på Azure Storage konto och använd sedan Azure Storage Explorer att ladda ned dem till en lokal dator.
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162637"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a><span data-ttu-id="e7d8a-103">Exportera dokument i en granskning som är inställd på ett Azure Storage konto</span><span class="sxs-lookup"><span data-stu-id="e7d8a-103">Export documents in a review set to an Azure Storage account</span></span>

<span data-ttu-id="e7d8a-104">När du exporterar dokument från en granskning i ett Advanced eDiscovery fall kan du exportera dem till ett Azure Storage konto som hanteras av din organisation.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-104">When you export documents from a review set in an Advanced eDiscovery case, you have the option to export them to an Azure Storage account managed by your organization.</span></span> <span data-ttu-id="e7d8a-105">Om du använde det här alternativet laddas dokumenten upp till din Azure Storage plats.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-105">If you used this option, the documents are uploaded to your Azure Storage location.</span></span> <span data-ttu-id="e7d8a-106">När de har exporterats kan du komma åt dokumenten (och ladda ned dem till en lokal dator eller annan plats) med hjälp av Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-106">After they are exported, you can access the documents (and download them to a local computer or other location) by using the Azure Storage Explorer.</span></span> <span data-ttu-id="e7d8a-107">Den här artikeln innehåller instruktioner för hur du exporterar dokument till ditt Azure Storage-konto och hur du använder Azure Storage Explorer för att ansluta till en Azure Storage-plats för att ladda ned exporterade dokument.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-107">This article provides instructions for how to export documents to your Azure Storage account and the use the Azure Storage Explorer to connect to an Azure Storage location to download the exported documents.</span></span> <span data-ttu-id="e7d8a-108">Mer information om Azure Storage Explorer finns i [Använda Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span><span class="sxs-lookup"><span data-stu-id="e7d8a-108">For more information about Azure Storage Explorer, see [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="before-you-export-documents-from-a-review-set"></a><span data-ttu-id="e7d8a-109">Innan du exporterar dokument från en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="e7d8a-109">Before you export documents from a review set</span></span>

- <span data-ttu-id="e7d8a-110">Du måste ange en SAS-token (delad åtkomstsignatur) för ditt Azure Storage-konto och URL-adressen för en viss behållare i lagringskontot för att exportera dokument från en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-110">You need to provide a shared access signature (SAS) token for your Azure Storage account and the URL for a specific container in the storage account to export documents from a review set.</span></span> <span data-ttu-id="e7d8a-111">Se till att ha dessa nära till hands (t.ex. kopierad till en textfil) när du utför steg 2</span><span class="sxs-lookup"><span data-stu-id="e7d8a-111">Be sure to have these at hand (for example, copied to a text file) when you perform Step 2</span></span>

  - <span data-ttu-id="e7d8a-112">**SAS token:** Se till att få SAS token är för ditt Azure Storage konto (och inte för behållaren).</span><span class="sxs-lookup"><span data-stu-id="e7d8a-112">**SAS token**: Be sure to get the SAS token is for your Azure Storage account (and not for the container).</span></span> <span data-ttu-id="e7d8a-113">Du kan generera en SAS-token för ditt konto i Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-113">You can generate an SAS token for your account in Azure Storage.</span></span> <span data-ttu-id="e7d8a-114">Det gör du genom att gå Azure Storage kontot och välja Dela åtkomstsignatur **under** Inställningar **inställningarna** i bladet för lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-114">To do this, go to the Azure Storage account, and select **Share access signature** under the **Settings** settings in the storage account blade.</span></span> <span data-ttu-id="e7d8a-115">Använd standardinställningarna och tillåt alla resurstyper när du genererar SAS-token.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-115">Use the default settings and allow all resource types when you generate the SAS token.</span></span>

  - <span data-ttu-id="e7d8a-116">**Behållar-URL:** Du måste skapa en behållare för att ladda upp granskningsuppsättningsdokumenten till och sedan få en kopia av URL-adressen för behållaren. till exempel `https://ediscoverydata.blob.core.windows.net/exportdata` .</span><span class="sxs-lookup"><span data-stu-id="e7d8a-116">**Container URL**: You need to create a container to upload the review set documents to, and then get a copy of the URL for the container; for example, `https://ediscoverydata.blob.core.windows.net/exportdata`.</span></span> <span data-ttu-id="e7d8a-117">Om du vill hämta URL:en går du till behållaren i Azure Storage och väljer **Egenskaper** under **Inställningar** i behållarbladet.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-117">To get the URL, go to the container in Azure Storage, and select **Properties** under the **Settings** section in the container blade.</span></span>

- <span data-ttu-id="e7d8a-118">Ladda ned och installera Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-118">Download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="e7d8a-119">Instruktioner finns i [Azure Storage Explorer verktyg](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span><span class="sxs-lookup"><span data-stu-id="e7d8a-119">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="e7d8a-120">Du använder det här verktyget för att ansluta till behållaren i Azure Storage-konto och ladda ned de dokument som du exporterade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-120">You use this tool to connect to the container in your Azure Storage account and download the documents that you exported in Step 1.</span></span>

## <a name="step-1-export-the-documents-from-a-review-set"></a><span data-ttu-id="e7d8a-121">Steg 1: Exportera dokument från en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="e7d8a-121">Step 1: Export the documents from a review set</span></span>

<span data-ttu-id="e7d8a-122">Det första steget är att skapa ett exportjobb för att exportera dokument från en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-122">The first step is to create an export job to export documents out of a review set.</span></span> <span data-ttu-id="e7d8a-123">Mer detaljerade anvisningar om alla exportalternativ finns i [Exportera dokument från en granskningsuppsättning](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="e7d8a-123">For more detailed instructions about all the export options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="e7d8a-124">I följande procedur markeras inställningarna för att exportera dokument till organisationens Azure Storage konto.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-124">The following procedure highlights the settings to export documents to your organization's Azure Storage account.</span></span>

1. <span data-ttu-id="e7d8a-125">I Microsoft 365 kompatibilitetscenter öppnar du Advanced eDiscovery, väljer fliken Granska **uppsättningar** och väljer sedan den granskningsuppsättning som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-125">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="e7d8a-126">Klicka på Åtgärdsexport i   >  **granskningsuppsättningen.**</span><span class="sxs-lookup"><span data-stu-id="e7d8a-126">In the review set, click **Action** > **Export**.</span></span>

3. <span data-ttu-id="e7d8a-127">På den **utfällbara** sidan Exportalternativ skriver du ett namn (obligatoriskt) och en beskrivning (valfritt) för exporten.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-127">On the **Export options** flyout page, type a name (required) and description (optional) for the export.</span></span>

4. <span data-ttu-id="e7d8a-128">Konfigurera inställningarna i avsnitten dokument, metadata, innehåll och alternativ.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-128">Configure the settings in the documents, metadata, content, and options sections.</span></span> <span data-ttu-id="e7d8a-129">Mer information om de här inställningarna finns i [Exportera dokument från en granskningsuppsättning](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="e7d8a-129">For more information about these settings, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

5. <span data-ttu-id="e7d8a-130">I avsnittet **Utdataalternativ** väljer du **alternativet Komprimerad katalogstruktur som exporterats till Azure Storage konto.**</span><span class="sxs-lookup"><span data-stu-id="e7d8a-130">In the **Output options** section, select the **Condensed directory structure exported to your Azure Storage account** option.</span></span>

6. <span data-ttu-id="e7d8a-131">Klistra in behållar-URL:en och SAS-token för ditt lagringskonto i motsvarande fält.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-131">Paste the container URL and the SAS token for your storage account in the corresponding fields.</span></span>

   ![Klistra in anslutnings-URL:en och SAS-token i motsvarande fält](../media/AzureStorageOutputOptions.png)

7. <span data-ttu-id="e7d8a-133">Klicka **på Exportera** för att skapa exportjobbet.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-133">Click **Export** to create the export job.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="e7d8a-134">Steg 2: Hämta SAS URL från exportjobbet</span><span class="sxs-lookup"><span data-stu-id="e7d8a-134">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="e7d8a-135">Nästa steg är att hämta SAS URL som genereras när du har skapat exportjobbet i steg 1.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-135">The next step is to obtain the SAS URL that's generated after you create the export job in Step 1.</span></span> <span data-ttu-id="e7d8a-136">Du använder SAS URL för att ansluta till behållaren i ditt Azure Storage konto som du exporterade granskningsuppsättningsdokumenten till.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-136">You use the SAS URL to connect to the container in your Azure Storage account that you exported the review set documents to.</span></span>

1. <span data-ttu-id="e7d8a-137">På **Advanced eDiscovery** sidan går du till ärendet och klickar sedan på **fliken Exporter.**</span><span class="sxs-lookup"><span data-stu-id="e7d8a-137">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="e7d8a-138">Klicka på **det** exportjobb som du vill ladda ned på fliken Exporter.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-138">On the **Exports** tab, click the export job that you want to download.</span></span> <span data-ttu-id="e7d8a-139">Det här är exportjobbet som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-139">This is the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="e7d8a-140">På den utfällade **sidan, under Platser,** kopierar du SAS URL som visas.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-140">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="e7d8a-141">Om det behövs kan du spara den i en textfil så att du kan komma åt den i steg 3.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-141">If necessary, you can save it to a text file so you can access it in Step 3.</span></span>

   ![Kopiera SAS URL som visas under Platser](../media/eDiscoExportJob.png)

   > [!TIP]
   > <span data-ttu-id="e7d8a-143">SAS URL som visas i exportjobbet är en sammanfogning av behållar-URL:en och SAS-token för ditt Azure Storage konto.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-143">The SAS URL that's displayed in the export job is a concatenation of the container URL and the SAS token for your Azure Storage account.</span></span> <span data-ttu-id="e7d8a-144">Du kan kopiera det från exportjobbet eller skapa det själv genom att kombinera URL- och SAS-token.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-144">You can copy it from the export job or create it yourself by combining the URL and the SAS token.</span></span>

## <a name="step-3-connect-to-the-azure-storage-container"></a><span data-ttu-id="e7d8a-145">Steg 3: Anslut till Azure Storage behållare</span><span class="sxs-lookup"><span data-stu-id="e7d8a-145">Step 3: Connect to the Azure Storage container</span></span>

<span data-ttu-id="e7d8a-146">Det sista steget är att använda Azure Storage Explorer och SAS URL för att ansluta till behållaren i ditt Azure Storage-konto och ladda ned exporterade dokument till en lokal dator.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-146">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the container in your Azure Storage account and download the exported documents to a local computer.</span></span>

1. <span data-ttu-id="e7d8a-147">Starta den Azure Storage Explorer du har laddat ned och installerat.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-147">Start the Azure Storage Explorer that you downloaded and installed.</span></span>

2. <span data-ttu-id="e7d8a-148">Klicka på **ikonen Anslut dialogruta.**</span><span class="sxs-lookup"><span data-stu-id="e7d8a-148">Click the **Open Connect Dialog** icon.</span></span>

   ![Klicka på ikonen Lägg till konto](../media/AzureStorageConnect.png)

3. <span data-ttu-id="e7d8a-150">På sidan **Anslut att Azure Storage** klickar du på **Blob-behållare**.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-150">On the **Connect to Azure Storage** page, click **Blob container**.</span></span>

4. <span data-ttu-id="e7d8a-151">På sidan **Välj autentiseringsmetod** väljer du alternativet **Delad åtkomstsignatur (SAS) och** klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="e7d8a-151">On the **Select Authentication Method** page, select the **Shared access signature (SAS)** option and then click **Next**.</span></span>

5. <span data-ttu-id="e7d8a-152">På sidan **Ange anslutningsinformation** klistrar du in SAS URL (som du fick i exportjobbet i steg 2) i **RUTAN SAS URL för Blob Container.**</span><span class="sxs-lookup"><span data-stu-id="e7d8a-152">On the **Enter Connection Info** page, paste the SAS URL (that you obtained in the export job in Step 2) in the **Blob Container SAS URL** box.</span></span>

    ![Klistra in SAS URL i rutan URI](../media/AzureStorageConnect3.png)

    <span data-ttu-id="e7d8a-154">Observera att behållarnamnet visas i **rutan Visningsnamn.**</span><span class="sxs-lookup"><span data-stu-id="e7d8a-154">Notice that the container name is displayed in the **Display name** box.</span></span> <span data-ttu-id="e7d8a-155">Du kan redigera det här namnet.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-155">You can edit this name.</span></span>

6. <span data-ttu-id="e7d8a-156">Klicka **på Nästa** för att visa **sammanfattningssidan** och klicka sedan på **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-156">Click **Next** to display the **summary** page and then click **Connect**.</span></span>

    <span data-ttu-id="e7d8a-157">**Blob-behållare-noden** **(Storage konton**  >  **(bifogade behållare)** \> öppnas.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-157">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Exportera jobb i noden Blobs-behållare](../media/AzureStorageConnect5.png)

    <span data-ttu-id="e7d8a-159">Den innehåller en behållare med namnet från steg 5.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-159">It contains a container named with the display name from step 5.</span></span> <span data-ttu-id="e7d8a-160">Den här behållaren innehåller en mapp för varje exportjobb som du har laddat ned till behållaren i Azure Storage konto.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-160">This container contains a folder for each export job that you've downloaded to the container in your Azure Storage account.</span></span> <span data-ttu-id="e7d8a-161">De här mapparna namnges med ett ID som motsvarar ID för exportjobbet.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-161">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="e7d8a-162">Du hittar export-ID:n (och namnet på exporten) under **Supportinformation** på den utfällda  sidan för varje Förbereda data för **exportjobb** som finns på fliken Jobb i Advanced eDiscovery fall.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-162">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab in the Advanced eDiscovery case.</span></span>

7. <span data-ttu-id="e7d8a-163">Dubbelklicka på mappen exportera jobb för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-163">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="e7d8a-164">En lista med mappar och exportrapporter visas.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-164">A list of folders and export reports is displayed.</span></span>

    ![Exportmappen innehåller exporterade filer och exportrapporter](../media/AzureStorageConnect6.png)

8. <span data-ttu-id="e7d8a-166">Om du vill exportera allt innehåll  från exportjobbet klickar du på uppåtpilen för att gå tillbaka till exportjobbmappen och klickar sedan på **Ladda ned.**</span><span class="sxs-lookup"><span data-stu-id="e7d8a-166">To export all contents from the export job, click the **Up** arrow to go back to the export job folder, and then click **Download**.</span></span>

9. <span data-ttu-id="e7d8a-167">Ange den plats där du vill ladda ned de exporterade filerna och klicka sedan på Välj mapp.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-167">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="e7d8a-168">Filen Azure Storage Explorer startar nedladdningen.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-168">The Azure Storage Explorer starts the download process.</span></span> <span data-ttu-id="e7d8a-169">Status för de exporterade objekten visas i **fönstret** Aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-169">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="e7d8a-170">Ett meddelande visas när nedladdningen är klar.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-170">A message is displayed when the download is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d8a-171">I stället för att ladda ned hela exportjobbet i Azure Storage Explorer kan du välja specifika objekt att ladda ned och visa.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-171">Instead of downloading the entire export job in Azure Storage Explorer, you can select specific items to download and view.</span></span>

## <a name="more-information"></a><span data-ttu-id="e7d8a-172">Mer information</span><span class="sxs-lookup"><span data-stu-id="e7d8a-172">More information</span></span>

- <span data-ttu-id="e7d8a-173">Mappen exportjobb innehåller följande objekt.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-173">The export job folder contains the following items.</span></span> <span data-ttu-id="e7d8a-174">De faktiska objekten i exportmappen bestäms av vilka exportalternativ som konfigurerades när exportjobbet skapades.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-174">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="e7d8a-175">Mer information om dessa alternativ finns i [Exportera dokument från en granskningsuppsättning.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="e7d8a-175">For more information about these options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

  - <span data-ttu-id="e7d8a-176">Export_load_file.csv: Den här CSV-filen är en detaljexportrapport som innehåller information om varje exporterat dokument.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-176">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="e7d8a-177">Filen består av en kolumn för varje metadataegenskap för ett dokument.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-177">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="e7d8a-178">En lista med och en beskrivning av metadata som  ingår i rapporten finns i kolumnen För exporterade fältnamn i tabellen i Dokumentmetadatafält [i Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="e7d8a-178">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>

  - <span data-ttu-id="e7d8a-179">Summary.txt: En textfil som innehåller en sammanfattning av exporten inklusive exportstatistik.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-179">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>

  - <span data-ttu-id="e7d8a-180">Extracted_text_files: Den här mappen innehåller en textfilversion av varje exporterat dokument.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-180">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>

  - <span data-ttu-id="e7d8a-181">NativeFiles: Den här mappen innehåller en inbyggd filversion av varje exporterat dokument.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-181">NativeFiles: This folder contains a native file version of each exported document.</span></span>

  - <span data-ttu-id="e7d8a-182">Error_files: Den här mappen innehåller följande objekt när exportjobbet innehåller felfiler:</span><span class="sxs-lookup"><span data-stu-id="e7d8a-182">Error_files: This folder includes the following items when the export job contains any error files:</span></span>

    - <span data-ttu-id="e7d8a-183">ExtractionError.csv: Den här CSV-filen innehåller tillgängliga metadata för filer som inte extraherades korrekt från det överordnade objektet.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-183">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>

    - <span data-ttu-id="e7d8a-184">ProcessingError: Den här mappen innehåller dokument med bearbetningsfel.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-184">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="e7d8a-185">Det här innehållet ligger på objektnivå, vilket innebär att om en bifogad fil hade ett bearbetningsfel inkluderas det dokument som innehåller den bifogade filen även i den här mappen.</span><span class="sxs-lookup"><span data-stu-id="e7d8a-185">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
