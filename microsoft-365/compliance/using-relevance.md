---
title: Använd modulen Relevans för att analysera data i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lär dig hur relevansmodulen analyserar data som bevis tillsammans med en beskrivning av arbetsflödet för relevans och utbildning i Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161627"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="edfe1-103">Använd modulen Relevans för att analysera data i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="edfe1-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="edfe1-104">I Advanced eDiscovery i relevansmodulen ingår relevansutbildning och granskning av filer som är relaterade till ett ärende.</span><span class="sxs-lookup"><span data-stu-id="edfe1-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="edfe1-105">Om du vill använda arbetsflödet Relevans går du till Hantera granskningsuppsättningen i en granskningsuppsättning och klickar på Visa relevans.</span><span class="sxs-lookup"><span data-stu-id="edfe1-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="edfe1-106">Det finns några steg du måste slutföra innan du kan starta arbetsflödet:</span><span class="sxs-lookup"><span data-stu-id="edfe1-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="edfe1-107">Process: varje inläsningsuppsättning som läggs till i granskningsuppsättningen visas som en "behållare" här.</span><span class="sxs-lookup"><span data-stu-id="edfe1-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="edfe1-108">Du måste bearbeta de här dokumenten innan du kan lägga till dem i relevansmodulen. Här kan du också markera dem som starttagg eller förtaggade för ett specifikt problem.</span><span class="sxs-lookup"><span data-stu-id="edfe1-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="edfe1-109">Lägg till i Relevans: Under Relevans läses in kan du lägga till dokument som har bearbetats i \> relevans för att göra dem tillgängliga för utbildning.</span><span class="sxs-lookup"><span data-stu-id="edfe1-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="edfe1-110">Arbetsflödet Relevans visas och beskrivs på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="edfe1-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Arbetsflöde för relevans](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="edfe1-112">**Utvärderings- och spårningscykler:**</span><span class="sxs-lookup"><span data-stu-id="edfe1-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="edfe1-113">**Utvärdering**: Möjliggör tidig utvärdering baserat på ett slumpmässigt urval av filer och använder den här utvärderingen för att tillämpa beslut för att fastställa prestanda för prediktiv kodningsprocess.</span><span class="sxs-lookup"><span data-stu-id="edfe1-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="edfe1-114">**Spåra**: Beräkna och visa interimresultaten från utvärderingen medan du övervakar processens statistiska giltighet.</span><span class="sxs-lookup"><span data-stu-id="edfe1-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="edfe1-115">**Cykler för utbildning och spårning**</span><span class="sxs-lookup"><span data-stu-id="edfe1-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="edfe1-116">**Tagg:** Advanced eDiscovery relevanskriterier som är specifika för varje problem baserat på expertens iterativa granskning och taggning av enskilda filer.</span><span class="sxs-lookup"><span data-stu-id="edfe1-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="edfe1-117">**Spåra**: Beräkna och visa interimresultat av relevansutbildningen samtidigt som du övervakar processens statistiska giltighet.</span><span class="sxs-lookup"><span data-stu-id="edfe1-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="edfe1-118">**Batchberäkning:** De ackumulerade och inlärda relevansvillkoren tillämpas på hela filsamlingen och ett relevansresultat genereras för varje fil.</span><span class="sxs-lookup"><span data-stu-id="edfe1-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="edfe1-119">**Bestäm**: Resultatet av analysen som tillämpas på hela ärendet visas efter Batchberäkning, och data som används för att fatta beslut om dokumentgranskning visas.</span><span class="sxs-lookup"><span data-stu-id="edfe1-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="edfe1-120">**Test:** Resultaten kan testas för att verifiera giltigheten och effektiviteten i Advanced eDiscovery bearbetningen.</span><span class="sxs-lookup"><span data-stu-id="edfe1-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="edfe1-121">**Sökning:** När relevansarbetsflödet har slutförts kan du använda utdata, till exempel läs percentilen av ett dokument för problemet, när du kör en fråga i din granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="edfe1-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="edfe1-122">Riktlinjer för relevansutbildning och granskning</span><span class="sxs-lookup"><span data-stu-id="edfe1-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="edfe1-123">Här följer en översikt över riktlinjer för relevansutbildning och granskning:</span><span class="sxs-lookup"><span data-stu-id="edfe1-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="edfe1-124">**Fel och inkonsekvenser:** Om taggningsfel görs under utbildningen återgår du till tidigare filexempel för att korrigera dem.</span><span class="sxs-lookup"><span data-stu-id="edfe1-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="edfe1-125">Om det finns för många fel att åtgärda, eller om ärendet har ett nytt perspektiv, bör relevansvillkoren definieras om av administratören och relevansutbildningen startas om.</span><span class="sxs-lookup"><span data-stu-id="edfe1-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="edfe1-126">**Märkning och utbildning:**</span><span class="sxs-lookup"><span data-stu-id="edfe1-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="edfe1-127">Filer ska taggas baserat på endast innehåll.</span><span class="sxs-lookup"><span data-stu-id="edfe1-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="edfe1-128">Ta inte hänsyn till metadata, t.ex. dokument, datum eller sökväg.</span><span class="sxs-lookup"><span data-stu-id="edfe1-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="edfe1-129">Överväg inte datumintervallsdikationer i texten när du taggar filer.</span><span class="sxs-lookup"><span data-stu-id="edfe1-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="edfe1-130">Överväg inte att bädda in grafiska bilder när du taggar filer.</span><span class="sxs-lookup"><span data-stu-id="edfe1-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="edfe1-131">Ignorera text som har relevans tas bort i det filinnehåll som visas i textvyn i Relevans.</span><span class="sxs-lookup"><span data-stu-id="edfe1-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="edfe1-132">Om värdena för Ignorera text har definierats efter att Relevansutbildning redan påbörjats, tillämpas den nya ignorerade texten på exempelfiler som skapades från den plats där den definierades.</span><span class="sxs-lookup"><span data-stu-id="edfe1-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="edfe1-133">Funktionen Ignorera text bör användas försiktig, eftersom dess användning kan försämra prestandan för filanalys</span><span class="sxs-lookup"><span data-stu-id="edfe1-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="edfe1-134">Använd alternativet **Hoppa över taggningen** endast när det behövs.</span><span class="sxs-lookup"><span data-stu-id="edfe1-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="edfe1-135">Advanced eDiscovery utbildas inte baserat på överhoppade filer.</span><span class="sxs-lookup"><span data-stu-id="edfe1-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="edfe1-136">Om det är svårt att avgöra om en fil är relevant är det bättre att tagga som Relevant (R) eller Inte relevant (NR) när det är möjligt i stället för att välja **Hoppa över**.</span><span class="sxs-lookup"><span data-stu-id="edfe1-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="edfe1-137">När Advanced eDiscovery utvärderar utbildning kan du sedan se hur bra de här typerna av filer har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="edfe1-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="edfe1-138">Även filer med mycket lite extraherad text ska om möjligt taggas i utbildning som R/NR i stället för som "Hoppa över".</span><span class="sxs-lookup"><span data-stu-id="edfe1-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="edfe1-139">Taggningen kan påverka klassificeraren så länge filen är läsbar och kan märkas som R/NR.</span><span class="sxs-lookup"><span data-stu-id="edfe1-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="edfe1-140">Med filsekvensnumret i listan Exempelfiler  på fliken Tagg kan användaren återgå till den ursprungliga visade ordningen för filerna.</span><span class="sxs-lookup"><span data-stu-id="edfe1-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="edfe1-141">Du kan gå tillbaka till ett urval och ändra taggningen för utvärderings- och utbildningsuppsättningsfilerna.</span><span class="sxs-lookup"><span data-stu-id="edfe1-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="edfe1-142">Ändringarna används när nästa exempel skapas.</span><span class="sxs-lookup"><span data-stu-id="edfe1-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="edfe1-143">Genomsökta Excel-filer i PDF-format bör behandlas på samma sätt som ursprungliga filer Excel filer när du taggar filer.</span><span class="sxs-lookup"><span data-stu-id="edfe1-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="edfe1-144">Om du är osäker på relevansmarkeringar för en fil bör du kontakta en expert.</span><span class="sxs-lookup"><span data-stu-id="edfe1-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="edfe1-145">Felaktiga taggningar under relevansutbildningen kan leda till förlorad tid senare i processen och kan också påverka kvaliteten på det övergripande resultatet negativt.</span><span class="sxs-lookup"><span data-stu-id="edfe1-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="edfe1-146">Nyckelord som har definierats i nyckelordslistor visas i färger som hjälper användaren att identifiera relevanta filer medan de taggas.</span><span class="sxs-lookup"><span data-stu-id="edfe1-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="edfe1-147">**Batchberäkning:** Filer som har taggats som R/NR av experten får poäng på antingen 0 eller 100.</span><span class="sxs-lookup"><span data-stu-id="edfe1-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="edfe1-148">Det här gäller taggning som gjorts före batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="edfe1-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="edfe1-149">Om experten bytte problemet till Inaktiv efter Batchberäkning och fortsätter att tagga problemet blir de nyligen taggade betygen inte 100/0 utan snarare det ursprungliga resultatet.</span><span class="sxs-lookup"><span data-stu-id="edfe1-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="edfe1-150">**Problem- och samplingsläge:** Ärenden är vanligtvis avstängt när arbete med dem har slutförts (Relevansutbildning har avslutats och Batchberäkning utfördes), när ärendena avbryts eller när en annan användare arbetar med ärendena.</span><span class="sxs-lookup"><span data-stu-id="edfe1-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="edfe1-151">Steg i Relevansutbildning</span><span class="sxs-lookup"><span data-stu-id="edfe1-151">Steps in Relevance training</span></span>

