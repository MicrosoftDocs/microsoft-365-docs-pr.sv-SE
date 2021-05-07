---
title: Exportera dokument från en granskningsuppsättning
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
description: Lär dig hur du markerar och exporterar innehåll från en Advanced eDiscovery granskningsuppsättning för presentationer eller externa granskningar.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162640"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="f0a39-103">Exportera dokument från en granskningsuppsättning i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f0a39-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="f0a39-104">Med export kan användarna anpassa innehållet som ingår i nedladdningspaketet när du exporterar dokument från en granskningsuppsättning i Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f0a39-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="f0a39-105">Så här exporterar du dokument från en granskningsuppsättning:</span><span class="sxs-lookup"><span data-stu-id="f0a39-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="f0a39-106">I Microsoft 365 kompatibilitetscenter öppnar du Advanced eDiscovery, väljer fliken Granska **uppsättningar** och väljer sedan den granskningsuppsättning som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="f0a39-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="f0a39-107">Klicka på Åtgärdsexport i   >  **granskningsuppsättningen.**</span><span class="sxs-lookup"><span data-stu-id="f0a39-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="f0a39-108">Med exportverktyget visas den utfällällade sidan med inställningar för att konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="f0a39-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="f0a39-109">Vissa alternativ är markerade som standard, men du kan ändra dessa.</span><span class="sxs-lookup"><span data-stu-id="f0a39-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="f0a39-110">I följande avsnitt finns beskrivningar av de exportalternativ som du kan konfigurera.</span><span class="sxs-lookup"><span data-stu-id="f0a39-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Konfigurationsalternativ för att exportera objekt från en granskningsuppsättning](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="f0a39-112">När du har konfigurerat exporten klickar du **på Exportera** för att starta exporten.</span><span class="sxs-lookup"><span data-stu-id="f0a39-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="f0a39-113">Beroende på det alternativ  du valde i avsnittet Utdataalternativ kan du komma åt exportfilerna genom direkt nedladdning eller i organisationens Azure Storage konto.</span><span class="sxs-lookup"><span data-stu-id="f0a39-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a39-114">Exportjobben behålls under hela ärendets livscykel.</span><span class="sxs-lookup"><span data-stu-id="f0a39-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="f0a39-115">Men du måste hämta innehållet från ett exportjobb inom 30 dagar efter att exportjobbet är klart.</span><span class="sxs-lookup"><span data-stu-id="f0a39-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="f0a39-116">Exportalternativ</span><span class="sxs-lookup"><span data-stu-id="f0a39-116">Export options</span></span>

