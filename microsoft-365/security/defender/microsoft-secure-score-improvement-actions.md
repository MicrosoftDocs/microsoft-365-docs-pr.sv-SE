---
title: Utvärdera säkerheten genom Microsoft Secure Score
description: Här beskrivs hur du kan vidta åtgärder för att förbättra Microsoft Secure Score i Säkerhetscenter för Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 2b211eb0f55a9fa9faad1290443d62ac406f8360
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072674"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="af05d-104">Utvärdera din säkerhet med Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="af05d-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="af05d-105">Microsoft Secure Score är ett mått på en organisations säkerhetssäkerhet, med ett högre tal som anger fler förbättringsåtgärder som vidtas.</span><span class="sxs-lookup"><span data-stu-id="af05d-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="af05d-106">Den finns på https://security.microsoft.com/securescore Säkerhetscenter för [Microsoft 365.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="af05d-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="af05d-107">Åtgärder för Microsoft-förbättringar är ordnade i grupper så att du snabbare kan hitta den information du behöver:</span><span class="sxs-lookup"><span data-stu-id="af05d-107">To help you find the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="af05d-108">Identitet (Azure Active Directory-konton & roller)</span><span class="sxs-lookup"><span data-stu-id="af05d-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="af05d-109">Enhet (Microsoft Defender för slutpunkt, som kallas [Microsoft Secure Score för enheter](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span><span class="sxs-lookup"><span data-stu-id="af05d-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="af05d-110">App (e-post- och molnappar, inklusive Office 365 och Microsoft Cloud App Security)</span><span class="sxs-lookup"><span data-stu-id="af05d-110">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="af05d-111">I den senaste versionen av Microsoft Secure Score har en förbättrad poängmodell släppts som gjort att Microsoft Secure Score tillfälligt inte är kompatibelt med Identity Secure Score och Graph API.</span><span class="sxs-lookup"><span data-stu-id="af05d-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="af05d-112">Visa information</span><span class="sxs-lookup"><span data-stu-id="af05d-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="af05d-113">På översiktssidan för Microsoft Secure Score kan du se hur punkterna delas upp mellan grupperna och vilka punkter som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="af05d-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="af05d-114">Du kan också få en fullständig uppfattning om totalresultatet, en historisk trend för ditt säkra resultat med jämförelser av riktmärken och prioriterade förbättringsåtgärder som kan vidtas för att förbättra ditt resultat.</span><span class="sxs-lookup"><span data-stu-id="af05d-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![Startsida för Secure Score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="af05d-116">Kontrollera ditt aktuella poängresultat</span><span class="sxs-lookup"><span data-stu-id="af05d-116">Check your current score</span></span>

<span data-ttu-id="af05d-117">Om du vill kontrollera ditt aktuella resultat går du till översiktssidan för Microsoft Secure Score och letar efter panelen där det **står Ditt säkra resultat.**</span><span class="sxs-lookup"><span data-stu-id="af05d-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="af05d-118">Poängen visas som procent tillsammans med antalet poäng som du har uppnått av det totala antalet möjliga poäng.</span><span class="sxs-lookup"><span data-stu-id="af05d-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="af05d-119">Om du väljer knappen Inkludera **bredvid** resultatet kan du dessutom välja olika vyer av poängen.</span><span class="sxs-lookup"><span data-stu-id="af05d-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="af05d-120">Dessa olika poängvyer visas i diagrammet på poängpanelen och punktfördelningsdiagrammet.</span><span class="sxs-lookup"><span data-stu-id="af05d-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="af05d-121">Följande är resultat som du kan lägga till i vyn över ditt övergripande resultat för att ge dig en mer fullständig bild av ditt övergripande resultat:</span><span class="sxs-lookup"><span data-stu-id="af05d-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="af05d-122">**Planerat resultat:** Visa projekterat resultat när planerade åtgärder har slutförts</span><span class="sxs-lookup"><span data-stu-id="af05d-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="af05d-123">**Aktuellt licensresultat:** Visa poäng som kan uppnås med din aktuella Microsoft-licens</span><span class="sxs-lookup"><span data-stu-id="af05d-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="af05d-124">**Uppnåbart resultat: Visa** poäng som kan uppnås med dina Microsoft-licenser och aktuellt riskgodkännande</span><span class="sxs-lookup"><span data-stu-id="af05d-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="af05d-125">Den här vyn ser ut så här om du har tagit med alla möjliga poängvyer:</span><span class="sxs-lookup"><span data-stu-id="af05d-125">This view is what it will look like if you've included all possible score views:</span></span>

![Ditt säkra resultat inklusive planerat poäng, aktuellt licensresultat och uppnåbart poäng](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="af05d-127">Vidta åtgärder för att förbättra ditt resultat</span><span class="sxs-lookup"><span data-stu-id="af05d-127">Take action to improve your score</span></span>

<span data-ttu-id="af05d-128">På **fliken Förbättringsåtgärder** visas säkerhetsrekommendationer som åtgärdar möjliga attackytor.</span><span class="sxs-lookup"><span data-stu-id="af05d-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="af05d-129">Den innehåller även deras status (för att hantera, planerade, godkända risker, lösas genom tredje part, lösas genom alternativ minskning och slutföras).</span><span class="sxs-lookup"><span data-stu-id="af05d-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="af05d-130">Du kan söka, filtrera och gruppera alla förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="af05d-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="af05d-131">Rankning</span><span class="sxs-lookup"><span data-stu-id="af05d-131">Ranking</span></span>

<span data-ttu-id="af05d-132">Rangordningen baseras på antalet punkter som återstår att uppnå, implementeringssvårigheter, användareffekter och komplexitet.</span><span class="sxs-lookup"><span data-stu-id="af05d-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="af05d-133">De förbättringsåtgärder som rangordnas högst har ett stort antal punkter som återstår med låg komplexitet, påverkan på användare och komplexitet.</span><span class="sxs-lookup"><span data-stu-id="af05d-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="af05d-134">Visa information om förbättringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="af05d-134">View improvement action details</span></span>

<span data-ttu-id="af05d-135">När du väljer en specifik förbättringsåtgärd visas en utfällig helsida.</span><span class="sxs-lookup"><span data-stu-id="af05d-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![Utfällt exempel på förbättringsåtgärd](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="af05d-137">Det finns några alternativ för att slutföra åtgärden:</span><span class="sxs-lookup"><span data-stu-id="af05d-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="af05d-138">Välj **Hantera** för att gå till konfigurationsskärmen och göra ändringen.</span><span class="sxs-lookup"><span data-stu-id="af05d-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="af05d-139">Sedan får du de poäng som åtgärden är värd, synlig i det flyg ut. Det brukar ta ungefär 24 timmar innan poäng har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="af05d-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="af05d-140">Välj **Dela** för att kopiera den direkta länken till förbättringsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="af05d-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="af05d-141">Du kan också välja plattformen för att dela länken, till exempel e-post, Microsoft Teams, Microsoft Planner eller ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="af05d-141">You can also choose the platform to share the link, such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="af05d-142">Om du väljer ServiceNow kan du skapa en ändrings biljett som visas i ServiceNow och säkerhetscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af05d-142">Selecting ServiceNow will let you create a change ticket that will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="af05d-143">Mer information finns i [Microsoft 365 säkerhetscenter och ServiceNow-integrering.](./tickets.md)</span><span class="sxs-lookup"><span data-stu-id="af05d-143">To learn more, see [Microsoft 365 security center and ServiceNow integration](./tickets.md).</span></span>

<span data-ttu-id="af05d-144">Lägg **till anteckningar** för att hålla reda på förloppet eller något annat du vill kommentera.</span><span class="sxs-lookup"><span data-stu-id="af05d-144">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="af05d-145">Om du lägger till egna **taggar i** förbättringsåtgärden kan du filtrera efter de taggarna.</span><span class="sxs-lookup"><span data-stu-id="af05d-145">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="af05d-146">Välj status för en förbättringsåtgärd</span><span class="sxs-lookup"><span data-stu-id="af05d-146">Choose an improvement action status</span></span>

<span data-ttu-id="af05d-147">Välj eventuella statusar och spela in anteckningar som är specifika för förbättringsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="af05d-147">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="af05d-148">**Åtgärda detta** – du känner igen att förbättringsåtgärden är nödvändig och planerar att åtgärda den vid något tillfälle i framtiden.</span><span class="sxs-lookup"><span data-stu-id="af05d-148">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="af05d-149">Det här tillståndet gäller även för åtgärder som identifieras som delvis, men inte helt slutförda.</span><span class="sxs-lookup"><span data-stu-id="af05d-149">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="af05d-150">**Planerat** – Det finns betongplaner på plats för att genomföra förbättringsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="af05d-150">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="af05d-151">**Accepterad** risk – Säkerheten bör alltid balanseras med användbarheten, och alla rekommendationer fungerar inte för din miljö.</span><span class="sxs-lookup"><span data-stu-id="af05d-151">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="af05d-152">När så är fallet kan du välja att acceptera risken, eller den återstående risken, och inte vidta någon förbättringsåtgärd.</span><span class="sxs-lookup"><span data-stu-id="af05d-152">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="af05d-153">Du får inga poäng men åtgärden visas inte längre i listan över förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="af05d-153">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="af05d-154">Du kan visa den här åtgärden i historiken eller ångra den när som helst.</span><span class="sxs-lookup"><span data-stu-id="af05d-154">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="af05d-155">**Löst genom tredje part** och **löst** genom alternativ minskning – Förbättringsåtgärden har redan åtgärdats av ett program eller en programvara från tredje part eller ett internt verktyg.</span><span class="sxs-lookup"><span data-stu-id="af05d-155">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="af05d-156">Då får du poäng som är värda åtgärden, så att poängen bättre speglar den övergripande säkerhetsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="af05d-156">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="af05d-157">Om en tredje part eller ett internt verktyg inte längre täcker kontrollen kan du välja en annan status.</span><span class="sxs-lookup"><span data-stu-id="af05d-157">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="af05d-158">Kom ihåg att Microsoft inte kommer att ha någon insyn i implementeringens fullständighet om förbättringsåtgärden markeras som någon av dessa statusar.</span><span class="sxs-lookup"><span data-stu-id="af05d-158">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="af05d-159">Hot & åtgärder för att förbättra sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="af05d-159">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="af05d-160">För förbättringsåtgärder i kategorin "Enhet" kan du inte välja status.</span><span class="sxs-lookup"><span data-stu-id="af05d-160">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="af05d-161">I stället hänvisas du till rekommendationen om [associerad](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) säkerhetsrisk och säkerhetshantering i Microsoft [Defender Säkerhetscenter för](/windows/security/threat-protection/microsoft-defender-atp/use) att vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="af05d-161">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="af05d-162">Det undantag du väljer och justering du skriver är specifikt för den portalen.</span><span class="sxs-lookup"><span data-stu-id="af05d-162">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="af05d-163">Den finns inte i Microsoft Secure Score-portalen.</span><span class="sxs-lookup"><span data-stu-id="af05d-163">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="af05d-164">Slutförda förbättringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="af05d-164">Completed improvement actions</span></span>

<span data-ttu-id="af05d-165">Förbättringsåtgärder har statusen "slutförd" när alla möjliga punkter för förbättringsåtgärden har uppnåtts.</span><span class="sxs-lookup"><span data-stu-id="af05d-165">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="af05d-166">Slutförda förbättringsåtgärder bekräftas via Microsoft-data och du kan inte ändra status.</span><span class="sxs-lookup"><span data-stu-id="af05d-166">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="af05d-167">Utvärdera information och granska användarnas påverkan</span><span class="sxs-lookup"><span data-stu-id="af05d-167">Assess information and review user impact</span></span>

<span data-ttu-id="af05d-168">I avsnittet som **heter Kort sagt** får du veta kategorin, attacker den kan skydda mot och produkten.</span><span class="sxs-lookup"><span data-stu-id="af05d-168">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="af05d-169">**Användarens** påverkan är vad användarna kommer att uppleva om  förbättringsåtgärden vidtas och Användare som påverkas är de personer som kommer att påverkas.</span><span class="sxs-lookup"><span data-stu-id="af05d-169">**User impact** is what the users will experience if the improvement action is enacted, and **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="af05d-170">Implementera förbättringsåtgärden</span><span class="sxs-lookup"><span data-stu-id="af05d-170">Implement the improvement action</span></span>

<span data-ttu-id="af05d-171">I **avsnittet** Implementering visas eventuella krav, stegvisa nästa steg för att slutföra förbättringsåtgärden, aktuell implementeringsstatus för förbättringsåtgärden och eventuella mer informationslänkar.</span><span class="sxs-lookup"><span data-stu-id="af05d-171">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="af05d-172">Kraven omfattar alla licenser som behövs eller åtgärder som ska slutföras innan förbättringsåtgärden åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="af05d-172">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="af05d-173">Kontrollera att du har tillräckligt med platser i licensen för att slutföra förbättringsåtgärden och att licenserna tillämpas på nödvändiga användare.</span><span class="sxs-lookup"><span data-stu-id="af05d-173">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="af05d-174">Vi vill höra från dig</span><span class="sxs-lookup"><span data-stu-id="af05d-174">We want to hear from you</span></span>

<span data-ttu-id="af05d-175">Om du har problem kan du meddela oss genom att publicera i communityn [säkerhet, & sekretess och](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="af05d-175">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="af05d-176">Vi övervakar communityn och kommer att hjälpa dig.</span><span class="sxs-lookup"><span data-stu-id="af05d-176">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="af05d-177">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="af05d-177">Related resources</span></span>

- [<span data-ttu-id="af05d-178">Översikt över Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="af05d-178">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="af05d-179">Spåra din Microsoft Secure Score-historik och nå dina mål</span><span class="sxs-lookup"><span data-stu-id="af05d-179">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="af05d-180">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="af05d-180">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="af05d-181">Nyheter</span><span class="sxs-lookup"><span data-stu-id="af05d-181">What's new</span></span>](microsoft-secure-score-whats-new.md)