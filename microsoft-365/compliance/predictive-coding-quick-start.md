---
title: Prediktiv kodning i Advanced eDiscovery – snabbstart
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
description: Lär dig hur du kommer igång med prediktiv kodningsmodulen i Advanced eDiscovery. Den här artikeln beskriver hur du kan använda förutsägelsekodning för att identifiera innehåll i en granskningsuppsättning som är mest relevant för din undersökning.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822623"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="735e3-104">Snabbstart: Förutsägelsekodning i Advanced eDiscovery (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="735e3-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="735e3-105">I den här artikeln får du en snabbstart med att använda förutsägelsekodning i Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="735e3-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="735e3-106">Prediktiv kodningsmodulen i Advanced eDiscovery använder intelligenta maskininlärningsfunktionerna i Advanced eDiscovery hjälper dig att minska mängden innehåll som ska granskas.</span><span class="sxs-lookup"><span data-stu-id="735e3-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="735e3-107">Med förutsägande kodning kan du minska och anpassa stora mängder ärendeinnehåll till en relevant uppsättning objekt som du kan prioritera för granskning.</span><span class="sxs-lookup"><span data-stu-id="735e3-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="735e3-108">Detta sker genom att skapa och träna egna prediktiv kodningsmodeller som hjälper dig att prioritera granskningen av de mest relevanta objekten i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="735e3-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="735e3-109">Här är en snabb överblick över prediktiv kodningsprocess:</span><span class="sxs-lookup"><span data-stu-id="735e3-109">Here's an a quick overview of the predictive coding process:</span></span>

