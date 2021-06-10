---
title: Analys av testrelevans i Advanced eDiscovery
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du använder fliken Test efter Batchberäkning i Advanced eDiscovery för att testa, jämföra och verifiera den övergripande kvaliteten på bearbetningen.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161776"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="af971-103">Analys av testrelevans i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="af971-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="af971-104">På fliken Test i Advanced eDiscovery du testa, jämföra och verifiera den övergripande bearbetningskvaliteten.</span><span class="sxs-lookup"><span data-stu-id="af971-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="af971-105">Dessa tester utförs efter batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="af971-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="af971-106">Genom att tagga filerna i samlingen får en expert ett slutligt beslut om varje taggad fil är relevant för ärendet.</span><span class="sxs-lookup"><span data-stu-id="af971-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="af971-107">I scenarier med en eller flera problem utförs tester vanligtvis per problem.</span><span class="sxs-lookup"><span data-stu-id="af971-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="af971-108">Resultaten kan visas efter varje test och testresultaten kan omarbetas med angivna exempeltestfiler.</span><span class="sxs-lookup"><span data-stu-id="af971-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="af971-109">Testar resten</span><span class="sxs-lookup"><span data-stu-id="af971-109">Testing the rest</span></span>

<span data-ttu-id="af971-110">Testet "Testa resten" används för att verifiera beslut om validering, till exempel för att bara granska filer ovanför en viss poäng för relevansrensning baserat på det slutliga Advanced eDiscovery resultaten.</span><span class="sxs-lookup"><span data-stu-id="af971-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="af971-111">Experten granskar ett urval filer under en vald poäng för att utvärdera antalet relevanta filer i uppsättningen.</span><span class="sxs-lookup"><span data-stu-id="af971-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="af971-112">Det här testet ger statistik och en jämförelse mellan uppsättningen Granska och testa restpopulationen.</span><span class="sxs-lookup"><span data-stu-id="af971-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="af971-113">Resultatet av granskningsuppsättningen är de som beräknas efter Relevans under utbildning.</span><span class="sxs-lookup"><span data-stu-id="af971-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="af971-114">Resultatet omfattar beräkningar baserade på inställningar och indataparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="af971-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="af971-115">Testa exempelstatistik för antalet filer i ett urval och identifierade relevanta filer.</span><span class="sxs-lookup"><span data-stu-id="af971-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="af971-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span><span class="sxs-lookup"><span data-stu-id="af971-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="af971-117">Inställningar för kostnadsparameter kan anges av administratören.</span><span class="sxs-lookup"><span data-stu-id="af971-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="af971-118">Så här kör du testet "Testa resten":</span><span class="sxs-lookup"><span data-stu-id="af971-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="af971-119">Öppna fliken **\> Relevanstest.**</span><span class="sxs-lookup"><span data-stu-id="af971-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="af971-120">Klicka på **Nytt** test på **fliken Test.**</span><span class="sxs-lookup"><span data-stu-id="af971-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="af971-121">Dialogrutan **Skapa** test visas enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="af971-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Relevanstesta resten av resultaten](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="af971-123">Skriv **namn och** beskrivning **i** Testnamn och Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="af971-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="af971-124">I listan **Testtyp** väljer du **Testa resten**</span><span class="sxs-lookup"><span data-stu-id="af971-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="af971-125">Välj **namnet på problemet** i listan Problem/kategori.</span><span class="sxs-lookup"><span data-stu-id="af971-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="af971-126">I listan **Läs in** väljer du inläsningen.</span><span class="sxs-lookup"><span data-stu-id="af971-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="af971-127">I **Läs %** godkänner du standardvärdet eller väljer ett värde för poäng för relevans för bryt skärning.</span><span class="sxs-lookup"><span data-stu-id="af971-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="af971-128">I **Ange storlek** eller godkänn standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="af971-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="af971-129">Återställningsikonerna återställer standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="af971-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="af971-130">Klicka **på Börja tagga**.</span><span class="sxs-lookup"><span data-stu-id="af971-130">Click **Start tagging**.</span></span> <span data-ttu-id="af971-131">Ett testexempel genereras.</span><span class="sxs-lookup"><span data-stu-id="af971-131">A test sample is generated.</span></span>

