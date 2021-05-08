---
title: Microsoft Secure Score
description: Här beskrivs Microsoft Secure Score Microsoft 365 säkerhetscenter, hur du kan förbättra säkerheten och vilka säkerhetsadministratörer kan förvänta sig.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 4a2c220cab15751671b9b38c3bb2fda3db12c9e1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245383"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="adaa5-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="adaa5-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="adaa5-105">Microsoft Secure Score är ett mått på en organisations säkerhetssäkerhet, med ett högre tal som anger fler förbättringsåtgärder som vidtas.</span><span class="sxs-lookup"><span data-stu-id="adaa5-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="adaa5-106">Den finns på Microsoft 365 https://security.microsoft.com/securescore [Säkerhetscenter.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="adaa5-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="adaa5-107">Om du följer rekommendationerna för Secure Score kan du skydda organisationen från hot.</span><span class="sxs-lookup"><span data-stu-id="adaa5-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="adaa5-108">Från en centraliserad instrumentpanel i Microsoft 365 säkerhetscenter kan organisationer övervaka och arbeta med säkerheten för sina Microsoft 365 identiteter, appar och enheter.</span><span class="sxs-lookup"><span data-stu-id="adaa5-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="adaa5-109">Secure Score hjälper organisationer att:</span><span class="sxs-lookup"><span data-stu-id="adaa5-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="adaa5-110">Rapport om den aktuella statusen för organisationens säkerhetsstatus.</span><span class="sxs-lookup"><span data-stu-id="adaa5-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="adaa5-111">Förbättra säkerheten genom att tillhandahålla förutsägbarhet, synlighet, vägledning och kontroll.</span><span class="sxs-lookup"><span data-stu-id="adaa5-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="adaa5-112">Jämför med riktvärden och skapa KPI:er (Key Performance Indicators).</span><span class="sxs-lookup"><span data-stu-id="adaa5-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="adaa5-113">Organisationer får tillgång till robusta visualiseringar av mätvärden och trender, integrering med andra Microsoft-produkter, resultatjämförelse med liknande organisationer och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="adaa5-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="adaa5-114">Poängen kan också återspegla när lösningar från tredje part har åtgärdat rekommenderade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="adaa5-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Startsida för Secure Score](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a><span data-ttu-id="adaa5-116">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="adaa5-116">How it works</span></span>

<span data-ttu-id="adaa5-117">Du får poäng för följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="adaa5-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="adaa5-118">Konfigurera rekommenderade säkerhetsfunktioner</span><span class="sxs-lookup"><span data-stu-id="adaa5-118">Configuring recommended security features</span></span>
- <span data-ttu-id="adaa5-119">Utföra säkerhetsrelaterade uppgifter</span><span class="sxs-lookup"><span data-stu-id="adaa5-119">Doing security-related tasks</span></span>
- <span data-ttu-id="adaa5-120">Åtgärda förbättringsåtgärden i ett program eller en programvara från tredje part, eller en alternativ minskning</span><span class="sxs-lookup"><span data-stu-id="adaa5-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="adaa5-121">Vissa förbättringsåtgärder ger endast poäng när de är slutförda.</span><span class="sxs-lookup"><span data-stu-id="adaa5-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="adaa5-122">Vissa ger delpunkter om de är slutförda för vissa enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="adaa5-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="adaa5-123">Om du inte kan eller inte vill utföra någon av förbättringsåtgärderna kan du välja att acceptera risken eller återstående risk.</span><span class="sxs-lookup"><span data-stu-id="adaa5-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="adaa5-124">Om du har en licens för någon av De Microsoft-produkter som stöds visas rekommendationer för dessa produkter.</span><span class="sxs-lookup"><span data-stu-id="adaa5-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="adaa5-125">Vi visar dig alla tänkbara förbättringar för en produkt, oavsett licensversion, prenumeration eller abonnemang.</span><span class="sxs-lookup"><span data-stu-id="adaa5-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="adaa5-126">På så sätt kan du förstå metodtips för säkerhet och förbättra ditt resultat.</span><span class="sxs-lookup"><span data-stu-id="adaa5-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="adaa5-127">Din absolut säkerhet som representeras av Secure Score förblir densamma oavsett vilka licenser din organisation äger för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="adaa5-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="adaa5-128">Kom ihåg att säkerheten bör balanseras med användbarheten, och alla rekommendationer kan inte fungera för din miljö.</span><span class="sxs-lookup"><span data-stu-id="adaa5-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="adaa5-129">Poängen uppdateras i realtid för att återspegla informationen som presenteras på visualiserings- och förbättringsåtgärdssidorna.</span><span class="sxs-lookup"><span data-stu-id="adaa5-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="adaa5-130">Secure Score synkroniseras också dagligen för att ta emot systemdata om dina uppnåde poäng för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="adaa5-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="adaa5-131">Viktiga scenarier</span><span class="sxs-lookup"><span data-stu-id="adaa5-131">Key scenarios</span></span>

