---
title: Appsupport för Microsoft 365-klient och -tjänster
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: I den här artikeln hittar du information om support för Microsoft 365-klient- och tjänstappen.
ms.openlocfilehash: 4e32e39281175ed66970a358ff632c2ddbb3ac1a
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097494"
---
# <a name="microsoft-365-client-and-services-app-support"></a><span data-ttu-id="9f798-103">Appsupport för Microsoft 365-klient och -tjänster</span><span class="sxs-lookup"><span data-stu-id="9f798-103">Microsoft 365 client and services app support</span></span>

<span data-ttu-id="9f798-104">Microsoft har stöd för ett brett utbud av säkerhets-, autentiserings- och efterlevnadsfunktioner för att skydda kunddata och gör att IT-administratörer kan anpassa principer i administrationscentret för Microsoft 365 för sina användare.</span><span class="sxs-lookup"><span data-stu-id="9f798-104">Microsoft supports a wide range of security, authentication, and compliance features to keep customer data safe and allows IT administrators to customize policies within the Microsoft 365 admin center for their users.</span></span> <span data-ttu-id="9f798-105">Följande funktioner är bara en del av de många företagsfunktioner som du kan konfigurera beroende på din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="9f798-105">The following features are just a subset of the many enterprise features that you can configure depending on your Microsoft 365 subscription.</span></span>

## <a name="client-and-service-support"></a><span data-ttu-id="9f798-106">Klient- och tjänstsupport</span><span class="sxs-lookup"><span data-stu-id="9f798-106">Client and service support</span></span>

### <a name="continuous-access-evaluation-preview"></a><span data-ttu-id="9f798-107">Utvärdering av kontinuerlig åtkomst (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="9f798-107">Continuous access evaluation (preview)</span></span>

<span data-ttu-id="9f798-108">Utvärdering av kontinuerlig åtkomst implementeras genom att tjänster som Exchange Online, SharePoint Online och Teams kan prenumerera på kritiska händelser i Azure Active Directory så att dessa händelser kan utvärderas och tillämpas nära i realtid.</span><span class="sxs-lookup"><span data-stu-id="9f798-108">Continuous access evaluation is implemented by enabling services, like Exchange Online, SharePoint Online, and Teams, to subscribe to critical events in Azure Active Directory so that those events can be evaluated and enforced near real time.</span></span> <span data-ttu-id="9f798-109">Utvärdering av kritiska händelser förlitar sig inte på villkorsstyrda åtkomstprinciper, vilket är tillgängligt i alla klientorganisationsklienter.</span><span class="sxs-lookup"><span data-stu-id="9f798-109">Critical event evaluation does not rely on Conditional Access policies so is available in any tenant.</span></span>

<span data-ttu-id="9f798-110">Följande händelser utvärderas för närvarande:</span><span class="sxs-lookup"><span data-stu-id="9f798-110">The following events are currently evaluated:</span></span>

- <span data-ttu-id="9f798-111">Ett användarkonto tas bort eller inaktiveras</span><span class="sxs-lookup"><span data-stu-id="9f798-111">A user account is deleted or disabled</span></span>
- <span data-ttu-id="9f798-112">Lösenordet för en användare ändras eller återställs</span><span class="sxs-lookup"><span data-stu-id="9f798-112">The password for a user is changed or reset</span></span>
- <span data-ttu-id="9f798-113">Multifaktorautentisering aktiveras för användaren</span><span class="sxs-lookup"><span data-stu-id="9f798-113">Multi-factor authentication is enabled for the user</span></span>
- <span data-ttu-id="9f798-114">Administratören återkallar uttryckligen alla uppdateringstoken för en användare</span><span class="sxs-lookup"><span data-stu-id="9f798-114">Administrator explicitly revokes all refresh tokens for a user</span></span>
- <span data-ttu-id="9f798-115">Förhöjd användarrisk upptäckt av Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="9f798-115">Elevated user risk detected by Azure AD Identity Protection</span></span>

<span data-ttu-id="9f798-116">Mer information om kontinuerlig åtkomstutvärdering för support av klient- och tjänstprogram finns i [Utvärdering av kontinuerlig åtkomst (förhandsversion).](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)</span><span class="sxs-lookup"><span data-stu-id="9f798-116">For more information about continuous access evaluation for client and services app support, see [Continuous access evaluation (preview)](/azure/active-directory/conditional-access/concept-continuous-access-evaluation).</span></span>

