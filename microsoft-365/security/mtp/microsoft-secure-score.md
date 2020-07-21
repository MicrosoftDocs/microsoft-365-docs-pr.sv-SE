---
title: Microsoft Secure Score
description: I artikeln beskrivs Microsoft Secure Score i säkerhetscentret Microsoft 365, hur du kan förbättra säkerhetspositionen och vad säkerhetsadministratörer kan förvänta sig.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
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
ms.openlocfilehash: 862a25eddda6048349df937641914377cb25874f
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200044"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="076dc-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="076dc-104">Microsoft Secure Score</span></span>

<span data-ttu-id="076dc-105">Microsoft Secure Score är ett mått på en organisations säkerhetsposition, med ett högre antal som anger fler förbättringsåtgärder som vidtas.</span><span class="sxs-lookup"><span data-stu-id="076dc-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="076dc-106">Den finns https://security.microsoft.com/securescore på i Microsoft [365 security center](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="076dc-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="076dc-107">Om du följer rekommendationerna för säker poäng kan du skydda din organisation från hot.</span><span class="sxs-lookup"><span data-stu-id="076dc-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="076dc-108">Från en centraliserad instrumentpanel i Microsoft 365-säkerhetscentret kan organisationer övervaka och arbeta med säkerheten för sina Microsoft 365-identiteter, data, appar, enheter och infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="076dc-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="076dc-109">Secure Score hjälper organisationer:</span><span class="sxs-lookup"><span data-stu-id="076dc-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="076dc-110">Rapport om det aktuella läget för organisationens säkerhetsposition.</span><span class="sxs-lookup"><span data-stu-id="076dc-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="076dc-111">Förbättra deras säkerhetsposition genom att tillhandahålla upptäckbarhet, synlighet, vägledning och kontroll.</span><span class="sxs-lookup"><span data-stu-id="076dc-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="076dc-112">Jämför med riktmärken och fastställ nyckeltal.</span><span class="sxs-lookup"><span data-stu-id="076dc-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="076dc-113">Organisationer får tillgång till robusta visualiseringar av mått och trender, integrering med andra Microsoft-produkter, poängjämlikhet med liknande organisationer och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="076dc-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="076dc-114">Poängen kan också återspegla när tredjepartslösningar har åtgärdat rekommenderade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="076dc-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Startsida för säkra poäng](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="076dc-116">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="076dc-116">How it works</span></span>

<span data-ttu-id="076dc-117">Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter eller åtgärda förbättringsåtgärden med ett program eller program från tredje part, eller en alternativ begränsning.</span><span class="sxs-lookup"><span data-stu-id="076dc-117">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="076dc-118">Vissa förbättringsåtgärder ger bara poäng när de är helt slutförda, och vissa ger partiella poäng om de slutförs för vissa enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="076dc-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="076dc-119">Om du inte kan eller inte vill anta någon av förbättringsåtgärderna kan du välja att acceptera risken eller den återstående risken.</span><span class="sxs-lookup"><span data-stu-id="076dc-119">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="076dc-120">Om du har en licens för en av microsoft-produkter som stöds visas rekommendationer för dessa produkter.</span><span class="sxs-lookup"><span data-stu-id="076dc-120">If you have a license for one of the supported Microsoft products, then you will see recommendations for those products.</span></span> <span data-ttu-id="076dc-121">Vi visar dig alla möjliga förbättringar för en produkt, oavsett licensutgåva, prenumeration eller abonnemang, så att du kan förstå bästa säkerhetspraxis och förbättra dina poäng.</span><span class="sxs-lookup"><span data-stu-id="076dc-121">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="076dc-122">Din absoluta säkerhetsposition representeras av Secure Score, som förblir densamma oavsett vilka licenser din organisation äger för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="076dc-122">Your absolute security posture is represented by Secure Score, which stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="076dc-123">Tänk på att säkerheten bör balanseras med användbarhet, och inte varje rekommendation kan fungera för din miljö.</span><span class="sxs-lookup"><span data-stu-id="076dc-123">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="076dc-124">Din poäng uppdateras i realtid för att återspegla den information som presenteras i visualiseringar och förbättring åtgärd sidor.</span><span class="sxs-lookup"><span data-stu-id="076dc-124">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="076dc-125">Secure Score synkroniserar också dagligen för att ta emot systemdata om dina uppnådda poäng för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="076dc-125">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="076dc-126">Viktiga scenarier</span><span class="sxs-lookup"><span data-stu-id="076dc-126">Key scenarios</span></span>

- [<span data-ttu-id="076dc-127">Kontrollera din aktuella poäng</span><span class="sxs-lookup"><span data-stu-id="076dc-127">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="076dc-128">Jämför dina poäng med organisationer som din</span><span class="sxs-lookup"><span data-stu-id="076dc-128">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="076dc-129">Visa förbättringsåtgärder och bestäm en handlingsplan</span><span class="sxs-lookup"><span data-stu-id="076dc-129">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="076dc-130">Initiera arbetsflöden för att undersöka eller implementera</span><span class="sxs-lookup"><span data-stu-id="076dc-130">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="076dc-131">Microsoft 365 säkerhetscenter och ServiceNow-integrering</span><span class="sxs-lookup"><span data-stu-id="076dc-131">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="076dc-132">Hur förbättringsåtgärder görs</span><span class="sxs-lookup"><span data-stu-id="076dc-132">How improvement actions are scored</span></span>

<span data-ttu-id="076dc-133">Varje förbättringsåtgärd är värd 10 poäng eller mindre.</span><span class="sxs-lookup"><span data-stu-id="076dc-133">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="076dc-134">De flesta görs på ett binärt sätt - om du genomför förbättringsåtgärden, som att skapa en ny princip eller aktivera en viss inställning, får du 100% av poängen.</span><span class="sxs-lookup"><span data-stu-id="076dc-134">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="076dc-135">För andra förbättringsåtgärder anges punkter som en procentandel av den totala konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="076dc-135">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="076dc-136">Till exempel, om förbättringen åtgärd stater du får 10 poäng genom att skydda alla dina användare med multifaktorautentisering och du bara har 50 av 100 totala användare skyddade, skulle du få en partiell poäng på 5 poäng (50 skyddade / 100 totalt \* 10 max poäng = 5 poäng partiell poäng).</span><span class="sxs-lookup"><span data-stu-id="076dc-136">For example, if the improvement action states you get 10 points by protecting all your users with multi-factor authentication and you only have 50 of 100 total users protected, you would be given a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="076dc-137">Produkter som ingår i Secure Score</span><span class="sxs-lookup"><span data-stu-id="076dc-137">Products included in Secure Score</span></span>

<span data-ttu-id="076dc-138">För närvarande finns det rekommendationer för Microsoft 365 (inklusive Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP och Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="076dc-138">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="076dc-139">Rekommendationer för andra säkerhetsprodukter kommer snart.</span><span class="sxs-lookup"><span data-stu-id="076dc-139">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="076dc-140">Rekommendationerna kommer inte att täcka alla angreppsytor som är associerade med varje produkt, men de är en bra baslinje.</span><span class="sxs-lookup"><span data-stu-id="076dc-140">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="076dc-141">Du kan också markera förbättringsåtgärderna som omfattas av en tredje part eller alternativ begränsning.</span><span class="sxs-lookup"><span data-stu-id="076dc-141">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="076dc-142">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="076dc-142">Security defaults</span></span>

<span data-ttu-id="076dc-143">Microsoft Secure Score har uppdaterade förbättringsåtgärder för att stödja [säkerhetsstandarder i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), vilket gör det enklare att skydda din organisation med förkonfigurerade säkerhetsinställningar för vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="076dc-143">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="076dc-144">Om du aktiverar standardvärden för säkerhet får du fullständiga poäng för följande förbättringsåtgärder:</span><span class="sxs-lookup"><span data-stu-id="076dc-144">If you turn on security defaults, you will be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="076dc-145">Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst (9 poäng)</span><span class="sxs-lookup"><span data-stu-id="076dc-145">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="076dc-146">Kräv MFA för administrativa roller (10 poäng)</span><span class="sxs-lookup"><span data-stu-id="076dc-146">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="076dc-147">Aktivera principen för att blockera äldre autentisering (7 poäng)</span><span class="sxs-lookup"><span data-stu-id="076dc-147">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="076dc-148">Standardinställningar för säkerhet omfattar säkerhetsfunktioner som ger liknande säkerhet som förbättringsåtgärderna för "inloggningsrisk" och "användarriskprincip".</span><span class="sxs-lookup"><span data-stu-id="076dc-148">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="076dc-149">I stället för att ställa in dessa principer ovanpå säkerhetsinställningarna rekommenderar vi att de uppdateras till "Löst genom alternativ begränsning".</span><span class="sxs-lookup"><span data-stu-id="076dc-149">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="076dc-150">Nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="076dc-150">Required permissions</span></span>

<span data-ttu-id="076dc-151">Om du vill ha behörighet att komma åt Microsoft Secure Score måste du tilldelas en av följande roller i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="076dc-151">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="076dc-152">Läs- och skrivroller</span><span class="sxs-lookup"><span data-stu-id="076dc-152">Read and write roles</span></span>

<span data-ttu-id="076dc-153">Med läs- och skrivåtkomst kan du göra ändringar och interagera direkt med Secure Score.</span><span class="sxs-lookup"><span data-stu-id="076dc-153">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="076dc-154">Du kan också tilldela skrivskyddad åtkomst till andra användare.</span><span class="sxs-lookup"><span data-stu-id="076dc-154">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="076dc-155">Global administratör</span><span class="sxs-lookup"><span data-stu-id="076dc-155">Global administrator</span></span>
* <span data-ttu-id="076dc-156">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="076dc-156">Security administrator</span></span>
* <span data-ttu-id="076dc-157">Exchange-administratör</span><span class="sxs-lookup"><span data-stu-id="076dc-157">Exchange administrator</span></span>
* <span data-ttu-id="076dc-158">SharePoint-administratör</span><span class="sxs-lookup"><span data-stu-id="076dc-158">SharePoint administrator</span></span>
* <span data-ttu-id="076dc-159">Kontoadministratör</span><span class="sxs-lookup"><span data-stu-id="076dc-159">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="076dc-160">Skrivskyddade roller</span><span class="sxs-lookup"><span data-stu-id="076dc-160">Read-only roles</span></span>

<span data-ttu-id="076dc-161">Med skrivskyddad åtkomst kan du inte redigera status eller anteckningar för en förbättringsåtgärd, redigera poängzoner eller redigera anpassade jämförelser.</span><span class="sxs-lookup"><span data-stu-id="076dc-161">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="076dc-162">Helpdesk-administratör</span><span class="sxs-lookup"><span data-stu-id="076dc-162">Helpdesk administrator</span></span>
* <span data-ttu-id="076dc-163">Användaradministratör</span><span class="sxs-lookup"><span data-stu-id="076dc-163">User administrator</span></span>
* <span data-ttu-id="076dc-164">Tjänstadministratör</span><span class="sxs-lookup"><span data-stu-id="076dc-164">Service administrator</span></span>
* <span data-ttu-id="076dc-165">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="076dc-165">Security reader</span></span>
* <span data-ttu-id="076dc-166">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="076dc-166">Security operator</span></span>
* <span data-ttu-id="076dc-167">Global läsare</span><span class="sxs-lookup"><span data-stu-id="076dc-167">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="076dc-168">Riskmedvetenhet</span><span class="sxs-lookup"><span data-stu-id="076dc-168">Risk awareness</span></span>

<span data-ttu-id="076dc-169">Microsoft Secure Score är en numerisk sammanfattning av din säkerhetsposition baserat på systemkonfigurationer, användarbeteende och andra säkerhetsrelaterade mätningar. Det är inte ett absolut mått på hur sannolikt ditt system eller data kommer att brytas.</span><span class="sxs-lookup"><span data-stu-id="076dc-169">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="076dc-170">Snarare är det i vilken utsträckning du har antagit säkerhetskontroller i din Microsoft-miljö som kan bidra till att kompensera risken för att brytas.</span><span class="sxs-lookup"><span data-stu-id="076dc-170">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="076dc-171">Ingen onlinetjänst är helt immun mot säkerhetsöverträdelser, och säker poäng bör inte tolkas som en garanti mot säkerhetsöverträdelse på något sätt.</span><span class="sxs-lookup"><span data-stu-id="076dc-171">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="076dc-172">Vi vill höra från dig</span><span class="sxs-lookup"><span data-stu-id="076dc-172">We want to hear from you</span></span>

<span data-ttu-id="076dc-173">Om du har några problem, vänligen meddela oss genom att publicera i [security, privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span><span class="sxs-lookup"><span data-stu-id="076dc-173">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="076dc-174">Vi övervakar samhället och kommer att ge hjälp.</span><span class="sxs-lookup"><span data-stu-id="076dc-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="076dc-175">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="076dc-175">Related resources</span></span>

- [<span data-ttu-id="076dc-176">Bedöm din säkerhetsposition</span><span class="sxs-lookup"><span data-stu-id="076dc-176">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="076dc-177">Spåra din Microsoft Secure Score-historik och uppnå mål</span><span class="sxs-lookup"><span data-stu-id="076dc-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="076dc-178">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="076dc-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="076dc-179">Nyheter</span><span class="sxs-lookup"><span data-stu-id="076dc-179">What's new</span></span>](microsoft-secure-score-whats-new.md)
