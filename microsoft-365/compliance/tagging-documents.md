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
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736307"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="3a7d3-103">Tagga dokument i en granskningsuppsättning i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3a7d3-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="3a7d3-104">Det är viktigt att ordna innehåll i en granskningsuppsättning för att slutföra olika arbetsflöden i eDiscovery-processen.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="3a7d3-105">Detta omfattar följande:</span><span class="sxs-lookup"><span data-stu-id="3a7d3-105">This includes:</span></span>

- <span data-ttu-id="3a7d3-106">Ta bort onödigt innehåll</span><span class="sxs-lookup"><span data-stu-id="3a7d3-106">Culling unnecessary content</span></span>

- <span data-ttu-id="3a7d3-107">Identifiera relevant innehåll</span><span class="sxs-lookup"><span data-stu-id="3a7d3-107">Identifying relevant content</span></span>

- <span data-ttu-id="3a7d3-108">Identifiera innehåll som måste granskas av en expert eller jurist</span><span class="sxs-lookup"><span data-stu-id="3a7d3-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="3a7d3-109">När experter, jurister eller andra användare granskar innehåll i en granskningsuppsättning kan deras åsikter om innehållet fångas upp med hjälp av taggar.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="3a7d3-110">Om syftet till exempel är att undvika onödigt innehåll kan en användare tagga dokument med en tagg, till exempel "svarar inte".</span><span class="sxs-lookup"><span data-stu-id="3a7d3-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="3a7d3-111">När innehåll har granskats och taggats kan du skapa en sökning med en granskningsuppsättning för att utesluta innehåll som är taggat som "icke-responsivt".</span><span class="sxs-lookup"><span data-stu-id="3a7d3-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="3a7d3-112">Med den här processen elimineras det icke-responsiva innehållet från nästa steg i eDiscovery-arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="3a7d3-113">Taggpanelen i en granskningsuppsättning kan anpassas för varje ärende så att taggarna stöder det avsedda granskningsarbetsflödet för ärendet.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="3a7d3-114">Omfattningen av taggar är ett Advanced eDiscovery ärende.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="3a7d3-115">Det innebär att ett ärende bara kan ha en uppsättning taggar som granskare kan använda för att tagga dokument med uppsättningsdokument.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="3a7d3-116">Du kan inte konfigurera en annan uppsättning taggar för användning i olika granskningsuppsättningar i samma fall.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="3a7d3-117">Taggtyper</span><span class="sxs-lookup"><span data-stu-id="3a7d3-117">Tag types</span></span>

<span data-ttu-id="3a7d3-118">Advanced eDiscovery innehåller två typer av taggar:</span><span class="sxs-lookup"><span data-stu-id="3a7d3-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="3a7d3-119">**Enkelvalstaggar:** Begränsar granskare att välja en enskild tagg i en grupp.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="3a7d3-120">Den här typen av taggar kan vara bra att se till att granskare inte väljer taggar i konflikt, till exempel "responsiv" och "svarar inte".</span><span class="sxs-lookup"><span data-stu-id="3a7d3-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="3a7d3-121">Taggar för enstaka val visas som alternativknappar.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="3a7d3-122">**Flervalstaggar:** Tillåta granskningar att markera flera taggar i en grupp.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="3a7d3-123">Den här typen av taggar visas som kryssrutor.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="3a7d3-124">Taggstruktur</span><span class="sxs-lookup"><span data-stu-id="3a7d3-124">Tag structure</span></span>

<span data-ttu-id="3a7d3-125">Förutom taggtyperna kan strukturen för hur taggar ordnas i taggpanelen användas för att göra taggningen av dokument mer intuitiv.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="3a7d3-126">Taggar är grupperade efter avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-126">Tags are grouped by sections.</span></span> <span data-ttu-id="3a7d3-127">Med sökfunktionen för granskning kan du söka efter tagg och taggavsnitt.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="3a7d3-128">Det innebär att du kan skapa en granskningsuppsättningssökning för att hämta dokument som är märkta med valfri tagg i ett avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Tagga avsnitt i taggpanelen](../media/TagTypes.png)

