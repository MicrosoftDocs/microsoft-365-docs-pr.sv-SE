---
title: Granska och hantera åtgärdsåtgärder i Microsoft Defender för Office 365
keywords: AIR, autoIR, Microsoft Defender för Slutpunkt, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.date: 06/10/2021
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108541"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="3a125-104">Granska och hantera åtgärdsåtgärder i Office 365</span><span class="sxs-lookup"><span data-stu-id="3a125-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="3a125-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="3a125-105">**Applies to**</span></span>
- [<span data-ttu-id="3a125-106">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="3a125-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="3a125-107">Eftersom automatiska undersökningar av e& och samarbetsinnehåll resulterar  i bedömningar, till exempel skadlig eller *misstänkt,* skapas vissa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="3a125-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="3a125-108">I Microsoft Defender Office 365 kan åtgärder som vidtas omfattar:</span><span class="sxs-lookup"><span data-stu-id="3a125-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="3a125-109">Mjuk borttagning av e-postmeddelanden och kluster</span><span class="sxs-lookup"><span data-stu-id="3a125-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="3a125-110">Stänga av vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="3a125-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="3a125-111">Dessa åtgärder vidtas inte om inte och tills ditt säkerhetsoperationsteam godkänner dem.</span><span class="sxs-lookup"><span data-stu-id="3a125-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="3a125-112">Vi rekommenderar att du granskar och godkänner eventuella väntande åtgärder så snart som möjligt så att de automatiserade undersökningarna kan slutföras i tid.</span><span class="sxs-lookup"><span data-stu-id="3a125-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="3a125-113">I vissa fall kan du ändra din skickade åtgärd.</span><span class="sxs-lookup"><span data-stu-id="3a125-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="3a125-114">Du måste vara en del av rollen & först ta bort innan du vidtar några åtgärder.</span><span class="sxs-lookup"><span data-stu-id="3a125-114">You need to be part of Search & purge role before taking any actions.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="3a125-115">Godkänna (eller avvisa) väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="3a125-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="3a125-116">Det finns fyra olika sätt att hitta och vidta åtgärder för automatisk undersökning:</span><span class="sxs-lookup"><span data-stu-id="3a125-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="3a125-117">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="3a125-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="3a125-118">Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="3a125-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="3a125-119">Själva undersökningen (åtkomst via incident eller från en avisering)</span><span class="sxs-lookup"><span data-stu-id="3a125-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="3a125-120">Kön för undersöknings- och åtgärdsundersökningar</span><span class="sxs-lookup"><span data-stu-id="3a125-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="3a125-121">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="3a125-121">Incident queue</span></span>

1. <span data-ttu-id="3a125-122">Öppna Microsoft 365 Defender ( <https://security.microsoft.com> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="3a125-122">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3a125-123">I navigeringsfönstret väljer du **Incidenter & eller > Incidenter.**</span><span class="sxs-lookup"><span data-stu-id="3a125-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="3a125-124">Välj namnet på ett incident så öppnas sammanfattningssidan.</span><span class="sxs-lookup"><span data-stu-id="3a125-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="3a125-125">Välj fliken **Bevis och** svar.</span><span class="sxs-lookup"><span data-stu-id="3a125-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="3a125-126">Markera ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="3a125-126">Select an item in the list.</span></span> <span data-ttu-id="3a125-127">Sidofönstret öppnas.</span><span class="sxs-lookup"><span data-stu-id="3a125-127">Its side pane opens.</span></span>
6. <span data-ttu-id="3a125-128">Godkänn eller avvisa åtgärder i sidofönstret.</span><span class="sxs-lookup"><span data-stu-id="3a125-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="3a125-129">Undersökningskö</span><span class="sxs-lookup"><span data-stu-id="3a125-129">Investigation queue</span></span>

1. <span data-ttu-id="3a125-130">Öppna Microsoft 365 Defender ( <https://security.microsoft.com> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="3a125-130">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3a125-131">Navigera från sidan aviseringar/incidenter.</span><span class="sxs-lookup"><span data-stu-id="3a125-131">Navigate from the alerts/incident page.</span></span>
3. <span data-ttu-id="3a125-132">På sidan Undersökning går du till fliken **Väntande** åtgärder.</span><span class="sxs-lookup"><span data-stu-id="3a125-132">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="3a125-133">Markera ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="3a125-133">Select an item in the list.</span></span> <span data-ttu-id="3a125-134">Sidofönstret öppnas.</span><span class="sxs-lookup"><span data-stu-id="3a125-134">Its side pane opens.</span></span>
5. <span data-ttu-id="3a125-135">Godkänn eller avvisa åtgärder i sidofönstret.</span><span class="sxs-lookup"><span data-stu-id="3a125-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="3a125-136">Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="3a125-136">Action center</span></span>

1. <span data-ttu-id="3a125-137">Öppna Microsoft 365 Defender ( <https://security.microsoft.com> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="3a125-137">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3a125-138">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="3a125-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="3a125-139">Granska listan **över åtgärder** som väntar på godkännande på fliken Väntande.</span><span class="sxs-lookup"><span data-stu-id="3a125-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="3a125-140">Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.</span><span class="sxs-lookup"><span data-stu-id="3a125-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="3a125-141">Välj **Godkänn** för att påbörja en väntande åtgärd.</span><span class="sxs-lookup"><span data-stu-id="3a125-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="3a125-142">Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.</span><span class="sxs-lookup"><span data-stu-id="3a125-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="3a125-143">Kön för undersöknings- och åtgärdsundersökningar</span><span class="sxs-lookup"><span data-stu-id="3a125-143">Investigation and remediation investigations queue</span></span>

1. <span data-ttu-id="3a125-144">Öppna Microsoft 365 Defender ( <https://security.microsoft.com> ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="3a125-144">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3a125-145">Öppna väntande undersökningar.</span><span class="sxs-lookup"><span data-stu-id="3a125-145">Open pending investigations.</span></span>
3. <span data-ttu-id="3a125-146">På sidan Undersökning går du till fliken **Väntande** åtgärder.</span><span class="sxs-lookup"><span data-stu-id="3a125-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="3a125-147">Markera ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="3a125-147">Select an item in the list.</span></span> <span data-ttu-id="3a125-148">Sidofönstret öppnas.</span><span class="sxs-lookup"><span data-stu-id="3a125-148">Its side pane opens.</span></span>
5. <span data-ttu-id="3a125-149">Godkänn eller avvisa åtgärder i sidofönstret.</span><span class="sxs-lookup"><span data-stu-id="3a125-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="3a125-150">Ändra eller ångra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="3a125-150">Change or undo one remediation action</span></span>

<span data-ttu-id="3a125-151">Det finns två olika sätt att ändra din skickade åtgärd:</span><span class="sxs-lookup"><span data-stu-id="3a125-151">There are two different ways to reconsider submitted actions:</span></span>

- <span data-ttu-id="3a125-152">Via det [enhetliga åtgärdscentret](https://security.microsoft.com/action-center).</span><span class="sxs-lookup"><span data-stu-id="3a125-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
- <span data-ttu-id="3a125-153">Fast Office [åtgärdscenter](https://security.microsoft.com/threatincidents).</span><span class="sxs-lookup"><span data-stu-id="3a125-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>

## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="3a125-154">Ändra eller ångra i det enhetliga åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="3a125-154">Change or undo through the unified action center</span></span>

1. <span data-ttu-id="3a125-155">Gå till [det enhetliga åtgärdscentret](https://security.microsoft.com/action-center) och logga in.</span><span class="sxs-lookup"><span data-stu-id="3a125-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="3a125-156">På fliken **Historik** väljer du en åtgärd som du vill ändra eller ångra.</span><span class="sxs-lookup"><span data-stu-id="3a125-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="3a125-157">I fönstret till höger på skärmen väljer du lämplig åtgärd **(flytta** till **Inkorgen,** gå till **skräppost,** flytta till borttagna objekt, **mjuk** borttagning eller **permanent borttagning**).</span><span class="sxs-lookup"><span data-stu-id="3a125-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, **soft delete**, or **hard delete**).</span></span>

## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="3a125-158">Ändra eller ångra i Office åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="3a125-158">Change or undo through the Office action center</span></span>

1. <span data-ttu-id="3a125-159">Gå till [Office åtgärdscenter](https://security.microsoft.com/threatincidents) och logga in.</span><span class="sxs-lookup"><span data-stu-id="3a125-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="3a125-160">Markera lämplig åtgärd.</span><span class="sxs-lookup"><span data-stu-id="3a125-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="3a125-161">I sidofönstret klickar du på posten för inskickade e-postmeddelanden och väntar på att listan läses in.</span><span class="sxs-lookup"><span data-stu-id="3a125-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span>
4. <span data-ttu-id="3a125-162">Vänta på åtgärdsknappen högst upp för att aktivera och välj knappen Åtgärd för att ändra åtgärdstyp.</span><span class="sxs-lookup"><span data-stu-id="3a125-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span>
5. <span data-ttu-id="3a125-163">Då skapas lämpliga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="3a125-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a125-164">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3a125-164">Next steps</span></span>

- [<span data-ttu-id="3a125-165">Använda Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="3a125-165">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="3a125-166">Admin/Manuella åtgärder</span><span class="sxs-lookup"><span data-stu-id="3a125-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="3a125-167">Så här rapporterar du falska positiva/negativa tal i automatiska undersöknings- och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="3a125-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="3a125-168">Se även</span><span class="sxs-lookup"><span data-stu-id="3a125-168">See also</span></span>

- [<span data-ttu-id="3a125-169">Visa information och resultat av en automatiserad undersökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="3a125-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
