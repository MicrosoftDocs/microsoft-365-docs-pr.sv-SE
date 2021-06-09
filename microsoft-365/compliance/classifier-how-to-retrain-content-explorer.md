---
title: Så här tränar du en klassificerare i innehållsutforskaren på nytt
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
description: Lär dig hur du ger feedback till en utbildare i Innehållsutforskaren.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793070"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="2e288-103">Så här tränar du en klassificerare i innehållsutforskaren på nytt</span><span class="sxs-lookup"><span data-stu-id="2e288-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="2e288-104">En Microsoft 365 trainable classifier är ett verktyg som du kan träna för att känna igen olika typer av innehåll genom att ge det urval att titta på.</span><span class="sxs-lookup"><span data-stu-id="2e288-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="2e288-105">När du har utbildat dig kan du använda den för att identifiera objekt för tillämpning Office av känslighetsetiketter, principer för kommunikationsefterlevnad och bevarandeetiketter.</span><span class="sxs-lookup"><span data-stu-id="2e288-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="2e288-106">I den här artikeln beskrivs hur du förbättrar prestanda för anpassade utbildare och vissa i förväg utbildade klassificerare genom att ge dem ytterligare feedback.</span><span class="sxs-lookup"><span data-stu-id="2e288-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="2e288-107">Mer information om de olika typerna av klassificerare finns i [Läs mer om utbildare.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="2e288-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="2e288-108">I den här videon får du en snabb sammanfattning av justerings- och omtämtningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2e288-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="2e288-109">Du måste fortfarande läsa den här fullständiga artikeln för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="2e288-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="2e288-110">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="2e288-110">Permissions</span></span>

