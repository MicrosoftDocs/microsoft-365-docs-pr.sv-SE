---
title: Utbilda en prediktiv kodningsmodell i Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 84ec1ad42f2cec2487debe7160a3f24e09bdd830
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288197"
---
# <a name="train-a-predictive-coding-model-preview"></a><span data-ttu-id="3b8aa-102">Utbilda en prediktiv kodningsmodell (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="3b8aa-102">Train a predictive coding model (preview)</span></span>

<span data-ttu-id="3b8aa-103">När du har skapat en prognoskodningsmodell i Advanced eDiscovery är nästa steg att utföra den första utbildningsomgången för att utbilda modellen på vad som är relevant och icke-relevant innehåll i din granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-103">After you create a predictive coding model in Advanced eDiscovery, the next step is to performing the first training round to train the model on what is relevant and non-relevant content in your review set.</span></span> <span data-ttu-id="3b8aa-104">När du har slutfört den första utbildningsomgången kan du utföra efterföljande utbildningsrundar för att förbättra modellens möjlighet att förutsäga relevant och icke relevant innehåll.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-104">After you complete the first round of training, you can perform subsequent training rounds to improve the model's ability to predict relevant and non-relevant content.</span></span>

<span data-ttu-id="3b8aa-105">Information om hur du granskar arbetsflödet för förutsägelsekodning finns [i Lär dig mer om prediktiv kodning i Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span><span class="sxs-lookup"><span data-stu-id="3b8aa-105">To review the predictive coding workflow, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span></span>

## <a name="before-you-train-a-model"></a><span data-ttu-id="3b8aa-106">Innan du utbildar en modell</span><span class="sxs-lookup"><span data-stu-id="3b8aa-106">Before you train a model</span></span>

- <span data-ttu-id="3b8aa-107">Under en utbildningsrunda kan du **ange** att objekten ska **vara relevanta** eller inte relevanta baserat på hur relevant innehållet i dokumentet är.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-107">During a training round, label items as **Relevant** or **Not relevant** based on the relevancy of the content in the document.</span></span> <span data-ttu-id="3b8aa-108">Basera inte ditt beslut på värdena i metadatafälten.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-108">Don't base your decision on the values in the metadata fields.</span></span> <span data-ttu-id="3b8aa-109">Om du till exempel vill skicka e Teams eller konversationer baserar du inte etikettbeslutet på meddelandedeltagarna.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-109">For example, for email messages or Teams conversations, don't base your labeling decision on the message participants.</span></span>

## <a name="train-a-model-for-the-first-time"></a><span data-ttu-id="3b8aa-110">Utbilda en modell för första gången</span><span class="sxs-lookup"><span data-stu-id="3b8aa-110">Train a model for the first time</span></span>

1. <span data-ttu-id="3b8aa-111">I Microsoft 365 Efterlevnadscenter öppnar du ett Advanced eDiscovery och väljer sedan **fliken Granska uppsättningar.**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-111">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="3b8aa-112">Öppna en granskningsuppsättning och klicka sedan **på Analys**  >  **Hantera prediktiv kodning (förhandsgranskning).**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-112">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

3. <span data-ttu-id="3b8aa-113">På sidan **Prediktiv kodningsmodeller (förhandsvisning)** väljer du den modell som du vill träna.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-113">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

4. <span data-ttu-id="3b8aa-114">Klicka på **Starta** nästa utbildningsrunda under **Avrunda 1** **på fliken Översikt.**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-114">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="3b8aa-115">Fliken **Utbildning** visas och innehåller 50 objekt som du kan lägga till etiketter för.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-115">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

5. <span data-ttu-id="3b8aa-116">Granska varje dokument och välj sedan **knappen Relevant** eller **Inte relevant** längst ned i läsfönstret för att märka det.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-116">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Märka varje dokument som relevant eller inte relevant](..\media\TrainModel1.png)

6. <span data-ttu-id="3b8aa-118">När du har etiketterat alla 50 objekt klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-118">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="3b8aa-119">Det tar några minuter innan systemet "lär sig" av etiketterna och uppdaterar modellen.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-119">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="3b8aa-120">När den här processen är klar visas **statusen för Ready** för modellen på sidan **Predictive coding models (preview).**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-120">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

## <a name="perform-additional-training-rounds"></a><span data-ttu-id="3b8aa-121">Utföra ytterligare utbildningsrundar</span><span class="sxs-lookup"><span data-stu-id="3b8aa-121">Perform additional training rounds</span></span>

<span data-ttu-id="3b8aa-122">När du har genomför den första utbildningsomgången kan du utföra efterföljande utbildningsrundar genom att följa stegen i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-122">After you perform the first round of training, you can perform subsequent training rounds by following the steps in the previous section.</span></span> <span data-ttu-id="3b8aa-123">Den enda skillnaden är att numret på utbildningsomgången uppdateras på fliken **Modellöversikt.** Efter den första utbildningsomgången kan du till exempel klicka på **Starta nästa utbildningsrunda** för att starta den andra utbildningsomgången.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-123">The only difference is the number of the training round will be updated on the model **Overview** tab. For example, after performing the first training round, you can click **Start next training round** to start the second round of training.</span></span> <span data-ttu-id="3b8aa-124">Och så vidare.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-124">And so on.</span></span>

<span data-ttu-id="3b8aa-125">Varje omgång med utbildning (både pågående och pågående) visas på **fliken Utbildning** för modellen.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-125">Each round of training (both those in progress and those that are complete) is displayed on the **Training** tab for the model.</span></span> <span data-ttu-id="3b8aa-126">När du väljer en utbildningsrunda visas en utfällbordssida med information och mått för avrundningen.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-126">When you select a training round, a flyout page with information and metrics for the round is displayed.</span></span>

## <a name="what-happens-after-you-perform-a-training-round"></a><span data-ttu-id="3b8aa-127">Vad händer efter att du har genomför en utbildningsrunda?</span><span class="sxs-lookup"><span data-stu-id="3b8aa-127">What happens after you perform a training round</span></span>

<span data-ttu-id="3b8aa-128">När du har genomför den första utbildningsomgången startas ett jobb som gör följande:</span><span class="sxs-lookup"><span data-stu-id="3b8aa-128">After you perform the first training round, a job is started that does the following things:</span></span>

- <span data-ttu-id="3b8aa-129">Modellen lär sig av dina etiketter och uppdateringar baserat på hur du har etiketterat 40 objekt i utbildningsuppsättningen för att göra den mer exakt.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-129">Based on how you labeled the 40 items in the training set, the model learns from your labeling and updates itself to become more accurate.</span></span>

- <span data-ttu-id="3b8aa-130">Modellen bearbetar sedan varje objekt i hela granskningsuppsättningen och tilldelar ett prognosresultat mellan **0** (inte relevant) och **1** (relevant).</span><span class="sxs-lookup"><span data-stu-id="3b8aa-130">The model then processes each item in the entire review set and assigns a prediction score between **0** (not relevant) and **1** (relevant).</span></span>

- <span data-ttu-id="3b8aa-131">Modellen tilldelar ett förutsägelseresultat till de 10 objekten i kontrolluppsättningen som du har angett under utbildningsomgången.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-131">The model assigns a prediction score to the 10 items in the control set that you labeled during the training round.</span></span> <span data-ttu-id="3b8aa-132">Modellen jämför förutsägelseresultatet för dessa 10 objekt med den faktiska etikett som du har tilldelat till objektet under utbildningsomgången.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-132">The model compares the prediction score of these 10 items with the actual label that you assigned to the item during the training round.</span></span> <span data-ttu-id="3b8aa-133">Utifrån denna jämförelse identifierar modellen följande klassificering (kallas kontrolluppsättningens förväxlingsmatris) för att bedöma modellens prognosprestanda:</span><span class="sxs-lookup"><span data-stu-id="3b8aa-133">Based on this comparison, the model identifies the following classification (called the *Control set confusion matrix*) to assess the model's prediction performance:</span></span>

  <br>

  ****

  |<span data-ttu-id="3b8aa-134">Etikett</span><span class="sxs-lookup"><span data-stu-id="3b8aa-134">Label</span></span>|<span data-ttu-id="3b8aa-135">Modell förutsägelser om att objekt är relevanta</span><span class="sxs-lookup"><span data-stu-id="3b8aa-135">Model predicts item is relevant</span></span>|<span data-ttu-id="3b8aa-136">Modell förutsägelser om att objekt inte är relevanta</span><span class="sxs-lookup"><span data-stu-id="3b8aa-136">Model predicts item is not relevant</span></span>|
  |---|---|---|
  |<span data-ttu-id="3b8aa-137">**Granskaren ser objekt som relevant**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-137">**Reviewer labels item as relevant**</span></span>|<span data-ttu-id="3b8aa-138">Sant positivt</span><span class="sxs-lookup"><span data-stu-id="3b8aa-138">True positive</span></span>|<span data-ttu-id="3b8aa-139">Falskt positivt resultat</span><span class="sxs-lookup"><span data-stu-id="3b8aa-139">False positive</span></span>|
  |<span data-ttu-id="3b8aa-140">**Granskaren ser att objektet inte är relevant**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-140">**Reviewer labels item as not relevant**</span></span>|<span data-ttu-id="3b8aa-141">Falskt negativt</span><span class="sxs-lookup"><span data-stu-id="3b8aa-141">False negative</span></span>|<span data-ttu-id="3b8aa-142">Sant negativt</span><span class="sxs-lookup"><span data-stu-id="3b8aa-142">True negative</span></span>|
  |

  <span data-ttu-id="3b8aa-143">Utifrån dessa jämförelser härleder modellen värden för måtten F-poäng, precision och återkallelse samt felmarginalen för var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-143">Based on these comparisons, the model derives values for the F-score, precision, and recall metrics and the margin of error for each one.</span></span> <span data-ttu-id="3b8aa-144">Resultat för dessa modellprestandamätvärden visas på en utfällbordssida för utbildningsomgången.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-144">Scores for these model performance metrics are displayed on a flyout page for the training round.</span></span> <span data-ttu-id="3b8aa-145">En beskrivning av mätvärdena finns i [Prediktiv kodningsreferens](predictive-coding-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3b8aa-145">For a description of these metrics, see [Predictive coding reference](predictive-coding-reference.md).</span></span>

- <span data-ttu-id="3b8aa-146">Slutligen avgör modellen de nästa 50 objekt som ska användas för nästa utbildningsomgång.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-146">Finally, the model determines the next 50 items that will be used for the next training round.</span></span> <span data-ttu-id="3b8aa-147">Den här gången kan modellen välja 20 objekt i kontrolluppsättningen och 30 nya objekt från granskningsuppsättningen och ange dem som utbildningsuppsättning för nästa omgång.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-147">This time, the model might select 20 items from the control set and 30 new items from the review set and designate them as the training set for the next round.</span></span> <span data-ttu-id="3b8aa-148">Samplingen för nästa utbildningsrunda sampel sker inte enhetligt.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-148">The sampling for the next training round is not uniformly sampled.</span></span> <span data-ttu-id="3b8aa-149">Modellen optimerar urval av objekt från granskningsuppsättningen för att välja objekt där prognosen är tvetydig, vilket innebär att prognosresultatet ligger i intervallet 0,5.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-149">The model will optimize the sampling selection of items from the review set to select items where the prediction is ambiguous, which means the prediction score is in the 0.5 range.</span></span> <span data-ttu-id="3b8aa-150">Den här processen kallas för *partisk markering.*</span><span class="sxs-lookup"><span data-stu-id="3b8aa-150">This process is known as *biased selection*.</span></span>

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a><span data-ttu-id="3b8aa-151">Vad som händer efter att du har avrundat efterföljande kurser</span><span class="sxs-lookup"><span data-stu-id="3b8aa-151">What happens after you perform subsequent training rounds</span></span>

<span data-ttu-id="3b8aa-152">När du har avrundat ytterligare utbildning (efter den första utbildningsomgången) gör modellen följande:</span><span class="sxs-lookup"><span data-stu-id="3b8aa-152">After you perform subsequent training rounds (after the first training round), the model does the following things:</span></span>

- <span data-ttu-id="3b8aa-153">Modellen uppdateras baserat på etiketterna som du har använt för utbildningsuppsättningen i den omgången av utbildningen.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-153">The model is updated based on the labels that you applied to the training set in that round of training.</span></span>

- <span data-ttu-id="3b8aa-154">Systemet utvärderar modellens prognosresultat på objekten i kontrolluppsättningen och kontrollerar om resultatet överensstämmer med hur du etiketterade objekt i kontrolluppsättningen.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-154">The system evaluates the model's prediction score on the items in the control set and check whether the score aligns with how you labeled items in the control set.</span></span> <span data-ttu-id="3b8aa-155">Utvärderingen utförs på alla märkta objekt från kontrolluppsättningen för alla utbildningsrundar.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-155">The evaluation is performed on all labeled items from control set for all training rounds.</span></span> <span data-ttu-id="3b8aa-156">Resultaten av den här utvärderingen har tagits med i instrumentpanelen på **fliken** Översikt för modellen.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-156">The results of this evaluation are incorporated in the dashboard on the **Overview** tab for the model.</span></span>

- <span data-ttu-id="3b8aa-157">Den uppdaterade modellen bearbetar alla objekt i granskningsuppsättningen och tilldelar varje objekt ett uppdaterat prognosresultat.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-157">The updated model reprocesses every item in the review set and assign each item an updated prediction score.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b8aa-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3b8aa-158">Next steps</span></span>

<span data-ttu-id="3b8aa-159">Efter att du har genomför den första utbildningsomgången kan du utföra fler utbildningsrundar eller använda modellens resultatfilter för förutsägelseresultat för granskningsuppsättningen för att visa de objekt som modellen har prognosterat som relevanta eller inte relevanta.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-159">After you perform the first training round, you can perform more training rounds or apply the model's prediction score filter to the review set to view the items the model has predicted as relevant or not relevant.</span></span> <span data-ttu-id="3b8aa-160">Mer information finns i Använda [ett filter för förutsägelseresultat i en granskningsuppsättning](predictive-coding-apply-prediction-filter.md).</span><span class="sxs-lookup"><span data-stu-id="3b8aa-160">For more information, see [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>
