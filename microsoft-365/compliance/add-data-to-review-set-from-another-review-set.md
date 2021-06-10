---
title: Lägga till data från en granskningsuppsättning i en annan granskningsuppsättning
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
description: Lär dig hur du väljer dokument från en granskningsuppsättning och arbetar med dem enskilt i en annan uppsättning Advanced eDiscovery fall.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161611"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="ebd79-103">Lägga till data i en granskningsuppsättning från en annan granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="ebd79-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="ebd79-104">I vissa fall kan det vara nödvändigt att välja dokument från en granskningsuppsättning och arbeta med dem enskilt i en annan granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="ebd79-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="ebd79-105">Det här är särskilt användbart om du har tagit bort innehåll i en granskningsuppsättning och vill köra analyser på delmängden data.</span><span class="sxs-lookup"><span data-stu-id="ebd79-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="ebd79-106">Följ arbetsflödet i den här artikeln om du vill lägga till innehåll från en granskningsuppsättning till en annan.</span><span class="sxs-lookup"><span data-stu-id="ebd79-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="ebd79-107">Skapa en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="ebd79-107">Create a review set</span></span>

<span data-ttu-id="ebd79-108">Innan du börjar måste du skapa en granskningsuppsättning där du kan lägga till data.</span><span class="sxs-lookup"><span data-stu-id="ebd79-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="ebd79-109">En ny granskningsuppsättning kan läggas till på **fliken Granska för** ärendet.</span><span class="sxs-lookup"><span data-stu-id="ebd79-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="ebd79-110">Mer information finns i [Skapa en granskningsuppsättning](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="ebd79-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="ebd79-111">Steg 1: Identifiera innehåll som du vill lägga till i en annan granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="ebd79-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="ebd79-112">Du kan lägga till innehåll från en granskningsuppsättning till en annan genom att välja specifika dokument i källgranskningsuppsättningen eller genom att markera alla objekt som returneras av en granskningsuppsättningsfråga.</span><span class="sxs-lookup"><span data-stu-id="ebd79-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="ebd79-113">Om du vill lägga till markerade objekt markerar du objekten, väljer **Åtgärd** och väljer sedan Lägg till **i en annan granskningsuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="ebd79-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Lägg till i en annan granskningsuppsättning i åtgärdsmenyn](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="ebd79-115">Steg 2: Ange alternativ för att lägga till i en annan granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="ebd79-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="ebd79-116">Välj den **granskningsuppsättning som du vill lägga** till objekt i på den utfällade sidan Lägg till i ytterligare granskningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="ebd79-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="ebd79-117">Välj om du vill **lägga till Alla sökresultat** eller Markerade **objekt**.</span><span class="sxs-lookup"><span data-stu-id="ebd79-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="ebd79-118">**Med ytterligare information** får du alternativ för att ta med alla  metadata från objekten och om du vill ta med taggarna (genom att markera kryssrutan Etiketter) från källgranskningsuppsättningen när dokumenten läggs till i den nya granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="ebd79-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Alternativ för att lägga till data i en annan granskningsuppsättning](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="ebd79-120">När du klickar **på Ok** skapas ett nytt jobb (med namnet Lägga till **data** i en annan granskningsuppsättning) för att lägga till innehållet i en annan granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="ebd79-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="ebd79-121">Du kan gå till fliken **Jobb** och övervaka förloppet för det här jobbet.</span><span class="sxs-lookup"><span data-stu-id="ebd79-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="ebd79-122">Mer information finns i [Hantera jobb.](managing-jobs-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="ebd79-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
