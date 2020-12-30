---
title: Microsoft Secure Score
description: Här beskrivs säker Poäng i Microsoft 365 Security Center, hur du förbättrar Posture och vilka säkerhets administratörer som kan förvänta dig.
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
ms.openlocfilehash: 6e9dd214e53e3fdd601fe51e5522a3a24a7fd3d0
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738005"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="c55c9-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="c55c9-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c55c9-105">Microsoft Secure score är ett mått på en organisations säkerhets Posture, med ett högre nummer som indikerar fler förbättrings åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c55c9-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="c55c9-106">Den finns https://security.microsoft.com/securescore i [säkerhets Center för Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="c55c9-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="c55c9-107">Genom att följa rekommendationerna för säker Poäng kan du skydda din organisation mot hot.</span><span class="sxs-lookup"><span data-stu-id="c55c9-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="c55c9-108">Från en central instrument panel i Microsoft 365 Security Center kan organisationer övervaka och arbeta med säkerheten hos sina Microsoft 365-identiteter, appar och enheter.</span><span class="sxs-lookup"><span data-stu-id="c55c9-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="c55c9-109">Säkra poäng gör att organisationer:</span><span class="sxs-lookup"><span data-stu-id="c55c9-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="c55c9-110">Rapportera om organisationens säkerhets Posture.</span><span class="sxs-lookup"><span data-stu-id="c55c9-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="c55c9-111">Förbättra deras säkerhets Posture genom att tillhandahålla upptäckter, synlighet, vägledning och kontroll.</span><span class="sxs-lookup"><span data-stu-id="c55c9-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="c55c9-112">Jämför med benchmarks och skapa KPI: er (Key Performance Indicators).</span><span class="sxs-lookup"><span data-stu-id="c55c9-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="c55c9-113">Organisationer får till gång till stabila visualiseringar av mått och trender, integrering med andra Microsoft-produkter, resultat jämförelse med liknande organisationer och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="c55c9-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="c55c9-114">Poängen kan också återspegla när lösningar från tredje part har åtgärdat rekommenderade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c55c9-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Säkra Poäng start sidan](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="c55c9-116">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="c55c9-116">How it works</span></span>

<span data-ttu-id="c55c9-117">Du får poäng för följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="c55c9-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="c55c9-118">Konfigurera rekommenderade säkerhetsfunktioner</span><span class="sxs-lookup"><span data-stu-id="c55c9-118">Configuring recommended security features</span></span>
- <span data-ttu-id="c55c9-119">Utföra säkerhetsrelaterade uppgifter</span><span class="sxs-lookup"><span data-stu-id="c55c9-119">Doing security-related tasks</span></span>
- <span data-ttu-id="c55c9-120">Adressera förbättrings åtgärden med ett program eller program från tredje part, eller en alternativ minskning</span><span class="sxs-lookup"><span data-stu-id="c55c9-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="c55c9-121">Vissa förbättrings åtgärder ger bara poäng när det är fullständigt ifyllt.</span><span class="sxs-lookup"><span data-stu-id="c55c9-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="c55c9-122">Vissa delar ger ofullständiga punkter om de är klara för vissa enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="c55c9-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="c55c9-123">Om du inte kan eller inte vill använda en av förbättrings åtgärderna kan du välja att acceptera risken eller återstående risk.</span><span class="sxs-lookup"><span data-stu-id="c55c9-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="c55c9-124">Om du har en licens för en av de Microsoft-produkter som stöds, ser du rekommendationer för dessa produkter.</span><span class="sxs-lookup"><span data-stu-id="c55c9-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="c55c9-125">Vi visar alla möjliga förbättringar för en produkt, oavsett om det gäller licens, abonnemang eller abonnemang.</span><span class="sxs-lookup"><span data-stu-id="c55c9-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="c55c9-126">På så sätt förstår du säkerhets rekommendationer och förbättrar poängen.</span><span class="sxs-lookup"><span data-stu-id="c55c9-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="c55c9-127">Dina absoluta säkerhets Posture, som representeras av säkra poäng, förblir desamma, oavsett vilka licenser organisationen äger för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="c55c9-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="c55c9-128">Tänk på att säkerheten bör balanseras med användbarhet och inte varje rekommendation kan fungera för din miljö.</span><span class="sxs-lookup"><span data-stu-id="c55c9-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="c55c9-129">Resultatet uppdateras i real tid för att visa informationen som visas i åtgärds sidorna visualiseringar och förbättring.</span><span class="sxs-lookup"><span data-stu-id="c55c9-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="c55c9-130">Säkra Poäng synkroniserar också varje dag med att ta emot system data om dina erhållna Poäng för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c55c9-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="c55c9-131">Viktiga scenarier</span><span class="sxs-lookup"><span data-stu-id="c55c9-131">Key scenarios</span></span>

