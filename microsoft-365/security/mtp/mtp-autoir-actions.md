---
title: Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning
description: Använd Åtgärdscentret för att hantera åtgärder som är relaterade till automatiserad undersökning och svar
keywords: åtgärd, centrum, autoair, automatiserad, utredning, svar, sanering
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 725d22629d2c81a0edf8f329602214afddde6511
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809005"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="a5953-104">Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="a5953-104">Approve or reject pending actions following an automated investigation</span></span>

<span data-ttu-id="a5953-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="a5953-105">**Applies to:**</span></span>
- <span data-ttu-id="a5953-106">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5953-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a5953-107">När en automatiserad undersökning körs kan det resultera i en eller flera [reparationsåtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) som kräver godkännande för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="a5953-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="a5953-108">Ett kluster med e-postmeddelanden kan till exempel behöva tas bort, eller så kan en fil i karantän behöva tas bort.</span><span class="sxs-lookup"><span data-stu-id="a5953-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="a5953-109">Det är viktigt att godkänna (eller avvisa) pågående åtgärder så snart som möjligt så att dina automatiserade undersökningar kan fortsätta och slutföra i tid.</span><span class="sxs-lookup"><span data-stu-id="a5953-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="a5953-110">Om du tror att något har missats eller upptäckts felaktigt genom automatiskundersökning och svarsfunktioner i Microsoft Threat Protection, låt oss veta!</span><span class="sxs-lookup"><span data-stu-id="a5953-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="a5953-111">Se [Hur du rapporterar falska positiva/negativa effekter i AIR-funktioner (Automated Investigation and Response) i Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="a5953-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="a5953-112">Väntande åtgärder kan granskas och godkännas med hjälp av [åtgärdscentret](#review-a-pending-action-in-the-action-center) eller [undersökningsinformationsvyn](#review-a-pending-action-in-the-investigation-details-view).</span><span class="sxs-lookup"><span data-stu-id="a5953-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="a5953-113">Du måste ha [rätt behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa reparationsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="a5953-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="a5953-114">Granska en väntande åtgärd i åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="a5953-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="a5953-115">Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in.</span><span class="sxs-lookup"><span data-stu-id="a5953-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="a5953-116">Välj **Åtgärdscenter i**navigeringsfönstret .</span><span class="sxs-lookup"><span data-stu-id="a5953-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="a5953-117">Välj ett objekt i listan på fliken **Väntande** i Åtgärdscenter.</span><span class="sxs-lookup"><span data-stu-id="a5953-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="a5953-118">Om du väljer ett objekt i kolumnen **Utredningsnummer** öppnas sidan för undersökningsinformation.</span><span class="sxs-lookup"><span data-stu-id="a5953-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="a5953-119">Där kan du visa resultatet av undersökningen och sedan antingen godkänna eller avvisa den rekommenderade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="a5953-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="a5953-120">Om du väljer en rad i listan öppnas ett utfällbart objekt där du kan visa information om objektet.</span><span class="sxs-lookup"><span data-stu-id="a5953-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="a5953-122">Använd länkarna för att visa en associerad avisering eller en undersökning och godkänna eller avvisa åtgärden.</span><span class="sxs-lookup"><span data-stu-id="a5953-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="a5953-123">Granska en väntande åtgärd i vyn för utredningsinformation</span><span class="sxs-lookup"><span data-stu-id="a5953-123">Review a pending action in the investigation details view</span></span>

![Uppgifter om utredning](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="a5953-125">På en [sida med undersökningsinformation](mtp-autoir-results.md) väljer du fliken **Väntande åtgärder** (eller **Åtgärder).**</span><span class="sxs-lookup"><span data-stu-id="a5953-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="a5953-126">Markera ett objekt i listan och välj sedan **Godkänna** eller **Avvisa**.</span><span class="sxs-lookup"><span data-stu-id="a5953-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a5953-127">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a5953-127">Next steps</span></span>

- [<span data-ttu-id="a5953-128">Läs mer om Åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="a5953-128">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="a5953-129">Läs mer om incidenter</span><span class="sxs-lookup"><span data-stu-id="a5953-129">Learn more about incidents</span></span>](incidents-overview.md)

- [<span data-ttu-id="a5953-130">Lär dig mer om jakt</span><span class="sxs-lookup"><span data-stu-id="a5953-130">Learn about hunting</span></span>](advanced-hunting-overview.md)