![Snabbstart för förutsägelsekodning](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="735e3-111">Kom igång genom att skapa en modell, etikettera så få som 50 objekt som relevanta eller inte relevanta.</span><span class="sxs-lookup"><span data-stu-id="735e3-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="735e3-112">Sedan använder systemet den här utbildningen för att tillämpa förutsägelseresultat på alla objekt i uppsättningen med granskning.</span><span class="sxs-lookup"><span data-stu-id="735e3-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="735e3-113">På så sätt kan du filtrera objekt baserat på förutsägelseresultatet, så att du först kan granska de mest relevanta (eller icke-relevanta) elementen.</span><span class="sxs-lookup"><span data-stu-id="735e3-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="735e3-114">Om du vill utbilda modeller med högre precision och återkallelsefrekvenser kan du fortsätta märka objekt i efterföljande utbildning avrundar tills modellen har en högre precision.</span><span class="sxs-lookup"><span data-stu-id="735e3-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="735e3-115">När modellen är bortfasad kan du använda det slutliga prognosfiltret och prioritera objekt att granska.</span><span class="sxs-lookup"><span data-stu-id="735e3-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="735e3-116">En detaljerad översikt över prediktiv kodning finns i [Lär dig mer om prediktiv kodning i Advanced eDiscovery](predictive-coding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="735e3-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="735e3-117">Steg 1: Skapa en ny prediktiv kodningsmodell</span><span class="sxs-lookup"><span data-stu-id="735e3-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="735e3-118">Det första steget är att skapa en ny prediktiv kodmodell i granskningsuppsättningen</span><span class="sxs-lookup"><span data-stu-id="735e3-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="735e3-119">I Microsoft 365, öppna ett ärende Advanced eDiscovery välj sedan fliken **Granska uppsättningar.**</span><span class="sxs-lookup"><span data-stu-id="735e3-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="735e3-120">Öppna en granskningsuppsättning och klicka sedan **på Analys**  >  **Hantera prediktiv kodning (förhandsgranskning).**</span><span class="sxs-lookup"><span data-stu-id="735e3-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![Klicka på listrutan Analysera i granskningsuppsättningen för att gå till sidan Predictive coding](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="735e3-122">Klicka på **Ny modell på sidan Prediktiv kodningsmodeller (förhandsversion).** </span><span class="sxs-lookup"><span data-stu-id="735e3-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="735e3-123">Ange ett namn för modellen och en valfri beskrivning på den utfällbara sidan.</span><span class="sxs-lookup"><span data-stu-id="735e3-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="735e3-124">Klicka **på** Spara för att skapa modellen.</span><span class="sxs-lookup"><span data-stu-id="735e3-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="735e3-125">Det tar några minuter innan systemet har förberett modellen.</span><span class="sxs-lookup"><span data-stu-id="735e3-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="735e3-126">När den är klar kan du utföra den första utbildningsomgången.</span><span class="sxs-lookup"><span data-stu-id="735e3-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="735e3-127">Mer detaljerade anvisningar finns i Skapa [en prediktiv kodningsmodell](predictive-coding-create-model.md).</span><span class="sxs-lookup"><span data-stu-id="735e3-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="735e3-128">Steg 2: Genomför den första utbildningsomgången</span><span class="sxs-lookup"><span data-stu-id="735e3-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="735e3-129">När du har skapat modellen är nästa steg att slutföra den första utbildningsomgången genom att märka objekt som relevanta eller inte relevanta.</span><span class="sxs-lookup"><span data-stu-id="735e3-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="735e3-130">Öppna granskningsuppsättningen och klicka sedan **på Analys**  >  **Hantera prediktiv kodning (förhandsgranskning).**</span><span class="sxs-lookup"><span data-stu-id="735e3-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="735e3-131">På sidan **Prediktiv kodningsmodeller (förhandsvisning)** väljer du den modell som du vill träna.</span><span class="sxs-lookup"><span data-stu-id="735e3-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="735e3-132">Klicka på **Starta** nästa utbildningsrunda under **Avrunda 1** **på fliken Översikt.**</span><span class="sxs-lookup"><span data-stu-id="735e3-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="735e3-133">Fliken **Utbildning** visas och innehåller 50 objekt som du kan lägga till etiketter för.</span><span class="sxs-lookup"><span data-stu-id="735e3-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="735e3-134">Granska varje dokument och välj sedan **knappen Relevant** eller **Inte relevant** längst ned i läsfönstret för att märka det.</span><span class="sxs-lookup"><span data-stu-id="735e3-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Märka varje dokument som relevant eller inte relevant](..\media\TrainModel1.png)

5. <span data-ttu-id="735e3-136">När du har etiketterat alla 50 objekt klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="735e3-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="735e3-137">Det tar några minuter innan systemet "lär sig" av etiketterna och uppdaterar modellen.</span><span class="sxs-lookup"><span data-stu-id="735e3-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="735e3-138">När den här processen är klar visas **statusen för Ready** för modellen på sidan **Predictive coding models (preview).**</span><span class="sxs-lookup"><span data-stu-id="735e3-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="735e3-139">Mer detaljerade anvisningar finns i Utbilda [en prediktiv kodningsmodell](predictive-coding-train-model.md).</span><span class="sxs-lookup"><span data-stu-id="735e3-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="735e3-140">Steg 3: Använd filtret för förutsägelseresultat för objekt i granskningsuppsättningen</span><span class="sxs-lookup"><span data-stu-id="735e3-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="735e3-141">När du har leasa en utbildningsrunda kan du använda filtret för förutsägelseresultat på objekt i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="735e3-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="735e3-142">Då kan du granska de objekt som modellen har prognosterat som relevanta eller inte relevanta.</span><span class="sxs-lookup"><span data-stu-id="735e3-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="735e3-143">Öppna granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="735e3-143">Open the review set.</span></span>

   ![Klicka på Filter för att visa den utfällade filtersidan](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="735e3-145">De förinstallerade standardfiltren visas högst upp på sidan för granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="735e3-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="735e3-146">Du kan låta dessa vara inställda på **Alla**.</span><span class="sxs-lookup"><span data-stu-id="735e3-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="735e3-147">Klicka **på Filter** så att den **utfällade sidan** Filter visas.</span><span class="sxs-lookup"><span data-stu-id="735e3-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="735e3-148">Expandera **analysavsnittet & förutsägelsekodning** för att visa en uppsättning filter.</span><span class="sxs-lookup"><span data-stu-id="735e3-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filter för förutsägelseresultat i & för förutsägelsekodning](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="735e3-150">Namngivningskonventioner för resultatfilter för **förutsägelser är Förutsägelseresultat (modellnamn).**</span><span class="sxs-lookup"><span data-stu-id="735e3-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="735e3-151">Namnet på filtret för förutsägelseresultat för en modell med namnet **Modell A** är till exempel **Prognosresultat (Modell A).**</span><span class="sxs-lookup"><span data-stu-id="735e3-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="735e3-152">Välj det filter för förutsägelseresultat som du vill använda och klicka sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="735e3-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="735e3-153">På sidan för granskningsuppsättningen klickar du på listrutan för filtret för förutsägelseresultat och anger minimi- och maxvärden för förutsägelseresultatintervallet.</span><span class="sxs-lookup"><span data-stu-id="735e3-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="735e3-154">Följande skärmbild visar till exempel ett resultatintervall för förutsägelse mellan **0,5** och **1,0.**</span><span class="sxs-lookup"><span data-stu-id="735e3-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Lägsta och högsta värden för filtret för förutsägelseresultat](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="735e3-156">Klicka utanför filtret så tillämpas filtret automatiskt på granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="735e3-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="735e3-157">En lista med dokument med ett förutsägelseresultat inom det angivna intervallet visas på sidan för granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="735e3-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="735e3-158">Mer detaljerade anvisningar finns i Använda [ett prognosfilter för en granskningsuppsättning](predictive-coding-apply-prediction-filter.md).</span><span class="sxs-lookup"><span data-stu-id="735e3-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="735e3-159">Steg 4: Genomför fler utbildningsrundar</span><span class="sxs-lookup"><span data-stu-id="735e3-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="735e3-160">Mer än troligt måste du utföra fler utbildningsrundar för att utbilda modulen för att bättre förutsäga relevanta och icke-relevanta objekt i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="735e3-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="735e3-161">I allmänhet kan du träna modellen tillräckligt många gånger tills den blir tillräckligt bra för att uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="735e3-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="735e3-162">Mer information finns i Utföra [ytterligare utbildning avrundar](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="735e3-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="735e3-163">Steg 5: Använd det slutliga betygsfiltret i förutsägelsen för att prioritera granskningen</span><span class="sxs-lookup"><span data-stu-id="735e3-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="735e3-164">Upprepa anvisningarna i steg 3 för att tillämpa det slutliga prognosresultatet på granskningsuppsättningen för att prioritera granskningen av relevanta och icke-relevanta objekt när du har slutfört alla utbildning avrundar och tillämpar modellen.</span><span class="sxs-lookup"><span data-stu-id="735e3-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