<span data-ttu-id="f0a39-117">Använd följande alternativ för att konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="f0a39-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="f0a39-118">**Exportera namn:** Namnet på exportjobbet.</span><span class="sxs-lookup"><span data-stu-id="f0a39-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="f0a39-119">**Beskrivning**: Fritt textfält där du kan lägga till en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f0a39-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="f0a39-120">**Exportera de här dokumenten**</span><span class="sxs-lookup"><span data-stu-id="f0a39-120">**Export these documents**</span></span>

  - <span data-ttu-id="f0a39-121">**Endast markerade dokument:** Med det här alternativet exporteras bara de dokument som är markerade för närvarande.</span><span class="sxs-lookup"><span data-stu-id="f0a39-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="f0a39-122">**Alla dokument i granskningsuppsättningen**: Med det här alternativet exporteras alla dokument i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="f0a39-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="f0a39-123">**Metadata**</span><span class="sxs-lookup"><span data-stu-id="f0a39-123">**Metadata**</span></span>
  
  - <span data-ttu-id="f0a39-124">**Läs in fil:** Den här filen innehåller metadata för varje fil.</span><span class="sxs-lookup"><span data-stu-id="f0a39-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="f0a39-125">Den här filen kan vanligtvis matas in med eDiscovery-verktyg från tredje part.</span><span class="sxs-lookup"><span data-stu-id="f0a39-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="f0a39-126">Mer information om vilka fält som ingår finns i [Dokumentera metadatafält i Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="f0a39-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="f0a39-127">**Taggar:** När det här alternativet valts inkluderas taggningsinformation i inläsningsfilen.</span><span class="sxs-lookup"><span data-stu-id="f0a39-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="f0a39-128">**Content**</span><span class="sxs-lookup"><span data-stu-id="f0a39-128">**Content**</span></span>
  
  - <span data-ttu-id="f0a39-129">**Ursprungliga filer:** Markera den här kryssrutan om du vill ta med de ursprungliga filerna i dokumenten i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="f0a39-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="f0a39-130">Om du väljer att exportera ursprungliga filer har du följande alternativ för hur du exporterar chattkonversationer.</span><span class="sxs-lookup"><span data-stu-id="f0a39-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="f0a39-131">**Konversationsalternativ**</span><span class="sxs-lookup"><span data-stu-id="f0a39-131">**Conversation options**</span></span>

    - <span data-ttu-id="f0a39-132">**Konversationsfiler:** Det här alternativet exporterar rekonstruerade chattkonversationer.</span><span class="sxs-lookup"><span data-stu-id="f0a39-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="f0a39-133">I det här formatet visas konversationer i ett formulär som liknar det som visas i det ursprungliga programmet.</span><span class="sxs-lookup"><span data-stu-id="f0a39-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="f0a39-134">**Enskilda chattmeddelanden:** Med det här alternativet exporteras de ursprungliga konversationsfilerna när de lagras i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0a39-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="f0a39-135">**Alternativ**</span><span class="sxs-lookup"><span data-stu-id="f0a39-135">**Options**</span></span>

  - <span data-ttu-id="f0a39-136">**Textfiler**: – Det här alternativet innehåller extraherade textversioner av ursprungliga filer i exporten.</span><span class="sxs-lookup"><span data-stu-id="f0a39-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="f0a39-137">**Ersätt ursprungliga original med konverterade** PDF-filer: Om pdf-filer som har omaktiverats genereras under granskning är dessa filer tillgängliga för export.</span><span class="sxs-lookup"><span data-stu-id="f0a39-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="f0a39-138">Du kan välja att exportera endast de ursprungliga filer som redigerades (genom att inte välja det här alternativet) eller så kan du välja det här alternativet om du vill exportera PDF-filer som innehåller de faktiska redigeringarna.</span><span class="sxs-lookup"><span data-stu-id="f0a39-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="f0a39-139">**Utdataalternativ:** Exporterat innehåll är antingen tillgängligt för nedladdning direkt via en webbläsare eller kan skickas till ett Azure Storage konto.</span><span class="sxs-lookup"><span data-stu-id="f0a39-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="f0a39-140">De två första alternativen ger möjlighet till direkt nedladdning.</span><span class="sxs-lookup"><span data-stu-id="f0a39-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="f0a39-141">Lösa filer och **PSTs (e-post** läggs till i PSTs om möjligt) : Filer exporteras i ett format som liknar den ursprungliga katalogstrukturen som användare i sina ursprungliga program ser.</span><span class="sxs-lookup"><span data-stu-id="f0a39-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="f0a39-142">Mer information finns i avsnittet [Lösa filer och PST-exportstruktur.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="f0a39-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="f0a39-143">**Komprimerad katalogstruktur:** Filerna exporteras och inkluderas i nedladdningen.</span><span class="sxs-lookup"><span data-stu-id="f0a39-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="f0a39-144">**Komprimerad katalogstruktur som exporterats till** Azure Storage-konto: Filer exporteras till organisationens Azure Storage konto.</span><span class="sxs-lookup"><span data-stu-id="f0a39-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="f0a39-145">För det här alternativet måste du ange URL-adressen för behållaren i ditt Azure Storage att exportera filerna till.</span><span class="sxs-lookup"><span data-stu-id="f0a39-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="f0a39-146">Du måste också ange SAS-token (delad åtkomstsignatur) för ditt Azure Storage konto.</span><span class="sxs-lookup"><span data-stu-id="f0a39-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="f0a39-147">Mer information finns i Exportera [dokument i en granskning som är inställd på ett Azure Storage konto](download-export-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="f0a39-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="f0a39-148">I följande avsnitt beskrivs mappstrukturen för lösa filer och komprimerade strukturalternativ.</span><span class="sxs-lookup"><span data-stu-id="f0a39-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="f0a39-149">Lösa filer och PST-exportstruktur</span><span class="sxs-lookup"><span data-stu-id="f0a39-149">Loose files and PST export structure</span></span>

<span data-ttu-id="f0a39-150">Om du väljer det här exportalternativet ordnas det exporterade innehållet i följande struktur:</span><span class="sxs-lookup"><span data-stu-id="f0a39-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="f0a39-151">Rotmapp: Den här mappen i namnet ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="f0a39-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="f0a39-152">Export_load_file.csv: metadatafilen.</span><span class="sxs-lookup"><span data-stu-id="f0a39-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="f0a39-153">Summary.csv: En sammanfattningsfil som även innehåller exportstatistik.</span><span class="sxs-lookup"><span data-stu-id="f0a39-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="f0a39-154">Exchange: Den här mappen innehåller allt innehåll Exchange i ursprungligt filformat.</span><span class="sxs-lookup"><span data-stu-id="f0a39-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="f0a39-155">Ursprungliga filer ersätts med omaktiverade PDF-filer om du väljer alternativet Ersätt **omaktiverade inbyggda filer med konverterade PDF-filer.**</span><span class="sxs-lookup"><span data-stu-id="f0a39-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="f0a39-156">SharePoint: Den här mappen innehåller allt inbyggt innehåll SharePoint i ett ursprungligt filformat.</span><span class="sxs-lookup"><span data-stu-id="f0a39-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="f0a39-157">Ursprungliga filer ersätts med omaktiverade PDF-filer om du väljer alternativet Ersätt **omaktiverade inbyggda filer med konverterade PDF-filer.**</span><span class="sxs-lookup"><span data-stu-id="f0a39-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="f0a39-158">Komprimerad katalogstruktur</span><span class="sxs-lookup"><span data-stu-id="f0a39-158">Condensed directory structure</span></span>

- <span data-ttu-id="f0a39-159">Rotmapp: Den här mappen heter ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="f0a39-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="f0a39-160">Export_load_file.csv: metadatafilen.</span><span class="sxs-lookup"><span data-stu-id="f0a39-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="f0a39-161">Summary.txt: En sammanfattningsfil som även innehåller exportstatistik.</span><span class="sxs-lookup"><span data-stu-id="f0a39-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="f0a39-162">NativeFiles: Den här mappen innehåller alla ursprungliga filer som exporterades.</span><span class="sxs-lookup"><span data-stu-id="f0a39-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="f0a39-163">Om du exporterar omaktiverade PDF-filer lagras de inte i PST-filer.</span><span class="sxs-lookup"><span data-stu-id="f0a39-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="f0a39-164">I stället läggs de till i en avgränsad mapp.</span><span class="sxs-lookup"><span data-stu-id="f0a39-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="f0a39-165">Error_files: Den här mappen innehåller följande felfiler, om de tas med i exporten:</span><span class="sxs-lookup"><span data-stu-id="f0a39-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="f0a39-166">ExtraheringFel: En CSV-fil som innehåller alla tillgängliga metadata för filer som inte extraherats korrekt från överordnade filer.</span><span class="sxs-lookup"><span data-stu-id="f0a39-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="f0a39-167">ProcessingError: Den här filen innehåller en lista över dokument med bearbetningsfel.</span><span class="sxs-lookup"><span data-stu-id="f0a39-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="f0a39-168">Innehållet är objektnivå, vilket innebär att om en bifogad fil resulterade i ett bearbetningsfel inkluderas e-postmeddelandet som innehåller den bifogade filen i den här mappen.</span><span class="sxs-lookup"><span data-stu-id="f0a39-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="f0a39-169">Extracted_text_files: Den här mappen innehåller alla extraherade textfiler som skapades vid bearbetningen.</span><span class="sxs-lookup"><span data-stu-id="f0a39-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
