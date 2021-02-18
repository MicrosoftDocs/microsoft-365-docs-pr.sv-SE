---
title: Adress som avslöjats användarkonton med automatisk undersökning och svar
keywords: AIR, autoIR, ATP, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd, komprometterat
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Lär dig hur du kan snabba upp processen med att identifiera och åtgärda komprometterade användarkonton med funktioner för automatisk undersökning och svar i Microsoft Defender för Office 365 abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dda8c9b4aec30fd35efa153aaf032eee23b5e8a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288747"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="a2176-104">Adress som avslöjats användarkonton med automatisk undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="a2176-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a2176-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="a2176-105">**Applies to**</span></span>
- [<span data-ttu-id="a2176-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a2176-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a2176-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="a2176-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a2176-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2176-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="a2176-109">[Microsoft Defender för Office 365 abonnemang 2 innehåller](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) kraftfulla funktioner [för automatisk undersökning och svar](office-365-air.md) (AIR).</span><span class="sxs-lookup"><span data-stu-id="a2176-109">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="a2176-110">Med sådana funktioner kan ditt säkerhetsteam spara mycket tid och arbete med att hantera hot.</span><span class="sxs-lookup"><span data-stu-id="a2176-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="a2176-111">Microsoft fortsätter att förbättra säkerhetsfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="a2176-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="a2176-112">Nyligen förbättrades AIR-funktionerna till att omfatta en komprometterad säkerhetsspelbok för användare (för närvarande i förhandsversionen).</span><span class="sxs-lookup"><span data-stu-id="a2176-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="a2176-113">Läs den här artikeln om du vill veta mer om den komprometterade säkerhetsspelboken för användare.</span><span class="sxs-lookup"><span data-stu-id="a2176-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="a2176-114">Och i blogginlägget går det snabbare att identifiera och svara på användarnas intrång och begränsa intrångsomfånget med Microsoft Defender för [Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) för mer information.</span><span class="sxs-lookup"><span data-stu-id="a2176-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Automatiserad undersökning för en komprometterad användare](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="a2176-116">Den komprometterade säkerhetsspelboken gör att organisationens säkerhetsteam kan:</span><span class="sxs-lookup"><span data-stu-id="a2176-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="a2176-117">Gör identifieringen av komprometterade användarkonton snabbare.</span><span class="sxs-lookup"><span data-stu-id="a2176-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="a2176-118">Begränsa omfattningen av ett intrång när ett konto har komprometterats. och</span><span class="sxs-lookup"><span data-stu-id="a2176-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="a2176-119">Reagera på komprometterade användare mer effektivt och effektivare.</span><span class="sxs-lookup"><span data-stu-id="a2176-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="a2176-120">Komprometterade användaraviseringar</span><span class="sxs-lookup"><span data-stu-id="a2176-120">Compromised user alerts</span></span>

<span data-ttu-id="a2176-121">När ett användarkonto har komprometterats uppstår atypiska eller onormala beteenden.</span><span class="sxs-lookup"><span data-stu-id="a2176-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="a2176-122">Till exempel kan nätfiske- och skräppostmeddelanden skickas internt från ett betrott användarkonto.</span><span class="sxs-lookup"><span data-stu-id="a2176-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="a2176-123">Defender för Office 365 kan identifiera sådana projekt i e-postmönster och samarbetsaktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="a2176-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="a2176-124">När detta inträffar utlöses varningar och åtgärder för hot börjar.</span><span class="sxs-lookup"><span data-stu-id="a2176-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="a2176-125">Här är till exempel en varning som utlöstes på grund av misstänkt e-postmeddelande:</span><span class="sxs-lookup"><span data-stu-id="a2176-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Avisering som utlösts på grund av misstänkt e-postutskick](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="a2176-127">Och här är ett exempel på en avisering som utlöstes när en avsändargräns nåddes för en användare:</span><span class="sxs-lookup"><span data-stu-id="a2176-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Avisering som utlösts genom att sändningsgränsen har nåtts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="a2176-129">Undersöka och svara en komprometterad användare</span><span class="sxs-lookup"><span data-stu-id="a2176-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="a2176-130">När ett användarkonto har komprometterats utlöses aviseringar.</span><span class="sxs-lookup"><span data-stu-id="a2176-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="a2176-131">Och i vissa fall blockeras användarkontot och hindras från att skicka ytterligare e-postmeddelanden tills problemet har lösts av organisationens säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="a2176-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="a2176-132">I andra fall påbörjas en automatiserad undersökning som kan leda till rekommenderade åtgärder som din säkerhetsgrupp ska vidta.</span><span class="sxs-lookup"><span data-stu-id="a2176-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="a2176-133">Visa och undersöka begränsade användare</span><span class="sxs-lookup"><span data-stu-id="a2176-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="a2176-134">Visa information om automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="a2176-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="a2176-135">Du måste ha tillräcklig behörighet för att utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a2176-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="a2176-136">Se [behörigheter som krävs för att använda AIR-funktioner.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="a2176-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="a2176-137">Visa och undersöka begränsade användare</span><span class="sxs-lookup"><span data-stu-id="a2176-137">View and investigate restricted users</span></span>

<span data-ttu-id="a2176-138">Det finns några alternativ för att navigera till en lista med begränsade användare.</span><span class="sxs-lookup"><span data-stu-id="a2176-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="a2176-139">I Säkerhets- och & till exempel gå till Granskning **av** begränsade användare för hantering \> **av** \> **hot.**</span><span class="sxs-lookup"><span data-stu-id="a2176-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="a2176-140">Följande procedur beskriver navigering  med instrumentpanelen Aviseringar, som är ett bra sätt att se olika typer av aviseringar som kan ha utlösts.</span><span class="sxs-lookup"><span data-stu-id="a2176-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="a2176-141">Gå till <https://protection.office.com> och logga in.</span><span class="sxs-lookup"><span data-stu-id="a2176-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="a2176-142">Välj Instrumentpanelen för aviseringar **i** \> **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="a2176-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="a2176-143">Välj Begränsade **användare i** widgeten **Andra aviseringar.**</span><span class="sxs-lookup"><span data-stu-id="a2176-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget för andra aviseringar](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="a2176-145">Listan över begränsade användare öppnas.</span><span class="sxs-lookup"><span data-stu-id="a2176-145">This opens the list of restricted users.</span></span>

   ![Begränsade användare i Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="a2176-147">Välj ett användarkonto i listan om du vill visa information och vidta åtgärder, till exempel släppa [en begränsad användare.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="a2176-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="a2176-148">Visa information om automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="a2176-148">View details about automated investigations</span></span>

<span data-ttu-id="a2176-149">När en automatiserad undersökning har startat kan du se dess information och resultat i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="a2176-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="a2176-150">Gå till **Hothanteringsundersökningar** \> och välj sedan en undersökning för att visa dess detaljer.</span><span class="sxs-lookup"><span data-stu-id="a2176-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="a2176-151">Mer information finns i [Visa information om en undersökning.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="a2176-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="a2176-152">Tänk på följande punkter</span><span class="sxs-lookup"><span data-stu-id="a2176-152">Keep the following points in mind</span></span>

- <span data-ttu-id="a2176-153">**Håll dig på dina aviseringar.**</span><span class="sxs-lookup"><span data-stu-id="a2176-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="a2176-154">Som du vet, ju längre en kompromiss går oupptäckta, desto större möjlighet till omfattande påverkan och kostnad för organisationen, kunder och partners.</span><span class="sxs-lookup"><span data-stu-id="a2176-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="a2176-155">Tidig identifiering och snabb respons är avgörande för att minimera hot, och särskilt när en användares konto har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="a2176-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="a2176-156">**Automation hjälper till, men ersätter inte ditt säkerhetsteam.**</span><span class="sxs-lookup"><span data-stu-id="a2176-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="a2176-157">Automatiska undersöknings- och svarsfunktioner kan upptäcka en komprometterad användare tidigt, men din säkerhetsgrupp måste troligtvis engagera sig och undersöka och åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="a2176-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="a2176-158">Behöver du hjälp med det här?</span><span class="sxs-lookup"><span data-stu-id="a2176-158">Need some help with this?</span></span> <span data-ttu-id="a2176-159">Se [Granska och godkänna åtgärder.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="a2176-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="a2176-160">**Förlita dig inte på en misstänkt inloggningsavisering eftersom det är den enda indikatorn.**</span><span class="sxs-lookup"><span data-stu-id="a2176-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="a2176-161">När ett användarkonto har komprometterats kan det hända att det utlöser en misstänkt inloggningsavisering.</span><span class="sxs-lookup"><span data-stu-id="a2176-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="a2176-162">Ibland är det en serie aktiviteter som inträffar när ett konto har komprometterats som utlöser en avisering.</span><span class="sxs-lookup"><span data-stu-id="a2176-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="a2176-163">Vill du veta mer om aviseringar?</span><span class="sxs-lookup"><span data-stu-id="a2176-163">Want to know more about alerts?</span></span> <span data-ttu-id="a2176-164">Se [aviseringsprinciper.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a2176-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2176-165">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a2176-165">Next steps</span></span>

- [<span data-ttu-id="a2176-166">Granska de behörigheter som krävs för att använda AIR-funktioner</span><span class="sxs-lookup"><span data-stu-id="a2176-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="a2176-167">Hitta och undersöka skadlig e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="a2176-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="a2176-168">Läs mer om AIR i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a2176-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="a2176-169">Besök Microsoft 365 Roadmap och se vad som kommer snart och lanseras</span><span class="sxs-lookup"><span data-stu-id="a2176-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
