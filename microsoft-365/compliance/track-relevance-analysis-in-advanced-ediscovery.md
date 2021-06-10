---
title: Spåra relevansanalys i Advanced eDiscovery
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du visar och tolkar relevansutbildningsstatus och resultat för ärenden i Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161775"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="87177-103">Spåra relevansanalys i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="87177-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="87177-104">I Advanced eDiscovery visas den beräknade giltigheten för relevansutbildningen som utförs på fliken Tagg på fliken Relevansspår på fliken Relevans och visar nästa steg att ta i den iterativa utbildningsprocessen i Relevans.</span><span class="sxs-lookup"><span data-stu-id="87177-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="87177-105">Spåra relevansutbildningsstatus</span><span class="sxs-lookup"><span data-stu-id="87177-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="87177-106">Visa följande information i Relevansspår för problem med ärendet, som du ser i följande exempel på dialogrutan **Problemnamn** nedan.</span><span class="sxs-lookup"><span data-stu-id="87177-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="87177-107">**Utvärdering**: Den här förloppsindikatorn visar i vilken grad relevansutbildningen som utförts i det här läget har uppnått utvärderingsmålet när det gäller marginaler för fel.</span><span class="sxs-lookup"><span data-stu-id="87177-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="87177-108">Relevansutbildningens relevansresultat visas också.</span><span class="sxs-lookup"><span data-stu-id="87177-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="87177-109">**Utbildning:** Den här färgkodade förloppsindikatorn och knapptipset anger stabilitet för relevansutbildningsresultat och en numerisk skala som visar antalet exempel på relevansutbildning taggade för varje problem.</span><span class="sxs-lookup"><span data-stu-id="87177-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="87177-110">Experten övervakar förloppet för iterativ relevans-utbildningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="87177-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="87177-111">**Batchberäkning:** Den här förloppsindikatorn innehåller information om slutförande av batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="87177-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="87177-112">**Nästa steg**: Visar rekommendationen för nästa steg som ska utföras.</span><span class="sxs-lookup"><span data-stu-id="87177-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="87177-113">I exemplet visas en genomförd bedömning för ett problem, som anges med indikatorn för slutfört färgförloppet och bockmarkeringen.</span><span class="sxs-lookup"><span data-stu-id="87177-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="87177-114">Taggningen pågår, men ärendet betraktas fortfarande som instabilt (stabilitetsstatus visas också i ett verktygstips).</span><span class="sxs-lookup"><span data-stu-id="87177-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="87177-115">Rekommendationen i nästa steg är "Utbildning".</span><span class="sxs-lookup"><span data-stu-id="87177-115">The next step recommendation is "Training".</span></span> 
  
    ![Relevans Spåra utbildning steg 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="87177-117">I den utökade vyn visas ytterligare information och alternativ.</span><span class="sxs-lookup"><span data-stu-id="87177-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="87177-118">Den aktuella felmarginalen som visas är felmarginalen för återkallelsen under aktuell bedömningstillstånd, givet de befintliga (redan taggade) utvärderingsfilerna.</span><span class="sxs-lookup"><span data-stu-id="87177-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="87177-119">Du kan kringgå utvärderingssteget genom att avmarkera **kryssrutan** Utvärdering per problem och sedan för "alla problem".</span><span class="sxs-lookup"><span data-stu-id="87177-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="87177-120">Därför finns det ingen statistik för det här problemet.</span><span class="sxs-lookup"><span data-stu-id="87177-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="87177-121">> Du **kan bara** avmarkera kryssrutan Utvärdering innan utvärderingen utförs.</span><span class="sxs-lookup"><span data-stu-id="87177-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="87177-122">Om det finns flera ärenden i ett ärende kringgås bedömningen endast om kryssrutan avmarkeras för varje ärende</span><span class="sxs-lookup"><span data-stu-id="87177-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="87177-123">När utvärderingen inte är klar med den första exempeluppsättningen med filer kan utvärderingen vara nästa steg för att tagga fler filer.</span><span class="sxs-lookup"><span data-stu-id="87177-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="87177-124">I  \> **Relevansspår** visar indikatorn och verktygstipset det uppskattade antalet ytterligare prover som behövs för att nå stabiliteten.</span><span class="sxs-lookup"><span data-stu-id="87177-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="87177-125">Den här uppskattningen ger riktlinjer för den ytterligare utbildning som krävs.</span><span class="sxs-lookup"><span data-stu-id="87177-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Relevans spåra utbildning](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="87177-127">När du är klar med taggningen och behöver fortsätta med utbildningen klickar du på **Utbildning.**</span><span class="sxs-lookup"><span data-stu-id="87177-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="87177-128">Ett annat exempel på filer genereras från den inlästa filuppsättningen för ytterligare utbildning.</span><span class="sxs-lookup"><span data-stu-id="87177-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="87177-129">Du kommer sedan tillbaka till fliken Tagga för att tagga och utbilda fler filer.</span><span class="sxs-lookup"><span data-stu-id="87177-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="87177-130">Nå stabila utbildningsnivåer</span><span class="sxs-lookup"><span data-stu-id="87177-130">Reaching stable training levels</span></span>

<span data-ttu-id="87177-131">När utvärderingsfilerna har besehållen en stabil nivå av utbildning är Advanced eDiscovery klar för batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="87177-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87177-132">Efter tre stabila utbildningsexempel är vanligtvis nästa steg "Batchberäkning".</span><span class="sxs-lookup"><span data-stu-id="87177-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="87177-133">Det kan finnas undantag, till exempel när det har gjorts ändringar av taggningen av filer från tidigare exempel eller när startfiler har lagts till.</span><span class="sxs-lookup"><span data-stu-id="87177-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="87177-134">Utföra batchberäkning</span><span class="sxs-lookup"><span data-stu-id="87177-134">Performing Batch calculation</span></span>

<span data-ttu-id="87177-135">Batchberäkning utförs som nästa steg när utbildningen har slutförts (när en stabil utbildningsstatus visas i förloppsfältet, en bockmarkering och en stabil status i verktygstipset.) Vid batchberäkning används kunskaper som förvärvats under relevansutbildningen för hela filpopulationen, för att bedöma filernas relevans och för att tilldela relevansresultat.</span><span class="sxs-lookup"><span data-stu-id="87177-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="87177-136">Om det finns mer än ett problem görs batchberäkningen per problem.</span><span class="sxs-lookup"><span data-stu-id="87177-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="87177-137">Vid batchberäkning övervakas förloppet under bearbetningen av alla filer.</span><span class="sxs-lookup"><span data-stu-id="87177-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="87177-138">Här är det rekommenderade nästa steg "Ingen", vilket betyder att det inte krävs någon ytterligare iterativ relevansutbildning i det här läget.</span><span class="sxs-lookup"><span data-stu-id="87177-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="87177-139">Nästa fas är fliken **Relevans \> Bestäm.**</span><span class="sxs-lookup"><span data-stu-id="87177-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="87177-140">Om du vill importera nya filer efter batchberäkningen kan administratören lägga till de importerade filerna i en ny inläsning.</span><span class="sxs-lookup"><span data-stu-id="87177-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87177-141">Om du klickar **på** Avbryt under batchberäkningen sparar processen det som redan utfördes.</span><span class="sxs-lookup"><span data-stu-id="87177-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="87177-142">Om du kör Batchberäkning igen fortsätter processen från den senaste körningspunkten.</span><span class="sxs-lookup"><span data-stu-id="87177-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="87177-143">Utvärdera taggningskonsekvens</span><span class="sxs-lookup"><span data-stu-id="87177-143">Assessing tagging consistency</span></span>

<span data-ttu-id="87177-144">Om det finns inkonsekvenser i filtaggarna kan det påverka analysen.</span><span class="sxs-lookup"><span data-stu-id="87177-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="87177-145">Du Advanced eDiscovery att tagga konsekvensprocessen när resultaten inte är optimala eller om konsekvensen är osäker.</span><span class="sxs-lookup"><span data-stu-id="87177-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="87177-146">En lista med möjliga inkonsekventa taggade filer returneras och de kan granskas och omtaggas vid behov.</span><span class="sxs-lookup"><span data-stu-id="87177-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87177-147">Efter sju eller fler utbildningsrundar efter bedömningen  kan konsekvent märkning visas i Relevans spåra problem \>  \>  \> **Detaljerade resultat** \> **Utbildning:**</span><span class="sxs-lookup"><span data-stu-id="87177-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="87177-148">Den här granskningen är klar för ett problem i taget.</span><span class="sxs-lookup"><span data-stu-id="87177-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="87177-149">Utöka **raden \> för** ett problem i Relevansspår.</span><span class="sxs-lookup"><span data-stu-id="87177-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="87177-150">Klicka på Ändra **till höger om** Nästa **steg.**</span><span class="sxs-lookup"><span data-stu-id="87177-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="87177-151">Välj **Tagga inkonsekvenser som** alternativet **Nästa steg,** efter sju utbildningsexempel och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="87177-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="87177-152">Välj **Tagga inkonsekvenser**.</span><span class="sxs-lookup"><span data-stu-id="87177-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="87177-153">Fliken **Flagga** öppnas och visar en lista över inkonsekvenser av att tagga om vid behov.</span><span class="sxs-lookup"><span data-stu-id="87177-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="87177-154">Skicka **ändringarna** genom att klicka på Beräkna.</span><span class="sxs-lookup"><span data-stu-id="87177-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="87177-155">Nästa steg efter taggningen av inkonsekvenser är "Utbildning".</span><span class="sxs-lookup"><span data-stu-id="87177-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="87177-156">Visa och använda relevansresultat</span><span class="sxs-lookup"><span data-stu-id="87177-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="87177-157">På fliken **\> Relevansspår** expanderar du raden för ett problem och klickar på **Visa** bredvid Detaljerade **resultat.**</span><span class="sxs-lookup"><span data-stu-id="87177-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="87177-158">Detaljerade resultatfönster visas enligt beskrivningen nedan.</span><span class="sxs-lookup"><span data-stu-id="87177-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Detaljerade resultat för relevansutbildning](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="87177-160">Tagga sammanfattning</span><span class="sxs-lookup"><span data-stu-id="87177-160">Tagging summary</span></span>

 <span data-ttu-id="87177-161">I exemplet nedan visar **taggningssammanfattningen** summor för varje process för bedömning, utbildning och uppföljningsfiltaggar.</span><span class="sxs-lookup"><span data-stu-id="87177-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Sammanfattning av relevansmarkeringar](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="87177-163">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="87177-163">Keywords</span></span>

<span data-ttu-id="87177-164">Ett nyckelord är en unik sträng, ett ord, en fras eller en sekvens av ord i en fil som identifieras av Advanced eDiscovery som en viktig indikator på om en fil är relevant.</span><span class="sxs-lookup"><span data-stu-id="87177-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="87177-165">Nyckelordet och vikterna för "Inkludera" i kolumner är märkta som relevanta och i kolumnerna "Uteslut" anges nyckelord och vikter i filer som är märkta som Inte relevanta.</span><span class="sxs-lookup"><span data-stu-id="87177-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="87177-166">Advanced eDiscovery tilldelar negativa eller positiva viktvärden.</span><span class="sxs-lookup"><span data-stu-id="87177-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="87177-167">Ju högre vikt, desto högre sannolikhet är det att en fil där nyckelordet visas tilldelas ett högre relevansresultat vid batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="87177-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="87177-168">Listan Advanced eDiscovery nyckelord kan användas för att komplettera en lista som skapats av en expert eller som en indirekt sanitetskontroll när som helst i filgranskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="87177-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="87177-169">Utbildningsstatus</span><span class="sxs-lookup"><span data-stu-id="87177-169">Training progress</span></span>

<span data-ttu-id="87177-170">Fönstret **Utbildningsstatus** innehåller ett diagram för utbildningsstatus och en kvalitetsindikator, som visas i exemplet nedan.</span><span class="sxs-lookup"><span data-stu-id="87177-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Relevans Spåra utbildningsstatus](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="87177-172">**Indikator för utbildningskvalitet**: Visar klassificeringen av taggningskonsekvensen enligt följande:</span><span class="sxs-lookup"><span data-stu-id="87177-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="87177-173">**Bra:** Filer är taggade konsekvent.</span><span class="sxs-lookup"><span data-stu-id="87177-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="87177-174">(Grön lampa visas)</span><span class="sxs-lookup"><span data-stu-id="87177-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="87177-175">**Medel:** Vissa filer kan vara taggade inkonsekventa.</span><span class="sxs-lookup"><span data-stu-id="87177-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="87177-176">(Gult ljus visas)</span><span class="sxs-lookup"><span data-stu-id="87177-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="87177-177">**Varning!** Många filer kan vara taggade inkonsekventa.</span><span class="sxs-lookup"><span data-stu-id="87177-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="87177-178">(Röd lampa visas)</span><span class="sxs-lookup"><span data-stu-id="87177-178">(Red light displayed)</span></span>

<span data-ttu-id="87177-179">**Diagram över utbildningsförlopp**: Visar graden av stabilitet för relevansutbildning efter många relevansutbildningscykler i jämförelse med värdet för F-mått.</span><span class="sxs-lookup"><span data-stu-id="87177-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="87177-180">När vi flyttar från vänster till höger över diagrammet för smalas konfidensintervallet och används, tillsammans med F-måttet, av Advanced eDiscovery Relevans för att säkerställa stabilitet när relevansutbildningsresultaten är optimerade.</span><span class="sxs-lookup"><span data-stu-id="87177-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87177-181">Relevans använder F2, ett F-måttmått där Återkallelse får dubbelt så stor vikt som precision.</span><span class="sxs-lookup"><span data-stu-id="87177-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="87177-182">I fall med hög relevans (över 25 %) använder relevansen F1 (förhållandet 1:1).</span><span class="sxs-lookup"><span data-stu-id="87177-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="87177-183">F-måttförhållandet kan konfigureras i **Relevansinställning** \> **Avancerade inställningar.**</span><span class="sxs-lookup"><span data-stu-id="87177-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="87177-184">Resultat av batchberäkning</span><span class="sxs-lookup"><span data-stu-id="87177-184">Batch calculation results</span></span>

<span data-ttu-id="87177-185">I **fönstret Batchberäkningsresultat** visas antalet filer som har poängts för relevans enligt följande:</span><span class="sxs-lookup"><span data-stu-id="87177-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="87177-186">**Lyckades**</span><span class="sxs-lookup"><span data-stu-id="87177-186">**Success**</span></span>
  
- <span data-ttu-id="87177-187">**Tom:** Innehåller ingen text, till exempel endast blanksteg/tabbar</span><span class="sxs-lookup"><span data-stu-id="87177-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="87177-188">**Misslyckades:** På grund av för stor storlek eller kunde inte läsas</span><span class="sxs-lookup"><span data-stu-id="87177-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="87177-189">**Ignoreras:** På grund av för stor storlek</span><span class="sxs-lookup"><span data-stu-id="87177-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="87177-190">**Nebulous**: Innehåller meningslös text eller inga funktioner som är relevanta för problemet</span><span class="sxs-lookup"><span data-stu-id="87177-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="87177-191">Empty, Failed, Ignored eller Nebulous får relevansresultatet -1.</span><span class="sxs-lookup"><span data-stu-id="87177-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="87177-192">Utbildningsstatistik</span><span class="sxs-lookup"><span data-stu-id="87177-192">Training statistics</span></span>

<span data-ttu-id="87177-193">I **fönstret Statistik** för utbildning visas statistik och diagram utifrån resultat från Advanced eDiscovery Relevansutbildning.</span><span class="sxs-lookup"><span data-stu-id="87177-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Relevans Spåra utbildning – statistik](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="87177-195">I den här vyn visas följande:</span><span class="sxs-lookup"><span data-stu-id="87177-195">This view shows the following:</span></span>
  
- <span data-ttu-id="87177-196">**Review-recall ratio**: Jämförelse av resultat i enlighet med relevansresultat i en korrekt linjär granskning.</span><span class="sxs-lookup"><span data-stu-id="87177-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="87177-197">Återkallandet beräknas givet den angivna storleken för granskningen.</span><span class="sxs-lookup"><span data-stu-id="87177-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="87177-198">**Parametrar:** Kumulativ beräknad statistik som hör till granskningsuppsättningen i relation till filens population för hela ärendet.</span><span class="sxs-lookup"><span data-stu-id="87177-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="87177-199">**Granska:** Procentandel av filer som ska granskas baserat på den här brytningen.</span><span class="sxs-lookup"><span data-stu-id="87177-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="87177-200">**Återkalla:** Procentandel av relevanta filer i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87177-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="87177-201">**Fördelning efter relevansresultat:** Filer i den mörkgrå visningen till vänster är under brytresultatet.</span><span class="sxs-lookup"><span data-stu-id="87177-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="87177-202">I en verktygstips visas Relevansresultat och den relaterade procentandelen filer i granskningsfilen som angetts i förhållande till det totala antalet filer.</span><span class="sxs-lookup"><span data-stu-id="87177-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