<span data-ttu-id="3a7d3-130">Du kan ordna taggarna ytterligare genom att kapsla in dem i ett avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="3a7d3-131">Om syftet till exempel är att identifiera och tagga behörighetsinnehåll kan kapsling användas för att göra det tydligt att granskare kan tagga ett dokument som "privilegierat" och välja typ av behörighet genom att markera rätt kapslad tagg.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Kapslade taggar i ett taggavsnitt](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="3a7d3-133">Skapa taggar</span><span class="sxs-lookup"><span data-stu-id="3a7d3-133">Create tags</span></span>

<span data-ttu-id="3a7d3-134">Innan du kan använda taggar i dokument i granskningsuppsättningen måste du skapa en taggstruktur.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="3a7d3-135">Öppna en granskningsuppsättning, gå till kommandofältet och välj **Tagga efter fråga.**</span><span class="sxs-lookup"><span data-stu-id="3a7d3-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="3a7d3-136">Välj Hantera taggalternativ i **taggpanelen**</span><span class="sxs-lookup"><span data-stu-id="3a7d3-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="3a7d3-137">Välj **Lägg till taggavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="3a7d3-138">Skriv en rubrik för tagggruppen och en valfri beskrivning och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="3a7d3-139">Markera den nedrullningsbara menyn med en tre punkt bredvid tagggruppens rubrik och klicka på **Lägg till kryssruta** eller **knappen Lägg till alternativ.**</span><span class="sxs-lookup"><span data-stu-id="3a7d3-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="3a7d3-140">Skriv ett namn och en beskrivning för kryssrutan eller alternativknappen.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="3a7d3-141">Upprepa proceduren för att skapa nya taggavsnitt, taggalternativ och kryssrutor.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![Konfigurera taggstruktur](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="3a7d3-143">Använda taggar</span><span class="sxs-lookup"><span data-stu-id="3a7d3-143">Applying tags</span></span>

<span data-ttu-id="3a7d3-144">När taggstrukturen är på plats kan granskare använda taggar i dokument i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="3a7d3-145">Det finns två olika sätt att använda taggar:</span><span class="sxs-lookup"><span data-stu-id="3a7d3-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="3a7d3-146">Tagga filer</span><span class="sxs-lookup"><span data-stu-id="3a7d3-146">Tag files</span></span>

- <span data-ttu-id="3a7d3-147">Tagga efter fråga</span><span class="sxs-lookup"><span data-stu-id="3a7d3-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="3a7d3-148">Tagga filer</span><span class="sxs-lookup"><span data-stu-id="3a7d3-148">Tag files</span></span>

<span data-ttu-id="3a7d3-149">Oavsett om du markerar ett enstaka objekt eller flera objekt i en granskningsuppsättning kan du tillämpa taggar på deras markering genom att klicka **på Tagga** filer i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="3a7d3-150">I taggpanelen kan du välja en tagg och den tillämpas automatiskt på de markerade dokumenten.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![Tagga markerade filer](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="3a7d3-152">Taggar kommer endast att tillämpas på markerade objekt i listan med objekt.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="3a7d3-153">Tagga efter fråga</span><span class="sxs-lookup"><span data-stu-id="3a7d3-153">Tag by query</span></span>

<span data-ttu-id="3a7d3-154">Genom att tagga efter fråga kan du använda taggar för alla objekt som visas av en filterfråga som för närvarande används i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="3a7d3-155">Avmarkera alla objekt i granskningsuppsättningen, gå till kommandofältet och välj **Tagga efter fråga.**</span><span class="sxs-lookup"><span data-stu-id="3a7d3-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="3a7d3-156">Markera den tagg du vill använda i taggpanelen.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="3a7d3-157">Under **listrutan Taggmarkering** finns det tre alternativ som avgör vilka objekt taggen ska användas för.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="3a7d3-158">**Objekt som matchar tillämpad** fråga: Tillämpar taggar på specifika objekt som matchar filterfrågans villkor.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="3a7d3-159">**Inkludera associerade familjeobjekt:** Tillämpar taggar på specifika objekt som matchar filterfrågans villkor och tillhörande familjeobjekt.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="3a7d3-160">*Familjeobjekt* är objekt som delar samma FamilyId-metadatavärde.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="3a7d3-161">**Ta med associerade konversationsobjekt:** Tillämpar taggar på objekt som matchar filterfrågans villkor och tillhörande konversationsobjekt.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="3a7d3-162">*Konversationsobjekt* är objekt som delar samma metadatavärden för ConversationId.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![Taggmarkering](../media/TagByQuery2.png)

4. <span data-ttu-id="3a7d3-164">Klicka **på Starta taggningsjobbet** för att utlösa taggningsjobbet.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="3a7d3-165">Taggfilter</span><span class="sxs-lookup"><span data-stu-id="3a7d3-165">Tag filter</span></span>

<span data-ttu-id="3a7d3-166">Använd taggfiltret i granskningsuppsättningen för att snabbt hitta eller exkludera objekt från frågeresultatet baserat på hur ett objekt är taggat.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="3a7d3-167">Välj **Filter** för att expandera filterpanelen.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="3a7d3-168">Markera och expandera **Objektegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="3a7d3-169">Rulla nedåt för att hitta filtret **med namnet Tagg**, markera kryssrutan och klicka sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="3a7d3-170">Om du vill inkludera eller exkludera objekt med en viss tagg från en fråga gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="3a7d3-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="3a7d3-171">**Inkludera objekt:** Välj taggvärdet och välj **Lika med något av** i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="3a7d3-172">Eller</span><span class="sxs-lookup"><span data-stu-id="3a7d3-172">Or</span></span>

   - <span data-ttu-id="3a7d3-173">**Uteslut objekt:** Välj taggvärdet och välj **Är lika med inget av i** listrinsmenyn.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![Taggfilter utesluter objekt](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="3a7d3-175">Uppdatera sidan så att taggfiltret visar de senaste ändringarna i taggstrukturen.</span><span class="sxs-lookup"><span data-stu-id="3a7d3-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
