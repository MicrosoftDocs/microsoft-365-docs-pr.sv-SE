---
title: Visa och hantera åtgärder i Åtgärdscenter
description: Använda Åtgärdscenter för att visa och hantera åtgärdsåtgärder
keywords: åtgärd, center, autoair, automatiserad, undersökning, svar, åtgärd
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: e3e842f812c5675334cc25fa35544165129db2b4
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245894"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="25703-104">Visa och hantera åtgärder i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="25703-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="25703-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="25703-105">**Applies to:**</span></span>
- <span data-ttu-id="25703-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25703-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="25703-107">Skyddsfunktioner i Microsoft 365 Defender kan resultera i vissa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="25703-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="25703-108">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="25703-108">Here are some examples:</span></span>
- <span data-ttu-id="25703-109">[Automatiserade undersökningar](m365d-autoir.md) kan resultera i åtgärder som vidtas automatiskt eller väntar på godkännande.</span><span class="sxs-lookup"><span data-stu-id="25703-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="25703-110">Antivirusprogram, program mot skadlig programvara och andra skyddsfunktioner mot hot kan resultera i åtgärder som att blockera en fil, url eller process, eller skicka en artefakt till karantän.</span><span class="sxs-lookup"><span data-stu-id="25703-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="25703-111">Ditt team för säkerhetsåtgärder kan vidta åtgärder manuellt, till exempel [under](advanced-hunting-overview.md) avancerad sökning eller under undersökning [av aviseringar](investigate-alerts.md) eller [incidenter.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="25703-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="25703-112">Du måste ha [tillräcklig behörighet](m365d-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="25703-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="25703-113">Mer information finns i Förutsättningar [för automatiserad undersökning och svar i Microsoft 365 Defender.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="25703-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="25703-114">Granska väntande åtgärder i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="25703-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="25703-115">Det är viktigt att godkänna (eller avvisa) väntande åtgärder så snart som möjligt så att de automatiska undersökningarna kan fortsätta och slutföras i tid.</span><span class="sxs-lookup"><span data-stu-id="25703-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="25703-117">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="25703-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="25703-118">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="25703-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="25703-119">Välj ett objekt i **listan på fliken** Väntande i Åtgärdscenter.</span><span class="sxs-lookup"><span data-stu-id="25703-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="25703-120">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="25703-120">Its flyout pane opens.</span></span>

4. <span data-ttu-id="25703-121">Granska informationen i det utfällfönster som visas och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="25703-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="25703-122">Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.</span><span class="sxs-lookup"><span data-stu-id="25703-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="25703-123">Välj **Godkänn** för att påbörja en väntande åtgärd.</span><span class="sxs-lookup"><span data-stu-id="25703-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="25703-124">Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.</span><span class="sxs-lookup"><span data-stu-id="25703-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="25703-125">Välj **Sök för** att gå till Avancerad [sökning](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="25703-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="25703-126">Ångra slutförda åtgärder</span><span class="sxs-lookup"><span data-stu-id="25703-126">Undo completed actions</span></span>

<span data-ttu-id="25703-127">Om du har fastställt att en enhet eller en fil inte är ett hot kan du ångra åtgärder som har vidtagits, oavsett om dessa åtgärder har vidtagits automatiskt eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="25703-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="25703-128">På fliken Historik i **Åtgärdscenter** kan du ångra något av följande:</span><span class="sxs-lookup"><span data-stu-id="25703-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="25703-129">Åtgärdskälla</span><span class="sxs-lookup"><span data-stu-id="25703-129">Action source</span></span> | <span data-ttu-id="25703-130">Åtgärder som stöds</span><span class="sxs-lookup"><span data-stu-id="25703-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="25703-131">- Automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="25703-131">- Automated investigation</span></span> <br/><span data-ttu-id="25703-132">- Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="25703-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="25703-133">- Manuella svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="25703-133">- Manual response actions</span></span> | <span data-ttu-id="25703-134">- Isolera enhet</span><span class="sxs-lookup"><span data-stu-id="25703-134">- Isolate device</span></span> <br/><span data-ttu-id="25703-135">- Begränsa kodkörning</span><span class="sxs-lookup"><span data-stu-id="25703-135">- Restrict code execution</span></span> <br/><span data-ttu-id="25703-136">- Sätt en fil i karantän</span><span class="sxs-lookup"><span data-stu-id="25703-136">- Quarantine a file</span></span> <br/><span data-ttu-id="25703-137">- Ta bort en registernyckel</span><span class="sxs-lookup"><span data-stu-id="25703-137">- Remove a registry key</span></span> <br/><span data-ttu-id="25703-138">- Stoppa en tjänst</span><span class="sxs-lookup"><span data-stu-id="25703-138">- Stop a service</span></span> <br/><span data-ttu-id="25703-139">- Inaktivera en drivrutin</span><span class="sxs-lookup"><span data-stu-id="25703-139">- Disable a driver</span></span> <br/><span data-ttu-id="25703-140">- Ta bort en schemalagd aktivitet</span><span class="sxs-lookup"><span data-stu-id="25703-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="25703-141">Ångra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="25703-141">Undo one remediation action</span></span>

1. <span data-ttu-id="25703-142">Gå till Åtgärdscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="25703-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="25703-143">Välj **en åtgärd** som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="25703-143">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="25703-144">I fönstret till höger på skärmen väljer du **Ångra**.</span><span class="sxs-lookup"><span data-stu-id="25703-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="25703-145">Ångra flera åtgärder</span><span class="sxs-lookup"><span data-stu-id="25703-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="25703-146">Gå till Åtgärdscenter https://security.microsoft.com/action-center) (och logga in).</span><span class="sxs-lookup"><span data-stu-id="25703-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="25703-147">Markera **de åtgärder** du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="25703-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="25703-148">Se till att markera objekt som har samma åtgärdstyp.</span><span class="sxs-lookup"><span data-stu-id="25703-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="25703-149">Ett utfällt fönster öppnas.</span><span class="sxs-lookup"><span data-stu-id="25703-149">A flyout pane opens.</span></span>

3. <span data-ttu-id="25703-150">Välj Ångra i den utfällade **rutan.**</span><span class="sxs-lookup"><span data-stu-id="25703-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="25703-151">Ta bort en fil från karantän på flera enheter</span><span class="sxs-lookup"><span data-stu-id="25703-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="25703-152">Gå till Åtgärdscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="25703-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="25703-153">På fliken **Historik** väljer du en fil som har karantänfilen **Åtgärdstyp.**</span><span class="sxs-lookup"><span data-stu-id="25703-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="25703-154">I fönstret till höger på skärmen väljer du Använd för **fler X-instanser** av den här filen och sedan **Ångra**.</span><span class="sxs-lookup"><span data-stu-id="25703-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="25703-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="25703-155">Next steps</span></span>

- [<span data-ttu-id="25703-156">Visa information och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="25703-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="25703-157">Lär dig hur du hanterar falska positiva/negativa tal (om du får ett)</span><span class="sxs-lookup"><span data-stu-id="25703-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
