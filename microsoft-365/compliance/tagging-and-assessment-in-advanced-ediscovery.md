---
title: Märkning och utvärdering i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Gå igenom stegen för att utföra utvärderingsutbildning, inklusive taggning av filer och granskning av utvärderingsresultat i Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161777"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="75052-103">Tagga och bedöma i modulen Relevans i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="75052-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="75052-104">I det här avsnittet beskrivs proceduren för Bedömning i modulen Relevans i Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="75052-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="75052-105">Utföra utvärderingsutbildning och -analys</span><span class="sxs-lookup"><span data-stu-id="75052-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="75052-106">Klicka på **Utvärdering \> på fliken** Relevansspår **för att** starta fallutvärderingen.</span><span class="sxs-lookup"><span data-stu-id="75052-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="75052-107">Till exempel i den här proceduren skapas ett exempel på en  utvärderingsuppsättning med 500 filer och fliken Tagg visas, som innehåller panelen Taggning, visat filinnehåll och andra taggningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="75052-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Fliken Relevanstagg för bedömning](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="75052-109">Granska varje fil i exemplet, fastställ filens relevans för varje ärendeproblem och tagga filen med hjälp av knapparna Relevans (R), Inte relevant (NR) och Hoppa över i fönstret **Taggning.**</span><span class="sxs-lookup"><span data-stu-id="75052-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="75052-110">För bedömningen krävs 500 taggade filer.</span><span class="sxs-lookup"><span data-stu-id="75052-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="75052-111">Om filerna "hoppas över" får du fler filer att tagga.</span><span class="sxs-lookup"><span data-stu-id="75052-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="75052-112">När du har taggt alla filer i exemplet klickar du på **Beräkna**.</span><span class="sxs-lookup"><span data-stu-id="75052-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="75052-113">Den aktuella felmarginalen och relevansen för  Utvärdering beräknas och visas på fliken Relevansspår med utökad information per problem, enligt nedan.</span><span class="sxs-lookup"><span data-stu-id="75052-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="75052-114">Mer information om den här dialogrutan finns i avsnittet [Granska utvärderingsresultat.](#reviewing-assessment-results)</span><span class="sxs-lookup"><span data-stu-id="75052-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Relevansspår – bedömning](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="75052-116">Som standard rekommenderar vi att du går vidare till standardsteget Nästa när indikatorn Utvärderingsstatus för problemet har slutförts, vilket indikerar att utvärderingsprovet har granskats och att tillräckliga relevanta filer har taggats.</span><span class="sxs-lookup"><span data-stu-id="75052-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="75052-117">> Om du vill visa resultaten  för fliken Spåra och kontrollera felmarginalen och  nästa steg klickar du annars på Ändra intill Nästa steg **,** väljer Fortsätt utvärdering och klickar sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="75052-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="75052-118">Klicka **på** Ändra till höger om kryssrutan **Utvärdering** för att visa och ange bedömningsparametrar per problem.</span><span class="sxs-lookup"><span data-stu-id="75052-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="75052-119">En **dialogruta** på utvärderingsnivå för varje problem visas, som i följande exempel:</span><span class="sxs-lookup"><span data-stu-id="75052-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Ärendeproblem på bedömningsnivå](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="75052-121">Följande parametrar för problemet beräknas och visas i **dialogrutan Utvärderingsnivå:**</span><span class="sxs-lookup"><span data-stu-id="75052-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="75052-122">**Målfelmarginal för uppskattningar av återkallelse**: Baserat på det här värdet beräknas det uppskattade antalet ytterligare filer som ska granskas.</span><span class="sxs-lookup"><span data-stu-id="75052-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="75052-123">Den marginal som används för återkallelsen är större än 75 % och med en konfidensnivå på 95 %.</span><span class="sxs-lookup"><span data-stu-id="75052-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="75052-124">**Ytterligare utvärderingsfiler** krävs: Anger hur många fler filer som behövs om den aktuella felmarginalens krav inte har uppfyllts.</span><span class="sxs-lookup"><span data-stu-id="75052-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="75052-125">Justera den aktuella felmarginalen och se effekten av olika felmarginaler (per problem):</span><span class="sxs-lookup"><span data-stu-id="75052-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="75052-126">Välj **ett problem** i listan Välj problem.</span><span class="sxs-lookup"><span data-stu-id="75052-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="75052-127">Ange **ett nytt värde i Målfelmarginal för** uppskattningar av återkallelse.</span><span class="sxs-lookup"><span data-stu-id="75052-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="75052-128">Klicka **på Uppdatera** värden om du vill se hur justeringarna kommer att påverkas.</span><span class="sxs-lookup"><span data-stu-id="75052-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="75052-129">Klicka **på** Avancerat **i dialogrutan Bedömningsnivå** för att se följande ytterligare parametrar och information:</span><span class="sxs-lookup"><span data-stu-id="75052-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Avancerade vyn Ärendeproblem på bedömningsnivå](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="75052-131">**Beräknad richness**: Beräknad richness enligt de aktuella utvärderingsresultaten</span><span class="sxs-lookup"><span data-stu-id="75052-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="75052-132">**För den antagna** återkallelsen: Som standard gäller målfelmarginalen för återkallelsen över 75 %.</span><span class="sxs-lookup"><span data-stu-id="75052-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="75052-133">Klicka **på** Redigera om du vill ändra den här parametern och kontrollera felmarginalen för ett annat intervall med återkallelsevärden.</span><span class="sxs-lookup"><span data-stu-id="75052-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="75052-134">**Konfidensnivå:** Som standard är den rekommenderade felmarginalen för konfidens 95 %.</span><span class="sxs-lookup"><span data-stu-id="75052-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="75052-135">Klicka **på** Redigera om du vill ändra den här parametern.</span><span class="sxs-lookup"><span data-stu-id="75052-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="75052-136">**Förväntad richness-felmarginal**: Det här är den förväntade felmarginalen när alla ytterligare utvärderingsfiler har granskats, givet de uppdaterade värdena.</span><span class="sxs-lookup"><span data-stu-id="75052-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="75052-137">**Ytterligare utvärderingsfiler** krävs: Med de uppdaterade värdena måste antalet ytterligare utvärderingsfiler granskas för att nå målet.</span><span class="sxs-lookup"><span data-stu-id="75052-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="75052-138">**Totalt antal utvärderingsfiler** krävs: Givet de uppdaterade värdena, totalt antal utvärderingsfiler som krävs för granskning.</span><span class="sxs-lookup"><span data-stu-id="75052-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="75052-139">**Förväntat antal relevanta filer under** bedömningen: Givet de uppdaterade värdena, visas det förväntade antalet relevanta filer i hela utvärderingen när alla ytterligare utvärderingsfiler har granskats.</span><span class="sxs-lookup"><span data-stu-id="75052-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="75052-140">Klicka **på Beräkna om värden** om parametrar ändras.</span><span class="sxs-lookup"><span data-stu-id="75052-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="75052-141">När du är klar och det finns ett problem klickar  du på **OK** för att spara ändringarna (eller Nästa när det finns flera problem att granska eller ändra och sedan **Slutför**).</span><span class="sxs-lookup"><span data-stu-id="75052-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="75052-142">När det finns flera problem, och alla problem har granskats eller justerats, visas en dialogruta för **Bedömningsnivå:** sammanfattning, enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="75052-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Sammanfattning av bedömningsnivå](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="75052-144">När utvärderingen är klar går du vidare till nästa steg i Relevansutbildning.</span><span class="sxs-lookup"><span data-stu-id="75052-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="75052-145">Granska utvärderingsresultat</span><span class="sxs-lookup"><span data-stu-id="75052-145">Reviewing assessment results</span></span>

<span data-ttu-id="75052-146">När ett utvärderingsexempel har taggats beräknas utvärderingsresultatet och visas på fliken Relevansspår.</span><span class="sxs-lookup"><span data-stu-id="75052-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="75052-147">Följande resultat visas i den utökade visningen av Spåra:</span><span class="sxs-lookup"><span data-stu-id="75052-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="75052-148">Utvärdering av aktuella felmarginaler för uppskattningar av återkallelse</span><span class="sxs-lookup"><span data-stu-id="75052-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="75052-149">Beräknad richness</span><span class="sxs-lookup"><span data-stu-id="75052-149">Estimated richness</span></span>

- <span data-ttu-id="75052-150">Ytterligare utvärderingsfiler krävs (för granskning)</span><span class="sxs-lookup"><span data-stu-id="75052-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="75052-151">Den aktuella utvärderingsfelmarginalen är den felmarginal som rekommenderas av Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="75052-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="75052-152">Talet som visas för de ytterligare utvärderingsfiler som krävs motsvarar den rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="75052-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="75052-153">Utvärderingsförloppet visar nivån för utvärderingens slutförande med hänsyn till den aktuella felmarginalen.</span><span class="sxs-lookup"><span data-stu-id="75052-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="75052-154">När utvärderingen pågår kommer användaren att tagga ett annat utvärderingsexempel.</span><span class="sxs-lookup"><span data-stu-id="75052-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="75052-155">När indikatorn för bedömningsförloppet visar utvärderingen som slutförd, innebär det att utvärderingsprovet har slutförts och att tillräckligt många relevanta filer har taggats.</span><span class="sxs-lookup"><span data-stu-id="75052-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="75052-156">I den utökade visningen Spåra visas det rekommenderade nästa steget, utvärderingsstatistik och åtkomst till detaljerade resultat.</span><span class="sxs-lookup"><span data-stu-id="75052-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="75052-157">När du är mycket låg är antalet ytterligare utvärderingsfiler som behövs för att nå ett minimalt antal relevanta filer för att få fram användbar statistik mycket hög.</span><span class="sxs-lookup"><span data-stu-id="75052-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="75052-158">Advanced eDiscovery du gå vidare till utbildningen.</span><span class="sxs-lookup"><span data-stu-id="75052-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="75052-159">Utvärderingsförloppet kommer att skuggas och ingen statistik är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="75052-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="75052-160">Om ingen statistiskt baserad stabilitet används ger det resultat med lägre precision och konfidensnivå.</span><span class="sxs-lookup"><span data-stu-id="75052-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="75052-161">Resultaten kan dock användas för att hitta relevanta filer när du inte behöver veta hur många procent av relevanta filer som hittats.</span><span class="sxs-lookup"><span data-stu-id="75052-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="75052-162">På samma sätt kan den här statusen användas för att utbilda problem med låg relevans, där relevansresultat kan påskynda åtkomsten till filer som är relevanta för ett visst problem.</span><span class="sxs-lookup"><span data-stu-id="75052-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="75052-163">På fliken **\> Relevansspår,** visa utökat problem, är följande visningsalternativ tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="75052-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="75052-164">Det rekommenderade nästa steget, till exempel Nästa **steg:** Du kan hoppa  över taggningen (per problem) genom att klicka på knappen Ändra till höger och sedan välja ett annat steg i **nästa steg.**</span><span class="sxs-lookup"><span data-stu-id="75052-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="75052-165">När utvärderingens förloppsindikator inte har slutförts kommer en utvärdering att vara nästa rekommenderade alternativ, att tagga fler utvärderingsfiler och öka statistikprecisionen.</span><span class="sxs-lookup"><span data-stu-id="75052-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="75052-166">Du kan ändra felmarginalen och bedöma dess påverkan genom att klicka på Ändra och i dialogrutan Utvärderingsnivå **,** ändra målfelmarginalen för uppskattningar av återkallelse **och** klicka på **Uppdatera värden.**</span><span class="sxs-lookup"><span data-stu-id="75052-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="75052-167">I den här dialogrutan kan du också visa avancerade alternativ genom att klicka på **Avancerat.**</span><span class="sxs-lookup"><span data-stu-id="75052-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="75052-168">Du kan visa ytterligare statistik för bedömningsnivån och deras påverkan genom att klicka på **Visa**.</span><span class="sxs-lookup"><span data-stu-id="75052-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="75052-169">I dialogrutan Med informationsresultat är statistik tillgänglig per problem, när det finns minst 500 taggade utvärderingsfiler och minst 18 filer är märkta som relevanta för problemet.</span><span class="sxs-lookup"><span data-stu-id="75052-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