10. <span data-ttu-id="af971-132">Granska och tagga varje fil på fliken **Relevanstagg \>** och klicka på Beräkna när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="af971-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="af971-133">På fliken Test kan du klicka på **Visa resultat för** att visa testresultaten.</span><span class="sxs-lookup"><span data-stu-id="af971-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="af971-134">Ett exempel visas i följande skärmbild.</span><span class="sxs-lookup"><span data-stu-id="af971-134">An example is shown in the following screenshot.</span></span>

    ![Testa resten av resultaten](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="af971-136">I den föregående  skärmbilden innehåller avsnittet Exempelparametrar i tabellen information om antalet filer i exemplet som taggats av experten och antalet relevanta filer som hittades i exemplet.</span><span class="sxs-lookup"><span data-stu-id="af971-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="af971-137">Avsnittet **Population-parametrar** i tabellen innehåller testresultaten, inklusive en population av filer i granskningsuppsättningen med ett resultat under den valda filpopulationen och "Resten" i populationen med ett resultat över den valda filuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="af971-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="af971-138">För varje population visas följande resultat:</span><span class="sxs-lookup"><span data-stu-id="af971-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="af971-139">Inkluderar filer med läst % – nämnt klipp</span><span class="sxs-lookup"><span data-stu-id="af971-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="af971-140">Det totala antalet filer</span><span class="sxs-lookup"><span data-stu-id="af971-140">The total number of files</span></span>

- <span data-ttu-id="af971-141">Det uppskattade antalet relevanta filer</span><span class="sxs-lookup"><span data-stu-id="af971-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="af971-142">Uppskattad richness</span><span class="sxs-lookup"><span data-stu-id="af971-142">The estimated richness</span></span>

- <span data-ttu-id="af971-143">Den genomsnittliga granskningskostnaden för att hitta en annan relevant fil</span><span class="sxs-lookup"><span data-stu-id="af971-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="af971-144">Testa utsnittet</span><span class="sxs-lookup"><span data-stu-id="af971-144">Testing the slice</span></span>

<span data-ttu-id="af971-145">Testet "Testa utsnittet" utför tester som liknar "Testa resten"-testet, men på ett segment av filuppsättningen som anges av Relevans läs %.</span><span class="sxs-lookup"><span data-stu-id="af971-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="af971-146">Så här kör du testet "Testa utsnittet":</span><span class="sxs-lookup"><span data-stu-id="af971-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="af971-147">Öppna fliken **\> Relevanstest.**</span><span class="sxs-lookup"><span data-stu-id="af971-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="af971-148">Klicka på **Nytt** test på **fliken Test.**</span><span class="sxs-lookup"><span data-stu-id="af971-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="af971-149">Dialogrutan **Skapa** test visas.</span><span class="sxs-lookup"><span data-stu-id="af971-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="af971-150">I **Testnamn** **och Beskrivning** skriver du in informationen.</span><span class="sxs-lookup"><span data-stu-id="af971-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="af971-151">Välj **Testa utsnittet** **i listan Testtyp.**</span><span class="sxs-lookup"><span data-stu-id="af971-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="af971-152">Välj **namnet på** problemet i listan Problem.</span><span class="sxs-lookup"><span data-stu-id="af971-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="af971-153">I listan **Läs in** väljer du inläsningen.</span><span class="sxs-lookup"><span data-stu-id="af971-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="af971-154">Acceptera **de lägsta och högsta** värdena i Läs % mellan eller välj värden för resultat av brytvärde för relevans för brytvärde.</span><span class="sxs-lookup"><span data-stu-id="af971-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="af971-155">I **Ange storlek** väljer du ett värde eller godkänner standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="af971-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="af971-156">Återställningsikonerna återställer standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="af971-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="af971-157">Klicka **på Börja tagga**.</span><span class="sxs-lookup"><span data-stu-id="af971-157">Click **Start tagging**.</span></span> <span data-ttu-id="af971-158">Ett testexempel genereras.</span><span class="sxs-lookup"><span data-stu-id="af971-158">A test sample is generated.</span></span>

10. <span data-ttu-id="af971-159">Granska och tagga varje fil på fliken **Relevanstagg \>** och klicka på Beräkna när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="af971-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="af971-160">På fliken Test kan du klicka på **Visa resultat för** att visa testresultaten.</span><span class="sxs-lookup"><span data-stu-id="af971-160">In the Test tab, you can click **View results** to see the test results.</span></span>
