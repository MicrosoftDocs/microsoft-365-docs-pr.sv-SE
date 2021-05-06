---
title: Tagga dokument i en granskningsuppsättning
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
ms.assetid: ''
description: Tagga dokument i en granskningsuppsättning hjälper till att ta bort onödigt innehåll och identifiera relevant innehåll i Advanced eDiscovery fall.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161612"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="1af37-103">Tagga dokument i en granskningsuppsättning i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1af37-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="1af37-104">Det är viktigt att ordna innehåll i en granskningsuppsättning för att slutföra olika arbetsflöden i eDiscovery-processen.</span><span class="sxs-lookup"><span data-stu-id="1af37-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="1af37-105">Det omfattar:</span><span class="sxs-lookup"><span data-stu-id="1af37-105">This includes:</span></span>

- <span data-ttu-id="1af37-106">Ta bort onödigt innehåll</span><span class="sxs-lookup"><span data-stu-id="1af37-106">Culling unnecessary content</span></span>

- <span data-ttu-id="1af37-107">Identifiera relevant innehåll</span><span class="sxs-lookup"><span data-stu-id="1af37-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="1af37-108">Identifiera innehåll som måste granskas av en expert eller en jurist</span><span class="sxs-lookup"><span data-stu-id="1af37-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="1af37-109">När experter, jurister eller andra användare granskar innehåll i en granskningsuppsättning kan deras åsikter om innehållet fångas upp med hjälp av taggar.</span><span class="sxs-lookup"><span data-stu-id="1af37-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="1af37-110">Om syftet till exempel är att undvika onödigt innehåll kan en användare tagga dokument med en tagg, till exempel "svarar inte".</span><span class="sxs-lookup"><span data-stu-id="1af37-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="1af37-111">När innehåll har granskats och taggats kan du skapa en granskningsuppsättningssökning för att utesluta innehåll som är taggat som "icke-responsivt", vilket eliminerar det här innehållet från nästa steg i eDiscovery-arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1af37-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="1af37-112">Märkningspanelen kan anpassas för varje ärende så att taggarna kan stödja det avsedda granskningsarbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1af37-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="1af37-113">Taggtyper</span><span class="sxs-lookup"><span data-stu-id="1af37-113">Tag types</span></span>

<span data-ttu-id="1af37-114">Advanced eDiscovery innehåller två typer av taggar:</span><span class="sxs-lookup"><span data-stu-id="1af37-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="1af37-115">**Enkelvalstaggar** – Begränsar användare att välja en enskild tagg i en grupp.</span><span class="sxs-lookup"><span data-stu-id="1af37-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="1af37-116">Det kan vara användbart för att säkerställa att användarna inte väljer taggar i konflikt, till exempel "responsiv" och "svarar inte".</span><span class="sxs-lookup"><span data-stu-id="1af37-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="1af37-117">De visas som alternativknappar.</span><span class="sxs-lookup"><span data-stu-id="1af37-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="1af37-118">**Flervalstaggar** – tillåt användare att markera flera taggar i en grupp.</span><span class="sxs-lookup"><span data-stu-id="1af37-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="1af37-119">De visas som kryssrutor.</span><span class="sxs-lookup"><span data-stu-id="1af37-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="1af37-120">Taggstruktur</span><span class="sxs-lookup"><span data-stu-id="1af37-120">Tag structure</span></span>

<span data-ttu-id="1af37-121">Förutom taggtyperna kan strukturen för hur taggar ordnas i taggpanelen användas för att göra taggningen av dokument mer intuitiv.</span><span class="sxs-lookup"><span data-stu-id="1af37-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="1af37-122">Taggar är grupperade efter avsnitt.</span><span class="sxs-lookup"><span data-stu-id="1af37-122">Tags are grouped by sections.</span></span> <span data-ttu-id="1af37-123">Med sökfunktionen för granskning kan du söka efter tagg och taggavsnitt.</span><span class="sxs-lookup"><span data-stu-id="1af37-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="1af37-124">Det innebär att du kan skapa en granskningsuppsättningssökning för att hämta dokument som är märkta med valfri tagg i ett avsnitt.</span><span class="sxs-lookup"><span data-stu-id="1af37-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Tagga avsnitt i taggpanelen](../media/Tagtypes.png)