## <a name="client-support"></a><span data-ttu-id="9f798-117">Klientsupport</span><span class="sxs-lookup"><span data-stu-id="9f798-117">Client support</span></span>

### <a name="certificate-based-authentication"></a><span data-ttu-id="9f798-118">Certifikatbaserad autentisering</span><span class="sxs-lookup"><span data-stu-id="9f798-118">Certificate-based authentication</span></span>

<span data-ttu-id="9f798-119">Certifikatbaserad autentisering (CBA) är användningen av ett digitalt certifikat för att identifiera en användare, dator eller enhet innan åtkomst till en resurs, ett nätverk, ett program eller en tjänst beviljas.</span><span class="sxs-lookup"><span data-stu-id="9f798-119">Certificate-based authentication (CBA) is the use of a digital certificate to identify a user, machine, or device before granting access to a resource, network, application, or service.</span></span> <span data-ttu-id="9f798-120">Inom användarautentisering distribueras det ofta i samverkan med traditionella metoder som användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="9f798-120">In user authentication, it is often deployed in coordination with traditional methods such as usernames and passwords.</span></span>

<span data-ttu-id="9f798-121">Vissa traditionella lösningar fungerar bara för användare, till exempel biometrisker och engångslösenord (OTP).</span><span class="sxs-lookup"><span data-stu-id="9f798-121">Some traditional solutions only work for users, such as biometrics and one-time passwords (OTP).</span></span> <span data-ttu-id="9f798-122">Med certifikatbaserad autentisering kan samma lösning användas för alla slutpunkter. användare, enheter och den växande Internet of Things (IoT).</span><span class="sxs-lookup"><span data-stu-id="9f798-122">With certificate-based authentication, the same solution can be used for all endpoints; users, devices, and the growing Internet of Things (IoT).</span></span>

