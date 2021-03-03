---
title: Granska och hantera åtgärder i Microsoft Defender för Office 365
keywords: AIR, autoIR, ATP, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Läs mer om åtgärder för automatisk undersökning och svar i Microsoft Defender för Office 365 abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 40d0d8a14e0dd340d931a1c43425854b96702c65
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407100"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="749c5-104">Granska och hantera åtgärder i Office 365</span><span class="sxs-lookup"><span data-stu-id="749c5-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="749c5-105">Eftersom automatiska undersökningar av e& och samarbetsinnehåll resulterar  i bedömningsresultat, till exempel skadliga eller *misstänkta,* skapas vissa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="749c5-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="749c5-106">I Microsoft Defender för Office 365 kan åtgärder omfatta:</span><span class="sxs-lookup"><span data-stu-id="749c5-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="749c5-107">Blockera en URL (tid för klickning)</span><span class="sxs-lookup"><span data-stu-id="749c5-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="749c5-108">Mjuk borttagning av e-postmeddelanden och kluster</span><span class="sxs-lookup"><span data-stu-id="749c5-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="749c5-109">Kvartil som e-post eller e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="749c5-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="749c5-110">Stänga av vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="749c5-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="749c5-111">Dessa åtgärder vidtas inte om inte och förrän säkerhetsteamet godkänner dem.</span><span class="sxs-lookup"><span data-stu-id="749c5-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="749c5-112">Vi rekommenderar att du granskar och godkänner alla väntande åtgärder så snart som möjligt så att de automatiserade undersökningarna slutförs i tid.</span><span class="sxs-lookup"><span data-stu-id="749c5-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="749c5-113">I vissa fall kan du ångra en åtgärdsåtgärd.</span><span class="sxs-lookup"><span data-stu-id="749c5-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="749c5-114">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="749c5-114">**Applies to**</span></span>
- [<span data-ttu-id="749c5-115">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="749c5-115">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="749c5-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="749c5-116">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="749c5-117">Godkänna (eller avvisa) väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="749c5-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="749c5-118">Gå till Microsoft 365 säkerhetscenter ( <https://security.microsoft.com> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="749c5-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="749c5-119">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="749c5-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="749c5-120">Granska **listan över åtgärder** som väntar på godkännande på fliken Väntande.</span><span class="sxs-lookup"><span data-stu-id="749c5-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="749c5-121">Markera ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="749c5-121">Select an item in the list.</span></span> <span data-ttu-id="749c5-122">Det utfällfönster som visas.</span><span class="sxs-lookup"><span data-stu-id="749c5-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="749c5-123">Granska informationen i det utfällfönster och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="749c5-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="749c5-124">Välj **sidan Öppna undersökning** om du vill visa mer information om undersökningen.</span><span class="sxs-lookup"><span data-stu-id="749c5-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="749c5-125">Välj **Godkänn för** att påbörja en väntande åtgärd.</span><span class="sxs-lookup"><span data-stu-id="749c5-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="749c5-126">Välj **Avvisa** om du vill förhindra att en väntande åtgärd vidtas.</span><span class="sxs-lookup"><span data-stu-id="749c5-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="749c5-127">Ångra en åtgärdsåtgärd</span><span class="sxs-lookup"><span data-stu-id="749c5-127">Undo one remediation action</span></span>

1. <span data-ttu-id="749c5-128">Gå till Åtgärdscenter <https://security.microsoft.com/action-center> () och logga in.</span><span class="sxs-lookup"><span data-stu-id="749c5-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="749c5-129">Välj en **åtgärd** som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="749c5-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="749c5-130">Välj Ångra i fönstret till höger på **skärmen.**</span><span class="sxs-lookup"><span data-stu-id="749c5-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="749c5-131">Ångra flera åtgärder</span><span class="sxs-lookup"><span data-stu-id="749c5-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="749c5-132">Gå till Åtgärdscenter <https://security.microsoft.com/action-center> () och logga in.</span><span class="sxs-lookup"><span data-stu-id="749c5-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="749c5-133">Markera **de** åtgärder som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="749c5-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="749c5-134">Se till att markera objekt som har samma åtgärdstyp.</span><span class="sxs-lookup"><span data-stu-id="749c5-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="749c5-135">Ett utfällt fönster öppnas.</span><span class="sxs-lookup"><span data-stu-id="749c5-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="749c5-136">Välj Ångra i det utfällade fönstret.</span><span class="sxs-lookup"><span data-stu-id="749c5-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="749c5-137">Ta bort en fil från karantän på flera enheter</span><span class="sxs-lookup"><span data-stu-id="749c5-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="749c5-138">Gå till Åtgärdscenter <https://security.microsoft.com/action-center> () och logga in.</span><span class="sxs-lookup"><span data-stu-id="749c5-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="749c5-139">Välj en **fil** som har karantänfilen åtgärdstyp på fliken **Historik.**</span><span class="sxs-lookup"><span data-stu-id="749c5-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="749c5-140">I fönstret till höger på skärmen väljer du Använd för **fler X-förekomster** av den här filen och sedan **Ångra.**</span><span class="sxs-lookup"><span data-stu-id="749c5-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="749c5-141">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="749c5-141">Next steps</span></span>

- [<span data-ttu-id="749c5-142">Använda HotUtforskaren</span><span class="sxs-lookup"><span data-stu-id="749c5-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="749c5-143">Hur du rapporterar falska positiva/negativa tal i automatiserad undersökning och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="749c5-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="749c5-144">Se även</span><span class="sxs-lookup"><span data-stu-id="749c5-144">See also</span></span>

- [<span data-ttu-id="749c5-145">Visa information och resultat av en automatiserad undersökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="749c5-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
