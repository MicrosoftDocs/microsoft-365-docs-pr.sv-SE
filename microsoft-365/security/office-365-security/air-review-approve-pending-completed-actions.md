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
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142699"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="1dd7f-104">Granska och hantera åtgärder i Office 365</span><span class="sxs-lookup"><span data-stu-id="1dd7f-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="1dd7f-105">Eftersom automatiska undersökningar av e& och samarbetsinnehåll resulterar  i bedömningsresultat, till exempel skadliga eller *misstänkta,* skapas vissa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="1dd7f-106">I Microsoft Defender för Office 365 kan åtgärder omfatta:</span><span class="sxs-lookup"><span data-stu-id="1dd7f-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="1dd7f-107">Blockera en URL (tid för klickning)</span><span class="sxs-lookup"><span data-stu-id="1dd7f-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="1dd7f-108">Mjuk borttagning av e-postmeddelanden och kluster</span><span class="sxs-lookup"><span data-stu-id="1dd7f-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="1dd7f-109">Kvartil som e-post eller e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="1dd7f-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="1dd7f-110">Inaktivera vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="1dd7f-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="1dd7f-111">Dessa åtgärder vidtas inte om inte och tills säkerhetsteamet godkänner dem.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="1dd7f-112">Vi rekommenderar att du granskar och godkänner alla väntande åtgärder så snart som möjligt så att de automatiserade undersökningarna slutförs i tid.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="1dd7f-113">I vissa fall kan du ångra en åtgärdsåtgärd.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-113">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="1dd7f-114">Godkänna (eller avvisa) väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="1dd7f-114">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="1dd7f-115">Gå till Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) säkerhetscenter) och logga in.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-115">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="1dd7f-116">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="1dd7f-116">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="1dd7f-117">Granska **listan över åtgärder** som väntar på godkännande på fliken Väntande.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-117">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="1dd7f-118">Markera ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-118">Select an item in the list.</span></span> <span data-ttu-id="1dd7f-119">Det utfällfönster som visas.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-119">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="1dd7f-120">Granska informationen i det utfällfönster och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="1dd7f-120">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="1dd7f-121">Välj **sidan Öppna undersökning** om du vill visa mer information om undersökningen.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-121">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="1dd7f-122">Välj **Godkänn** för att påbörja en väntande åtgärd.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-122">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="1dd7f-123">Välj **Avvisa** om du vill förhindra att en väntande åtgärd vidtas.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-123">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="1dd7f-124">Ångra en åtgärdsåtgärd</span><span class="sxs-lookup"><span data-stu-id="1dd7f-124">Undo one remediation action</span></span>

1. <span data-ttu-id="1dd7f-125">Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-125">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="1dd7f-126">Välj en **åtgärd** som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-126">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="1dd7f-127">Välj Ångra i fönstret till höger på **skärmen.**</span><span class="sxs-lookup"><span data-stu-id="1dd7f-127">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="1dd7f-128">Ångra flera åtgärder</span><span class="sxs-lookup"><span data-stu-id="1dd7f-128">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="1dd7f-129">Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-129">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="1dd7f-130">Markera **de** åtgärder som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-130">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="1dd7f-131">Se till att markera objekt som har samma åtgärdstyp.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-131">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="1dd7f-132">Ett utfällt fönster öppnas.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-132">A flyout pane opens.</span></span>
3. <span data-ttu-id="1dd7f-133">Välj Ångra i det utfällade fönstret.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-133">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="1dd7f-134">Ta bort en fil från karantän på flera enheter</span><span class="sxs-lookup"><span data-stu-id="1dd7f-134">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="1dd7f-135">Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="1dd7f-135">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="1dd7f-136">Välj en **fil** som har karantänfilen åtgärdstyp på **fliken Historik.**</span><span class="sxs-lookup"><span data-stu-id="1dd7f-136">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="1dd7f-137">I fönstret till höger på skärmen väljer du Använd för **fler X-förekomster** av den här filen och sedan **Ångra.**</span><span class="sxs-lookup"><span data-stu-id="1dd7f-137">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1dd7f-138">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1dd7f-138">Next steps</span></span>

- [<span data-ttu-id="1dd7f-139">Använda HotUtforskaren</span><span class="sxs-lookup"><span data-stu-id="1dd7f-139">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="1dd7f-140">Hur du rapporterar falska positiva/negativa tal i automatiserad undersökning och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="1dd7f-140">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="1dd7f-141">Se även</span><span class="sxs-lookup"><span data-stu-id="1dd7f-141">See also</span></span>

- [<span data-ttu-id="1dd7f-142">Visa information och resultat av en automatiserad undersökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="1dd7f-142">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
