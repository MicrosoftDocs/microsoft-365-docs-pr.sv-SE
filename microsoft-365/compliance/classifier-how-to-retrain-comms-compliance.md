---
title: Så här tränar du en klassificerare i kommunikationsefterlevnad på nytt
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig hur du ger feedback till en utbildare som klassificerar enligt kommunikationsefterlevnad.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162015"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="7f4fb-103">Så här tränar du en klassificerare i kommunikationsefterlevnad på nytt</span><span class="sxs-lookup"><span data-stu-id="7f4fb-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="7f4fb-104">En Microsoft 365 trainable classifier är ett verktyg som du kan träna för att känna igen olika typer av innehåll genom att ge det urval att titta på.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="7f4fb-105">När du har utbildat dig kan du använda den för att identifiera objekt för tillämpning Office av känslighetsetiketter, principer för kommunikationsefterlevnad och bevarandeetiketter.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="7f4fb-106">I den här artikeln beskrivs hur du förbättrar prestanda för anpassade utbildare och vissa i förväg utbildade klassificerare genom att ge dem ytterligare feedback.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="7f4fb-107">Mer information om de olika typerna av klassificerare finns i [Läs mer om utbildare.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="7f4fb-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="7f4fb-108">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="7f4fb-108">Permissions</span></span>

<span data-ttu-id="7f4fb-109">Så här kommer du åt klassificerare i Microsoft 365 kompatibilitetscenter:</span><span class="sxs-lookup"><span data-stu-id="7f4fb-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="7f4fb-110">Administratörsrollen för efterlevnad eller dataefterlevnad krävs för att utbilda en klassificerare</span><span class="sxs-lookup"><span data-stu-id="7f4fb-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="7f4fb-111">Du behöver konton med de här behörigheterna för att använda klassificerare i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="7f4fb-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="7f4fb-112">Scenario: Scenario för kommunikationsefterlevnadspolicy: Insider-riskhanteringsadministratör, övervakande granskningsadministratör</span><span class="sxs-lookup"><span data-stu-id="7f4fb-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="7f4fb-113">Övergripande arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="7f4fb-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f4fb-114">Du ger feedback i den efterlevnadslösning som använder klassificeraren som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="7f4fb-115">**Om du inte har en princip för kommunikationsefterlevnad som använder en klassificerare som ett villkor ska du sluta här.**</span><span class="sxs-lookup"><span data-stu-id="7f4fb-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="7f4fb-116">När du använder dina klassificerare kanske du vill öka precisionen för klassificeringarna som de gör.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="7f4fb-117">Det gör du genom att utvärdera kvaliteten på klassificeringarna för objekt som den har identifierat som en matchning eller inte en matchning.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="7f4fb-118">När du har gör 30 utvärderingar för en klassificerare krävs den feedbacken och automatiskt omtämnande för sig själv.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="7f4fb-119">Mer information om det övergripande arbetsflödet för att omtämna en klassificerare finns i Processflöde för att [omtämna en klassificerare.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="7f4fb-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="7f4fb-120">En klassificerare måste redan ha publicerats och användas innan den kan tränas om.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="7f4fb-121">Så här kör du om en klassificerare i principer för kommunikationsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="7f4fb-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="7f4fb-122">Öppna den princip för kommunikationsefterlevnad som använder en klassificerare som ett villkor och välj ett av de identifierade objekten i **listan Väntande.**</span><span class="sxs-lookup"><span data-stu-id="7f4fb-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="7f4fb-123">Välj ellipsen och **Förbättra klassificering**.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="7f4fb-124">I fönstret **Detaljerad feedback** väljer du **Matcha** om objektet är positivt.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="7f4fb-125">Om objektet är en falsk positiv inställning, att det är det som felaktigt inkluderades i kategorin, väljer **du Inte en matchning**.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="7f4fb-126">Om det finns en annan klassificerare som är lämpligare för objektet kan du välja det i listan Föreslå andra klassificerare som **kan klassificeras.**</span><span class="sxs-lookup"><span data-stu-id="7f4fb-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="7f4fb-127">Det här utlöser att den andra klassificeraren utvärderar objektet.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="7f4fb-128">Du kan ge feedback på flera objekt samtidigt genom att välja alla och sedan **välja Ge detaljerad feedback** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="7f4fb-129">Välj **Skicka feedback** för att skicka din utvärdering av , `match` `not a match` klassificeringar och föreslå andra utbildare.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="7f4fb-130">När du har angett 30 instanser av feedback till en klassificerare kommer den automatiskt att tränas om.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="7f4fb-131">Det kan ta mellan 1 och 4 timmar att träna.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="7f4fb-132">Klassificerare kan bara omtämnas två gånger per dag.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f4fb-133">Den här informationen går till klassificeraren i klientorganisationen, **den går inte tillbaka till Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="7f4fb-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="7f4fb-134">Öppna sidan **Dataklassificering** i Microsoft 365 **kompatibilitetscenter.**</span><span class="sxs-lookup"><span data-stu-id="7f4fb-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="7f4fb-135">Öppna **Utbildare som klassificerar**.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="7f4fb-136">Den klassificerare som använts i efterlevnadsprincipen för kommunikation visas under **rubriken Omutbildning.**</span><span class="sxs-lookup"><span data-stu-id="7f4fb-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![klassificerare i omtrainingsstatus](../media/classifier-retraining.png)

9. <span data-ttu-id="7f4fb-138">När du är klar med omtrainningen väljer du klassificeraren för att öppna översikten för omtraining.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![översikt över klassningsresultat](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="7f4fb-140">Granska den rekommenderade åtgärden och förutsägelsejämförelserna för de omtämta och publicerade versionerna av klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="7f4fb-141">Om du är nöjd med resultatet av uttröjningen väljer **du Publicera om.**</span><span class="sxs-lookup"><span data-stu-id="7f4fb-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="7f4fb-142">Om du inte är nöjd med resultatet av omtämningen kan du välja att ge ytterligare feedback till klassificeraren i gränssnittet för kommunikationsefterlevnad och starta en annan omtrainingscykel eller inte göra någonting. I sådant fall används den publicerade versionen av klassificeraren fortsatt.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="7f4fb-143">Information om att publicera om rekommendationer</span><span class="sxs-lookup"><span data-stu-id="7f4fb-143">Details on republishing recommendations</span></span>

<span data-ttu-id="7f4fb-144">Här är lite information om hur vi sammanställer rekommendationen om att publicera om en omtämnad klassificerare eller föreslå ytterligare omtraining.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="7f4fb-145">För det krävs lite djupare förståelse för hur utbildande klassificerare fungerar.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="7f4fb-146">Efter en omtrainning utvärderar vi klassificeraren prestanda för både objekten med feedback och de objekt som ursprungligen användes för att utbilda klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="7f4fb-147">För inbyggda modeller är objekt som används för att utbilda klassificeraren de objekt som används av Microsoft för att skapa modellen.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="7f4fb-148">För anpassade modeller kommer objekt som används i den ursprungliga utbildningen som klassificeraren kommer från de webbplatser som du har lagt till för test och granskning.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="7f4fb-149">Vi jämför prestandanumren för båda uppsättningarna med objekt för den omtämnad och publicerade klassificeraren för att ge en rekommendation om huruvida det fanns förbättring av publiceringen på nytt.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="7f4fb-150">Se även</span><span class="sxs-lookup"><span data-stu-id="7f4fb-150">See also</span></span>

- [<span data-ttu-id="7f4fb-151">Mer information om utbildningsbara klassificerare</span><span class="sxs-lookup"><span data-stu-id="7f4fb-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="7f4fb-152">Förvalda filnamnstillägg och filtyper som crawlas och analyseras i SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="7f4fb-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)