- [<span data-ttu-id="adaa5-132">Kontrollera ditt aktuella poängresultat</span><span class="sxs-lookup"><span data-stu-id="adaa5-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="adaa5-133">Jämför poäng med organisationer som ditt</span><span class="sxs-lookup"><span data-stu-id="adaa5-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="adaa5-134">Visa förbättringsåtgärder och bestäm en handlingsplan</span><span class="sxs-lookup"><span data-stu-id="adaa5-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="adaa5-135">Initiera arbetsflöden att undersöka eller implementera</span><span class="sxs-lookup"><span data-stu-id="adaa5-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="adaa5-136">Så här poängas förbättringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="adaa5-136">How improvement actions are scored</span></span>

<span data-ttu-id="adaa5-137">Varje förbättringsåtgärd är värd 10 punkter eller mindre och de flesta poängs på binärt sätt.</span><span class="sxs-lookup"><span data-stu-id="adaa5-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="adaa5-138">Om du implementerar förbättringsåtgärden, till exempel skapar en ny princip eller aktiverar en viss inställning, får du 100 % av punkterna.</span><span class="sxs-lookup"><span data-stu-id="adaa5-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="adaa5-139">För andra förbättringsåtgärder anges punkter som procent av den totala konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="adaa5-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="adaa5-140">En förbättringsåtgärd ger dig till exempel 10 poäng genom att skydda alla användare med multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="adaa5-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="adaa5-141">Du har bara 50 av 100 totala användare skyddade, så du får en partiell poäng på 5 poäng (50 skyddade / 100 totalt \* 10 max pts = 5 pts).</span><span class="sxs-lookup"><span data-stu-id="adaa5-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="adaa5-142">Produkter som ingår i Secure Score</span><span class="sxs-lookup"><span data-stu-id="adaa5-142">Products included in Secure Score</span></span>

<span data-ttu-id="adaa5-143">Det finns för närvarande rekommendationer för följande produkter:</span><span class="sxs-lookup"><span data-stu-id="adaa5-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="adaa5-144">Microsoft 365 (inklusive Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="adaa5-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="adaa5-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="adaa5-145">Azure Active Directory</span></span>
- <span data-ttu-id="adaa5-146">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="adaa5-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="adaa5-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="adaa5-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="adaa5-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="adaa5-148">Cloud App Security</span></span>
- <span data-ttu-id="adaa5-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="adaa5-149">Microsoft Teams</span></span>

<span data-ttu-id="adaa5-150">Rekommendationer för andra säkerhetsprodukter kommer snart.</span><span class="sxs-lookup"><span data-stu-id="adaa5-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="adaa5-151">Rekommendationerna täcker inte alla attackytor som är kopplade till varje produkt, men de är en bra baslinje.</span><span class="sxs-lookup"><span data-stu-id="adaa5-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="adaa5-152">Du kan också markera de förbättringsåtgärder som omfattas av en tredje part eller en alternativ minskning.</span><span class="sxs-lookup"><span data-stu-id="adaa5-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="adaa5-153">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="adaa5-153">Security defaults</span></span>

<span data-ttu-id="adaa5-154">Microsoft Secure Score har uppdaterat förbättringsåtgärder för att stödja säkerhetsstandarder i [Azure Active Directory,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)vilket gör det enklare att skydda organisationen med förkonfigurerade säkerhetsinställningar för vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="adaa5-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="adaa5-155">Om du aktiverar säkerhetsstandardvärden tilldelas du fullständiga poäng för följande förbättringsåtgärder:</span><span class="sxs-lookup"><span data-stu-id="adaa5-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="adaa5-156">Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst (9 punkter)</span><span class="sxs-lookup"><span data-stu-id="adaa5-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="adaa5-157">Kräv MFA för administrativa roller (10 poäng)</span><span class="sxs-lookup"><span data-stu-id="adaa5-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="adaa5-158">Aktivera princip för att blockera äldre autentisering (7 punkter)</span><span class="sxs-lookup"><span data-stu-id="adaa5-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="adaa5-159">Säkerhetsstandarder omfattar säkerhetsfunktioner som ger liknande säkerhet som förbättringsåtgärderna "inloggningsriskpolicy" och "användarriskpolicy".</span><span class="sxs-lookup"><span data-stu-id="adaa5-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="adaa5-160">I stället för att konfigurera dessa principer ovanpå säkerhetsstandardvärdena rekommenderar vi att du uppdaterar deras status till "Löst genom alternativ minskning".</span><span class="sxs-lookup"><span data-stu-id="adaa5-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="adaa5-161">Behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="adaa5-161">Required permissions</span></span>

<span data-ttu-id="adaa5-162">För att ha behörighet att komma åt Microsoft Secure Score måste du tilldelas en av följande roller i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="adaa5-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="adaa5-163">Läs- och skrivroller</span><span class="sxs-lookup"><span data-stu-id="adaa5-163">Read and write roles</span></span>

<span data-ttu-id="adaa5-164">Med läs- och skrivåtkomst kan du göra ändringar och interagera direkt med Secure Score.</span><span class="sxs-lookup"><span data-stu-id="adaa5-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="adaa5-165">Du kan också tilldela skrivskyddsåtkomst till andra användare.</span><span class="sxs-lookup"><span data-stu-id="adaa5-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="adaa5-166">Global administratör</span><span class="sxs-lookup"><span data-stu-id="adaa5-166">Global administrator</span></span>
* <span data-ttu-id="adaa5-167">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="adaa5-167">Security administrator</span></span>
* <span data-ttu-id="adaa5-168">Exchange-administratör</span><span class="sxs-lookup"><span data-stu-id="adaa5-168">Exchange administrator</span></span>
* <span data-ttu-id="adaa5-169">SharePoint-administratör</span><span class="sxs-lookup"><span data-stu-id="adaa5-169">SharePoint administrator</span></span>
* <span data-ttu-id="adaa5-170">Kontoadministratör</span><span class="sxs-lookup"><span data-stu-id="adaa5-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="adaa5-171">Skrivskyddade roller</span><span class="sxs-lookup"><span data-stu-id="adaa5-171">Read-only roles</span></span>

<span data-ttu-id="adaa5-172">Med skrivskydd kan du inte redigera status eller anteckningar för en förbättringsåtgärd, redigera poängzoner eller redigera anpassade jämförelser.</span><span class="sxs-lookup"><span data-stu-id="adaa5-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="adaa5-173">Helpdesk-administratör</span><span class="sxs-lookup"><span data-stu-id="adaa5-173">Helpdesk administrator</span></span>
* <span data-ttu-id="adaa5-174">Användaradministratör</span><span class="sxs-lookup"><span data-stu-id="adaa5-174">User administrator</span></span>
* <span data-ttu-id="adaa5-175">Tjänstadministratör</span><span class="sxs-lookup"><span data-stu-id="adaa5-175">Service administrator</span></span>
* <span data-ttu-id="adaa5-176">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="adaa5-176">Security reader</span></span>
* <span data-ttu-id="adaa5-177">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="adaa5-177">Security operator</span></span>
* <span data-ttu-id="adaa5-178">Global läsare</span><span class="sxs-lookup"><span data-stu-id="adaa5-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="adaa5-179">Riskmedvetande</span><span class="sxs-lookup"><span data-stu-id="adaa5-179">Risk awareness</span></span>

<span data-ttu-id="adaa5-180">Microsoft Secure Score är en numerisk sammanfattning av din säkerhetskonfiguration baserad på systemkonfigurationer, användarbeteende och andra säkerhetsrelaterade mått.</span><span class="sxs-lookup"><span data-stu-id="adaa5-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="adaa5-181">Det är inte ett absolut mått på hur troligt det är att ditt system eller dina data bryts.</span><span class="sxs-lookup"><span data-stu-id="adaa5-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="adaa5-182">Den representerar i stället den utsträckning som du har infört säkerhetskontroller i din Microsoft-miljö som kan hjälpa till att uppväga risken för intrång.</span><span class="sxs-lookup"><span data-stu-id="adaa5-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="adaa5-183">Ingen onlinetjänst är en del av säkerhetsbrister och säkra poäng ska inte tolkas som en garanti för säkerhetsbrister på något sätt.</span><span class="sxs-lookup"><span data-stu-id="adaa5-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="adaa5-184">Vi vill höra från dig</span><span class="sxs-lookup"><span data-stu-id="adaa5-184">We want to hear from you</span></span>

<span data-ttu-id="adaa5-185">Om du har problem kan du meddela oss genom att publicera i communityn [säkerhet, & sekretess och](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="adaa5-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="adaa5-186">Vi övervakar communityn och kommer att hjälpa dig.</span><span class="sxs-lookup"><span data-stu-id="adaa5-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="adaa5-187">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="adaa5-187">Related resources</span></span>

- [<span data-ttu-id="adaa5-188">Utvärdera din säkerhetsstatus</span><span class="sxs-lookup"><span data-stu-id="adaa5-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="adaa5-189">Spåra din Microsoft Secure Score-historik och nå dina mål</span><span class="sxs-lookup"><span data-stu-id="adaa5-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="adaa5-190">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="adaa5-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="adaa5-191">Vad är det senaste</span><span class="sxs-lookup"><span data-stu-id="adaa5-191">What's new</span></span>](microsoft-secure-score-whats-new.md)