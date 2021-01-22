---
title: Godkänna eller avvisa väntande åtgärder efter en automatiserad undersökning
description: Använda Åtgärdscenter för att hantera åtgärder relaterade till automatiserad undersökning och svar
keywords: åtgärd, center, autoair, automatiserad, undersökning, svar, åtgärd
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930384"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="efe02-104">Godkänna eller avvisa väntande åtgärder efter en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="efe02-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="efe02-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="efe02-105">**Applies to:**</span></span>
- <span data-ttu-id="efe02-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="efe02-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="efe02-107">När en automatiserad undersökning körs kan det resultera i en eller [flera åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) som kräver godkännande för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="efe02-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="efe02-108">Till exempel kan ett kluster av e-postmeddelanden behöva tas bort eller så kan en karantänfil behöva tas bort.</span><span class="sxs-lookup"><span data-stu-id="efe02-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="efe02-109">Det är viktigt att godkänna (eller avvisa) väntande åtgärder så snart som möjligt så att automatiserade undersökningar kan fortsätta och slutföras i tid.</span><span class="sxs-lookup"><span data-stu-id="efe02-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="efe02-110">Om du tror att något har missats eller identifierats felaktigt av en automatiserad undersökning och svarsfunktioner i Microsoft 365 Defender, berätta det för oss!</span><span class="sxs-lookup"><span data-stu-id="efe02-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="efe02-111">Se hur du rapporterar falska positiva/negativa tal i automatisk undersökning och [svarsfunktioner (AIR) i Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="efe02-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="efe02-112">Väntande åtgärder kan granskas och godkännas med hjälp av [åtgärdscenter](#review-a-pending-action-in-the-action-center) eller [vyn med undersökningsinformation.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="efe02-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="efe02-113">Du måste ha [tillräcklig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="efe02-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="efe02-114">Mer information finns i [Förutsättningarna för automatisk undersökning och svar i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="efe02-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="efe02-115">Granska en väntande åtgärd i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="efe02-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="efe02-116">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="efe02-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="efe02-117">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="efe02-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="efe02-118">Markera ett objekt i listan på **fliken** Väntande i Åtgärdscenter.</span><span class="sxs-lookup"><span data-stu-id="efe02-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="efe02-119">Om du väljer ett objekt i **kolumnen Undersökningsnummer** öppnas sidan undersökningsinformation.</span><span class="sxs-lookup"><span data-stu-id="efe02-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="efe02-120">Där kan du visa resultatet av undersökningen och sedan godkänna eller avvisa den rekommenderade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="efe02-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="efe02-121">Om du markerar en rad i listan öppnas en utfällig meny där du kan visa information om objektet.</span><span class="sxs-lookup"><span data-stu-id="efe02-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="efe02-123">Använd länkarna för att visa en associerad varning eller undersökning och godkänn eller avvisa åtgärden.</span><span class="sxs-lookup"><span data-stu-id="efe02-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="efe02-124">Granska en väntande åtgärd i vyn med undersökningsinformation</span><span class="sxs-lookup"><span data-stu-id="efe02-124">Review a pending action in the investigation details view</span></span>

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="efe02-126">På en [sida med undersökningsinformation](mtp-autoir-results.md) väljer du **fliken Väntande åtgärder** **(eller** Åtgärder). Objekt som väntar på godkännande visas här.</span><span class="sxs-lookup"><span data-stu-id="efe02-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="efe02-127">Markera ett objekt i listan och välj sedan **Godkänn** eller **Avvisa.**</span><span class="sxs-lookup"><span data-stu-id="efe02-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="efe02-128">Ångra slutförda åtgärder</span><span class="sxs-lookup"><span data-stu-id="efe02-128">Undo completed actions</span></span>

<span data-ttu-id="efe02-129">Om du har fastställt att en enhet eller en fil inte är ett hot kan du ångra åtgärder som har vidtagits, oavsett om dessa åtgärder har vidtagits automatiskt eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="efe02-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="efe02-130">På fliken Historik i **Åtgärdscenter** kan du ångra något av följande:</span><span class="sxs-lookup"><span data-stu-id="efe02-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="efe02-131">Åtgärdskälla</span><span class="sxs-lookup"><span data-stu-id="efe02-131">Action source</span></span> | <span data-ttu-id="efe02-132">Åtgärder som stöds</span><span class="sxs-lookup"><span data-stu-id="efe02-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="efe02-133">- Automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="efe02-133">- Automated investigation</span></span> <br/><span data-ttu-id="efe02-134">- Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="efe02-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="efe02-135">- Manuella svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="efe02-135">- Manual response actions</span></span> | <span data-ttu-id="efe02-136">- Isolera enhet</span><span class="sxs-lookup"><span data-stu-id="efe02-136">- Isolate device</span></span> <br/><span data-ttu-id="efe02-137">- Begränsa kodkörning</span><span class="sxs-lookup"><span data-stu-id="efe02-137">- Restrict code execution</span></span> <br/><span data-ttu-id="efe02-138">- Sätt en fil i karantän</span><span class="sxs-lookup"><span data-stu-id="efe02-138">- Quarantine a file</span></span> <br/><span data-ttu-id="efe02-139">- Ta bort en registernyckel</span><span class="sxs-lookup"><span data-stu-id="efe02-139">- Remove a registry key</span></span> <br/><span data-ttu-id="efe02-140">- Stoppa en tjänst</span><span class="sxs-lookup"><span data-stu-id="efe02-140">- Stop a service</span></span> <br/><span data-ttu-id="efe02-141">- Inaktivera en drivrutin</span><span class="sxs-lookup"><span data-stu-id="efe02-141">- Disable a driver</span></span> <br/><span data-ttu-id="efe02-142">- Ta bort en schemalagd aktivitet</span><span class="sxs-lookup"><span data-stu-id="efe02-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="efe02-143">Ångra en åtgärdsåtgärd</span><span class="sxs-lookup"><span data-stu-id="efe02-143">To undo a remediation action</span></span>

1. <span data-ttu-id="efe02-144">Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="efe02-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="efe02-145">Välj en **åtgärd** som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="efe02-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="efe02-146">Välj Ångra i fönstret till höger på **skärmen.**</span><span class="sxs-lookup"><span data-stu-id="efe02-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="efe02-147">Ta bort en fil från karantän på flera enheter</span><span class="sxs-lookup"><span data-stu-id="efe02-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="efe02-148">Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="efe02-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="efe02-149">Välj en **fil** som har karantänfilen åtgärdstyp på fliken **Historik.**</span><span class="sxs-lookup"><span data-stu-id="efe02-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="efe02-150">I fönstret till höger på skärmen väljer du Använd för **fler X-förekomster** av den här filen och sedan **Ångra.**</span><span class="sxs-lookup"><span data-stu-id="efe02-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="efe02-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="efe02-151">Next steps</span></span>

- [<span data-ttu-id="efe02-152">Visa information och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="efe02-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="efe02-153">Hantera falska positiva/negativa tal i automatisk undersökning och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="efe02-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