<span data-ttu-id="2e288-111">Så här kommer du åt klassificerare i Microsoft 365 kompatibilitetscenter:</span><span class="sxs-lookup"><span data-stu-id="2e288-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="2e288-112">Administratörsrollen för efterlevnad eller dataefterlevnad krävs för att utbilda en klassificerare</span><span class="sxs-lookup"><span data-stu-id="2e288-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="2e288-113">Du behöver konton med de här behörigheterna för att använda klassificerare i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="2e288-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="2e288-114">Scenario för bevarandeprincip: Roller för arkiveringshantering och bevarandehantering</span><span class="sxs-lookup"><span data-stu-id="2e288-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="2e288-115">Övergripande arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2e288-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e288-116">Du ger feedback i Innehållsutforskaren om att tillämpa bevarandeprinciper automatiskt Exchange objekt och använder klassificeraren som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="2e288-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="2e288-117">**Om du inte har någon bevarandeprincip som automatiskt tillämpar en bevarandeetikett på alla Exchange objekt och använder en klassificerare som villkor, slutar du här.**</span><span class="sxs-lookup"><span data-stu-id="2e288-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="2e288-118">När du använder dina klassificerare kanske du vill öka precisionen för klassificeringarna som de gör.</span><span class="sxs-lookup"><span data-stu-id="2e288-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="2e288-119">Det gör du genom att utvärdera kvaliteten på klassificeringarna för objekt som den har identifierat som en matchning eller inte en matchning.</span><span class="sxs-lookup"><span data-stu-id="2e288-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="2e288-120">När du har gör 30 utvärderingar för en klassificerare krävs den feedbacken och automatiskt omtämnande för sig själv.</span><span class="sxs-lookup"><span data-stu-id="2e288-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="2e288-121">Mer information om det övergripande arbetsflödet för att omtämna en klassificerare finns i Processflöde för att [omtämna en klassificerare.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="2e288-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="2e288-122">En klassificerare måste redan ha publicerats och användas innan den kan tränas om.</span><span class="sxs-lookup"><span data-stu-id="2e288-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="2e288-123">Så här tränar du en klassificerare i innehållsutforskaren på nytt</span><span class="sxs-lookup"><span data-stu-id="2e288-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="2e288-124">Logga in på Microsoft 365 efterlevnadscenter med rollåtkomst för efterlevnadsadministratörer eller säkerhetsadministratörer och öppna **Microsoft 365 dataklassificeringscenter**  >  **för**  >  **innehållsutforskaren för dataklassificering.**</span><span class="sxs-lookup"><span data-stu-id="2e288-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="2e288-125">Under listan **Filtrera på etiketter, informationstyper eller kategorier** **expanderar du Utbildande klassificerare.**</span><span class="sxs-lookup"><span data-stu-id="2e288-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e288-126">Det kan ta upp till åtta dagar för aggregerade objekt att visas under rubriken för de utbildande klassificerarna.</span><span class="sxs-lookup"><span data-stu-id="2e288-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="2e288-127">Välj den utbildare som du använde i den automatiska bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="2e288-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="2e288-128">Det här är den utbildande klassificerare som du kan ge feedback om.</span><span class="sxs-lookup"><span data-stu-id="2e288-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="2e288-129">Om ett objekt har en post i kolumnen **Bevarandeetikett** innebär det att objektet har klassificerats som ett `match` .</span><span class="sxs-lookup"><span data-stu-id="2e288-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="2e288-130">Om ett objekt inte har en post i kolumnen **Bevarandeetikett** innebär det att det klassificerades som ett `close match` .</span><span class="sxs-lookup"><span data-stu-id="2e288-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="2e288-131">Du kan förbättra klassificerarprecisionen mest genom att ge feedback på `close match` objekt.</span><span class="sxs-lookup"><span data-stu-id="2e288-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="2e288-132">Välj ett objekt och öppna det.</span><span class="sxs-lookup"><span data-stu-id="2e288-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="2e288-133">Du kan ge feedback på flera objekt samtidigt genom att välja alla och sedan välja **Förbättra klassificering** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="2e288-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="2e288-134">Välj **Ge feedback.**</span><span class="sxs-lookup"><span data-stu-id="2e288-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="2e288-135">I fönstret **Detaljerad feedback** väljer du **Matcha** om objektet är positivt.</span><span class="sxs-lookup"><span data-stu-id="2e288-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="2e288-136">Om objektet är en falsk positiv inställning, att det är det som felaktigt inkluderades i kategorin, väljer **du Inte en matchning**.</span><span class="sxs-lookup"><span data-stu-id="2e288-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="2e288-137">Om det finns en annan klassificerare som är lämpligare för objektet kan du välja det i listan Föreslå andra klassificerare som **kan klassificeras.**</span><span class="sxs-lookup"><span data-stu-id="2e288-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="2e288-138">Det här utlöser att den andra klassificeraren utvärderar objektet.</span><span class="sxs-lookup"><span data-stu-id="2e288-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="2e288-139">Välj **Skicka feedback** för att skicka din utvärdering av , `match` `not a match` klassificeringar och föreslå andra utbildare.</span><span class="sxs-lookup"><span data-stu-id="2e288-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="2e288-140">När du har angett 30 instanser av feedback till en klassificerare kommer den automatiskt att tränas om.</span><span class="sxs-lookup"><span data-stu-id="2e288-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="2e288-141">Omtämnad kan ta från en till fyra timmar.</span><span class="sxs-lookup"><span data-stu-id="2e288-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="2e288-142">Klassificerare kan bara omtämnas två gånger per dag.</span><span class="sxs-lookup"><span data-stu-id="2e288-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e288-143">Den här informationen går till klassificeraren i klientorganisationen, **den går inte tillbaka till Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="2e288-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="2e288-144">Öppna **Utbildare som klassificerar**.</span><span class="sxs-lookup"><span data-stu-id="2e288-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="2e288-145">Den klassificerare som använts i efterlevnadsprincipen för kommunikation visas under **rubriken Omutbildning.**</span><span class="sxs-lookup"><span data-stu-id="2e288-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![klassificerare i omtrainingsstatus](../media/classifier-retraining.png)

11. <span data-ttu-id="2e288-147">När du är klar med omtrainningen väljer du klassificeraren för att öppna översikten för omtraining.</span><span class="sxs-lookup"><span data-stu-id="2e288-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![översikt över klassningsresultat](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="2e288-149">Granska den rekommenderade åtgärden och förutsägelsejämförelserna för de omtämta och publicerade versionerna av klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="2e288-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="2e288-150">Om du är nöjd med resultatet av uttröjningen väljer **du Publicera om.**</span><span class="sxs-lookup"><span data-stu-id="2e288-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="2e288-151">Om du inte är nöjd med resultatet av utträmningen kan du välja att ge ytterligare feedback till klassificeraren i gränssnittet för Innehållsutforskaren och starta en annan omtrainingscykel eller inte göra någonting. I sådant fall används den publicerade versionen av klassificeraren fortsatt.</span><span class="sxs-lookup"><span data-stu-id="2e288-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Content Explorer interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="2e288-152">Information om att publicera om rekommendationer</span><span class="sxs-lookup"><span data-stu-id="2e288-152">Details on republishing recommendations</span></span>

<span data-ttu-id="2e288-153">Här är lite information om hur vi sammanställer rekommendationen om att publicera om en omtämnad klassificerare eller föreslå ytterligare omtraining.</span><span class="sxs-lookup"><span data-stu-id="2e288-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="2e288-154">För det krävs lite djupare förståelse för hur utbildande klassificerare fungerar.</span><span class="sxs-lookup"><span data-stu-id="2e288-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="2e288-155">Efter en omtrainning utvärderar vi klassificeraren prestanda för både objekten med feedback och de objekt som ursprungligen användes för att utbilda klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="2e288-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="2e288-156">För inbyggda modeller är objekt som används för att utbilda klassificeraren de objekt som används av Microsoft för att skapa modellen.</span><span class="sxs-lookup"><span data-stu-id="2e288-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="2e288-157">För anpassade modeller kommer objekt som används i den ursprungliga utbildningen som klassificeraren kommer från de webbplatser som du har lagt till för test och granskning.</span><span class="sxs-lookup"><span data-stu-id="2e288-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="2e288-158">Vi jämför prestandanumren för båda uppsättningarna med objekt för den omtämnad och publicerade klassificeraren för att ge en rekommendation om huruvida det fanns förbättring av publiceringen på nytt.</span><span class="sxs-lookup"><span data-stu-id="2e288-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2e288-159">Se även</span><span class="sxs-lookup"><span data-stu-id="2e288-159">See also</span></span>

- [<span data-ttu-id="2e288-160">Mer information om utbildningsbara klassificerare</span><span class="sxs-lookup"><span data-stu-id="2e288-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="2e288-161">Förvalda filnamnstillägg och filtyper som crawlas och analyseras i SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="2e288-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)