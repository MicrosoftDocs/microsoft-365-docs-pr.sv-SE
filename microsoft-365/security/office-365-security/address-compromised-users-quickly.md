---
title: Lösa användar konton med automatisk undersökning och svar
keywords: LUFT, autoIR, ATP, automatiserad, undersökning, svar, reparation, hot, Avancerat, hot, skydd, kompromissad
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Lär dig hur du påskyndar processen att upptäcka och rikta in användar konton med automatiserade undersökningar och svars funktioner i Microsoft Defender för Office 365 abonnemang 2.
ms.openlocfilehash: 19c9bad33263178f92c6fe523b44497cf38ebd53
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616743"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="df5d8-104">Lösa användar konton med automatisk undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="df5d8-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="df5d8-105">[Microsoft Defender för Office 365 abonnemang 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) inkluderar kraftfulla [automatiserade undersökningar och svar](office-365-air.md) (Air).</span><span class="sxs-lookup"><span data-stu-id="df5d8-105">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="df5d8-106">Sådana funktioner kan spara din säkerhets åtgärds grupp mycket tid och ansträngning för att hantera hot.</span><span class="sxs-lookup"><span data-stu-id="df5d8-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="df5d8-107">Microsoft fortsätter att förbättra säkerhets funktionerna.</span><span class="sxs-lookup"><span data-stu-id="df5d8-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="df5d8-108">De senaste lösningarna har förbättrats för att omfatta Playbook (för närvarande för hands version).</span><span class="sxs-lookup"><span data-stu-id="df5d8-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="df5d8-109">Läs den här artikeln om du vill ha mer information om säkerhets Playbook.</span><span class="sxs-lookup"><span data-stu-id="df5d8-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="df5d8-110">Och se hur det går [snabbare att upptäcka och reagera på användarnas kompromisser och begränsa eventuella överträdelser med Microsoft Defender för Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) .</span><span class="sxs-lookup"><span data-stu-id="df5d8-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Automatiserad undersökning av en användare med kompromiss](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="df5d8-112">Användarens säkerhets Playbook gör att organisationens säkerhets team kan:</span><span class="sxs-lookup"><span data-stu-id="df5d8-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="df5d8-113">Snabb identifiering av obehöriga användar konton;</span><span class="sxs-lookup"><span data-stu-id="df5d8-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="df5d8-114">Begränsa omfattningen av en överträdelse när ett konto äventyras; och</span><span class="sxs-lookup"><span data-stu-id="df5d8-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="df5d8-115">Reagera på äventyrade användare effektivt och effektivt.</span><span class="sxs-lookup"><span data-stu-id="df5d8-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="df5d8-116">Obehöriga användar aviseringar</span><span class="sxs-lookup"><span data-stu-id="df5d8-116">Compromised user alerts</span></span>

