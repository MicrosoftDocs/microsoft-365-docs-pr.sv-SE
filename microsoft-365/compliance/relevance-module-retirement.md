---
title: Relevansmodulen i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Relevansmodulen i Advanced eDiscovery dras tillbaka den 10 mars 2021. I den här artikeln förklaras vad du kan göra innan Relevans dras tillbaka. Mer specifikt kan du avsluta alla oavslutade modeller genom att köra batchberäkningar så att du kan behålla metadata från modellen.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822003"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="9d388-105">Relevansmodulen i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9d388-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="9d388-106">Den 10 mars 2021 drar vi tillbaka relevansmodulen i Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9d388-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="9d388-107">Det innebär att organisationer inte längre har tillgång till relevansmodulen (genom att gå till Hantera granskningsuppsättning relevans i ett Advanced eDiscovery fall) eller kan komma åt befintliga  >   relevansmodeller.</span><span class="sxs-lookup"><span data-stu-id="9d388-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="9d388-108">Den aktuella relevansmodulen som dras tillbaka ersätts med en ny prediktiv kodningslösning i Q2 CY 2021.</span><span class="sxs-lookup"><span data-stu-id="9d388-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="9d388-109">Med de nya funktionerna kan organisationer skapa egna prediktiv kodningsmodeller i ett enklare och mer intuitivt arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="9d388-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="9d388-110">För att förbereda för den här kommande ingången rekommenderar vi att organisationer som använder relevansmodulen exporterar sina modellers utdata innan utgångsdatumet genom att köra en batchberäkning för alla befintliga modeller.</span><span class="sxs-lookup"><span data-stu-id="9d388-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="9d388-111">Alla relevansresultat från din modell lagras permanent i motsvarande granskningsuppsättning och är tillgängliga när dokument exporteras.</span><span class="sxs-lookup"><span data-stu-id="9d388-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="9d388-112">Relevansresultat sparas också som metadata i inläsningsfilen.</span><span class="sxs-lookup"><span data-stu-id="9d388-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="9d388-113">Du kan också fortfarande filtrera innehåll i granskningsuppsättningen baserat på relevansresultat och få åtkomst till alla metadata som skapas av dina relevansmodeller.</span><span class="sxs-lookup"><span data-stu-id="9d388-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="9d388-114">Slutföra oavslutade modeller</span><span class="sxs-lookup"><span data-stu-id="9d388-114">Complete unfinished models</span></span>

<span data-ttu-id="9d388-115">För alla oavslutade relevansmodeller bör du utföra en utvärdering, utbildning och batchberäkning så att du kan använda modellen på dokumenten i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="9d388-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="9d388-116">När du slutför batchberäkningen behålls informationen efter att relevansmodulen har avslutats.</span><span class="sxs-lookup"><span data-stu-id="9d388-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="9d388-117">Här är stegen för att slutföra alla oavslutade modeller:</span><span class="sxs-lookup"><span data-stu-id="9d388-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="9d388-118">Utbilda modellen tills den har omts och är redo för batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="9d388-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="9d388-119">Se [Tagga och relevansutbildning.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="9d388-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="9d388-120">På följande skärmbild visas en modul som är redo för en batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="9d388-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="9d388-121">Lägg märke till att utvärdering och utbildning är klar och att nästa steg är att köra Batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="9d388-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Skärmbild av modell klar för batchberäkning](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="9d388-123">Kör batchberäkningen.</span><span class="sxs-lookup"><span data-stu-id="9d388-123">Run the Batch calculation.</span></span> <span data-ttu-id="9d388-124">Mer information [finns i Utföra batchberäkningar.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="9d388-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="9d388-125">Kontrollera att batchberäkningen har lyckats.</span><span class="sxs-lookup"><span data-stu-id="9d388-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="9d388-126">Läs [Batchberäkningsresultat](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span><span class="sxs-lookup"><span data-stu-id="9d388-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="9d388-127">Om du behöver hjälp med att slutföra oavslutade relevansmodeller kontaktar du Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="9d388-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
