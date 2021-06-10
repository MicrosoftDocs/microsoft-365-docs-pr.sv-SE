---
title: Använda filtret för förutsägelseresultat för objekt i en granskningsuppsättning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Använd ett filter för förutsägelseresultat för att visa objekt som en prediktiv kodmodell som förutsagd som relevant eller inte relevant.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822591"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="c87d6-103">Använda ett filter för förutsägelseresultat i en granskningsuppsättning (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="c87d6-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="c87d6-104">När du har skapat en prognoskodningsmodell i Advanced eDiscovery och tränat den till den punkt där den är stabil, kan du använda poängfiltret för förutsägelse för att visa granskade objekt som har fastställt av modellen är relevanta (eller inte relevanta).</span><span class="sxs-lookup"><span data-stu-id="c87d6-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="c87d6-105">När du skapar en modell skapas också ett motsvarande filter för förutsägelseresultat.</span><span class="sxs-lookup"><span data-stu-id="c87d6-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="c87d6-106">Du kan använda filtret för att visa objekt som tilldelats ett förutsägelseresultat inom ett visst område.</span><span class="sxs-lookup"><span data-stu-id="c87d6-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="c87d6-107">I allmänhet tilldelas förutsägelser för resultat mellan **0** och **0,5** till objekt som har prognosterats i modellen.</span><span class="sxs-lookup"><span data-stu-id="c87d6-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="c87d6-108">Objekt som tilldelats **förutsägelseresultat mellan 0,5** och **1,0** är objekt som modellen har prognosterat är relevanta.</span><span class="sxs-lookup"><span data-stu-id="c87d6-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="c87d6-109">Du kan använda filtret för förutsägelseresultat på två sätt:</span><span class="sxs-lookup"><span data-stu-id="c87d6-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="c87d6-110">Prioritera granskningen av objekt i en granskningsuppsättning som modellen har prognosterat är relevant.</span><span class="sxs-lookup"><span data-stu-id="c87d6-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="c87d6-111">Objekt från granskningsuppsättningen som modellen har prognosterat är inte relevanta.</span><span class="sxs-lookup"><span data-stu-id="c87d6-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="c87d6-112">Alternativt kan du använda filtret för förutsägelseresultat för att avprioritera granskningen av icke-relevanta objekt.</span><span class="sxs-lookup"><span data-stu-id="c87d6-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="c87d6-113">Innan du använder ett filter för förutsägelseresultat</span><span class="sxs-lookup"><span data-stu-id="c87d6-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="c87d6-114">Skapa en prediktiv kodningsmodell så att ett motsvarande filter för förutsägelseresultat skapas.</span><span class="sxs-lookup"><span data-stu-id="c87d6-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="c87d6-115">Du kan använda ett filter för förutsägelseresultat efter någon av utbildningarna.</span><span class="sxs-lookup"><span data-stu-id="c87d6-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="c87d6-116">Men det kan vara bra att vänta efter att ha utfört flera omgångar eller tills modellen är stabil innan du använder filtret för prognosresultat.</span><span class="sxs-lookup"><span data-stu-id="c87d6-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="c87d6-117">Använda ett filter för förutsägelseresultat</span><span class="sxs-lookup"><span data-stu-id="c87d6-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="c87d6-118">I Microsoft 365 öppnar du fliken Advanced eDiscovery, väljer fliken Granska **uppsättningar** och öppnar sedan granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="c87d6-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![Klicka på Filter för att visa den utfällade filtersidan](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="c87d6-120">De förinstallerade standardfiltren visas högst upp på sidan för granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="c87d6-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="c87d6-121">Du kan låta dessa vara inställda på **Alla**.</span><span class="sxs-lookup"><span data-stu-id="c87d6-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="c87d6-122">Klicka **på Filter** så att den **utfällade sidan** Filter visas.</span><span class="sxs-lookup"><span data-stu-id="c87d6-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="c87d6-123">Expandera **analysavsnittet & förutsägelsekodning** för att visa en uppsättning filter.</span><span class="sxs-lookup"><span data-stu-id="c87d6-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filter för förutsägelseresultat i & för förutsägelsekodning](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="c87d6-125">Namngivningskonventioner för resultatfilter för **förutsägelser är Förutsägelseresultat (modellnamn).**</span><span class="sxs-lookup"><span data-stu-id="c87d6-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="c87d6-126">Namnet på filtret för förutsägelseresultat för en modell med namnet **Modell A** är till exempel **Prognosresultat (Modell A).**</span><span class="sxs-lookup"><span data-stu-id="c87d6-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="c87d6-127">Välj det filter för förutsägelseresultat som du vill använda och klicka sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="c87d6-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="c87d6-128">På sidan för granskningsuppsättningen klickar du på listrutan för filtret för förutsägelseresultat och anger minimi- och maxvärden för förutsägelseresultatintervallet.</span><span class="sxs-lookup"><span data-stu-id="c87d6-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="c87d6-129">Följande skärmbild visar till exempel ett resultatintervall för förutsägelse mellan **0,5** och **1,0.**</span><span class="sxs-lookup"><span data-stu-id="c87d6-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Lägsta och högsta värden för filtret för förutsägelseresultat](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="c87d6-131">Klicka utanför filtret så tillämpas filtret automatiskt på granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="c87d6-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="c87d6-132">En lista med dokument med ett förutsägelseresultat inom det angivna intervallet visas på sidan för granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="c87d6-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="c87d6-133">Om du vill visa det faktiska förutsägelseresultatet för ett dokument kan du klicka på **fliken Metadata** i läsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c87d6-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="c87d6-134">Förutsägelseresultat för alla modeller i granskningsuppsättningen visas i **metadataegenskapen RelevanceScores.**</span><span class="sxs-lookup"><span data-stu-id="c87d6-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="c87d6-135">Mer information</span><span class="sxs-lookup"><span data-stu-id="c87d6-135">More information</span></span>

- <span data-ttu-id="c87d6-136">Mer information om hur du använder filter finns i [Skapa frågor och filtrera innehåll i en granskningsuppsättning](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="c87d6-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