<span data-ttu-id="df5d8-117">När ett användar konto är skadat uppstår atypical eller avvikande beteende.</span><span class="sxs-lookup"><span data-stu-id="df5d8-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="df5d8-118">Till exempel kan nätfiske och skräp post skickas internt från ett betrott användar konto.</span><span class="sxs-lookup"><span data-stu-id="df5d8-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="df5d8-119">Defender för Office 365 kan upptäcka sådana avvikelser i e-postmönster och samarbets aktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="df5d8-119">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="df5d8-120">När detta inträffar utlöses notifieringar och hotets minsknings processen påbörjas.</span><span class="sxs-lookup"><span data-stu-id="df5d8-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="df5d8-121">Här är en avisering som utlöstes på grund av misstänkt e-post:</span><span class="sxs-lookup"><span data-stu-id="df5d8-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Avisering utlöses på grund av misstänkt e-post](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="df5d8-123">Här är ett exempel på en avisering som utlöstes när en användares skickade gräns nåddes:</span><span class="sxs-lookup"><span data-stu-id="df5d8-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Avisering utlöst för att skicka gräns har uppnåtts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="df5d8-125">Undersöka och svara på en användare med kompromiss</span><span class="sxs-lookup"><span data-stu-id="df5d8-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="df5d8-126">När ett användar konto är skadat utlöses notifieringarna.</span><span class="sxs-lookup"><span data-stu-id="df5d8-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="df5d8-127">I vissa fall blockeras användar kontot och förhindras från att skicka fler e-postmeddelanden förrän problemet löses av organisationens säkerhets åtgärds team.</span><span class="sxs-lookup"><span data-stu-id="df5d8-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="df5d8-128">I andra fall börjar en automatisk undersökning som kan resultera i rekommenderade åtgärder som din säkerhets grupp bör vidta.</span><span class="sxs-lookup"><span data-stu-id="df5d8-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="df5d8-129">Visa och undersöka begränsade användare</span><span class="sxs-lookup"><span data-stu-id="df5d8-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="df5d8-130">Visa information om automatiserade utredningar</span><span class="sxs-lookup"><span data-stu-id="df5d8-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="df5d8-131">Du måste ha nödvändig behörighet för att utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="df5d8-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="df5d8-132">Se vilka [behörigheter som krävs för att använda Air-funktioner](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="df5d8-132">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="df5d8-133">Visa och undersöka begränsade användare</span><span class="sxs-lookup"><span data-stu-id="df5d8-133">View and investigate restricted users</span></span>

<span data-ttu-id="df5d8-134">Det finns några olika alternativ för att gå till en lista över begränsade användare.</span><span class="sxs-lookup"><span data-stu-id="df5d8-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="df5d8-135">I säkerhets & Compliance Center kan du till exempel gå till **Threat Management** \> **Granska** \> **begränsade användare**.</span><span class="sxs-lookup"><span data-stu-id="df5d8-135">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="df5d8-136">I följande procedur beskrivs navigering med instrument panelen **aviseringar** , som är ett bra sätt att se olika typer av aviseringar som kan ha utlösts.</span><span class="sxs-lookup"><span data-stu-id="df5d8-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="df5d8-137">Gå till <https://protection.office.com> och logga in.</span><span class="sxs-lookup"><span data-stu-id="df5d8-137">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="df5d8-138">Välj instrument panel för **aviseringar** i navigerings fönstret \> .</span><span class="sxs-lookup"><span data-stu-id="df5d8-138">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="df5d8-139">I widgeten **andra varningar** väljer **du begränsade användare**.</span><span class="sxs-lookup"><span data-stu-id="df5d8-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widgeten andra varningar](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="df5d8-141">Listan med begränsade användare öppnas.</span><span class="sxs-lookup"><span data-stu-id="df5d8-141">This opens the list of restricted users.</span></span>

   ![Begränsade användare i Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="df5d8-143">Välj ett användar konto i listan för att visa information och vidta åtgärder, till exempel [att släppa den begränsade användaren](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="df5d8-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="df5d8-144">Visa information om automatiserade utredningar</span><span class="sxs-lookup"><span data-stu-id="df5d8-144">View details about automated investigations</span></span>

<span data-ttu-id="df5d8-145">När en automatiserad undersökning har påbörjats kan du se dess information och resultaten i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="df5d8-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="df5d8-146">Gå till **Threat Management** \> **utredningar** och välj sedan en undersökning för att visa dess uppgifter.</span><span class="sxs-lookup"><span data-stu-id="df5d8-146">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="df5d8-147">Mer information finns i [Visa information om en undersökning](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="df5d8-147">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="df5d8-148">Tänk på följande saker</span><span class="sxs-lookup"><span data-stu-id="df5d8-148">Keep the following points in mind</span></span>

- <span data-ttu-id="df5d8-149">**Håll koll på dina aviseringar**.</span><span class="sxs-lookup"><span data-stu-id="df5d8-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="df5d8-150">Som du vet är det längre en kompromiss som försvinner, desto större potential och kostnad för din organisation, kunder och partners.</span><span class="sxs-lookup"><span data-stu-id="df5d8-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="df5d8-151">Tidiga identifieringar och svars tiden är kritiska för att minska risken för hot, särskilt när en användares konto äventyras.</span><span class="sxs-lookup"><span data-stu-id="df5d8-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="df5d8-152">**Automatisering hjälper, men ersätter inte, din säkerhets åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="df5d8-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="df5d8-153">Automatiserade undersökningar och svars funktioner kan upptäcka en användare som är utsatt för tidigt, men din säkerhets åtgärd är antagligen tvungen att delta och göra vissa undersökningar och ny hjälp.</span><span class="sxs-lookup"><span data-stu-id="df5d8-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="df5d8-154">Behöver du hjälp med det här?</span><span class="sxs-lookup"><span data-stu-id="df5d8-154">Need some help with this?</span></span> <span data-ttu-id="df5d8-155">Se [Granska och godkänna åtgärder](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="df5d8-155">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="df5d8-156">**Använd inte en misstänkt inloggnings avisering som indikator**.</span><span class="sxs-lookup"><span data-stu-id="df5d8-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="df5d8-157">Det kan hända att det inte går att utlösa en varning om misstänkt inloggning när ett användar konto är skadat.</span><span class="sxs-lookup"><span data-stu-id="df5d8-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="df5d8-158">Ibland är det en serie aktiviteter som inträffar efter att ett konto har blivit utsatt för en avisering.</span><span class="sxs-lookup"><span data-stu-id="df5d8-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="df5d8-159">Vill du veta mer om aviseringar?</span><span class="sxs-lookup"><span data-stu-id="df5d8-159">Want to know more about alerts?</span></span> <span data-ttu-id="df5d8-160">Se [aviserings principer](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="df5d8-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="df5d8-161">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="df5d8-161">Next steps</span></span>

- [<span data-ttu-id="df5d8-162">Granska de behörigheter som krävs för att använda AIR-funktioner</span><span class="sxs-lookup"><span data-stu-id="df5d8-162">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="df5d8-163">Hitta och undersöka skadlig e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="df5d8-163">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="df5d8-164">Lär dig mer om AIR i Microsoft Defender för slut punkten</span><span class="sxs-lookup"><span data-stu-id="df5d8-164">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="df5d8-165">Besök Microsoft 365-översikten för att se vad som kommer snart och lanseras</span><span class="sxs-lookup"><span data-stu-id="df5d8-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
