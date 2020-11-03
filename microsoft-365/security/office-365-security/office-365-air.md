---
title: Automatiserad undersökning och svar (AIR)-komma igång
keywords: LUFT, autoIR, ATP, automatiserad, undersökning, svar, reparation, hot, Avancerat, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Komma igång med automatiska undersökningar och svars funktioner i Microsoft Defender för Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 54dbd419380c18e23119887c93a71885c6f9ce7d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845810"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="d8be6-104">Komma igång med automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="d8be6-104">Get started using automated investigation and response (AIR) in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d8be6-105">[Microsoft Defender för Office 365](office-365-atp.md) inkluderar kraftfulla automatiserade undersökningar och svars funktioner som kan spara tid och ansträngning för arbets uppgifter.</span><span class="sxs-lookup"><span data-stu-id="d8be6-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="d8be6-106">När notifieringar utlöses är det upp till din säkerhets åtgärd för att granska, prioritera och svara på dessa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="d8be6-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="d8be6-107">Det är lätt att hålla kontakten med volymen av inkommande varningar.</span><span class="sxs-lookup"><span data-stu-id="d8be6-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="d8be6-108">Att automatisera vissa av detta kan vara till hjälp.</span><span class="sxs-lookup"><span data-stu-id="d8be6-108">Automating some of this can help.</span></span> <span data-ttu-id="d8be6-109">Med flyg kan din säkerhets åtgärds grupp fokusera på aktiviteter med högre prioritet utan att förlora varningar som utlöses.</span><span class="sxs-lookup"><span data-stu-id="d8be6-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="d8be6-110">Den här artikeln innehåller:</span><span class="sxs-lookup"><span data-stu-id="d8be6-110">This article includes:</span></span>
- <span data-ttu-id="d8be6-111">LUFT [flödet](#the-overall-flow-of-air) .</span><span class="sxs-lookup"><span data-stu-id="d8be6-111">The [overall flow](#the-overall-flow-of-air) of AIR;</span></span>
- <span data-ttu-id="d8be6-112">[Hur man kommer igång](#how-to-get-air); och</span><span class="sxs-lookup"><span data-stu-id="d8be6-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="d8be6-113">De [behörigheter som krävs](#required-permissions-to-use-air-capabilities) för att konfigurera eller använda Air-funktioner.</span><span class="sxs-lookup"><span data-stu-id="d8be6-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="d8be6-114">Det allmänna luft flödet</span><span class="sxs-lookup"><span data-stu-id="d8be6-114">The overall flow of AIR</span></span>

<span data-ttu-id="d8be6-115">På en hög nivå utlöses en avisering och en säkerhets Playbook påbörjar en automatiserad undersökning som ger resultat och rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="d8be6-115">At a high level, an alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="d8be6-116">Här är det allmänna flödet för luft, steg för steg:</span><span class="sxs-lookup"><span data-stu-id="d8be6-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="d8be6-117">En automatiserad undersökning initieras på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d8be6-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="d8be6-118">En [avisering](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) utlöses av en Office-händelse som skapar en olycka.</span><span class="sxs-lookup"><span data-stu-id="d8be6-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="d8be6-119">Beroende på vilken typ av händelse det gäller påbörjar en [Playbook](automated-investigation-response-office.md#security-playbooks) en automatisk undersökning.</span><span class="sxs-lookup"><span data-stu-id="d8be6-119">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="d8be6-120">---eller---</span><span class="sxs-lookup"><span data-stu-id="d8be6-120">--- or ---</span></span>
   
   - <span data-ttu-id="d8be6-121">En säkerhetsanalytiker [startar en automatisk undersökning](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) när du använder [Threat Explorer](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="d8be6-121">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="d8be6-122">När en automatiserad undersökning körs samlar den in ytterligare information om e-postmeddelandet i fråga och enheter som är relaterade till e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="d8be6-122">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="d8be6-123">Sådana enheter kan innehålla filer, URL: er och mottagare.</span><span class="sxs-lookup"><span data-stu-id="d8be6-123">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="d8be6-124">Undersökningens omfattning kan öka när nya och relaterade notifieringar utlöses.</span><span class="sxs-lookup"><span data-stu-id="d8be6-124">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="d8be6-125">Under och efter en automatisk undersökning finns [information och resultat](air-view-investigation-results.md) tillgängliga för visning.</span><span class="sxs-lookup"><span data-stu-id="d8be6-125">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="d8be6-126">Resultaten innehåller [rekommenderade åtgärder](air-remediation-actions.md) som kan vidtas för att svara och åtgärda eventuella hot som hittats.</span><span class="sxs-lookup"><span data-stu-id="d8be6-126">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="d8be6-127">Dessutom är en [Playbook-logg](air-view-investigation-results.md#playbook-log) som visar alla undersöknings aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="d8be6-127">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="d8be6-128">Om din organisation använder en anpassad rapporterings lösning eller en lösning från tredje part kan du [använda API: t för hanterings aktiviteten för Office 365](air-custom-reporting.md) för att visa information om automatiserade utredningar och hot.</span><span class="sxs-lookup"><span data-stu-id="d8be6-128">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="d8be6-129">Säkerhets åtgärds gruppen granskar [undersöknings resultat och rekommendationer](air-view-investigation-results.md)och [godkänner eller avvisar reparations åtgärder](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="d8be6-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

    <span data-ttu-id="d8be6-130">Eftersom pågående reparations åtgärder är godkända (eller nekade) är den automatiska undersökningen klar.</span><span class="sxs-lookup"><span data-stu-id="d8be6-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="d8be6-131">I Microsoft Defender för Office 365 vidtas ingen reparations åtgärd automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d8be6-131">In Microsoft Defender for Office 365, no remediation actions are taken automatically.</span></span> <span data-ttu-id="d8be6-132">Reparations åtgärder vidtas endast vid godkännande av organisationens säkerhets team.</span><span class="sxs-lookup"><span data-stu-id="d8be6-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="d8be6-133">Under och efter en automatiserad gransknings process kan säkerhets teamet göra följande:</span><span class="sxs-lookup"><span data-stu-id="d8be6-133">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="d8be6-134">Visa information om en avisering om en undersökning</span><span class="sxs-lookup"><span data-stu-id="d8be6-134">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="d8be6-135">Visa resultat informationen för en undersökning</span><span class="sxs-lookup"><span data-stu-id="d8be6-135">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="d8be6-136">Granska och godkänna åtgärder som ett resultat av en undersökning</span><span class="sxs-lookup"><span data-stu-id="d8be6-136">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="d8be6-137">Mer information finns i [så här fungerar luften](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span><span class="sxs-lookup"><span data-stu-id="d8be6-137">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="d8be6-138">Så här kommer du till luften</span><span class="sxs-lookup"><span data-stu-id="d8be6-138">How to get AIR</span></span>

<span data-ttu-id="d8be6-139">AIR-funktioner ingår i [Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span><span class="sxs-lookup"><span data-stu-id="d8be6-139">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="d8be6-140">Men dina [principer måste konfigureras](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) för att luften ska fungera som förväntat.</span><span class="sxs-lookup"><span data-stu-id="d8be6-140">However, your [policies must be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="d8be6-141">Dessutom bör du kontrol lera att du har granskat och kanske konfigurerar organisationens [notifieringsregler](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="d8be6-141">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="d8be6-142">Microsoft 365 innehåller många inbyggda aviserings principer som hjälper dig att identifiera behörigheter för Exchange-administratörer om missbruk, skadlig program vara, potentiella externa och interna hot samt informations hanterings risker.</span><span class="sxs-lookup"><span data-stu-id="d8be6-142">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="d8be6-143">Flera av [standard aviserings principerna](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan utlösa automatiserade utredningar.</span><span class="sxs-lookup"><span data-stu-id="d8be6-143">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="d8be6-144">Bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="d8be6-144">These include the following:</span></span>

- <span data-ttu-id="d8be6-145">En potentiellt skadlig URL-klickning identifieras</span><span class="sxs-lookup"><span data-stu-id="d8be6-145">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="d8be6-146">Ett e-postmeddelande rapporteras av en användare som Phish</span><span class="sxs-lookup"><span data-stu-id="d8be6-146">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="d8be6-147">E-postmeddelanden med skadlig kod tas bort efter leverans</span><span class="sxs-lookup"><span data-stu-id="d8be6-147">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="d8be6-148">E-postmeddelanden som innehåller Phish URL-adresser tas bort efter leverans</span><span class="sxs-lookup"><span data-stu-id="d8be6-148">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="d8be6-149">Misstänkta e-postmeddelanden som skickar mönster identifieras</span><span class="sxs-lookup"><span data-stu-id="d8be6-149">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="d8be6-150">En användare är begränsad från att skicka e-post</span><span class="sxs-lookup"><span data-stu-id="d8be6-150">A user is restricted from sending email</span></span>

<span data-ttu-id="d8be6-151">[Lär dig mer om aviseringar och luft](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span><span class="sxs-lookup"><span data-stu-id="d8be6-151">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="d8be6-152">Nödvändig behörighet för att använda AIR-funktioner</span><span class="sxs-lookup"><span data-stu-id="d8be6-152">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="d8be6-153">Behörigheter beviljas via vissa roller, till exempel de som beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="d8be6-153">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="d8be6-154">Uppgift</span><span class="sxs-lookup"><span data-stu-id="d8be6-154">Task</span></span> |<span data-ttu-id="d8be6-155">Nödvändiga roller</span><span class="sxs-lookup"><span data-stu-id="d8be6-155">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="d8be6-156">Så här ställer du in AIR-funktioner</span><span class="sxs-lookup"><span data-stu-id="d8be6-156">To set up AIR features</span></span> |<span data-ttu-id="d8be6-157">En av följande roller:</span><span class="sxs-lookup"><span data-stu-id="d8be6-157">One of the following roles:</span></span> <br/><span data-ttu-id="d8be6-158">-Global administratör</span><span class="sxs-lookup"><span data-stu-id="d8be6-158">- Global Administrator</span></span><br/><span data-ttu-id="d8be6-159">-Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="d8be6-159">- Security Administrator</span></span> <br/><span data-ttu-id="d8be6-160">Dessa roller kan tilldelas i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="d8be6-160">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="d8be6-161">För att godkänna eller avvisa rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="d8be6-161">To approve or reject recommended actions</span></span>|<span data-ttu-id="d8be6-162">En av följande roller, tilldelad i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span><span class="sxs-lookup"><span data-stu-id="d8be6-162">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="d8be6-163">-Global administratör</span><span class="sxs-lookup"><span data-stu-id="d8be6-163">- Global Administrator</span></span> <br/><span data-ttu-id="d8be6-164">-Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="d8be6-164">- Security Administrator</span></span><br/><span data-ttu-id="d8be6-165">-Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="d8be6-165">- Security Reader</span></span> <br/><span data-ttu-id="d8be6-166">---och---</span><span class="sxs-lookup"><span data-stu-id="d8be6-166">--- and ---</span></span><br/><span data-ttu-id="d8be6-167">-Sök och Töm (den här rollen tilldelas endast i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="d8be6-167">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="d8be6-168">Du kanske måste skapa en ny roll grupp och lägga till rollen Sök och rensa i den nya roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="d8be6-168">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

<span data-ttu-id="d8be6-169">Licenser [för Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) ska tilldelas:</span><span class="sxs-lookup"><span data-stu-id="d8be6-169">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="d8be6-170">Säkerhets administratörer (inklusive globala administratörer)</span><span class="sxs-lookup"><span data-stu-id="d8be6-170">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="d8be6-171">Organisationens säkerhets åtgärds team (inklusive säkerhets läsare och de som har rollen Sök och rensa)</span><span class="sxs-lookup"><span data-stu-id="d8be6-171">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="d8be6-172">Slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="d8be6-172">End users</span></span>

<span data-ttu-id="d8be6-173">Dessutom måste [principer för Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) definieras och användas för att skydd ska kunna användas.</span><span class="sxs-lookup"><span data-stu-id="d8be6-173">In addition, [Microsoft Defender for Office 365 policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) must be defined and applied in order for protection to be in place.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8be6-174">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d8be6-174">Next steps</span></span>

- [<span data-ttu-id="d8be6-175">Visa information och resultat från en automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="d8be6-175">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="d8be6-176">Granska och godkänna pågående åtgärder</span><span class="sxs-lookup"><span data-stu-id="d8be6-176">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="d8be6-177">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="d8be6-177">Related articles</span></span>

- [<span data-ttu-id="d8be6-178">Automatisk undersökning och reparation i Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="d8be6-178">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="d8be6-179">Automatisk undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8be6-179">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
