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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094804"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="ee08b-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="ee08b-104">Microsoft Secure Score</span></span>

<span data-ttu-id="ee08b-105">Microsoft Secure Score är ett mått på en organisations säkerhetsposition, med ett högre antal som anger fler förbättringsåtgärder som vidtas.</span><span class="sxs-lookup"><span data-stu-id="ee08b-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="ee08b-106">Den finns https://security.microsoft.com/securescore på i Microsoft [365 security center](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="ee08b-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="ee08b-107">Om du följer rekommendationerna för säker poäng kan du skydda din organisation från hot.</span><span class="sxs-lookup"><span data-stu-id="ee08b-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="ee08b-108">Från en centraliserad instrumentpanel i Microsoft 365-säkerhetscentret kan organisationer övervaka och arbeta med säkerheten för sina Microsoft 365-identiteter, data, appar, enheter och infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="ee08b-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="ee08b-109">Secure Score hjälper organisationer:</span><span class="sxs-lookup"><span data-stu-id="ee08b-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="ee08b-110">Rapport om det aktuella läget för organisationens säkerhetsposition.</span><span class="sxs-lookup"><span data-stu-id="ee08b-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="ee08b-111">Förbättra deras säkerhetsposition genom att tillhandahålla upptäckbarhet, synlighet, vägledning och kontroll.</span><span class="sxs-lookup"><span data-stu-id="ee08b-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="ee08b-112">Jämför med riktmärken och fastställ nyckeltal.</span><span class="sxs-lookup"><span data-stu-id="ee08b-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="ee08b-113">Organisationer får tillgång till robusta visualiseringar av mått och trender, integrering med andra Microsoft-produkter, poängjämlikhet med liknande organisationer och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="ee08b-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="ee08b-114">Poängen kan också återspegla när tredjepartslösningar har åtgärdat rekommenderade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ee08b-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Startsida för säkra poäng](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="ee08b-116">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="ee08b-116">How it works</span></span>

<span data-ttu-id="ee08b-117">Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter eller åtgärda förbättringsåtgärden med ett program eller program från tredje part, eller en alternativ begränsning.</span><span class="sxs-lookup"><span data-stu-id="ee08b-117">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="ee08b-118">Vissa förbättringsåtgärder ger bara poäng när de är helt slutförda, och vissa ger partiella poäng om de slutförs för vissa enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="ee08b-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="ee08b-119">Om du inte kan eller inte vill anta någon av förbättringsåtgärderna kan du välja att acceptera risken eller den återstående risken.</span><span class="sxs-lookup"><span data-stu-id="ee08b-119">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="ee08b-120">Vi visar dig alla möjliga förbättringar, oavsett licens, så att du kan förstå bästa praxis för säkerhet och förbättra dina poäng.</span><span class="sxs-lookup"><span data-stu-id="ee08b-120">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="ee08b-121">Din absoluta säkerhetsposition representeras av Secure Score, som förblir densamma oavsett vilka produktlicenser din organisation äger.</span><span class="sxs-lookup"><span data-stu-id="ee08b-121">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="ee08b-122">Tänk på att säkerheten bör balanseras med användbarhet, och inte varje rekommendation kan fungera för din miljö.</span><span class="sxs-lookup"><span data-stu-id="ee08b-122">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="ee08b-123">Din poäng uppdateras i realtid för att återspegla den information som presenteras i visualiseringar och förbättring åtgärd sidor.</span><span class="sxs-lookup"><span data-stu-id="ee08b-123">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="ee08b-124">Secure Score synkroniserar också dagligen för att ta emot systemdata om dina uppnådda poäng för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="ee08b-124">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="ee08b-125">Viktiga scenarier</span><span class="sxs-lookup"><span data-stu-id="ee08b-125">Key scenarios</span></span>

