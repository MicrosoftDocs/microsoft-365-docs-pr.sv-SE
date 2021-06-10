---
title: Konfigurera smarta etiketter i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Med smarta etiketter kan du använda maskininlärningsfunktionerna när du granskar innehåll i Advanced eDiscovery fall. Använd smarta märkningsgrupper för att visa resultatet av modeller för maskininlärning, till exempel modellen för juristklientprivilegier.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "52161503"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="ca455-104">Konfigurera smarta etiketter i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ca455-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="ca455-105">Maskininlärningsfunktionerna (ML) i Advanced eDiscovery kan hjälpa dig att effektivisera beslutsprocessen när du granskar ärendedokument i en uppsättning med granskning.</span><span class="sxs-lookup"><span data-stu-id="ca455-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="ca455-106">Smarta etiketter är ett sätt att ta ML de funktioner som ingår i beslutet: när du taggar dokument under granskning.</span><span class="sxs-lookup"><span data-stu-id="ca455-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="ca455-107">När du skapar en grupp för smarta etiketter visas de beslut som är resultatet av den ML-modell som du har kopplat till gruppen för smarta etiketter i linje med taggarna i tagggruppen.</span><span class="sxs-lookup"><span data-stu-id="ca455-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="ca455-108">På så sätt kan ML se resultatinformationen i linje när du granskar specifika dokument.</span><span class="sxs-lookup"><span data-stu-id="ca455-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="ca455-109">Konfigurera en grupp för smarta etiketter</span><span class="sxs-lookup"><span data-stu-id="ca455-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="ca455-110">I en granskningsuppsättning klickar du **på Hantera granskningsuppsättning** och sedan på **Hantera taggar**.</span><span class="sxs-lookup"><span data-stu-id="ca455-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="ca455-111">Klicka **på Lägg till tagggrupp** och välj sedan Lägg till grupp för smarta **etiketter.**</span><span class="sxs-lookup"><span data-stu-id="ca455-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="ca455-112">Välj ML modell som du vill koppla till tagggruppen.</span><span class="sxs-lookup"><span data-stu-id="ca455-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="ca455-113">Då skapas en tagggrupp och *N* underordnade taggar, *där N* är antalet möjliga utdata för modellen.</span><span class="sxs-lookup"><span data-stu-id="ca455-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="ca455-114">Modellen för identifiering av [behörigheter för juristklienter](attorney-privilege-detection.md) har till exempel två möjliga utdata:</span><span class="sxs-lookup"><span data-stu-id="ca455-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="ca455-115">**Positivt** – används för att tagga dokument som innehåller innehåll som är behörig att göra en juristklient.</span><span class="sxs-lookup"><span data-stu-id="ca455-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="ca455-116">**Negativ** – används för att tagga dokument som inte innehåller innehåll som är behörig att göra med jurister.</span><span class="sxs-lookup"><span data-stu-id="ca455-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="ca455-117">Om du väljer den här modellen skapas en tagggrupp med  två underordnade taggar (en underordnad tagg med namnet Positivt och den andra med namnet **Negativ**) för granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="ca455-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="ca455-118">I det här exemplet motsvarar varje underordnad tagg något av de möjliga resultaten från modellen för identifiering av behörigheter för juristklienter.</span><span class="sxs-lookup"><span data-stu-id="ca455-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="ca455-119">Du kan också byta namn på tagggruppen och underordnade taggar.</span><span class="sxs-lookup"><span data-stu-id="ca455-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="ca455-120">Du kan till exempel byta namn på **taggen Positiv** till **Privilegierad** och **Negativ till** **Inte behörig.**</span><span class="sxs-lookup"><span data-stu-id="ca455-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="ca455-121">Så här använder du smarta etiketter</span><span class="sxs-lookup"><span data-stu-id="ca455-121">How to use smart tags</span></span>

<span data-ttu-id="ca455-122">När du granskar ett dokument visas modellens resultat bredvid lämplig underordnad tagg.</span><span class="sxs-lookup"><span data-stu-id="ca455-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="ca455-123">Om du till exempel har en smart etikettgrupp för identifiering av juristklientbehörighet och du granskar ett dokument som kan vara privilegierat visas orsaken till den slutsatsen bredvid motsvarande tagg.</span><span class="sxs-lookup"><span data-stu-id="ca455-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="ca455-124">Det är viktigt att observera att taggen inte tillämpas automatiskt i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="ca455-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="ca455-125">Granskaren kan fatta ett beslut om hur dokumentet ska tagga.</span><span class="sxs-lookup"><span data-stu-id="ca455-125">The reviewer makes the decision about how to tag the document.</span></span>