<span data-ttu-id="9f798-123">Mer information om certifikatbaserad autentisering för stöd för klient- och tjänstprogram finns i supporten för [Microsoft 365-klientappen: Certifikatbaserad autentisering.](microsoft-365-client-support-certificate-based-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="9f798-123">For more information about certificate-based authentication for client and services app support, see [Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).</span></span>

### <a name="conditional-access"></a><span data-ttu-id="9f798-124">Villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="9f798-124">Conditional Access</span></span>

<span data-ttu-id="9f798-125">Villkorsstyrd åtkomst är verktyget som används av Azure Active Directory för att föra samman signaler, fatta beslut och genomdriva principer för organisationsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="9f798-125">Conditional Access is the tool used by Azure Active Directory to bring signals together, to make decisions, and enforce organizational access policies.</span></span> <span data-ttu-id="9f798-126">Villkorsstyrd åtkomst är kärnan i den nya identitetsdrivna kontrollmodellen.</span><span class="sxs-lookup"><span data-stu-id="9f798-126">Conditional Access is at the heart of the new identity-driven control model.</span></span>

<span data-ttu-id="9f798-127">Villkorsstyrda access-principer är om-sedan-instruktioner för att bevilja åtkomst till resurser.</span><span class="sxs-lookup"><span data-stu-id="9f798-127">Conditional Access policies are if-then statements for granting access to resources.</span></span> <span data-ttu-id="9f798-128">Om en användare vill komma åt en resurs måste användaren slutföra en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9f798-128">If a user wants to access a resource, then the user must complete an action.</span></span> <span data-ttu-id="9f798-129">Vanliga signaler som villkorsstyrd åtkomst kan använda när man ska fatta ett beslut om principåtkomst är bland annat:</span><span class="sxs-lookup"><span data-stu-id="9f798-129">Common signals that Conditional Access can use when making a policy access decision include:</span></span>

- <span data-ttu-id="9f798-130">Användare- eller gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="9f798-130">User or group membership</span></span>
- <span data-ttu-id="9f798-131">IP-platsinformation</span><span class="sxs-lookup"><span data-stu-id="9f798-131">IP location information</span></span>
- <span data-ttu-id="9f798-132">Enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="9f798-132">Device information</span></span>
- <span data-ttu-id="9f798-133">Programinformation</span><span class="sxs-lookup"><span data-stu-id="9f798-133">Application information</span></span>
- <span data-ttu-id="9f798-134">Identifiering av risker i realtid och beräknad</span><span class="sxs-lookup"><span data-stu-id="9f798-134">Real-time and calculated risk detection</span></span>
- <span data-ttu-id="9f798-135">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="9f798-135">Microsoft Cloud App Security (MCAS)</span></span>

<span data-ttu-id="9f798-136">När dessa åtkomstbeslut ska fattas kan principerna vidta olika åtgärder:</span><span class="sxs-lookup"><span data-stu-id="9f798-136">When making these access decisions, the policies can take different actions:</span></span>

- <span data-ttu-id="9f798-137">Principen kan blockera åtkomst: Den här konfigurationen är den mest restriktiva åtgärden och hindrar användaren från att komma åt resursen.</span><span class="sxs-lookup"><span data-stu-id="9f798-137">The policy can block access: This configuration is the most restrictive action and prevents the user from accessing the resource.</span></span>
- <span data-ttu-id="9f798-138">Principen kan bevilja åtkomst: Den här konfigurationen är ett mindre restriktivt beslut och kan fortfarande kräva ett eller flera av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="9f798-138">The policy can grant access: This configuration is a less restrictive decision and may still require one or more of the following options:</span></span>

    - <span data-ttu-id="9f798-139">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="9f798-139">Multi-factor authentication</span></span>
    - <span data-ttu-id="9f798-140">Enheten som ska markeras som kompatibel</span><span class="sxs-lookup"><span data-stu-id="9f798-140">The device to be marked as compliant</span></span>
    - <span data-ttu-id="9f798-141">Enheten är Azure AD-hybrid ansluten</span><span class="sxs-lookup"><span data-stu-id="9f798-141">The device is hybrid Azure AD joined</span></span>
    - <span data-ttu-id="9f798-142">En godkänd klientapp</span><span class="sxs-lookup"><span data-stu-id="9f798-142">An approved client app</span></span>
    - <span data-ttu-id="9f798-143">Programskyddsprincip konfigurerad (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="9f798-143">App protection policy configured (preview)</span></span>

<span data-ttu-id="9f798-144">Mer information om villkorsstyrd åtkomst för stöd för klient- och tjänsterprogram finns i:</span><span class="sxs-lookup"><span data-stu-id="9f798-144">For more information about Conditional Access for client and services app support, see:</span></span>

- [<span data-ttu-id="9f798-145">Microsoft 365 Client App Support: Enhetsbaserad villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="9f798-145">Microsoft 365 Client App Support: Device-based Conditional Access</span></span>](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a><span data-ttu-id="9f798-146">Hantering av mobilprogram</span><span class="sxs-lookup"><span data-stu-id="9f798-146">Mobile application management</span></span>

<span data-ttu-id="9f798-147">Användare får ofta åtkomst till både organisations- och personliga dokument, e-post och data från samma mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="9f798-147">Users often access both organization and personal documents, email, and data from the same mobile device.</span></span> <span data-ttu-id="9f798-148">Dessa enheter ägs ofta personligen och bör konfigureras för att skydda både organisationsdata och användarens personliga integritet.</span><span class="sxs-lookup"><span data-stu-id="9f798-148">Those devices are often personally owned and should be configured to protect both organization data and the user's personal privacy.</span></span>

<span data-ttu-id="9f798-149">När en användare får åtkomst till organisationsdata måste organisationen vara säker på att organisationsprinciper, till exempel konfigurationsprinciper och skyddsprinciper, tillämpas för att skydda organisationsdata på enheten.</span><span class="sxs-lookup"><span data-stu-id="9f798-149">When a user accesses organization data, the organization must be confident that organization policies, such as configuration policies and protection policies, are applied to help protect organization data on the device.</span></span> <span data-ttu-id="9f798-150">Dessutom bör användarens personliga innehåll på enheten ligga kvar utanför organisationens kontroll.</span><span class="sxs-lookup"><span data-stu-id="9f798-150">Additionally, the user's personal content on the device should remain outside of the organization's control.</span></span>

<span data-ttu-id="9f798-151">För organisations hanterat innehåll kan du använda principer för programhantering för att styra hur data används, delas och används med Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="9f798-151">For organization-managed content, you can apply application management policies to control how data is accessed, shared, and used by using Microsoft Intune.</span></span> <span data-ttu-id="9f798-152">Följande åtgärder stöds till exempel:</span><span class="sxs-lookup"><span data-stu-id="9f798-152">For example, the following actions are supported:</span></span>

- <span data-ttu-id="9f798-153">Fjärr-rensning av hanterat organisationsinnehåll (kallas även organisationsdata)</span><span class="sxs-lookup"><span data-stu-id="9f798-153">Remote wipe the managed organization content (also referred to org data)</span></span>
- <span data-ttu-id="9f798-154">Förhindra att organisationsinnehåll klistras in till platser utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="9f798-154">Prevent pasting organization content into non-organization locations</span></span>
- <span data-ttu-id="9f798-155">Kräv en PIN-kod för åtkomst till organisationsinnehåll</span><span class="sxs-lookup"><span data-stu-id="9f798-155">Require a PIN to access organization content</span></span>
- <span data-ttu-id="9f798-156">Förhindra hanterade appar från att köras på jailbroken eller rotade enheter</span><span class="sxs-lookup"><span data-stu-id="9f798-156">Prevent managed apps from running on jailbroken or rooted devices</span></span>
- <span data-ttu-id="9f798-157">Förhindra att organisationsinnehåll sparas på en molnlagringsleverantör som inte godkänts</span><span class="sxs-lookup"><span data-stu-id="9f798-157">Prevent organization content from being saved to unapproved cloud storage providers</span></span>
- <span data-ttu-id="9f798-158">Förhindra att innehåll som inte godkänts överförs till hanterade program</span><span class="sxs-lookup"><span data-stu-id="9f798-158">Prevent unapproved content from being transferred into managed applications</span></span>
- <span data-ttu-id="9f798-159">Tillåt åtkomst till organisationsinnehåll endast efter att principer har tillämpats</span><span class="sxs-lookup"><span data-stu-id="9f798-159">Allow access to organization content only after policies have been applied</span></span>
- <span data-ttu-id="9f798-160">Leverera programkonfiguration för att hantera programmets beteende och inställningar</span><span class="sxs-lookup"><span data-stu-id="9f798-160">Deliver application configuration to manage the application's behavior and settings</span></span>
- <span data-ttu-id="9f798-161">Begränsa det hanterade programmet till en definierad identitet genom att inaktivera funktioner för flera identiteter eller personlig användning</span><span class="sxs-lookup"><span data-stu-id="9f798-161">Restrict the managed application to a defined identity by disabling multi-identity capabilities or personal usage</span></span>

<span data-ttu-id="9f798-162">Mer information om hantering av mobilprogram med Microsoft Intune finns i [Vad är apphantering för Microsoft Intune?](/mem/intune/apps/app-management)</span><span class="sxs-lookup"><span data-stu-id="9f798-162">For more information about mobile application management with Microsoft Intune, see [What is Microsoft Intune app management?](/mem/intune/apps/app-management)</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="9f798-163">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="9f798-163">Multi-factor authentication</span></span>

<span data-ttu-id="9f798-164">[Multifaktorautentisering (MFA) är en metod för datoråtkomstkontroll där en användare beviljas åtkomst endast efter att ha presenterat flera olika bevis för en autentiseringsmekanism.</span><span class="sxs-lookup"><span data-stu-id="9f798-164">[Multi-factor authentication (MFA) is a method of computer access control in which a user is granted access only after successfully presenting several separate pieces of evidence to an authentication mechanism.</span></span> <span data-ttu-id="9f798-165">Den här metoden använder vanligtvis minst två av följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="9f798-165">This method typically uses at least two of the following categories:</span></span>

- <span data-ttu-id="9f798-166">Kunskap (något de känner till)</span><span class="sxs-lookup"><span data-stu-id="9f798-166">Knowledge (something they know)</span></span>
- <span data-ttu-id="9f798-167">Innehavardel (något de har)</span><span class="sxs-lookup"><span data-stu-id="9f798-167">Possession (something they have)</span></span>
- <span data-ttu-id="9f798-168">Inherence (något de är)</span><span class="sxs-lookup"><span data-stu-id="9f798-168">Inherence (something they are)</span></span>

<span data-ttu-id="9f798-169">Mer information om multifaktorautentisering för support för klient- och tjänsteprogram finns i supporten för [Microsoft 365-klientappen: Multifaktorautentisering.](microsoft-365-client-support-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="9f798-169">For more information about multi-factor authentication for client and services app support, see [Microsoft 365 Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).</span></span>

### <a name="single-sign-on"></a><span data-ttu-id="9f798-170">Enkel inloggning</span><span class="sxs-lookup"><span data-stu-id="9f798-170">Single sign-on</span></span>

<span data-ttu-id="9f798-171">Enkel inloggning (SSO) ger säkerhet och enkelhet när användarna loggar in på program i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f798-171">Single sign-on (SSO) adds security and convenience when your users sign-on to applications in Azure Active Directory.</span></span> <span data-ttu-id="9f798-172">Med enkel inloggning loggar användarna in en gång med ett konto för att komma åt lokala Active Directory DS-enheter (AD DS), programvara som en tjänstprogram (SaaS) och webbprogram i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9f798-172">With single sign-on, users sign in once with one account to access on-premises Active Directory Domain Services (AD DS) domain-joined devices, software as a service (SaaS) applications, and web applications in your organization.</span></span>

<span data-ttu-id="9f798-173">Mer information om enkel inloggning för support för klient- och tjänstprogram finns i Support för [Microsoft 365-klientappen: Enkel inloggning.](microsoft-365-client-support-single-sign-on.md)</span><span class="sxs-lookup"><span data-stu-id="9f798-173">For more information about single sign-on for client and services app support, see [Microsoft 365 Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md).</span></span>

## <a name="services-support"></a><span data-ttu-id="9f798-174">Support för tjänster</span><span class="sxs-lookup"><span data-stu-id="9f798-174">Services support</span></span>

### <a name="modern-authentication"></a><span data-ttu-id="9f798-175">Modern autentisering</span><span class="sxs-lookup"><span data-stu-id="9f798-175">Modern authentication</span></span>

<span data-ttu-id="9f798-176">Modern autentisering innebär att nya scenarier för kunder kan autentiseras mot Office 365 och för innehavaradministratörer att tillämpa specifika autentiseringskrav i Hela Office 365-innehavet, till exempel:</span><span class="sxs-lookup"><span data-stu-id="9f798-176">Modern authentication enables new scenarios for customers to authenticate against Office 365 and for tenant admins to enforce specific authentication requirements across the Office 365 tenancy, such as:</span></span>

- <span data-ttu-id="9f798-177">Stöd för multifaktorautentisering för administrativ interaktion med klient och tjänster och slutanvändarens interaktion med program och deras data</span><span class="sxs-lookup"><span data-stu-id="9f798-177">Multi-factor authentication support for administrative interaction with the tenancy and services, and end-user interaction with applications and their data</span></span>
- <span data-ttu-id="9f798-178">Villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="9f798-178">Conditional access</span></span>
- <span data-ttu-id="9f798-179">SAML-baserad inloggning från tredjepartsidentitetsleverantör</span><span class="sxs-lookup"><span data-stu-id="9f798-179">SAML-based third-party identity provider sign-in</span></span>
- <span data-ttu-id="9f798-180">Smartkortslogg på persondatorer</span><span class="sxs-lookup"><span data-stu-id="9f798-180">Smartcard log on personal computers</span></span>
- <span data-ttu-id="9f798-181">Certifikatbaserad autentisering på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="9f798-181">Certificate-based authentication on mobile devices</span></span>
- <span data-ttu-id="9f798-182">Det krävs inte längre överföring av autentiseringsuppgifter över grundläggande autentisering.</span><span class="sxs-lookup"><span data-stu-id="9f798-182">No longer require the transmission of credentials over basic authentication.</span></span>

<span data-ttu-id="9f798-183">Mer information om stöd för moderna autentiseringstjänster finns i [Autentisering kontra auktorisering.](/azure/active-directory/develop/authentication-vs-authorization)</span><span class="sxs-lookup"><span data-stu-id="9f798-183">For more information about modern authentication services support, see [Authentication vs. authorization](/azure/active-directory/develop/authentication-vs-authorization).</span></span>

### <a name="azure-active-directory-conditional-access"></a><span data-ttu-id="9f798-184">Villkorsstyrd åtkomst i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9f798-184">Azure Active Directory Conditional Access</span></span>

<span data-ttu-id="9f798-185">Med villkorsstyrda åtkomstregler i Azure Active Directory (Azure AD) kan kunderna kontrollera åtkomsten till onlinetjänster, baserat på attribut som enhetsefterlevnad eller nätverksplats.</span><span class="sxs-lookup"><span data-stu-id="9f798-185">Azure Active Directory (Azure AD) Conditional Access rules allow customers to control access to online services, based on attributes such as device compliance or network location.</span></span> <span data-ttu-id="9f798-186">Följande lösningar kan användas:</span><span class="sxs-lookup"><span data-stu-id="9f798-186">The following solutions may be used:</span></span>

- <span data-ttu-id="9f798-187">Azure AD, flerfaktorautentiseringsbaserad villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="9f798-187">Azure AD multi-factor authentication-based Conditional Access</span></span>
- <span data-ttu-id="9f798-188">Azure AD platsbaserad villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="9f798-188">Azure AD location-based Conditional Access</span></span>
- <span data-ttu-id="9f798-189">Azure AD enhetsbaserad villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="9f798-189">Azure AD device-based Conditional Access</span></span>

<span data-ttu-id="9f798-190">Villkorsstyrda åtkomstregler i Azure AD tillämpas per program och är tillgängliga för kunder att styra åtkomsten baserat på olika villkor.</span><span class="sxs-lookup"><span data-stu-id="9f798-190">Azure AD Conditional access rules are applied per-application and are available for customers to control access based on different conditions.</span></span> <span data-ttu-id="9f798-191">Med [Mobile Device Management (MDM) eller Intune](/mem/intune/fundamentals/what-is-device-management)måste kunderna kunna begränsa åtkomsten till Microsoft 365 till endast de användare som använder en organisationsenhet eller som har registrerat sin personliga enhet för hantering.</span><span class="sxs-lookup"><span data-stu-id="9f798-191">Using [Mobile Device Management (MDM) or Intune](/mem/intune/fundamentals/what-is-device-management), customers must be able to restrict access to Microsoft 365 to only those users who are using an organization device or who have enrolled their personal device for management.</span></span> <span data-ttu-id="9f798-192">Kunder kan till exempel konfigurera regler för villkorsstyrd åtkomst för att tillämpa kontroller som:</span><span class="sxs-lookup"><span data-stu-id="9f798-192">For example, customers may configure Conditional Access rules to enforce controls such as:</span></span>

- <span data-ttu-id="9f798-193">Tillåt endast åtkomst från enheter som är domän anslutna eller domänkompatibla</span><span class="sxs-lookup"><span data-stu-id="9f798-193">Only allow access from devices that are domain joined or domain compliant</span></span>
- <span data-ttu-id="9f798-194">Tillämpa multifaktorautentisering för all åtkomst till Exchange Online-tjänster</span><span class="sxs-lookup"><span data-stu-id="9f798-194">Enforce multi-factor authentication for all access to Exchange Online services</span></span>

<span data-ttu-id="9f798-195">Mer information om villkorsstyrd åtkomst i Azure Active Directory finns i [Vad är villkorlig åtkomst?](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="9f798-195">For more information about Azure Active Directory Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span>

### <a name="tls-12-support"></a><span data-ttu-id="9f798-196">Stöd för TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="9f798-196">TLS 1.2 support</span></span>

<span data-ttu-id="9f798-197">Microsoft planerar att upphöra med stödet för TLS-versionerna 1.0 och 1.1 i Office 365 och Office 365 GCC för att ge våra kunder den bästa krypteringen i klassen.</span><span class="sxs-lookup"><span data-stu-id="9f798-197">To provide the best-in-class encryption to our customers, Microsoft plans to discontinue support for Transport Layer Security (TLS) versions 1.0 and 1.1 in Office 365 and Office 365 GCC.</span></span>

<span data-ttu-id="9f798-198">Vi förstår att din data är viktig, och vi är måna om transparensen om ändringar som kan påverka din användning av tjänsten TLS.</span><span class="sxs-lookup"><span data-stu-id="9f798-198">We understand that the security of your data is important, and we're committed to transparency about changes that may affect your use of the TLS service.</span></span> <span data-ttu-id="9f798-199">Vi rekommenderar att alla kombinationer av klientserver och webbläsarserver använder TLS 1.2 (eller en senare version) för att upprätthålla anslutningen till Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="9f798-199">We recommend that all client-server and browser-server combinations use TLS 1.2 (or a later version) to maintain connection to Office 365 services.</span></span> <span data-ttu-id="9f798-200">Du kan behöva uppdatera vissa kombinationer av klient- och webbläsarservrar.</span><span class="sxs-lookup"><span data-stu-id="9f798-200">You might have to update certain client-server and browser-server combinations.</span></span>

<span data-ttu-id="9f798-201">Mer information om TLS 1.2-support och TLS 2-support finns i Förbereda för [TLS 1.2 i Office 365 och Office 365 GCC.](/microsoft-365/compliance/prepare-tls-1.2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="9f798-201">For more information about TLS 1.2 support and services support, see [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](/microsoft-365/compliance/prepare-tls-1.2-in-office-365).</span></span>