- [<span data-ttu-id="ee08b-126">Kontrollera din aktuella poäng</span><span class="sxs-lookup"><span data-stu-id="ee08b-126">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="ee08b-127">Jämför dina poäng med organisationer som din</span><span class="sxs-lookup"><span data-stu-id="ee08b-127">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="ee08b-128">Visa förbättringsåtgärder och bestäm en handlingsplan</span><span class="sxs-lookup"><span data-stu-id="ee08b-128">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="ee08b-129">Initiera arbetsflöden för att undersöka eller implementera</span><span class="sxs-lookup"><span data-stu-id="ee08b-129">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="ee08b-130">Microsoft 365 säkerhetscenter och ServiceNow-integrering</span><span class="sxs-lookup"><span data-stu-id="ee08b-130">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="ee08b-131">Hur förbättringsåtgärder görs</span><span class="sxs-lookup"><span data-stu-id="ee08b-131">How improvement actions are scored</span></span>

<span data-ttu-id="ee08b-132">Varje förbättringsåtgärd är värd 10 poäng eller mindre.</span><span class="sxs-lookup"><span data-stu-id="ee08b-132">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="ee08b-133">De flesta görs på ett binärt sätt - om du genomför förbättringsåtgärden, som att skapa en ny princip eller aktivera en viss inställning, får du 100% av poängen.</span><span class="sxs-lookup"><span data-stu-id="ee08b-133">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="ee08b-134">För andra förbättringsåtgärder anges punkter som en procentandel av den totala konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ee08b-134">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="ee08b-135">Till exempel, om förbättringen åtgärd stater du får 10 poäng genom att skydda alla dina användare med multifaktorautentisering och du bara har 50 av 100 totala användare skyddade, skulle du få en partiell poäng på 5 poäng (50 skyddade / 100 totalt \* 10 max poäng = 5 poäng partiell poäng).</span><span class="sxs-lookup"><span data-stu-id="ee08b-135">For example, if the improvement action states you get 10 points by protecting all your users with multi-factor authentication and you only have 50 of 100 total users protected, you would be given a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="ee08b-136">Produkter som ingår i Secure Score</span><span class="sxs-lookup"><span data-stu-id="ee08b-136">Products included in Secure Score</span></span>

<span data-ttu-id="ee08b-137">För närvarande finns det rekommendationer för Microsoft 365 (inklusive Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP och Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="ee08b-137">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="ee08b-138">Rekommendationer för andra säkerhetsprodukter kommer snart.</span><span class="sxs-lookup"><span data-stu-id="ee08b-138">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="ee08b-139">Rekommendationerna kommer inte att täcka alla angreppsytor som är associerade med varje produkt, men de är en bra baslinje.</span><span class="sxs-lookup"><span data-stu-id="ee08b-139">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="ee08b-140">Du kan också markera förbättringsåtgärderna som omfattas av en tredje part eller alternativ begränsning.</span><span class="sxs-lookup"><span data-stu-id="ee08b-140">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="ee08b-141">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="ee08b-141">Security defaults</span></span>

<span data-ttu-id="ee08b-142">Microsoft Secure Score har uppdaterade förbättringsåtgärder för att stödja [säkerhetsstandarder i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), vilket gör det enklare att skydda din organisation med förkonfigurerade säkerhetsinställningar för vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="ee08b-142">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="ee08b-143">Om du aktiverar standardvärden för säkerhet får du fullständiga poäng för följande förbättringsåtgärder:</span><span class="sxs-lookup"><span data-stu-id="ee08b-143">If you turn on security defaults, you will be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="ee08b-144">Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst (9 poäng)</span><span class="sxs-lookup"><span data-stu-id="ee08b-144">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="ee08b-145">Kräv MFA för administrativa roller (10 poäng)</span><span class="sxs-lookup"><span data-stu-id="ee08b-145">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="ee08b-146">Aktivera principen för att blockera äldre autentisering (7 poäng)</span><span class="sxs-lookup"><span data-stu-id="ee08b-146">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="ee08b-147">Standardinställningar för säkerhet omfattar säkerhetsfunktioner som ger liknande säkerhet som förbättringsåtgärderna för "inloggningsrisk" och "användarriskprincip".</span><span class="sxs-lookup"><span data-stu-id="ee08b-147">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="ee08b-148">I stället för att ställa in dessa principer ovanpå säkerhetsinställningarna rekommenderar vi att de uppdateras till "Löst genom alternativ begränsning".</span><span class="sxs-lookup"><span data-stu-id="ee08b-148">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="ee08b-149">Nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="ee08b-149">Required permissions</span></span>

<span data-ttu-id="ee08b-150">Om du vill ha behörighet att komma åt Microsoft Secure Score måste du tilldelas en av följande roller i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ee08b-150">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="ee08b-151">Läs- och skrivroller</span><span class="sxs-lookup"><span data-stu-id="ee08b-151">Read and write roles</span></span>

<span data-ttu-id="ee08b-152">Med läs- och skrivåtkomst kan du göra ändringar och interagera direkt med Secure Score.</span><span class="sxs-lookup"><span data-stu-id="ee08b-152">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="ee08b-153">Du kan också tilldela skrivskyddad åtkomst till andra användare.</span><span class="sxs-lookup"><span data-stu-id="ee08b-153">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="ee08b-154">Global administratör</span><span class="sxs-lookup"><span data-stu-id="ee08b-154">Global administrator</span></span>
* <span data-ttu-id="ee08b-155">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="ee08b-155">Security administrator</span></span>
* <span data-ttu-id="ee08b-156">Exchange-administratör</span><span class="sxs-lookup"><span data-stu-id="ee08b-156">Exchange administrator</span></span>
* <span data-ttu-id="ee08b-157">SharePoint-administratör</span><span class="sxs-lookup"><span data-stu-id="ee08b-157">SharePoint administrator</span></span>
* <span data-ttu-id="ee08b-158">Kontoadministratör</span><span class="sxs-lookup"><span data-stu-id="ee08b-158">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="ee08b-159">Skrivskyddade roller</span><span class="sxs-lookup"><span data-stu-id="ee08b-159">Read-only roles</span></span>

<span data-ttu-id="ee08b-160">Med skrivskyddad åtkomst kan du inte redigera status eller anteckningar för en förbättringsåtgärd, redigera poängzoner eller redigera anpassade jämförelser.</span><span class="sxs-lookup"><span data-stu-id="ee08b-160">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="ee08b-161">Helpdesk-administratör</span><span class="sxs-lookup"><span data-stu-id="ee08b-161">Helpdesk administrator</span></span>
* <span data-ttu-id="ee08b-162">Användaradministratör</span><span class="sxs-lookup"><span data-stu-id="ee08b-162">User administrator</span></span>
* <span data-ttu-id="ee08b-163">Tjänstadministratör</span><span class="sxs-lookup"><span data-stu-id="ee08b-163">Service administrator</span></span>
* <span data-ttu-id="ee08b-164">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="ee08b-164">Security reader</span></span>
* <span data-ttu-id="ee08b-165">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="ee08b-165">Security operator</span></span>
* <span data-ttu-id="ee08b-166">Global läsare</span><span class="sxs-lookup"><span data-stu-id="ee08b-166">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="ee08b-167">Riskmedvetenhet</span><span class="sxs-lookup"><span data-stu-id="ee08b-167">Risk awareness</span></span>

<span data-ttu-id="ee08b-168">Microsoft Secure Score är en numerisk sammanfattning av din säkerhetsposition baserat på systemkonfigurationer, användarbeteende och andra säkerhetsrelaterade mätningar. Det är inte ett absolut mått på hur sannolikt ditt system eller data kommer att brytas.</span><span class="sxs-lookup"><span data-stu-id="ee08b-168">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="ee08b-169">Snarare är det i vilken utsträckning du har antagit säkerhetskontroller i din Microsoft-miljö som kan bidra till att kompensera risken för att brytas.</span><span class="sxs-lookup"><span data-stu-id="ee08b-169">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="ee08b-170">Ingen onlinetjänst är helt immun mot säkerhetsöverträdelser, och säker poäng bör inte tolkas som en garanti mot säkerhetsöverträdelse på något sätt.</span><span class="sxs-lookup"><span data-stu-id="ee08b-170">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="ee08b-171">Vad är nytt?</span><span class="sxs-lookup"><span data-stu-id="ee08b-171">What's new?</span></span> 

<span data-ttu-id="ee08b-172">För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition har vi gjort vissa ändringar.</span><span class="sxs-lookup"><span data-stu-id="ee08b-172">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="ee08b-173">Mer information om planerade ändringar finns [i Vad som kommer i Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="ee08b-173">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="ee08b-174">Inkompatibilitet med Identity Secure Score och Graph API</span><span class="sxs-lookup"><span data-stu-id="ee08b-174">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="ee08b-175">I den senaste versionen av Microsoft Secure Score har en förbättrad poängsättningsmodell släppts.</span><span class="sxs-lookup"><span data-stu-id="ee08b-175">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="ee08b-176">Dessa ändringar möjliggör en mer flexibel och korrekt bild av din säkerhetsposition.</span><span class="sxs-lookup"><span data-stu-id="ee08b-176">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="ee08b-177">Dessa uppdateringar har dock gjort Microsoft Secure Score tillfälligt inkompatibelt med Identity Secure Score och Graph API.</span><span class="sxs-lookup"><span data-stu-id="ee08b-177">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="ee08b-178">Med tiden antar Identity Secure Score och Graph API den nya bedömningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="ee08b-178">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="ee08b-179">Fram till dess ser kunderna skillnader i poängen som rapporteras av Microsoft Secure Score, Identity Secure Score och Graph API.</span><span class="sxs-lookup"><span data-stu-id="ee08b-179">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="ee08b-180">Vi ber om ursäkt för eventuella besvär detta orsakar, och arbetar för att säkerställa dessa erfarenheter är mer kompatibla i framtiden.</span><span class="sxs-lookup"><span data-stu-id="ee08b-180">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

### <a name="updated-improvement-actions"></a><span data-ttu-id="ee08b-181">Uppdaterade förbättringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="ee08b-181">Updated improvement actions</span></span>

- <span data-ttu-id="ee08b-182">Lade till förbättringarsåtgärder för Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ee08b-182">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="ee08b-183">Lade till Azure Advanced Threat Protection improvement-åtgärder</span><span class="sxs-lookup"><span data-stu-id="ee08b-183">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="ee08b-184">Stöd för säkerhetsrekommendationer för Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="ee08b-184">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="ee08b-185">Alla utgivna säkerhetsrekommendationer från TVM finns nu tillgängliga</span><span class="sxs-lookup"><span data-stu-id="ee08b-185">All released security recommendations supplied by TVM are now available</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="ee08b-186">Uppdaterat gränssnitt och funktionalitet</span><span class="sxs-lookup"><span data-stu-id="ee08b-186">Updated interface and functionality</span></span>

* <span data-ttu-id="ee08b-187">Alla nya statistik- och trendersvyer för CISO- och leadnivådiskussioner</span><span class="sxs-lookup"><span data-stu-id="ee08b-187">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="ee08b-188">Nya sätt att spåra och jämföra din poäng</span><span class="sxs-lookup"><span data-stu-id="ee08b-188">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="ee08b-189">Bättre spårning och förståelse för poängregressioner</span><span class="sxs-lookup"><span data-stu-id="ee08b-189">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="ee08b-190">Filtrera, tagga, söka och gruppera förbättringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="ee08b-190">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="ee08b-191">Hantera mot dina framtida mål med hjälp av resultatprognoser och planerade åtgärder</span><span class="sxs-lookup"><span data-stu-id="ee08b-191">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="ee08b-192">Och mer!</span><span class="sxs-lookup"><span data-stu-id="ee08b-192">And more!</span></span>

### <a name="june-2020"></a><span data-ttu-id="ee08b-193">Juni 2020</span><span class="sxs-lookup"><span data-stu-id="ee08b-193">June 2020</span></span>

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="ee08b-194">Borttagen förbättringsåtgärd för Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ee08b-194">Removed improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="ee08b-195">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="ee08b-195">Turn on Attack Surface Reduction rules</span></span>

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="ee08b-196">Lade till förbättringsåtgärder för Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ee08b-196">Added improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="ee08b-197">Blockera Adobe Reader från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="ee08b-197">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="ee08b-198">Använd avancerat skydd mot ransomware</span><span class="sxs-lookup"><span data-stu-id="ee08b-198">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="ee08b-199">Blockera alla Office-program från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="ee08b-199">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="ee08b-200">Blockera Office-program från att skapa körbart innehåll</span><span class="sxs-lookup"><span data-stu-id="ee08b-200">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="ee08b-201">Blockera JavaScript eller VBScript från att starta nedladdat körbart innehåll</span><span class="sxs-lookup"><span data-stu-id="ee08b-201">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="ee08b-202">Blockera körning av potentiellt fördunklade skript</span><span class="sxs-lookup"><span data-stu-id="ee08b-202">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="ee08b-203">Blockera körbart innehåll från e-postklient och webbmail</span><span class="sxs-lookup"><span data-stu-id="ee08b-203">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="ee08b-204">Blockera Office-kommunikationsprogram från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="ee08b-204">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="ee08b-205">Blockera ej betrodda och osignerade processer som körs från USB</span><span class="sxs-lookup"><span data-stu-id="ee08b-205">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="ee08b-206">Blockera persistens genom WMI-händelseprenumeration</span><span class="sxs-lookup"><span data-stu-id="ee08b-206">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="ee08b-207">Blockera Office-program från att injicera kod i andra processer</span><span class="sxs-lookup"><span data-stu-id="ee08b-207">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="ee08b-208">Blockera körbara filer från att köras om de inte uppfyller ett prevalens-, ålders- eller tillförlitligt listkriterium</span><span class="sxs-lookup"><span data-stu-id="ee08b-208">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="ee08b-209">Blockera processskapanden från PSExec- och WMI-kommandon</span><span class="sxs-lookup"><span data-stu-id="ee08b-209">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="ee08b-210">Blockera stöld av autentiseringsuppgifter från undersystemet Windows lokala säkerhetsmyndighet (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="ee08b-210">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="ee08b-211">Blockera Win32 API-anrop från Office-makron</span><span class="sxs-lookup"><span data-stu-id="ee08b-211">Block Win32 API calls from Office macros</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="ee08b-212">Vi vill höra från dig</span><span class="sxs-lookup"><span data-stu-id="ee08b-212">We want to hear from you</span></span>

<span data-ttu-id="ee08b-213">Om du har några problem, vänligen meddela oss genom att publicera i [security, privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span><span class="sxs-lookup"><span data-stu-id="ee08b-213">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="ee08b-214">Vi övervakar samhället och kommer att ge hjälp.</span><span class="sxs-lookup"><span data-stu-id="ee08b-214">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="ee08b-215">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="ee08b-215">Related resources</span></span>

- [<span data-ttu-id="ee08b-216">Få insyn i din säkerhetsposition</span><span class="sxs-lookup"><span data-stu-id="ee08b-216">Gain visibility into your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="ee08b-217">Spåra din Microsoft Secure Score-historik och uppnå mål</span><span class="sxs-lookup"><span data-stu-id="ee08b-217">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="ee08b-218">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="ee08b-218">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
