---
title: Skapa en fråga för innehållet i en granskningsuppsättning
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
description: Lär dig hur du skapar och kör en fråga i en granskningsuppsättning för att ordna innehåll för en effektivare granskning i Advanced eDiscovery ärende.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736457"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="5e5ed-103">Fråga och filtrera innehåll i en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="5e5ed-103">Query and filter content in a review set</span></span>

<span data-ttu-id="5e5ed-104">I de flesta fall kan det vara bra att gå djupare in på innehållet i en granskningsuppsättning och ordna den för att underlätta en effektivare granskning.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="5e5ed-105">Om du använder filter och frågor i en granskningsuppsättning kan du fokusera på en delmängd dokument som uppfyller villkoren för din granskning.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="5e5ed-106">Standardfilter</span><span class="sxs-lookup"><span data-stu-id="5e5ed-106">Default filters</span></span>

<span data-ttu-id="5e5ed-107">I en granskningsuppsättning finns det fem standardfilter som är förinstallerade i granskningsuppsättningen:</span><span class="sxs-lookup"><span data-stu-id="5e5ed-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="5e5ed-108">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="5e5ed-108">Keywords</span></span>
- <span data-ttu-id="5e5ed-109">Datum</span><span class="sxs-lookup"><span data-stu-id="5e5ed-109">Date</span></span>
- <span data-ttu-id="5e5ed-110">Avsändare/författare</span><span class="sxs-lookup"><span data-stu-id="5e5ed-110">Sender/Author</span></span>
- <span data-ttu-id="5e5ed-111">Ämne/rubrik</span><span class="sxs-lookup"><span data-stu-id="5e5ed-111">Subject/Title</span></span>
- <span data-ttu-id="5e5ed-112">Taggar</span><span class="sxs-lookup"><span data-stu-id="5e5ed-112">Tags</span></span>

![Standardfiltertyper](../media/DefaultFilterTypes.png)

