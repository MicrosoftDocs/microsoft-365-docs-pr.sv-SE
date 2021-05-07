---
title: Prediktiv kodningsmodul för Advanced eDiscovery (förhandsversion)
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
description: Den nya prediktiv kodningsmodulen i Advanced eDiscovery använder maskininlärning för att analysera dokument i en granskningsuppsättning för att förutsäga vilka dokument som är relevanta för ditt ärende eller undersökning.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162538"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="44411-103">Prediktiv kodningsmodul för Advanced eDiscovery (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="44411-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="44411-104">Med den nya prediktiv kodningsmodulen i Advanced eDiscovery kan du skapa och skapa en modell för att prioritera granskning av dokument med början i de mest relevanta dokumenten.</span><span class="sxs-lookup"><span data-stu-id="44411-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="44411-105">För att komma igång kan du skapa en modell, märka upp till 50 dokument och sedan filtrera dokument efter resultat från modellförutsägelse för att granska relevanta dokument som inte är relevanta.</span><span class="sxs-lookup"><span data-stu-id="44411-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="44411-106">Här är en snabb överblick av arbetsflödet:</span><span class="sxs-lookup"><span data-stu-id="44411-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="44411-107">Öppna modulen prediktiv kodning i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="44411-107">Open the predictive coding module in a review set.</span></span>

   ![Klicka på listrutan Analysera i en granskning för att gå till modulen Prediktiv kodning](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="44411-109">På sidan **Prediktiv kodningsmodeller** klickar du **på Ny modell för** att skapa en ny prediktiv kodningsmodell.</span><span class="sxs-lookup"><span data-stu-id="44411-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![Skapa en ny modell](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="44411-111">Ange minst 50 dokument som **relevanta** eller **Inte relevanta.**</span><span class="sxs-lookup"><span data-stu-id="44411-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="44411-112">Etiketten används för att träna systemet.</span><span class="sxs-lookup"><span data-stu-id="44411-112">This labeling is used to train the system.</span></span>

   ![Ange att dokument ska vara relevanta eller inte relevanta för att utbilda systemet](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="44411-114">Använd filtret **Förutsägelseresultat** för modellen i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="44411-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="44411-115">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="44411-115">To do this:</span></span>

   1. <span data-ttu-id="44411-116">Klicka på Filter i **granskningsuppsättningen.**</span><span class="sxs-lookup"><span data-stu-id="44411-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="44411-117">På den **utfällna** sidan Filter expanderar du avsnittet  **Analys/ML** och väljer sedan kryssrutan Prognosresultat för den modell som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="44411-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="44411-118">I filtret **Förutsägelseresultat** anger du ett prognosresultat.</span><span class="sxs-lookup"><span data-stu-id="44411-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="44411-119">Filtret visar dokumenten i granskningsuppsättningen som matchar prognosresultatet.</span><span class="sxs-lookup"><span data-stu-id="44411-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![Ange ett resultat för förutsägelse för att filtrera dokument](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="44411-121">Övervaka modellens prestanda, status och stabilitet.</span><span class="sxs-lookup"><span data-stu-id="44411-121">Monitor the performance, status, and stability of your model.</span></span>

   ![Övervaka prestanda, status och stabilitet för din modell](..\media\PredictiveCoding5.png)