<span data-ttu-id="1af37-126">Taggar kan ordnas ytterligare genom att kapsla in dem i ett avsnitt.</span><span class="sxs-lookup"><span data-stu-id="1af37-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="1af37-127">Om avsikten till exempel är att identifiera och tagga behörighetsinnehåll kan kapsling användas för att göra det tydligt att en användare kan tagga ett dokument som "behörig" och välja typ av behörighet genom att markera rätt kapslad tagg.</span><span class="sxs-lookup"><span data-stu-id="1af37-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Kapslade taggar i ett taggavsnitt](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="1af37-129">Använda taggar</span><span class="sxs-lookup"><span data-stu-id="1af37-129">Applying tags</span></span>

<span data-ttu-id="1af37-130">Det finns flera sätt att använda en tagg på innehåll.</span><span class="sxs-lookup"><span data-stu-id="1af37-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="1af37-131">Tagga ett enskilt dokument</span><span class="sxs-lookup"><span data-stu-id="1af37-131">Tagging a single document</span></span>

<span data-ttu-id="1af37-132">När du visar ett dokument i en granskningsuppsättning kan du visa de taggar som en granskning kan använda genom att klicka **på Taggningspanel**.</span><span class="sxs-lookup"><span data-stu-id="1af37-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Klicka på Taggpanelen för att visa taggpanelen](../media/Singledoctag.png)

<span data-ttu-id="1af37-134">Då kan du använda taggar i dokumentet som visas i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="1af37-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="1af37-135">Masstaggar</span><span class="sxs-lookup"><span data-stu-id="1af37-135">Bulk tagging</span></span>

<span data-ttu-id="1af37-136">Du kan masstagga genom att markera flera filer i resultatrutnätet och sedan använda taggarna i panelen Taggning som liknar taggning av enstaka dokument. </span><span class="sxs-lookup"><span data-stu-id="1af37-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="1af37-137">Massmarkering kan göras genom att markera taggar två gånger. Det första klicket använder taggen och det andra valet säkerställer att taggen är avmarkerad för alla valda filer.</span><span class="sxs-lookup"><span data-stu-id="1af37-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![En skärmbild av en beskrivning av en mobiltelefon automatiskt genererad](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="1af37-139">Vid masstaggar visar märkningspanelen antalet filer som är märkta för varje tagg i panelen.</span><span class="sxs-lookup"><span data-stu-id="1af37-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="1af37-140">Tagga i andra granskningspaneler</span><span class="sxs-lookup"><span data-stu-id="1af37-140">Tagging in other review panels</span></span>

<span data-ttu-id="1af37-141">När du granskar dokument kan du använda de andra granskningspanelerna för att granska andra egenskaper för dokument i resultatrutnätet.</span><span class="sxs-lookup"><span data-stu-id="1af37-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="1af37-142">Det omfattar granskning av andra relaterade dokument, e-posttrådar, nära dubbletter och hash-dubbletter.</span><span class="sxs-lookup"><span data-stu-id="1af37-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="1af37-143">När du till exempel granskar relaterade dokument  (med hjälp av panelen Dokumentfamiljgranskning) kan du minska granskningstiden avsevärt genom att masstagga relaterade dokument.</span><span class="sxs-lookup"><span data-stu-id="1af37-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="1af37-144">Till exempel om ett e-postmeddelande har flera bifogade filer och du vill vara säker på att hela familjen är taggad konsekvent.</span><span class="sxs-lookup"><span data-stu-id="1af37-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="1af37-145">Så här visar du till exempel panelen **Taggning när du** använder panelen **Dokumentfamiljgranskning:**</span><span class="sxs-lookup"><span data-stu-id="1af37-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="1af37-146">Med granskningspanelen öppen för ett markerat dokument (om listan med  relaterat innehåll visas i granskningspanelen för dokumentfamilj klickar du till exempel på **Tagga** dokument under granskningspanelen för dokumentfamilj.</span><span class="sxs-lookup"><span data-stu-id="1af37-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="1af37-147">Taggpanelen visas som ett popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="1af37-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="1af37-148">Välj en eller flera taggar för att använda det valda dokumentet.</span><span class="sxs-lookup"><span data-stu-id="1af37-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="1af37-149">Om du vill tagga alla  dokument markerar du alla dokument i dokumentfamiljpanelen, klickar på Tagga dokument och väljer sedan de taggar som ska gälla för hela dokumentfamiljen.</span><span class="sxs-lookup"><span data-stu-id="1af37-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![En skärmbild av en postbeskrivning i sociala medier som genererats automatiskt](../media/Relatedtag.png)