<span data-ttu-id="5e5ed-114">Klicka på varje filter för att expandera det och tilldela ett värde.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="5e5ed-115">Klicka utanför filtret så tillämpas filtret automatiskt på granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="5e5ed-116">Följande skärmbild visar det datumfilter som har konfigurerats för att visa dokument inom ett datumintervall.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![Standardfilter expanderat](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="5e5ed-118">Lägga till eller ta bort filter</span><span class="sxs-lookup"><span data-stu-id="5e5ed-118">Add or remove filters</span></span>

<span data-ttu-id="5e5ed-119">Om du vill lägga till eller ta  bort filter som visas för granskningsuppsättningen väljer du Filter för att öppna filterpanelen, som visas på en utfällbladssida.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![Filterpanel](../media/FilterPanel.png)

<span data-ttu-id="5e5ed-121">De tillgängliga filtren är ordnade i fyra avsnitt:</span><span class="sxs-lookup"><span data-stu-id="5e5ed-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="5e5ed-122">**Sök:** Filter som ger olika sökfunktioner.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="5e5ed-123">**Analys &** förutsägelsekodning: Filter för egenskaper som genereras och läggs till i dokument när du kör dokumentet & e-postanalysjobb eller använder prediktiv kodningsmodeller. </span><span class="sxs-lookup"><span data-stu-id="5e5ed-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="5e5ed-124">**ID:n:** Filter för alla ID-egenskaper för dokument.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="5e5ed-125">**Objektegenskaper:** Filter för dokumentegenskaper.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="5e5ed-126">Expandera varje avsnitt och markera eller avmarkera filter för att lägga till eller ta bort dem i filteruppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="5e5ed-127">När du lägger till ett filter visas det i filteruppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-127">When you add a filter, it's displayed in the filter set.</span></span> 

![Lista över filteravsnitt och egenskaper i filterpanelen](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="5e5ed-129">När du expanderar ett avsnitt i filterpanelen märker du att standardfiltertyperna är markerade.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="5e5ed-130">Du kan behålla dessa markerade eller avmarkera dem och ta bort dem från filteruppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="5e5ed-131">Filtertyper</span><span class="sxs-lookup"><span data-stu-id="5e5ed-131">Filter types</span></span>

<span data-ttu-id="5e5ed-132">Alla sökbara fält i en granskningsuppsättning har ett motsvarande filter som du kan använda för att filtrera objekt baserat på ett visst fält.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="5e5ed-133">Det finns flera typer av filter:</span><span class="sxs-lookup"><span data-stu-id="5e5ed-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="5e5ed-134">**Fritext**: Ett fritextfilter används på textfält som exempelvis "Ämne".</span><span class="sxs-lookup"><span data-stu-id="5e5ed-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="5e5ed-135">Du kan lista flera sökord genom att avgränsa dem med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="5e5ed-136">**Datum:** Ett datumfilter används för datumfält som "Senast ändrad, datum".</span><span class="sxs-lookup"><span data-stu-id="5e5ed-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="5e5ed-137">**Sökalternativ:** Ett sökalternativfilter ger en lista med möjliga värden (varje värde visas med en kryssruta som du kan välja) för vissa fält i granskningen.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="5e5ed-138">Filtret används för fält, till exempel "Avsändare", där det finns ett ändlig antal möjliga värden i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="5e5ed-139">**Nyckelord:** Ett nyckelordsvillkor är en specifik instans av fritextvillkor som du kan använda för att söka efter termer.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="5e5ed-140">Du kan också använda KQL-liknande frågespråk i den här typen av filter.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="5e5ed-141">Mer information finns i avsnitten Frågespråk och Avancerat frågeverktyg i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="5e5ed-142">Inkludera och exkludera filterrelationer</span><span class="sxs-lookup"><span data-stu-id="5e5ed-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="5e5ed-143">Du kan ändra inkludera- och exkludera-relationen för ett visst filter.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="5e5ed-144">I filtret Taggar kan du till exempel utesluta objekt som är märkta med en viss tagg genom att välja **Är lika** med inget av i listrutan.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![Exkludera taggfilter](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="5e5ed-146">Spara filter som frågor</span><span class="sxs-lookup"><span data-stu-id="5e5ed-146">Save filters as queries</span></span>

<span data-ttu-id="5e5ed-147">När du är nöjd med dina filter kan du spara filterkombinationen som en filterfråga.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="5e5ed-148">Då kan du använda filtret i kommande granskningssessioner.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="5e5ed-149">Om du vill spara ett filter **väljer du Spara frågan** och ge den ett namn.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="5e5ed-150">Du eller andra granskare kan köra tidigare sparade filterfrågor genom att välja listrutan Sparade filterfrågor och välja en filterfråga att tillämpa på dokument som **angetts.**</span><span class="sxs-lookup"><span data-stu-id="5e5ed-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![Spara en filterfråga](../media/SaveFilterQuery.png)

<span data-ttu-id="5e5ed-152">Om du vill ta bort en filterfråga öppnar du filterpanelen och väljer papperskorgsikonen bredvid frågan.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![Ta bort en filterfråga](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="5e5ed-154">Frågespråk</span><span class="sxs-lookup"><span data-stu-id="5e5ed-154">Query language</span></span>

<span data-ttu-id="5e5ed-155">Förutom att använda filter kan du också använda ett KQL-liknande frågespråk i filtret Nyckelord för att skapa din frågeuppsättning.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="5e5ed-156">Frågespråket för granskningsuppsättningsfrågor har stöd för booleska standardoperatorer som **AND,** **OR,** **NOT** och **NEAR.**</span><span class="sxs-lookup"><span data-stu-id="5e5ed-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="5e5ed-157">Det har också stöd för ett jokertecken (?) och ett jokertecken (\*).</span><span class="sxs-lookup"><span data-stu-id="5e5ed-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="5e5ed-158">Avancerat frågeverktyg</span><span class="sxs-lookup"><span data-stu-id="5e5ed-158">Advanced query builder</span></span>

<span data-ttu-id="5e5ed-159">Du kan också skapa mer avancerade frågor för att söka efter dokument i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="5e5ed-160">Öppna filterpanelen, välj **Filter** och expandera **avsnittet** Sök.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![Lägga till ett KQL-filter](../media/AddKQLFilter.png)

2. <span data-ttu-id="5e5ed-162">Välj **KQL-filtret** och klicka på **Öppna frågeverktyget**.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="5e5ed-163">I den här panelen kan du skapa komplexa KQL-frågor med hjälp av frågeverktyget.</span><span class="sxs-lookup"><span data-stu-id="5e5ed-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="5e5ed-164">Du kan lägga till villkor eller villkorsgrupper som består av flera villkor som är logiskt sammankopplade av **OCH-** eller **ELLER-relationer.**</span><span class="sxs-lookup"><span data-stu-id="5e5ed-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![Använda frågeverktyget för att konfigurera komplexa filterfrågor](../media/ComplexQuery.png)