<span data-ttu-id="edfe1-152">På fliken **\> Relevansspår** finns Advanced eDiscovery rekommendationer om hur du går vidare i bearbetningen, med följande steg.</span><span class="sxs-lookup"><span data-stu-id="edfe1-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="edfe1-153">Konsekvenserna beskrivs nedan när var och en av följande steg rekommenderas i relevansutbildningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="edfe1-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="edfe1-154">Taggning/fortsätt-taggning: Filgranskning och relevanstaggar som utförs av en expert för varje fil och problem i ett urval.</span><span class="sxs-lookup"><span data-stu-id="edfe1-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="edfe1-155">Implication: Ett befintligt urval måste märkas.</span><span class="sxs-lookup"><span data-stu-id="edfe1-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="edfe1-156">Utvärdering/Fortsätt bedömning: Möjliggör tidig validering av relevans för ärende och en preliminär vy av relevansen för den importerade filpopulationen för det aktuella ärendet.</span><span class="sxs-lookup"><span data-stu-id="edfe1-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="edfe1-157">Implication: More assessment is required or recommended.</span><span class="sxs-lookup"><span data-stu-id="edfe1-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="edfe1-158">Utbildning/Fortsätt utbildning: Processen under vilken Advanced eDiscovery lär sig av experten som taggar filproven och får möjlighet att identifiera relevanskriterier som är relevanta för varje problem inom ramen för varje ärende.</span><span class="sxs-lookup"><span data-stu-id="edfe1-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="edfe1-159">Implication: The issue needs more training; Nästa exempel bör skapas och taggas.</span><span class="sxs-lookup"><span data-stu-id="edfe1-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="edfe1-160">Batchberäkning: Relevansprocessen där Advanced eDiscovery kunskap från utbildningsfasen tillämpas på hela filpopulationen.</span><span class="sxs-lookup"><span data-stu-id="edfe1-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="edfe1-161">Alla filer i den relevanta filgruppen bedöms som relevanta och tilldelas ett relevansresultat.</span><span class="sxs-lookup"><span data-stu-id="edfe1-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="edfe1-162">Implication: The issue has enkelt, and Batch calculation can be performed.</span><span class="sxs-lookup"><span data-stu-id="edfe1-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="edfe1-163">Uppläsning: Relevans anger när en expert granskar och taggar ett urval av filer som valts ut vid ytterligare filinläsning under ett scenario med rullnings läses in.</span><span class="sxs-lookup"><span data-stu-id="edfe1-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="edfe1-164">Implication: A new load has been added, and Catch-up is required to continue working.</span><span class="sxs-lookup"><span data-stu-id="edfe1-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="edfe1-165">Tagga inkonsekvenser: Processen identifierar, via en Advanced eDiscovery-algoritm, inkonsekvenser i filtaggsprocessen som kan påverka analysen negativt.</span><span class="sxs-lookup"><span data-stu-id="edfe1-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="edfe1-166">Implication: I nästa exempel visas filer som har taggats i tidigare exempel, och deras taggning måste göras om.</span><span class="sxs-lookup"><span data-stu-id="edfe1-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="edfe1-167">Uppdatera klassificerare: Gör att användaren kan använda taggning eller lägga till ändringar.</span><span class="sxs-lookup"><span data-stu-id="edfe1-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="edfe1-168">Implication: Tagga och lägga till ändringar kan användas utan att du behöver köra ett annat exempel på Relevans manuellt.</span><span class="sxs-lookup"><span data-stu-id="edfe1-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="edfe1-169">Väntad: Relevansutbildningsprocessen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="edfe1-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="edfe1-170">Implication: No Relevance training is required at this point.</span><span class="sxs-lookup"><span data-stu-id="edfe1-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="edfe1-171">Även om Advanced eDiscovery hjälper dig genom processen, med rekommenderade steg i Nästa i olika steg, kan du också navigera mellan flikar och sidor och göra val för att ta itu med situationer som kan vara relevanta för ditt ärende, problem eller dokumentgranskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="edfe1-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="edfe1-172">Det går att godkänna eller åsidosätta bearbetningsalternativen Advanced eDiscovery nästa steg.</span><span class="sxs-lookup"><span data-stu-id="edfe1-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="edfe1-173">Om du vill utföra ett annat steg än  det rekommenderade nästa steget klickar du på nästa  steg som visas i den expanderade problemvisningen i dialogrutan, klickar på knappen Ändra bredvid nästa steg och väljer ett annat alternativ för Nästa steg.</span><span class="sxs-lookup"><span data-stu-id="edfe1-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="edfe1-174">Vissa alternativ kan vara inaktiverade efter upplåsning eftersom de inte stöds för användning vid den tidpunkten.</span><span class="sxs-lookup"><span data-stu-id="edfe1-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="edfe1-175">Mer information</span><span class="sxs-lookup"><span data-stu-id="edfe1-175">More information</span></span>

[<span data-ttu-id="edfe1-176">Förstå utvärdering i relevans</span><span class="sxs-lookup"><span data-stu-id="edfe1-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edfe1-177">Märkning och utvärdering</span><span class="sxs-lookup"><span data-stu-id="edfe1-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edfe1-178">Tagga och relevansutbildning</span><span class="sxs-lookup"><span data-stu-id="edfe1-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edfe1-179">Spåra relevansanalys</span><span class="sxs-lookup"><span data-stu-id="edfe1-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edfe1-180">Bestämma resultat</span><span class="sxs-lookup"><span data-stu-id="edfe1-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edfe1-181">Testa relevansanalys</span><span class="sxs-lookup"><span data-stu-id="edfe1-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="edfe1-182">Fråga data i en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="edfe1-182">Query the data in a review set</span></span>](review-set-search.md)