- [<span data-ttu-id="c55c9-132">Kontrol lera aktuell Poäng</span><span class="sxs-lookup"><span data-stu-id="c55c9-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="c55c9-133">Jämför poängen med dina organisationer som dina</span><span class="sxs-lookup"><span data-stu-id="c55c9-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="c55c9-134">Visa förbättrings åtgärder och bestäm ett åtgärds abonnemang</span><span class="sxs-lookup"><span data-stu-id="c55c9-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="c55c9-135">Initiera och implementera arbets flöden</span><span class="sxs-lookup"><span data-stu-id="c55c9-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="c55c9-136">Hur förbättrings åtgärder betygs ätts</span><span class="sxs-lookup"><span data-stu-id="c55c9-136">How improvement actions are scored</span></span>

<span data-ttu-id="c55c9-137">Varje förbättrings åtgärd är värt 10 Poäng eller mindre och de flesta är på ett binärt sätt.</span><span class="sxs-lookup"><span data-stu-id="c55c9-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="c55c9-138">Om du implementerar förbättrings åtgärden, till exempel skapa en ny princip eller aktiverar en specifik inställning, får du 100% av punkterna.</span><span class="sxs-lookup"><span data-stu-id="c55c9-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="c55c9-139">För andra förbättrings åtgärder anges Poäng som en procent andel av den totala konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="c55c9-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="c55c9-140">En förbättrings åtgärd visar till exempel 10 Poäng genom att skydda alla användare med multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="c55c9-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="c55c9-141">Du har bara 50 av 100 totalt antal användare som är skyddade, så du får lite poäng med 5 Poäng (50 skyddat/100 totalt \* 10 Max punkter = 5 punkter).</span><span class="sxs-lookup"><span data-stu-id="c55c9-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="c55c9-142">Produkter ingår i säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="c55c9-142">Products included in Secure Score</span></span>

<span data-ttu-id="c55c9-143">För närvarande finns det rekommendationer för följande produkter:</span><span class="sxs-lookup"><span data-stu-id="c55c9-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="c55c9-144">Microsoft 365 (inklusive Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="c55c9-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="c55c9-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c55c9-145">Azure Active Directory</span></span>
- <span data-ttu-id="c55c9-146">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c55c9-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="c55c9-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c55c9-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="c55c9-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c55c9-148">Cloud App Security</span></span>

<span data-ttu-id="c55c9-149">Rekommendationer för andra säkerhets produkter kommer snart.</span><span class="sxs-lookup"><span data-stu-id="c55c9-149">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="c55c9-150">Rekommendationerna täcker inte alla de attack ytor som är associerade med varje produkt, men de är en bra original plan.</span><span class="sxs-lookup"><span data-stu-id="c55c9-150">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="c55c9-151">Du kan också markera förbättrings åtgärderna som täcks av tredje part eller annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c55c9-151">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="c55c9-152">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="c55c9-152">Security defaults</span></span>

<span data-ttu-id="c55c9-153">Microsofts säkra poäng har uppdaterat förbättrings åtgärder för att hantera [säkerhets standarder i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), vilket gör det enklare att skydda din organisation med förkonfigurerade säkerhets inställningar för vanliga angrepp.</span><span class="sxs-lookup"><span data-stu-id="c55c9-153">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="c55c9-154">Om du aktiverar säkerhets inställningar får du fullständiga Points för följande förbättringar:</span><span class="sxs-lookup"><span data-stu-id="c55c9-154">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="c55c9-155">Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst (9 Poäng)</span><span class="sxs-lookup"><span data-stu-id="c55c9-155">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="c55c9-156">Kräv MFA för administrativa roller (10 Poäng)</span><span class="sxs-lookup"><span data-stu-id="c55c9-156">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="c55c9-157">Aktivera princip för blockering av bakåtkompatibel-inloggningsautentisering (7 Poäng)</span><span class="sxs-lookup"><span data-stu-id="c55c9-157">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="c55c9-158">Säkerhets standarder inkluderar säkerhetsfunktioner som ger liknande säkerhet i avsnittet "policy för inloggnings risker" och "förbättring av användar risk policy".</span><span class="sxs-lookup"><span data-stu-id="c55c9-158">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="c55c9-159">I stället för att konfigurera dessa principer ovanpå säkerhets standardinställningarna rekommenderar vi att du uppdaterar deras status till "löst via annan begränsning".</span><span class="sxs-lookup"><span data-stu-id="c55c9-159">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="c55c9-160">Nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="c55c9-160">Required permissions</span></span>

<span data-ttu-id="c55c9-161">För att få åtkomst till Microsoft Secure score måste du ha en av följande roller i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c55c9-161">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="c55c9-162">Läsa och skriva roller</span><span class="sxs-lookup"><span data-stu-id="c55c9-162">Read and write roles</span></span>

<span data-ttu-id="c55c9-163">Med Läs-och skriv åtkomst kan du göra ändringar och direkt interagera med säkra poäng.</span><span class="sxs-lookup"><span data-stu-id="c55c9-163">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="c55c9-164">Du kan också tilldela skrivskyddad åtkomst till andra användare.</span><span class="sxs-lookup"><span data-stu-id="c55c9-164">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="c55c9-165">Global administratör</span><span class="sxs-lookup"><span data-stu-id="c55c9-165">Global administrator</span></span>
* <span data-ttu-id="c55c9-166">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="c55c9-166">Security administrator</span></span>
* <span data-ttu-id="c55c9-167">Exchange-administratör</span><span class="sxs-lookup"><span data-stu-id="c55c9-167">Exchange administrator</span></span>
* <span data-ttu-id="c55c9-168">SharePoint-administratör</span><span class="sxs-lookup"><span data-stu-id="c55c9-168">SharePoint administrator</span></span>
* <span data-ttu-id="c55c9-169">Konto administratör</span><span class="sxs-lookup"><span data-stu-id="c55c9-169">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="c55c9-170">Skrivskyddade roller</span><span class="sxs-lookup"><span data-stu-id="c55c9-170">Read-only roles</span></span>

<span data-ttu-id="c55c9-171">Med skrivskyddad åtkomst kan du inte redigera status eller anteckningar för en förbättrings åtgärd, redigera Poäng zoner eller redigera anpassade jämförelser.</span><span class="sxs-lookup"><span data-stu-id="c55c9-171">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="c55c9-172">Helpdesk-administratör</span><span class="sxs-lookup"><span data-stu-id="c55c9-172">Helpdesk administrator</span></span>
* <span data-ttu-id="c55c9-173">Användaradministratör</span><span class="sxs-lookup"><span data-stu-id="c55c9-173">User administrator</span></span>
* <span data-ttu-id="c55c9-174">Tjänst administratör</span><span class="sxs-lookup"><span data-stu-id="c55c9-174">Service administrator</span></span>
* <span data-ttu-id="c55c9-175">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="c55c9-175">Security reader</span></span>
* <span data-ttu-id="c55c9-176">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="c55c9-176">Security operator</span></span>
* <span data-ttu-id="c55c9-177">Global läsare</span><span class="sxs-lookup"><span data-stu-id="c55c9-177">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="c55c9-178">Risk medvetenhet</span><span class="sxs-lookup"><span data-stu-id="c55c9-178">Risk awareness</span></span>

<span data-ttu-id="c55c9-179">Microsofts säkra poäng är en numerisk Sammanfattning av dina säkerhets Posture, baserat på systemkonfigurationer, användar beteende och andra säkerhetsrelaterade mått.</span><span class="sxs-lookup"><span data-stu-id="c55c9-179">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="c55c9-180">Det är inte ett absolut mått på hur troligt det är att systemet eller data blir.</span><span class="sxs-lookup"><span data-stu-id="c55c9-180">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="c55c9-181">I stället representerar den utsträckning som du har antagit säkerhets kontroller i din Microsoft-miljö som kan hjälpa till att undanröja risken att bli intrång.</span><span class="sxs-lookup"><span data-stu-id="c55c9-181">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="c55c9-182">Ingen online tjänst är immun mot säkerhets brott och säkra Poäng bör inte tolkas som en garanti mot säkerhets brott på något sätt.</span><span class="sxs-lookup"><span data-stu-id="c55c9-182">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="c55c9-183">Vi vill höra från dig</span><span class="sxs-lookup"><span data-stu-id="c55c9-183">We want to hear from you</span></span>

<span data-ttu-id="c55c9-184">Om du har några problem kan du meddela oss genom att publicera det i [säkerhets-, integritets &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span><span class="sxs-lookup"><span data-stu-id="c55c9-184">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="c55c9-185">Vi övervakar communityn och ger hjälp.</span><span class="sxs-lookup"><span data-stu-id="c55c9-185">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="c55c9-186">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="c55c9-186">Related resources</span></span>

- [<span data-ttu-id="c55c9-187">Utvärdera säkerhets genom övergå molnet</span><span class="sxs-lookup"><span data-stu-id="c55c9-187">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="c55c9-188">Spåra din Microsoft säkra Poäng historik och uppfylla målen</span><span class="sxs-lookup"><span data-stu-id="c55c9-188">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="c55c9-189">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="c55c9-189">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="c55c9-190">Nyheter</span><span class="sxs-lookup"><span data-stu-id="c55c9-190">What's new</span></span>](microsoft-secure-score-whats-new.md)
