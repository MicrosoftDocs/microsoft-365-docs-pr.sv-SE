---
title: Utvärdera dina säkerhets Posture via Microsofts säkra Poäng
description: Här beskrivs hur du utför en åtgärd för att förbättra dina säkra Microsoft-poäng i säkerhets Center för Microsoft 365.
keywords: Microsoft säkra poäng, säkra poäng, Office 365 säkra poäng, säkerhets poäng, Microsoft 365 säkerhets Center, förbättrings åtgärder
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: cb2aad70b8ba6ccd9075513b5f383ede42ebd6c0
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295134"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="0b482-104">Utvärdera dina säkerhets Posture med Microsofts säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="0b482-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0b482-105">Microsoft Secure score är ett mått på en organisations säkerhets Posture, med ett högre nummer som indikerar fler förbättrings åtgärder.</span><span class="sxs-lookup"><span data-stu-id="0b482-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="0b482-106">Den finns https://security.microsoft.com/securescore i [säkerhets Center för Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="0b482-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="0b482-107">För att hjälpa dig att hitta den information du behöver snabbare är Microsoft Improvement åtgärder ordnade i grupper:</span><span class="sxs-lookup"><span data-stu-id="0b482-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="0b482-108">Identitet (Azure Active Directory-konton & roller)</span><span class="sxs-lookup"><span data-stu-id="0b482-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="0b482-109">Data (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="0b482-109">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="0b482-110">Enhet (Microsoft Defender ATP, kallas [Microsofts säkra Poäng för enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span><span class="sxs-lookup"><span data-stu-id="0b482-110">Device (Microsoft Defender ATP, known as [Microsoft Secure Score for Devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="0b482-111">App (e-post och Cloud-appar, inklusive Office 365 och Microsoft Cloud App Security)</span><span class="sxs-lookup"><span data-stu-id="0b482-111">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="0b482-112">Infrastruktur (inga förbättrings åtgärder)</span><span class="sxs-lookup"><span data-stu-id="0b482-112">Infrastructure (no improvement actions for now)</span></span>

