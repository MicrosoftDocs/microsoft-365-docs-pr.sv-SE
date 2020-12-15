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
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683373"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="2c83d-104">Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="2c83d-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2c83d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2c83d-105">**Applies to:**</span></span>
- <span data-ttu-id="2c83d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c83d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2c83d-107">När en automatisk undersökning körs kan den resultera i en eller flera [reparations åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) som kräver godkännande för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="2c83d-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="2c83d-108">Ett kluster med e-postmeddelanden kan till exempel behöva tas bort, eller så måste en fil i karantän tas bort.</span><span class="sxs-lookup"><span data-stu-id="2c83d-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="2c83d-109">Det är viktigt att godkänna (eller avvisa) pågående åtgärder så snart som möjligt så att dina automatiserade utredningar kan fortsätta och genomföras i god tid.</span><span class="sxs-lookup"><span data-stu-id="2c83d-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="2c83d-110">Om du tror att något har missats eller upptäckts felaktigt av automatiserade undersökningar och svars funktioner i Microsoft 365 Defender kan du tala om det för oss!</span><span class="sxs-lookup"><span data-stu-id="2c83d-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="2c83d-111">Lär dig [hur du rapporterar falskta positiva eller negativa negativ i en automatiserad undersökning och svar (Air) i Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="2c83d-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="2c83d-112">Väntande åtgärder kan granskas och godkännas med hjälp av [Åtgärds centret](#review-a-pending-action-in-the-action-center) eller [vyn granska information](#review-a-pending-action-in-the-investigation-details-view).</span><span class="sxs-lookup"><span data-stu-id="2c83d-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="2c83d-113">Du måste ha [rätt behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa reparations åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2c83d-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="2c83d-114">För mer information, se [förutsättningar för automatisk undersökning och svar i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="2c83d-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="2c83d-115">Granska en väntande åtgärd i åtgärds centret</span><span class="sxs-lookup"><span data-stu-id="2c83d-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="2c83d-116">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="2c83d-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="2c83d-117">I navigerings fönstret väljer du **Åtgärds Center**.</span><span class="sxs-lookup"><span data-stu-id="2c83d-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="2c83d-118">På fliken **förestående** i åtgärds Center väljer du ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="2c83d-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="2c83d-119">Om du markerar ett objekt i kolumnen **analys nummer** öppnas sidan med gransknings information.</span><span class="sxs-lookup"><span data-stu-id="2c83d-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="2c83d-120">Där kan du se resultatet av undersökningen och sedan antingen godkänna eller avvisa den rekommenderade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="2c83d-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="2c83d-121">Om du markerar en rad i listan öppnas en utfällbar tabell där du kan visa information om objektet.</span><span class="sxs-lookup"><span data-stu-id="2c83d-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="2c83d-123">Använd länkarna för att visa en associerad avisering eller en undersökning och godkänna eller avvisa åtgärden.</span><span class="sxs-lookup"><span data-stu-id="2c83d-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="2c83d-124">Granska en väntande åtgärd i vyn granska information</span><span class="sxs-lookup"><span data-stu-id="2c83d-124">Review a pending action in the investigation details view</span></span>

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="2c83d-126">På en [undersöknings](mtp-autoir-results.md) sida väljer du fliken **pågående åtgärder** (eller **åtgärder**). Objekt som väntar på godkännande finns här.</span><span class="sxs-lookup"><span data-stu-id="2c83d-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="2c83d-127">Markera ett objekt i listan och välj sedan **Godkänn** eller **avvisa**.</span><span class="sxs-lookup"><span data-stu-id="2c83d-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2c83d-128">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2c83d-128">Next steps</span></span>

- [<span data-ttu-id="2c83d-129">Visa information och resultat från en automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="2c83d-129">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="2c83d-130">Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner</span><span class="sxs-lookup"><span data-stu-id="2c83d-130">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
