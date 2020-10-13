---
title: Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning
description: Använd åtgärds centret för att hantera åtgärder relaterade till automatiserad undersökning och svar
keywords: åtgärd, Center, autoair, automatiserad, undersökning, svar, reparation
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 22a40e3c0c804800f2de02e705d1dfec6e296db0
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429617"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="6f66c-104">Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="6f66c-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f66c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6f66c-105">**Applies to:**</span></span>
- <span data-ttu-id="6f66c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6f66c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6f66c-107">När en automatisk undersökning körs kan den resultera i en eller flera [reparations åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) som kräver godkännande för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="6f66c-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="6f66c-108">Ett kluster med e-postmeddelanden kan till exempel behöva tas bort, eller så måste en fil i karantän tas bort.</span><span class="sxs-lookup"><span data-stu-id="6f66c-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="6f66c-109">Det är viktigt att godkänna (eller avvisa) pågående åtgärder så snart som möjligt så att dina automatiserade utredningar kan fortsätta och genomföras i god tid.</span><span class="sxs-lookup"><span data-stu-id="6f66c-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="6f66c-110">Om du tror att något har missats eller upptäckts felaktigt av den automatiska undersöknings-och svars funktionerna i Microsoft Threat Protection, tala om det för oss!</span><span class="sxs-lookup"><span data-stu-id="6f66c-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="6f66c-111">Lär dig [hur du rapporterar falskta positiva eller negativa negativ i en automatiserad undersökning och svar (Air) i Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="6f66c-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="6f66c-112">Väntande åtgärder kan granskas och godkännas med hjälp av [Åtgärds centret](#review-a-pending-action-in-the-action-center) eller [vyn granska information](#review-a-pending-action-in-the-investigation-details-view).</span><span class="sxs-lookup"><span data-stu-id="6f66c-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="6f66c-113">Du måste ha [rätt behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa reparations åtgärder.</span><span class="sxs-lookup"><span data-stu-id="6f66c-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="6f66c-114">Granska en väntande åtgärd i åtgärds centret</span><span class="sxs-lookup"><span data-stu-id="6f66c-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="6f66c-115">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="6f66c-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="6f66c-116">I navigerings fönstret väljer du **Åtgärds Center**.</span><span class="sxs-lookup"><span data-stu-id="6f66c-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="6f66c-117">På fliken **förestående** i åtgärds Center väljer du ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="6f66c-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="6f66c-118">Om du markerar ett objekt i kolumnen **analys nummer** öppnas sidan med gransknings information.</span><span class="sxs-lookup"><span data-stu-id="6f66c-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="6f66c-119">Där kan du se resultatet av undersökningen och sedan antingen godkänna eller avvisa den rekommenderade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="6f66c-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="6f66c-120">Om du markerar en rad i listan öppnas en utfällbar tabell där du kan visa information om objektet.</span><span class="sxs-lookup"><span data-stu-id="6f66c-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="6f66c-122">Använd länkarna för att visa en associerad avisering eller en undersökning och godkänna eller avvisa åtgärden.</span><span class="sxs-lookup"><span data-stu-id="6f66c-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="6f66c-123">Granska en väntande åtgärd i vyn granska information</span><span class="sxs-lookup"><span data-stu-id="6f66c-123">Review a pending action in the investigation details view</span></span>

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="6f66c-125">På en [undersöknings](mtp-autoir-results.md) sida väljer du fliken **pågående åtgärder** (eller **åtgärder**). Objekt som väntar på godkännande finns här.</span><span class="sxs-lookup"><span data-stu-id="6f66c-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="6f66c-126">Markera ett objekt i listan och välj sedan **Godkänn** eller **avvisa**.</span><span class="sxs-lookup"><span data-stu-id="6f66c-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f66c-127">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6f66c-127">Next steps</span></span>

- [<span data-ttu-id="6f66c-128">Visa information och resultat från en automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="6f66c-128">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="6f66c-129">Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner</span><span class="sxs-lookup"><span data-stu-id="6f66c-129">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
