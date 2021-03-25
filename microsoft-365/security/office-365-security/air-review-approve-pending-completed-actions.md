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
description: Läs mer om åtgärder i funktioner för automatisk undersökning och svar i Microsoft Defender för Office 365 abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 61e9df45419cc73dae27b86dad47e1938183593d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207041"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="ad3a9-104">Granska och hantera åtgärder i Office 365</span><span class="sxs-lookup"><span data-stu-id="ad3a9-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="ad3a9-105">Eftersom automatiska undersökningar av e& och samarbetsinnehåll resulterar  i bedömningar, till exempel skadlig eller *misstänkt,* skapas vissa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="ad3a9-106">I Microsoft Defender för Office 365 kan åtgärder omfatta:</span><span class="sxs-lookup"><span data-stu-id="ad3a9-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="ad3a9-107">Blockera en URL (tid för klickning)</span><span class="sxs-lookup"><span data-stu-id="ad3a9-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="ad3a9-108">Mjuk borttagning av e-postmeddelanden och kluster</span><span class="sxs-lookup"><span data-stu-id="ad3a9-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="ad3a9-109">Kvarantitiska e-postmeddelanden och e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="ad3a9-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="ad3a9-110">Stänga av vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="ad3a9-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="ad3a9-111">Dessa åtgärder vidtas inte om inte och tills ditt säkerhetsoperationsteam godkänner dem.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="ad3a9-112">Vi rekommenderar att du granskar och godkänner eventuella väntande åtgärder så snart som möjligt så att de automatiserade undersökningarna kan slutföras i tid.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="ad3a9-113">I vissa fall kan du ångra en åtgärdsåtgärd.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="ad3a9-114">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="ad3a9-114">**Applies to**</span></span>
- [<span data-ttu-id="ad3a9-115">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="ad3a9-115">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ad3a9-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad3a9-116">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="ad3a9-117">Godkänna (eller avvisa) väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="ad3a9-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="ad3a9-118">Gå till Säkerhetscenter för Microsoft 365 ( <https://security.microsoft.com> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="ad3a9-119">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="ad3a9-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="ad3a9-120">Granska listan **över åtgärder** som väntar på godkännande på fliken Väntande.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="ad3a9-121">Markera ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-121">Select an item in the list.</span></span> <span data-ttu-id="ad3a9-122">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="ad3a9-123">Granska informationen i det utfällfönster som visas och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="ad3a9-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="ad3a9-124">Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="ad3a9-125">Välj **Godkänn** för att påbörja en väntande åtgärd.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="ad3a9-126">Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="ad3a9-127">Ångra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="ad3a9-127">Undo one remediation action</span></span>

1. <span data-ttu-id="ad3a9-128">Gå till Åtgärdscenter ( <https://security.microsoft.com/action-center> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ad3a9-129">Välj **en åtgärd** som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="ad3a9-130">I fönstret till höger på skärmen väljer du **Ångra**.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="ad3a9-131">Ångra flera åtgärder</span><span class="sxs-lookup"><span data-stu-id="ad3a9-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="ad3a9-132">Gå till Åtgärdscenter ( <https://security.microsoft.com/action-center> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ad3a9-133">Markera **de åtgärder** du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="ad3a9-134">Se till att markera objekt som har samma åtgärdstyp.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="ad3a9-135">Ett utfällt fönster öppnas.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="ad3a9-136">Välj Ångra i det utfällade fönstret.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="ad3a9-137">Ta bort en fil från karantän på flera enheter</span><span class="sxs-lookup"><span data-stu-id="ad3a9-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="ad3a9-138">Gå till Åtgärdscenter ( <https://security.microsoft.com/action-center> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="ad3a9-139">På fliken **Historik** väljer du en fil som har karantänfilen **Åtgärdstyp.**</span><span class="sxs-lookup"><span data-stu-id="ad3a9-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="ad3a9-140">I fönstret till höger på skärmen väljer du Använd för **fler X-instanser** av den här filen och sedan **Ångra**.</span><span class="sxs-lookup"><span data-stu-id="ad3a9-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ad3a9-141">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ad3a9-141">Next steps</span></span>

- [<span data-ttu-id="ad3a9-142">Använda Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="ad3a9-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="ad3a9-143">Så här rapporterar du falska positiva/negativa tal i automatiska undersöknings- och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="ad3a9-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="ad3a9-144">Se även</span><span class="sxs-lookup"><span data-stu-id="ad3a9-144">See also</span></span>

- [<span data-ttu-id="ad3a9-145">Visa information och resultat från en automatiserad undersökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="ad3a9-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
