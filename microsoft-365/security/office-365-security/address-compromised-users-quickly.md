---
title: Adress komprometterade användarkonton med automatiserad undersökning och svar
keywords: AIR, autoIR, Microsoft Defender för Slutpunkt, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd, komprometterat
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
ms.openlocfilehash: c500221a10c00cc3b8d9d99c102ce8ec54fa2a48
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934699"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="00e99-104">Adress komprometterade användarkonton med automatiserad undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="00e99-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="00e99-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="00e99-105">**Applies to**</span></span>
- [<span data-ttu-id="00e99-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="00e99-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="00e99-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="00e99-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="00e99-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00e99-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="00e99-109">[Microsoft Defender för Office 365 abonnemang 2 innehåller](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) kraftfulla [funktioner för automatisk undersökning och](office-365-air.md) svar (AIR).</span><span class="sxs-lookup"><span data-stu-id="00e99-109">[Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="00e99-110">Med sådana funktioner kan ditt säkerhetsteam spara mycket tid och arbete på att hantera hot.</span><span class="sxs-lookup"><span data-stu-id="00e99-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="00e99-111">Microsoft fortsätter att förbättra säkerhetsfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="00e99-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="00e99-112">Nyligen har AIR-funktionerna förbättrats med en säkerhetsspelbok för användare som komprometterats (för närvarande i förhandsversionen).</span><span class="sxs-lookup"><span data-stu-id="00e99-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="00e99-113">Läs den här artikeln om du vill veta mer om den komprometterade säkerhetsspelboken för användare.</span><span class="sxs-lookup"><span data-stu-id="00e99-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="00e99-114">Mer information finns i blogginlägget Snabba på tiden för att upptäcka och svara på användarnas intrång och begränsa intrångsomfånget med Microsoft Defender för [Office 365.](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)</span><span class="sxs-lookup"><span data-stu-id="00e99-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Automatisk undersökning för en komprometterad användare](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="00e99-116">Den komprometterade säkerhetsspelboken för användare gör det möjligt för organisationens säkerhetsteam att:</span><span class="sxs-lookup"><span data-stu-id="00e99-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="00e99-117">Snabbare identifiering av komprometterade användarkonton.</span><span class="sxs-lookup"><span data-stu-id="00e99-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="00e99-118">Begränsa omfattningen av ett intrång när ett konto har komprometterats. och</span><span class="sxs-lookup"><span data-stu-id="00e99-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="00e99-119">Reagera på komprometterade användare mer effektivt och effektivare.</span><span class="sxs-lookup"><span data-stu-id="00e99-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="00e99-120">Komprometterade användaraviseringar</span><span class="sxs-lookup"><span data-stu-id="00e99-120">Compromised user alerts</span></span>

<span data-ttu-id="00e99-121">När ett användarkonto har komprometterats uppstår ett fel som är atypiskt eller onormalt.</span><span class="sxs-lookup"><span data-stu-id="00e99-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="00e99-122">Till exempel kan nätfiske och skräppost skickas internt från ett betrott användarkonto.</span><span class="sxs-lookup"><span data-stu-id="00e99-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="00e99-123">Defender för Office 365 kan upptäcka sådana problem i e-postmönster och samarbetsaktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="00e99-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="00e99-124">I så fall inträffar aviseringar och åtgärder som innebär hot börjar.</span><span class="sxs-lookup"><span data-stu-id="00e99-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="00e99-125">Här är till exempel ett meddelande som utlöstes på grund av misstänkt e-postmeddelande:</span><span class="sxs-lookup"><span data-stu-id="00e99-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Avisering som utlösts på grund av att misstänkta e-postmeddelanden skickas](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="00e99-127">Och här är ett exempel på en varning som utlöstes när en avsändargräns nåddes för en användare:</span><span class="sxs-lookup"><span data-stu-id="00e99-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Avisering som utlöstes genom att sändningsgränsen har nåtts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="00e99-129">Undersöka och svara på en komprometterad användare</span><span class="sxs-lookup"><span data-stu-id="00e99-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="00e99-130">När ett användarkonto har komprometterats utlöses aviseringar.</span><span class="sxs-lookup"><span data-stu-id="00e99-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="00e99-131">Och i vissa fall blockeras och hindras användarkontot från att skicka ytterligare e-postmeddelanden tills problemet har lösts av organisationens team för säkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="00e99-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="00e99-132">I andra fall påbörjas en automatiserad undersökning som kan leda till rekommenderade åtgärder som din säkerhetsgrupp ska vidta.</span><span class="sxs-lookup"><span data-stu-id="00e99-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="00e99-133">Visa och undersöka begränsade användare</span><span class="sxs-lookup"><span data-stu-id="00e99-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="00e99-134">Visa information om automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="00e99-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="00e99-135">Du måste ha tillräcklig behörighet för att utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="00e99-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="00e99-136">Se [Behörigheter som krävs för att använda AIR-funktioner](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="00e99-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="00e99-137">Visa och undersöka begränsade användare</span><span class="sxs-lookup"><span data-stu-id="00e99-137">View and investigate restricted users</span></span>

<span data-ttu-id="00e99-138">Du har några alternativ för att navigera till en lista med begränsade användare.</span><span class="sxs-lookup"><span data-stu-id="00e99-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="00e99-139">I säkerhets- och efterlevnadscentret för & kan du till exempel gå till **Granska** begränsade användare \> **för** \> **hothantering.**</span><span class="sxs-lookup"><span data-stu-id="00e99-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="00e99-140">I följande procedur beskrivs  navigering med instrumentpanelen Aviseringar, som är ett bra sätt att se olika typer av aviseringar som kan ha utlösts.</span><span class="sxs-lookup"><span data-stu-id="00e99-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="00e99-141">Gå till <https://protection.office.com> och logga in.</span><span class="sxs-lookup"><span data-stu-id="00e99-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="00e99-142">Välj Instrumentpanelen aviseringar  i \> **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="00e99-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="00e99-143">Välj Restricted **Users (begränsade användare)** i **widgeten Other alerts (andra aviseringar).**</span><span class="sxs-lookup"><span data-stu-id="00e99-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget för andra aviseringar](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="00e99-145">Listan med begränsade användare öppnas.</span><span class="sxs-lookup"><span data-stu-id="00e99-145">This opens the list of restricted users.</span></span>

   ![Begränsade användare i Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="00e99-147">Välj ett användarkonto i listan för att visa information och vidta åtgärder, t.ex. [släppa en begränsad användare.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="00e99-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="00e99-148">Visa information om automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="00e99-148">View details about automated investigations</span></span>

<span data-ttu-id="00e99-149">När en automatiserad undersökning har påbörjats kan du se dess information och resultat i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="00e99-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="00e99-150">Gå till **Undersökning av** \> **hothantering** och välj sedan en undersökning för att visa dess detaljer.</span><span class="sxs-lookup"><span data-stu-id="00e99-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="00e99-151">Mer information finns i [Visa information om en undersökning](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="00e99-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="00e99-152">Tänk på följande</span><span class="sxs-lookup"><span data-stu-id="00e99-152">Keep the following points in mind</span></span>

- <span data-ttu-id="00e99-153">**Håll dig borta från dina aviseringar.**</span><span class="sxs-lookup"><span data-stu-id="00e99-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="00e99-154">Som du vet kommer en kompromiss att bli oupptäckta ju längre bort, desto större möjlighet till negativt påverkan och kostnad för organisationen, kunder och partner.</span><span class="sxs-lookup"><span data-stu-id="00e99-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="00e99-155">Tidiga identifieringar och snabba svar är avgörande för att minska hot, och särskilt när en användares konto har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="00e99-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="00e99-156">**Automationen hjälper till, men ersätter inte, ditt säkerhetsteam.**</span><span class="sxs-lookup"><span data-stu-id="00e99-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="00e99-157">Automatiska undersöknings- och svarsfunktioner kan upptäcka en komprometterad användare tidigt, men din säkerhetsgrupp måste troligtvis engagera sig och undersöka och åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="00e99-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="00e99-158">Behöver du hjälp med det här?</span><span class="sxs-lookup"><span data-stu-id="00e99-158">Need some help with this?</span></span> <span data-ttu-id="00e99-159">Se [Granska och godkänna åtgärder](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="00e99-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="00e99-160">**Förlita dig inte på en avisering om misstänkt inloggning, bara din .**</span><span class="sxs-lookup"><span data-stu-id="00e99-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="00e99-161">När ett användarkonto har komprometterats kan det hända att det utlöser en avisering om misstänkt inloggning.</span><span class="sxs-lookup"><span data-stu-id="00e99-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="00e99-162">Ibland är det en serie aktiviteter som inträffar när ett konto har komprometterats som utlöser en avisering.</span><span class="sxs-lookup"><span data-stu-id="00e99-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="00e99-163">Vill du veta mer om aviseringar?</span><span class="sxs-lookup"><span data-stu-id="00e99-163">Want to know more about alerts?</span></span> <span data-ttu-id="00e99-164">Se [Aviseringsprinciper.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="00e99-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="00e99-165">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="00e99-165">Next steps</span></span>

- [<span data-ttu-id="00e99-166">Granska de behörigheter som krävs för att använda AIR-funktioner</span><span class="sxs-lookup"><span data-stu-id="00e99-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="00e99-167">Hitta och undersöka skadlig e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="00e99-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="00e99-168">Läs mer om AIR i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="00e99-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="00e99-169">Besök Microsoft 365-översikt och se vad som kommer snart och lanseras</span><span class="sxs-lookup"><span data-stu-id="00e99-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)