>[!NOTE]
><span data-ttu-id="0b482-113">I den senaste versionen av Microsofts säkra poäng har en förbättrad beräknings modell släppts som gjorde den tillfälligt inkompatibel med identitets säkra poäng och diagram-API: t.</span><span class="sxs-lookup"><span data-stu-id="0b482-113">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="0b482-114">Visa information</span><span class="sxs-lookup"><span data-stu-id="0b482-114">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="0b482-115">På sidan Microsofts säkra Poäng översikt kan du se hur Poäng delas mellan dessa grupper och vilka Poäng som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="0b482-115">In the Microsoft Secure Score overview page, see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="0b482-116">Du kan också få en hel del av den totala poängen, historisk trenden för dina säkra poäng med benchmark-jämförelser och prioriterade förbättrings åtgärder som kan vidtas för att förbättra din poäng.</span><span class="sxs-lookup"><span data-stu-id="0b482-116">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![Säkra Poäng start sidan](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="0b482-118">Kontrol lera aktuell Poäng</span><span class="sxs-lookup"><span data-stu-id="0b482-118">Check your current score</span></span>

<span data-ttu-id="0b482-119">Om du vill kontrol lera din aktuella poäng går du till sidan Microsoft-översikt över säkra poäng och letar efter brickan med **din säkra Poäng**.</span><span class="sxs-lookup"><span data-stu-id="0b482-119">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="0b482-120">Poängen visas som en procents ATS, tillsammans med antalet poäng som du har uppnått av totalt antal möjliga poäng.</span><span class="sxs-lookup"><span data-stu-id="0b482-120">Your score will be shown as a percentage, along with the number of points you've achieved out of a total possible points.</span></span>

<span data-ttu-id="0b482-121">Om du väljer knappen **Inkludera** bredvid poängen kan du välja olika vyer för poängen.</span><span class="sxs-lookup"><span data-stu-id="0b482-121">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="0b482-122">De här vyerna visas i diagrammet på Poäng panelen och diagrammet med punkt diagram.</span><span class="sxs-lookup"><span data-stu-id="0b482-122">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="0b482-123">Här följer resultat som du kan lägga till i din vy av total poängen för att ge dig en fullständig bild av ditt totala poäng värde:</span><span class="sxs-lookup"><span data-stu-id="0b482-123">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="0b482-124">**Planerat Poäng**: Visa projektschemat när planerade åtgärder är klara</span><span class="sxs-lookup"><span data-stu-id="0b482-124">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="0b482-125">**Aktuell licens Poäng**: Visa poängen som kan uppnås med din nuvarande Microsoft-licens</span><span class="sxs-lookup"><span data-stu-id="0b482-125">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="0b482-126">**Möjlig Poäng**: Visa poängen som kan uppnås med Microsoft-licenser och nuvarande risk godkännande</span><span class="sxs-lookup"><span data-stu-id="0b482-126">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="0b482-127">Den här vyn ser ut om du har inkluderat alla möjliga åsikter:</span><span class="sxs-lookup"><span data-stu-id="0b482-127">This view is what it will look like if you've included all possible score views:</span></span>

![Din säkra Poäng inklusive planerat poäng, aktuell licens Poäng och möjligt Poäng](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="0b482-129">Vidta åtgärder för att förbättra din Poäng</span><span class="sxs-lookup"><span data-stu-id="0b482-129">Take action to improve your score</span></span>

<span data-ttu-id="0b482-130">På fliken **förbättrings åtgärder** visas de säkerhets rekommendationer som kan användas för att hantera möjliga attacker.</span><span class="sxs-lookup"><span data-stu-id="0b482-130">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="0b482-131">Det inkluderar också deras status (till adress, planerad, risk som accepterats av tredje part, löst via annan åtgärd och ifylld).</span><span class="sxs-lookup"><span data-stu-id="0b482-131">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="0b482-132">Du kan söka, filtrera och gruppera alla förbättringar.</span><span class="sxs-lookup"><span data-stu-id="0b482-132">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="0b482-133">Ranknings</span><span class="sxs-lookup"><span data-stu-id="0b482-133">Ranking</span></span>

<span data-ttu-id="0b482-134">Rangordning baseras på antalet Points kvar för att uppnå, implementera problem, användar påverkan och komplexitet.</span><span class="sxs-lookup"><span data-stu-id="0b482-134">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="0b482-135">De högsta åtgärderna för bättre rangordning har ett stort antal Points kvar med nedsatt syn, användar påverkan och komplexitet.</span><span class="sxs-lookup"><span data-stu-id="0b482-135">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="0b482-136">Visa information om förbättrings åtgärder</span><span class="sxs-lookup"><span data-stu-id="0b482-136">View improvement action details</span></span>

<span data-ttu-id="0b482-137">När du väljer en särskild förbättrings åtgärd visas en hel sida med utfällbar text.</span><span class="sxs-lookup"><span data-stu-id="0b482-137">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="0b482-138">![Förbättrings instruktionen utfälld exempel ](../../media/secure-score/secure-score-improvement-action-details.png)
 *figur 2: förbättrings åtgärd utfällbar exempel*</span><span class="sxs-lookup"><span data-stu-id="0b482-138">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="0b482-139">Om du vill slutföra åtgärden har du några alternativ:</span><span class="sxs-lookup"><span data-stu-id="0b482-139">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="0b482-140">Välj **Hantera** för att gå till sidan konfiguration och göra ändringen.</span><span class="sxs-lookup"><span data-stu-id="0b482-140">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="0b482-141">Då får du de punkter som åtgärden är värd för, synlig i flyg ut. Det tar vanligt vis ungefär 24 timmar att uppdatera det.</span><span class="sxs-lookup"><span data-stu-id="0b482-141">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="0b482-142">Välj **dela** för att kopiera den direkta länken till förbättrings åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0b482-142">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="0b482-143">Du kan också välja plattformen för att dela länken, till exempel e-post, Microsoft Teams, Microsoft Planner eller ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="0b482-143">You can also choose the platform to share the link, such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="0b482-144">Om du väljer ServiceNow kan du skapa en ändrings biljett som visas i ServiceNow och Microsoft 365 Security Center Home.</span><span class="sxs-lookup"><span data-stu-id="0b482-144">Selecting ServiceNow will let you create a change ticket that will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="0b482-145">Mer information finns i [Microsoft 365 Security Center och ServiceNow integration](tickets-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="0b482-145">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="0b482-146">Välj en förbättrings åtgärds status</span><span class="sxs-lookup"><span data-stu-id="0b482-146">Choose an improvement action status</span></span>

<span data-ttu-id="0b482-147">Välj status och anteckningar för förbättrings åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0b482-147">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="0b482-148">**Adress** – du känner igen att förbättrings åtgärden är nödvändig och att du planerar att adressera den vid något tillfälle i framtiden.</span><span class="sxs-lookup"><span data-stu-id="0b482-148">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="0b482-149">Det här läget gäller även för åtgärder som identifieras som delvis men inte fullständigt slutförda.</span><span class="sxs-lookup"><span data-stu-id="0b482-149">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="0b482-150">**Planerat** – det finns konkreta planer för att slutföra förbättrings åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0b482-150">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="0b482-151">**Risk accepterad** – säkerheten bör alltid bal anse ras och inte varje rekommendation fungera för din miljö.</span><span class="sxs-lookup"><span data-stu-id="0b482-151">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="0b482-152">I så fall kan du välja att acceptera risken, eller den återstående risken, och inte vidta förbättrings åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0b482-152">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="0b482-153">Du får inga poäng, men åtgärden kommer inte längre att synas i listan över förbättrings åtgärder.</span><span class="sxs-lookup"><span data-stu-id="0b482-153">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="0b482-154">Du kan visa den här åtgärden i historik eller när som helst.</span><span class="sxs-lookup"><span data-stu-id="0b482-154">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="0b482-155">**Löstes genom tredje part** och **löses genom den alternativa begränsningen** -åtgärden har redan åtgärd ATS av ett tredjepartsprogram eller program vara från tredje part, eller ett internt verktyg.</span><span class="sxs-lookup"><span data-stu-id="0b482-155">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="0b482-156">Du får de punkter som åtgärden är värd för, så din poäng bättre återspeglar ditt totala säkerhets Posture.</span><span class="sxs-lookup"><span data-stu-id="0b482-156">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="0b482-157">Om en tredje part eller ett internt verktyg inte längre täcker kontrollen kan du välja en annan status.</span><span class="sxs-lookup"><span data-stu-id="0b482-157">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="0b482-158">Kom ihåg att Microsoft inte har någon insyn i fullständig implementering om förbättrings åtgärden är markerad som någon av dessa status värden.</span><span class="sxs-lookup"><span data-stu-id="0b482-158">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="0b482-159">Hot & sårbarhet för hanterings förbättring</span><span class="sxs-lookup"><span data-stu-id="0b482-159">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="0b482-160">För förbättrings åtgärder i kategorin "enhet" kan du inte välja status.</span><span class="sxs-lookup"><span data-stu-id="0b482-160">For improvement actions in the "Device" category, you won't be able to choose statuses.</span></span> <span data-ttu-id="0b482-161">I stället dirigeras du om till den associerade [Threat & säkerhets rekommendation för hantering (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) i [Microsoft Defender säkerhets Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) för att vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="0b482-161">Instead, you'll be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="0b482-162">Det undantag du väljer och motivering du skriver är specifikt för den portalen.</span><span class="sxs-lookup"><span data-stu-id="0b482-162">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="0b482-163">Det finns inte på Microsofts säkra Poäng-Portal.</span><span class="sxs-lookup"><span data-stu-id="0b482-163">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="0b482-164">Slutförda förbättrings åtgärder</span><span class="sxs-lookup"><span data-stu-id="0b482-164">Completed improvement actions</span></span>

<span data-ttu-id="0b482-165">Förbättrings åtgärder har statusen "slutfört" när alla möjliga poäng för förbättrings åtgärden har uppnåtts.</span><span class="sxs-lookup"><span data-stu-id="0b482-165">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="0b482-166">Slutförda förbättrings åtgärder bekräftas, men du kommer inte att kunna ändra den.</span><span class="sxs-lookup"><span data-stu-id="0b482-166">Completed improvement actions are confirmed though Microsoft data, and you won't be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="0b482-167">Utvärdera information och granska användar påverkan</span><span class="sxs-lookup"><span data-stu-id="0b482-167">Assess information and review user impact</span></span>

<span data-ttu-id="0b482-168">I det avsnitt som heter kan du berätta för dig kategorin, angripna den **för** att skydda mot och produkten.</span><span class="sxs-lookup"><span data-stu-id="0b482-168">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="0b482-169">**Användarens påverkan** visar vad användarna kommer att uppleva om förbättrings åtgärden utförs, och användare som **påverkas** av din upplevelse.</span><span class="sxs-lookup"><span data-stu-id="0b482-169">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="0b482-170">Implementera förbättrings åtgärden</span><span class="sxs-lookup"><span data-stu-id="0b482-170">Implement the improvement action</span></span>

<span data-ttu-id="0b482-171">I **implementerings** avsnittet visas eventuella förutsättningar för att förbättra förbättrings åtgärden, steg för steg-steg och anvisningar för förbättrings åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0b482-171">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="0b482-172">Förutsättningar innehåller alla licenser som måste erhållas eller åtgärder som måste slutföras innan förbättrings åtgärden åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="0b482-172">Prerequisites include any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="0b482-173">Kontrol lera att du har tillräckligt många platser i din licens för att slutföra förbättrings åtgärden och att dessa licenser tillämpas på de användare som behövs.</span><span class="sxs-lookup"><span data-stu-id="0b482-173">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="0b482-174">Vi vill höra från dig</span><span class="sxs-lookup"><span data-stu-id="0b482-174">We want to hear from you</span></span>

<span data-ttu-id="0b482-175">Om du har några problem kan du meddela oss genom att publicera det i [säkerhets-, integritets &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span><span class="sxs-lookup"><span data-stu-id="0b482-175">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="0b482-176">Vi övervakar communityn och ger hjälp.</span><span class="sxs-lookup"><span data-stu-id="0b482-176">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="0b482-177">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="0b482-177">Related resources</span></span>

- [<span data-ttu-id="0b482-178">Översikt över Microsofts säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="0b482-178">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="0b482-179">Spåra din Microsoft säkra Poäng historik och uppfylla målen</span><span class="sxs-lookup"><span data-stu-id="0b482-179">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="0b482-180">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="0b482-180">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="0b482-181">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0b482-181">What's new</span></span>](microsoft-secure-score-whats-new.md)
