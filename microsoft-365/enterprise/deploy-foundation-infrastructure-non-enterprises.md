---
title: Grundläggande infrastruktur för Microsoft 365 för företag för andra än stora företag
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Gå igenom de förenklade faserna i den grundläggande infrastrukturen för Microsoft 365 för företag för andra organisationer än stora företag.
ms.openlocfilehash: cad142f2f26eb999431eb5bb531cb4520e4d6102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638266"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="56c27-103">Grundläggande infrastruktur för Microsoft 365 för företag för andra än stora företag</span><span class="sxs-lookup"><span data-stu-id="56c27-103">Microsoft 365 for enterprise foundation infrastructure for non-enterprises</span></span>

<span data-ttu-id="56c27-104">Andra organisationer än stora företag kan också distribuera Microsoft 365 för företag och uppleva affärsvärdet för en integrerad och säker infrastruktur som gör det möjligt att samarbeta och frigöra kreativitet.</span><span class="sxs-lookup"><span data-stu-id="56c27-104">Non-enterprise organizations can also deploy Microsoft 365 for enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="56c27-105">Andra organisationer än stora företag har vanligtvis:</span><span class="sxs-lookup"><span data-stu-id="56c27-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="56c27-106">En mindre del lokal IT-infrastruktur, t.ex. e-post och filservrar och en AD DS-domän (Active Directory Domain Services), eller ingen alls.</span><span class="sxs-lookup"><span data-stu-id="56c27-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="56c27-107">En liten IT-personalstyrka, varav de flesta är IT-generalister snarare än specialister inom en specifik teknik eller ett kunskapsområde, t.ex. nätverk eller e-post.</span><span class="sxs-lookup"><span data-stu-id="56c27-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="56c27-108">För mindre organisationer erbjuder Microsoft [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span><span class="sxs-lookup"><span data-stu-id="56c27-108">For smaller, non-enterprise organizations, Microsoft offers [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="56c27-109">Det finns dock anledningar till varför du kan behöva Microsoft 365 för företag, till exempel:</span><span class="sxs-lookup"><span data-stu-id="56c27-109">However, there are reasons why you might need Microsoft 365 for enterprise, such as:</span></span>

- <span data-ttu-id="56c27-110">Din organisation behöver mer eller kommer att behöva mer än 300 Microsoft 365-licenser, vilket är maximalt antal för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="56c27-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 for business.</span></span>
- <span data-ttu-id="56c27-111">Din organisation behöver de avancerade funktionerna för produktivitet, rösttjänster, säkerhet och analys som inte finns i Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="56c27-111">Your organization needs the advanced productivity, voice, security, and analytics capabilities that are not available with Microsoft 365 for business.</span></span>

<span data-ttu-id="56c27-112">I den här artikeln beskrivs en förenklad distribution av den grundläggande infrastrukturen för Microsoft 365 för företag, som passar företag som inte har lika stora behov som storföretag.</span><span class="sxs-lookup"><span data-stu-id="56c27-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 for enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="56c27-113">Konfigurera först din prenumeration</span><span class="sxs-lookup"><span data-stu-id="56c27-113">First, set up your subscription</span></span>

<span data-ttu-id="56c27-114">Du måste konfigurera DNS-domänerna (Domain Name System) för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="56c27-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="56c27-115">Om du redan har en Microsoft 365-prenumeration borde detta vara gjort.</span><span class="sxs-lookup"><span data-stu-id="56c27-115">If you already have a Microsoft 365 subscription, this should have been done.</span></span> <span data-ttu-id="56c27-116">Annars följer du anvisningarna i [Lägga till en domän i Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="56c27-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="56c27-117">Därefter måste du konfigurera ytterligare säkerhet för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56c27-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="56c27-118">Följ anvisningarna i [Konfigurera ökad säkerhet](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="56c27-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="56c27-119">Fas 1: Nätverk</span><span class="sxs-lookup"><span data-stu-id="56c27-119">Phase 1: Networking</span></span>

<span data-ttu-id="56c27-120">Organisationer som inte är stora företag har vanligtvis lokala Internetanslutningar på varje kontor och använder inte proxyservrar, brandväggar eller enheter för paketkontroll.</span><span class="sxs-lookup"><span data-stu-id="56c27-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="56c27-121">Den Internetleverantör som betjänar varje kontor har en regional lokal DNS-server så att trafiken dirigeras till den Microsoft 365-nätverksplats som ligger närmast dina kontor och de lokala användarna.</span><span class="sxs-lookup"><span data-stu-id="56c27-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span> <span data-ttu-id="56c27-122">Mer information finns i [Konfigurera lokala Internetanslutningar för varje kontor](networking-dns-resolution-same-location.md).</span><span class="sxs-lookup"><span data-stu-id="56c27-122">For more information, see [Configure local Internet connections for each office](networking-dns-resolution-same-location.md).</span></span>

<span data-ttu-id="56c27-123">Därför behöver du bara verifiera med din Internetleverantör att anslutningen på var och en av dina kontorsplatser:</span><span class="sxs-lookup"><span data-stu-id="56c27-123">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="56c27-124">Använder en regional lokal DNS-server.</span><span class="sxs-lookup"><span data-stu-id="56c27-124">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="56c27-125">Passar för nuvarande och framtida behov allteftersom användarna börjar använda fler Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="56c27-125">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="56c27-126">Om du använder proxyservrar, brandväggar eller enheter för paketkontroll kan du läsa [Konfigurera förbikoppling av trafik](networking-configure-proxies-firewalls.md) för mer information om hur du optimerar prestanda för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="56c27-126">If you do use proxy servers, firewalls, or packet inspection devices, see [Configure traffic bypass](networking-configure-proxies-firewalls.md) for information on how to optimize performance to Microsoft 365 services.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="56c27-127">Din konfiguration hittills</span><span class="sxs-lookup"><span data-stu-id="56c27-127">Your configuration so far</span></span>

<span data-ttu-id="56c27-128">Här är en visuell sammanfattning med fas 1-elementet markerat.</span><span class="sxs-lookup"><span data-stu-id="56c27-128">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="56c27-129">**Din organisation** kan bestå av flera kontor, som vart och ett har en lokal Internetanslutning med en Internetleverantör som använder en regional lokal DNS-server.</span><span class="sxs-lookup"><span data-stu-id="56c27-129">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="56c27-130">Via Internetleverantören kan användarna på varje kontor nå närmaste Microsoft 365-nätverksplats och resurserna för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="56c27-130">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![Din organisation efter nätverksfasen](../media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="56c27-132">Fas 2: Identitet</span><span class="sxs-lookup"><span data-stu-id="56c27-132">Phase 2: Identity</span></span>

<span data-ttu-id="56c27-133">Alla anställda i din organisation måste kunna logga in, vilket kräver ett användarkonto i Azure Active Directory-klientorganisationen (Azure AD) för Microsoft 365 för företag-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="56c27-133">Each employee of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 for enterprise subscription.</span></span> <span data-ttu-id="56c27-134">Grupper används sedan för att hålla samman användarkonton och andra grupper för att kommunicera och få tillgång till resurser som kräver behörighet, t.ex. en SharePoint Online-webbplats eller ett team.</span><span class="sxs-lookup"><span data-stu-id="56c27-134">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="56c27-135">Administratörskonton</span><span class="sxs-lookup"><span data-stu-id="56c27-135">Administrator accounts</span></span>

<span data-ttu-id="56c27-136">Skydda dina användarkonton för global administratör genom att kräva starka lösenord och multifaktorautentisering (MFA).</span><span class="sxs-lookup"><span data-stu-id="56c27-136">Protect your global administrator user accounts by requiring strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="56c27-137">Mer information finns i [Skydda globala administratörskonton](identity-create-protect-global-admins.md#protect-global-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="56c27-137">See [Protect global administrator accounts](identity-create-protect-global-admins.md#protect-global-administrator-accounts) for more information.</span></span>

<span data-ttu-id="56c27-138">Om din organisation kräver hög säkerhet och du har Microsoft 365 E5, använder du Azure AD Privileged Identity Management för att aktivera just-in-time-administratörsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="56c27-138">If your organization requires high security and you have Microsoft 365 E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="56c27-139">Mer information finns i [Konfigurera globala administratörer på begäran](identity-create-protect-global-admins.md#identity-pim).</span><span class="sxs-lookup"><span data-stu-id="56c27-139">See [Set up on-demand global administrators](identity-create-protect-global-admins.md#identity-pim) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="56c27-140">Rekommendationer för grupper</span><span class="sxs-lookup"><span data-stu-id="56c27-140">Recommendations for groups</span></span>

<span data-ttu-id="56c27-141">Om du har en lokal AD DS-domän fortsätter du att använda dessa grupper i Microsoft 365 för företag som grupper i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56c27-141">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 for enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="56c27-142">Om du inte har en lokal AD DS-domän skapar du säkerhetsgrupper i Azure AD med dessa säkerhetsnivåer.</span><span class="sxs-lookup"><span data-stu-id="56c27-142">If you don't have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="56c27-143">Säkerhetsnivå</span><span class="sxs-lookup"><span data-stu-id="56c27-143">Security level</span></span> | <span data-ttu-id="56c27-144">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="56c27-144">Description</span></span> | <span data-ttu-id="56c27-145">Exempel</span><span class="sxs-lookup"><span data-stu-id="56c27-145">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="56c27-146">Grundläggande</span><span class="sxs-lookup"><span data-stu-id="56c27-146">Baseline</span></span> | <span data-ttu-id="56c27-147">Det här är en minimal standard för att skydda data och identiteter och enheter som har åtkomst till dina data.</span><span class="sxs-lookup"><span data-stu-id="56c27-147">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="56c27-148">Det här är vanligtvis den största delen av organisationens data som hanteras av de flesta av användarna.</span><span class="sxs-lookup"><span data-stu-id="56c27-148">This is typically most of your organization's data managed by most of your users.</span></span> | <span data-ttu-id="56c27-149">Grupper för personal som jobbar på fältet och med kunder, till exempel försäljning, marknadsföring, support, administration och tillverkning.</span><span class="sxs-lookup"><span data-stu-id="56c27-149">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="56c27-150">Känslig</span><span class="sxs-lookup"><span data-stu-id="56c27-150">Sensitive</span></span> | <span data-ttu-id="56c27-151">Det här är ytterligare skydd för en underuppsättning av dina data som måste skyddas mer än på grundläggande nivå.</span><span class="sxs-lookup"><span data-stu-id="56c27-151">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="56c27-152">Dessa grupper innehåller användare som använder och skapar känsliga data som är avsedda för avdelningar och projekt som inte är avsedda att bli tillgängliga för alla.</span><span class="sxs-lookup"><span data-stu-id="56c27-152">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="56c27-153">Produkt- eller marknadsgrupper som utvecklar kommande produkter</span><span class="sxs-lookup"><span data-stu-id="56c27-153">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="56c27-154">Strikt reglerad</span><span class="sxs-lookup"><span data-stu-id="56c27-154">Highly regulated</span></span> | <span data-ttu-id="56c27-155">Det här är den högsta skyddsnivån för en liten mängd data som är strikt sekretessbelagda, vilka kan vara intellektuella egendomar eller affärshemligheter eller data som måste följa säkerhetsföreskrifter.</span><span class="sxs-lookup"><span data-stu-id="56c27-155">This is the highest level of protection for a typically small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to security regulations.</span></span> |  <span data-ttu-id="56c27-156">Forskningsteam och juridiska och ekonomiska team, eller team som lagrar eller använder kund- eller partnerdata.</span><span class="sxs-lookup"><span data-stu-id="56c27-156">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="56c27-157">Hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="56c27-157">Hybrid identity</span></span>

<span data-ttu-id="56c27-158">Om du har en lokal AD DS-domän måste du synkronisera uppsättningen användarkonton, grupper och kontakter för din domän med Azure AD-klientorganisationen för din Microsoft 365 för företag-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="56c27-158">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 for enterprise subscription.</span></span> <span data-ttu-id="56c27-159">För andra än stora företag konfigurerar du Azure AD Connect på en server med synkronisering av lösenordshash (PHS).</span><span class="sxs-lookup"><span data-stu-id="56c27-159">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="56c27-160">Mer information finns i [Synkronisera identiteter](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="56c27-160">See [Synchronize identities](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="56c27-161">Säkrare användaråtkomst med principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="56c27-161">More secure user access with Conditional Access policies</span></span>

<span data-ttu-id="56c27-162">Med Azure AD utvärderas villkoren för användarinloggningar, och principer för villkorsstyrd åtkomst kan användas för att bevilja eller neka åtkomst och för att vidta fler åtgärder som måste utföras för att slutföra inloggningen.</span><span class="sxs-lookup"><span data-stu-id="56c27-162">Azure AD evaluates the conditions of user sign-ins and can use Conditional Access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="56c27-163">Om till exempel Azure AD fastställer att inloggningen sker under medelhög eller hög risknivå, kan det krävas att användaren utför MFA för att slutföra inloggningen.</span><span class="sxs-lookup"><span data-stu-id="56c27-163">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="56c27-164">Du kan använda principer för villkorsstyrd åtkomst för användarkonton eller grupper.</span><span class="sxs-lookup"><span data-stu-id="56c27-164">You apply Conditional Access policies to user accounts or groups.</span></span> <span data-ttu-id="56c27-165">Om du vill göra det enklare att använda principer för villkorsstyrd åtkomst skapar du följande Azure AD-säkerhetsgrupper i din organisation:</span><span class="sxs-lookup"><span data-stu-id="56c27-165">To facilitate an easier assignment of Conditional Access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="56c27-166">BASELINE</span><span class="sxs-lookup"><span data-stu-id="56c27-166">BASELINE</span></span>

  <span data-ttu-id="56c27-167">Innehåller grupper eller användarkonton för användare med åtkomst till grundläggande data.</span><span class="sxs-lookup"><span data-stu-id="56c27-167">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="56c27-168">SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="56c27-168">SENSITIVE</span></span>

  <span data-ttu-id="56c27-169">Innehåller grupper eller användarkonton för användare med åtkomst till känsliga data.</span><span class="sxs-lookup"><span data-stu-id="56c27-169">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="56c27-170">HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-170">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="56c27-171">Innehåller grupper eller användarkonton för användare med åtkomst till strikt reglerade data.</span><span class="sxs-lookup"><span data-stu-id="56c27-171">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="56c27-172">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="56c27-172">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="56c27-173">En tom grupp som du kan använda för att tillfälligt undanta en användare från principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="56c27-173">An empty group that you can use to temporarily exclude a user from Conditional Access policies.</span></span>

<span data-ttu-id="56c27-174">Här följer en lista över principer för villkorsstyrd åtkomst i Azure AD att aktivera eller skapa.</span><span class="sxs-lookup"><span data-stu-id="56c27-174">Here is the list of Azure AD Conditional Access policies to enable or create.</span></span>

| <span data-ttu-id="56c27-175">Princip för villkorsstyrd åtkomst i Azure AD</span><span class="sxs-lookup"><span data-stu-id="56c27-175">Azure AD Conditional Access policy</span></span> | <span data-ttu-id="56c27-176">Grupper som den gäller för</span><span class="sxs-lookup"><span data-stu-id="56c27-176">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="56c27-177">Grundläggande princip: Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="56c27-177">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="56c27-178">Principen gäller för administratörsroller, så inga grupper måste anges.</span><span class="sxs-lookup"><span data-stu-id="56c27-178">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="56c27-179">Principen behöver bara aktiveras.</span><span class="sxs-lookup"><span data-stu-id="56c27-179">This policy just needs to be enabled.</span></span> <span data-ttu-id="56c27-180">Alla efterföljande principer måste skapas och aktiveras.</span><span class="sxs-lookup"><span data-stu-id="56c27-180">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="56c27-181">Blockera klienter som inte har stöd för modern autentisering</span><span class="sxs-lookup"><span data-stu-id="56c27-181">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="56c27-182">Välj Alla användare i principinställningarna.</span><span class="sxs-lookup"><span data-stu-id="56c27-182">Select "All users" in the policy settings.</span></span> |
| <span data-ttu-id="56c27-183">Kräv MFA när inloggningsrisken är medelhög eller hög (kräver Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="56c27-183">Require MFA when sign-in risk is medium or high (requires Microsoft 365 E5)</span></span> | <span data-ttu-id="56c27-184">BASELINE</span><span class="sxs-lookup"><span data-stu-id="56c27-184">BASELINE</span></span> |
| <span data-ttu-id="56c27-185">Kräv MFA när inloggningsrisken är låg, medel eller hög (kräver Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="56c27-185">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 E5)</span></span> | <span data-ttu-id="56c27-186">SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="56c27-186">SENSITIVE</span></span> |
| <span data-ttu-id="56c27-187">Kräv alltid MFA</span><span class="sxs-lookup"><span data-stu-id="56c27-187">Always require MFA</span></span> | <span data-ttu-id="56c27-188">HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-188">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="56c27-189">Kräv godkända appar på iOS- och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="56c27-189">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="56c27-190">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-190">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="56c27-191">Kräv kompatibla PC-datorer</span><span class="sxs-lookup"><span data-stu-id="56c27-191">Require compliant PCs</span></span> | <span data-ttu-id="56c27-192">BASELINE</span><span class="sxs-lookup"><span data-stu-id="56c27-192">BASELINE</span></span> |
| <span data-ttu-id="56c27-193">Kräv kompatibla PC-datorer och iOS- och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="56c27-193">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="56c27-194">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-194">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="56c27-195">Det här är användarriskprincipen Azure AD Identity Protection (kräver Microsoft 365 E5) som du kan skapa och aktivera.</span><span class="sxs-lookup"><span data-stu-id="56c27-195">Here is the Azure AD Identity Protection (requires Microsoft 365 E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="56c27-196">Användarriskprincipen Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="56c27-196">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="56c27-197">Grupper som den gäller för</span><span class="sxs-lookup"><span data-stu-id="56c27-197">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="56c27-198">Användare med hög risk måste byta lösenord</span><span class="sxs-lookup"><span data-stu-id="56c27-198">High risk users must change passwords</span></span> | <span data-ttu-id="56c27-199">Välj Alla användare i principinställningarna.</span><span class="sxs-lookup"><span data-stu-id="56c27-199">Select "All users" in the policy settings.</span></span> |
|||

<span data-ttu-id="56c27-200">Mer information finns i [Vanliga principer för identitets- och enhetsåtkomst](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="56c27-200">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="56c27-201">Grupper för enklare hantering</span><span class="sxs-lookup"><span data-stu-id="56c27-201">Groups for easier management</span></span>

<span data-ttu-id="56c27-202">Här är några av de funktioner som kan göra grupp- och licenshantering lättare för dig.</span><span class="sxs-lookup"><span data-stu-id="56c27-202">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="56c27-203">Funktion</span><span class="sxs-lookup"><span data-stu-id="56c27-203">Feature</span></span> | <span data-ttu-id="56c27-204">Användning</span><span class="sxs-lookup"><span data-stu-id="56c27-204">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="56c27-205">Grupphantering för självbetjäning</span><span class="sxs-lookup"><span data-stu-id="56c27-205">Self-service group management</span></span> | <span data-ttu-id="56c27-206">Tillåt hantering av Azure AD-grupper för gruppägare istället för IT-personal.</span><span class="sxs-lookup"><span data-stu-id="56c27-206">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="56c27-207">Mer information finns i [Grupphantering för självbetjäning](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups).</span><span class="sxs-lookup"><span data-stu-id="56c27-207">See [Self-service group management](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="56c27-208">Dynamiskt gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="56c27-208">Dynamic group membership</span></span> | <span data-ttu-id="56c27-209">Konfigurera automatiskt tillägg eller borttagning av användarkonton från Azure AD-grupper baserat på användarkontons attribut, t.ex. avdelning eller land.</span><span class="sxs-lookup"><span data-stu-id="56c27-209">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="56c27-210">Mer information finns i [Dynamiskt gruppmedlemskap](identity-use-group-management.md#set-up-dynamic-group-membership).</span><span class="sxs-lookup"><span data-stu-id="56c27-210">See [Dynamic group membership](identity-use-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="56c27-211">Gruppbaserad licensiering</span><span class="sxs-lookup"><span data-stu-id="56c27-211">Group-based licensing</span></span> | <span data-ttu-id="56c27-212">Använd gruppmedlemskap för att automatiskt tilldela eller ta bort licenser för användarkonton.</span><span class="sxs-lookup"><span data-stu-id="56c27-212">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="56c27-213">Mer information finns i [Gruppbaserad licensiering](identity-use-group-management.md#set-up-automatic-licensing).</span><span class="sxs-lookup"><span data-stu-id="56c27-213">See [Group-based licensing](identity-use-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="56c27-214">Om du använder gruppbaserad licensiering kan du skapa en grupp med namnet LICENSED för användarkontonamn som tilldelats en Microsoft 365 för företag-licens.</span><span class="sxs-lookup"><span data-stu-id="56c27-214">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 for enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="56c27-215">Övervaka användaråtkomst</span><span class="sxs-lookup"><span data-stu-id="56c27-215">Monitor user access</span></span>

<span data-ttu-id="56c27-216">Om du har Microsoft 365 E5 kan du med hjälp av Azure AD Identity Protection övervaka och analysera användarinloggningar för att upptäcka angrepp mot autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="56c27-216">If you have Microsoft 365 E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="56c27-217">Mer information finns i [Skydda mot obehörig inloggning](identity-secure-user-sign-ins.md#protect-against-credential-compromise).</span><span class="sxs-lookup"><span data-stu-id="56c27-217">See [Protect against credential compromise](identity-secure-user-sign-ins.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="56c27-218">Din konfiguration hittills</span><span class="sxs-lookup"><span data-stu-id="56c27-218">Your configuration so far</span></span>

<span data-ttu-id="56c27-219">Här är en visuell sammanfattning av identitetsfasen för hybrididentitet, med befintliga och nya element markerade.</span><span class="sxs-lookup"><span data-stu-id="56c27-219">Here is a visual summary of the Identity phase for hybrid identity, with existing and new elements highlighted.</span></span>

![Din organisation efter identitetsfasen för hybrididentitet](../media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="56c27-221">De nya och markerade hybrididentitetselementen inkluderar:</span><span class="sxs-lookup"><span data-stu-id="56c27-221">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![En lokal AD DS-domän med användarkonton och grupper](../media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="56c27-223">En lokal AD DS-domän med användarkonton och grupper.</span><span class="sxs-lookup"><span data-stu-id="56c27-223">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![En Windows-baserad server med Azure AD Connect](../media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="56c27-225">En Windows-baserad server med Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="56c27-225">A Windows-based server running Azure AD Connect.</span></span> |
| ![Synkroniserad uppsättning av AD DS-användarkonton och grupper i Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="56c27-227">Synkroniserad uppsättning av AD DS-användarkonton och grupper i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56c27-227">The synchronized set of AD DS user accounts and groups in Azure AD.</span></span> |
| ![Azure AD-inställningar för autentisering, skydd av globala konton och enklare hantering av grupper och licenser](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="56c27-229">Azure AD-inställningar för autentisering, skydd av globala konton och enklare hantering av grupper och licenser.</span><span class="sxs-lookup"><span data-stu-id="56c27-229">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![Principer för villkorsstyrd åtkomst i Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="56c27-231">Principer för villkorsstyrd åtkomst i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56c27-231">Azure AD Conditional Access policies.</span></span> |
|||

<span data-ttu-id="56c27-232">Här är en visuell sammanfattning av fasen för helt molnbaserad identitet, med nya element markerade.</span><span class="sxs-lookup"><span data-stu-id="56c27-232">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![Din organisation efter identitetsfasen för helt molnbaserad identitet](../media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="56c27-234">De nya och markerade elementen för helt molnbaserad identitet inbegriper:</span><span class="sxs-lookup"><span data-stu-id="56c27-234">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![Användarkonton och grupper i Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts-cloud-only.png) | <span data-ttu-id="56c27-236">Användarkonton och grupper i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56c27-236">The user accounts and groups in Azure AD.</span></span> |
| ![Azure AD-inställningar för autentisering, skydd av globala konton och enklare hantering av grupper och licenser](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="56c27-238">Azure AD-inställningar för autentisering, skydd av globala konton och enklare hantering av grupper och licenser.</span><span class="sxs-lookup"><span data-stu-id="56c27-238">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![Principer för villkorsstyrd åtkomst i Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="56c27-240">Principer för villkorsstyrd åtkomst i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56c27-240">Azure AD Conditional Access policies.</span></span> |
|||

## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="56c27-241">Fas 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="56c27-241">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="56c27-242">Här är dina alternativ för att säkerställa att dina Windows 10 Enterprise-enheter är integrerade i identitets- och säkerhetsinfrastrukturen för Microsoft 365 för företag:</span><span class="sxs-lookup"><span data-stu-id="56c27-242">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365 for enterprise, here are your options:</span></span>

- <span data-ttu-id="56c27-243">Hybrid (du har en lokal AD DS-domän)</span><span class="sxs-lookup"><span data-stu-id="56c27-243">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="56c27-244">Varje befintlig Windows 10 Enterprise-enhet som redan är ansluten till din AD DS-domän, ska du ansluta till Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="56c27-244">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="56c27-245">Mer information finns i [Konfigurera hybridanslutna Azure Active Directory-enheter](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="56c27-245">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="56c27-246">Varje ny Windows 10 Enterprise-enhet ska du ansluta till din AD DS-domän, och sedan ansluta dem till Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="56c27-246">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="56c27-247">Varje Windows 10 Enterprise-enhet ska du registrera för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="56c27-247">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="56c27-248">Anvisningar finns i [Registrera en Windows 10-enhet med Intune med hjälp av en grupprincip](https://go.microsoft.com/fwlink/p/?linkid=872871).</span><span class="sxs-lookup"><span data-stu-id="56c27-248">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="56c27-249">Endast molnet (du har inte en lokal AD DS-domän)</span><span class="sxs-lookup"><span data-stu-id="56c27-249">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="56c27-250">Anslut varje Windows 10 Enterprise-enhet till Azure AD-klientorganisationen för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="56c27-250">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="56c27-251">Mer information finns [Ansluta din arbetsenhet till organisationens nätverk](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network).</span><span class="sxs-lookup"><span data-stu-id="56c27-251">See [Join your work device to your organization's network](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="56c27-252">När du har installerat och anslutit, installerar varje Windows 10 Enterprise-enhet automatiskt uppdateringar från molntjänsten Windows Update för företag.</span><span class="sxs-lookup"><span data-stu-id="56c27-252">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="56c27-253">Det finns vanligtvis inget behov av att konfigurera en infrastruktur för distribution och installation av Windows 10-uppdateringar i organisationer som inte är stora företag.</span><span class="sxs-lookup"><span data-stu-id="56c27-253">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="56c27-254">Din konfiguration hittills</span><span class="sxs-lookup"><span data-stu-id="56c27-254">Your configuration so far</span></span>

<span data-ttu-id="56c27-255">Här är en visuell sammanfattning av Windows 10 Enterprise-fasen med nya element markerade.</span><span class="sxs-lookup"><span data-stu-id="56c27-255">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![Din organisation efter Windows 10 Enterprise-fasen](../media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="56c27-257">De nya och markerade Windows 10 Enterprise-elementen inkluderar:</span><span class="sxs-lookup"><span data-stu-id="56c27-257">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![Windows 10 Enterprise installerat på Windows-enheter](../media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="56c27-259">Windows 10 Enterprise installerat på Windows-enheter, med en lokal bärbar dator som exempel.</span><span class="sxs-lookup"><span data-stu-id="56c27-259">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![Volume Licensing Service Center](../media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="56c27-261">Volume Licensing Service Center, som innehåller avbildningar för nya installationer av Windows 10 Enterprise, och tjänsten Windows Update för företag, som innehåller de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="56c27-261">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="56c27-262">Fas 4: Microsoft 365-applikationer för företag</span><span class="sxs-lookup"><span data-stu-id="56c27-262">Phase 4: Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="56c27-263">Microsoft 365 Enterprise innehåller Microsoft 365-applikationer för företag, prenumerationsversionen av Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="56c27-263">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="56c27-264">Som Office 2016 eller Office 2019 installeras Microsoft 365-applikationer för företag direkt på dina klientenheter.</span><span class="sxs-lookup"><span data-stu-id="56c27-264">Like Office 2016 or Office 2019, Microsoft 365 Apps for enterprise is installed directly on your client devices.</span></span> <span data-ttu-id="56c27-265">Microsoft 365-applikationer för företag får däremot regelbundet uppdateringar som innehåller nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="56c27-265">However, Microsoft 365 Apps for enterprise receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="56c27-266">Mer information finns i [Om Microsoft 365-applikationer för företag i företaget](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="56c27-266">See [About Microsoft 365 Apps for enterprise in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="56c27-267">För andra organisationer än stora företag installerar du Microsoft 365-applikationer för företag manuellt på enheterna, som kan omfatta Windows-, iOS- och Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="56c27-267">For your non-enterprise organization, you manually install Microsoft 365 Apps for enterprise on devices, which can include Windows, iOS, and Android devices.</span></span> <span data-ttu-id="56c27-268">Detta kan göras som en del av att förbereda en ny enhet för användning, eller av användaren som en del av introduktionsprocessen.</span><span class="sxs-lookup"><span data-stu-id="56c27-268">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="56c27-269">I båda fallen loggar administratören eller användaren in på Office 365-portalen på https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="56c27-269">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="56c27-270">På fliken **Microsoft Office Home** klickar du på **Installera Office** och genomför installationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="56c27-270">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="56c27-271">Funktionsuppdateringar för Microsoft 365-applikationer för företag laddas ned varje månad av alla datorer där de är installerade.</span><span class="sxs-lookup"><span data-stu-id="56c27-271">Feature updates to Microsoft 365 Apps for enterprise are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="56c27-272">Det finns vanligtvis inget behov av att konfigurera en infrastruktur för distribution av uppdateringar för Microsoft 365-applikationer för företag i organisationer som inte är stora företag.</span><span class="sxs-lookup"><span data-stu-id="56c27-272">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Microsoft 365 Apps for enterprise updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="56c27-273">Din konfiguration hittills</span><span class="sxs-lookup"><span data-stu-id="56c27-273">Your configuration so far</span></span>

<span data-ttu-id="56c27-274">Här är en visuell sammanfattning av fasen för Microsoft 365-applikationer för företag med nya element markerade.</span><span class="sxs-lookup"><span data-stu-id="56c27-274">Here is a visual summary of the Microsoft 365 Apps for enterprise phase with the new elements highlighted.</span></span>

![Din organisation efter fasen för Microsoft 365-applikationer för företag](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="56c27-276">De nya och markerade elementen för Microsoft 365-applikationer för företag omfattar:</span><span class="sxs-lookup"><span data-stu-id="56c27-276">The new and highlighted Microsoft 365 Apps for enterprise elements include:</span></span>
 
|||
|:------:|:-----|
| ![Microsoft 365-applikationer för företag installerat på enheter](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="56c27-278">Microsoft 365-applikationer för företag installerat på enheter, med en lokal bärbar dator som exempel.</span><span class="sxs-lookup"><span data-stu-id="56c27-278">Microsoft 365 Apps for enterprise installed on devices, with an on-premises laptop as an example.</span></span> |
| ![Office Content Delivery Network (CDN) för Microsoft 365-applikationer för företag](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="56c27-280">Office Content Delivery Network (CDN) för Microsoft 365-applikationer för företag, som enheterna har tillgång till för uppdateringar för Microsoft 365-applikationer för företag.</span><span class="sxs-lookup"><span data-stu-id="56c27-280">The Office Content Delivery Network (CDN) for Microsoft 365 Apps for enterprise, which devices access for Microsoft 365 Apps for enterprise updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="56c27-281">Fas 5: Hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="56c27-281">Phase 5: Mobile device management</span></span>

<span data-ttu-id="56c27-282">Microsoft 365 för företag innehåller Microsoft Intune för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="56c27-282">Microsoft 365 for enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="56c27-283">Med Intune kan du hantera enheter för Windows, iOS, Android och macOS och skydda åtkomsten till organisationens resurser, inklusive data.</span><span class="sxs-lookup"><span data-stu-id="56c27-283">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="56c27-284">I Intune används användar-, grupp- och datorkonton för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56c27-284">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="56c27-285">Intune tillhandahåller två typer av hantering av mobila enheter:</span><span class="sxs-lookup"><span data-stu-id="56c27-285">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="56c27-286">MDM (Mobile Device Management) är när enheter registreras i Intune.</span><span class="sxs-lookup"><span data-stu-id="56c27-286">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="56c27-287">När de har registrerats är de hanterade enheter och kan ta emot principer, regler och inställningar som används av din organisation.</span><span class="sxs-lookup"><span data-stu-id="56c27-287">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="56c27-288">Dessa typer av enheter ägs vanligtvis av din organisation och utfärdas till dina anställda.</span><span class="sxs-lookup"><span data-stu-id="56c27-288">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="56c27-289">Användare med egna personliga enheter kanske inte vill registrera sina enheter eller att de hanteras av Intune med dina principer och inställningar.</span><span class="sxs-lookup"><span data-stu-id="56c27-289">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="56c27-290">Men du måste ändå skydda organisationens resurser och data.</span><span class="sxs-lookup"><span data-stu-id="56c27-290">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="56c27-291">I det här scenariot kan du skydda dina appar med MAM (hantering av mobilprogram).</span><span class="sxs-lookup"><span data-stu-id="56c27-291">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="56c27-292">Intune-principer kan upprätthålla enhetsefterlevnad och programskydd.</span><span class="sxs-lookup"><span data-stu-id="56c27-292">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="56c27-293">Här följer en lista över Intune-principer som du kan skapa.</span><span class="sxs-lookup"><span data-stu-id="56c27-293">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="56c27-294">Intune-principer</span><span class="sxs-lookup"><span data-stu-id="56c27-294">Intune policies</span></span> | <span data-ttu-id="56c27-295">Grupper som den gäller för</span><span class="sxs-lookup"><span data-stu-id="56c27-295">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="56c27-296">Policy för enhetsefterlevnad för Windows</span><span class="sxs-lookup"><span data-stu-id="56c27-296">Device compliance policy for Windows</span></span> | <span data-ttu-id="56c27-297">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-297">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="56c27-298">Policy för enhetsefterlevnad för iOS</span><span class="sxs-lookup"><span data-stu-id="56c27-298">Device compliance policy for iOS</span></span> | <span data-ttu-id="56c27-299">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-299">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="56c27-300">Enhetsefterlevnad för macOS</span><span class="sxs-lookup"><span data-stu-id="56c27-300">Device compliance for macOS</span></span> | <span data-ttu-id="56c27-301">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-301">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="56c27-302">Policy för enhetsefterlevnad för Android och Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="56c27-302">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="56c27-303">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-303">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="56c27-304">Appskyddsprincip för iOS</span><span class="sxs-lookup"><span data-stu-id="56c27-304">App protection policy for iOS</span></span> | <span data-ttu-id="56c27-305">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-305">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="56c27-306">Appskyddsprincip för macOS</span><span class="sxs-lookup"><span data-stu-id="56c27-306">App protection policy for macOS</span></span> | <span data-ttu-id="56c27-307">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-307">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="56c27-308">Appskyddsprincip för Android och Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="56c27-308">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="56c27-309">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-309">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="56c27-310">Mer information finns i [Vanliga principer för identitets- och enhetsåtkomst](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="56c27-310">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="56c27-311">Din konfiguration hittills</span><span class="sxs-lookup"><span data-stu-id="56c27-311">Your configuration so far</span></span>

<span data-ttu-id="56c27-312">Här är en visuell sammanfattning av fasen för hantering av mobila enheter, med nya element markerade.</span><span class="sxs-lookup"><span data-stu-id="56c27-312">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![Din organisation efter fasen för hantering av mobila enheter](../media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="56c27-314">De nya och markerade elementen för hantering av mobila enheter inkluderar:</span><span class="sxs-lookup"><span data-stu-id="56c27-314">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![Enheter som är registrerade i Intune](../media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="56c27-316">Enheter som är registrerade i Intune, som visar en lokal bärbar dator med Windows 10 Enterprise som exempel.</span><span class="sxs-lookup"><span data-stu-id="56c27-316">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![Intune-principer för enhetsefterlevnad och programskydd](../media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="56c27-318">Intune-principer för enhetsefterlevnad och programskydd.</span><span class="sxs-lookup"><span data-stu-id="56c27-318">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="56c27-319">Fas 6: Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="56c27-319">Phase 6: Information protection</span></span>

<span data-ttu-id="56c27-320">Microsoft 365 för företag har en mängd funktioner för informationsskydd som gör att du kan hantera klassificering av data på olika sätt genom att tillämpa olika nivåer av styrning, säkerhet och skydd.</span><span class="sxs-lookup"><span data-stu-id="56c27-320">Microsoft 365 for enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="56c27-321">Normal korrespondens mellan de flesta anställda och de dokument som de arbetar med behöver till exempel en viss grundläggande skyddsnivå.</span><span class="sxs-lookup"><span data-stu-id="56c27-321">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="56c27-322">Ekonomiposter, kunddata och intellektuell egendom kräver en högre skyddsnivå.</span><span class="sxs-lookup"><span data-stu-id="56c27-322">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="56c27-323">Det första steget för en strategi för informationsskydd är att fastställa skyddsnivåer.</span><span class="sxs-lookup"><span data-stu-id="56c27-323">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="56c27-324">Många organisationer använder de här nivåerna, som redan används för principer för villkorsstyrd åtkomst:</span><span class="sxs-lookup"><span data-stu-id="56c27-324">Many organizations use these levels, which are already being used for Conditional Access policies:</span></span>

- <span data-ttu-id="56c27-325">Grundläggande</span><span class="sxs-lookup"><span data-stu-id="56c27-325">Baseline</span></span>

  <span data-ttu-id="56c27-326">Exempel är normal företagskommunikation (e-post) och filer för administrations-, försäljnings- och supportpersonal.</span><span class="sxs-lookup"><span data-stu-id="56c27-326">Examples include normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="56c27-327">Känslig</span><span class="sxs-lookup"><span data-stu-id="56c27-327">Sensitive</span></span>

  <span data-ttu-id="56c27-328">Exempel är ekonomisk och juridisk information och data för forskning och utveckling för nya produkter eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="56c27-328">Examples include financial and legal information and research and development data for new products or services.</span></span>

- <span data-ttu-id="56c27-329">Strikt reglerad</span><span class="sxs-lookup"><span data-stu-id="56c27-329">Highly regulated</span></span>

  <span data-ttu-id="56c27-330">I exemplen ingår personligt identifierbar information om kunder och partner och organisationens strategiska planer eller intellektuella egendom.</span><span class="sxs-lookup"><span data-stu-id="56c27-330">Examples include customer and partner personally identifiable information and your organization's strategic plans or intellectual property.</span></span>

<span data-ttu-id="56c27-331">Baserat på dessa datasäkerhetsnivåer är nästa steg att identifiera och implementera:</span><span class="sxs-lookup"><span data-stu-id="56c27-331">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="56c27-332">Vanliga typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="56c27-332">Custom sensitive information types</span></span>

  <span data-ttu-id="56c27-333">Microsoft 365 tillhandahåller ett brett urval av olika typer av känslig information, t.ex. sjukvård och kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="56c27-333">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="56c27-334">Om du inte hittar den du behöver i den angivna listan kan du skapa din egen.</span><span class="sxs-lookup"><span data-stu-id="56c27-334">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="56c27-335">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="56c27-335">Retention labels</span></span>

  <span data-ttu-id="56c27-336">Om du vill följa organisationens principer och regionala bestämmelser kan du behöva ange hur länge vissa typer av dokument eller dokument med specifikt innehåll ska behållas.</span><span class="sxs-lookup"><span data-stu-id="56c27-336">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="56c27-337">Du kan implementera det för e-post och dokument med hjälp av kvarhållningsetiketter.</span><span class="sxs-lookup"><span data-stu-id="56c27-337">You can implement this for email and documents using retention labels.</span></span> <span data-ttu-id="56c27-338">Kvarhållningsetiketter kan också användas tillsammans med DLP-principer (dataförlustskydd) som kan begränsa delning av filer eller e-post utanför din organisation.</span><span class="sxs-lookup"><span data-stu-id="56c27-338">Retention labels can also be used in conjunction with Data Loss Prevention (DLP) policies that can restrict the sharing of files or email outside your organization.</span></span>

- <span data-ttu-id="56c27-339">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="56c27-339">Sensitivity labels</span></span>

  <span data-ttu-id="56c27-340">Du kan märka e-post eller dokument med en beskrivande känslighetsetikett så att ytterligare säkerhetsnivåer kan tillämpas.</span><span class="sxs-lookup"><span data-stu-id="56c27-340">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="56c27-341">Exempel är vattenstämplar, kryptering och behörigheter, som anger vem som har behörighet att komma åt e-postmeddelandet eller dokumentet och vad de har tillåtelse att göra.</span><span class="sxs-lookup"><span data-stu-id="56c27-341">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="56c27-342">Mer information finns i [Klassificeringstyper i Microsoft 365](infoprotect-configure-classification.md#microsoft-365-classification-types).</span><span class="sxs-lookup"><span data-stu-id="56c27-342">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="56c27-343">Om du använder känslighetsetiketter med behörigheter kan du behöva skapa ytterligare säkerhetsgrupper för att definiera vem som får göra vad med e-post och dokument som har tillämpade känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="56c27-343">If you use sensitivity labels with permissions, you might have to create additional security groups to define who is allowed to do what with email and documents that have the sensitivity label applied.</span></span> 

<span data-ttu-id="56c27-344">Du måste till exempel skapa känslighetsetiketten RESEARCH för att skydda e-post och dokument i forskningsteam.</span><span class="sxs-lookup"><span data-stu-id="56c27-344">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="56c27-345">Du fastställer att:</span><span class="sxs-lookup"><span data-stu-id="56c27-345">You determine that:</span></span>

- <span data-ttu-id="56c27-346">Forskare måste ha möjlighet att ändra dokument som har markerats med känslighetsetiketten RESEARCH.</span><span class="sxs-lookup"><span data-stu-id="56c27-346">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="56c27-347">Medarbetare som inte är forskare bara ska ha möjlighet att visa dokument som har markerats med känslighetsetiketten RESEARCH.</span><span class="sxs-lookup"><span data-stu-id="56c27-347">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="56c27-348">Det innebär att du måste skapa och hantera två ytterligare Microsoft 365-grupper:</span><span class="sxs-lookup"><span data-stu-id="56c27-348">This means you need to create and manage two additional Microsoft 365 groups:</span></span>

- <span data-ttu-id="56c27-349">RESEARCH-ALL</span><span class="sxs-lookup"><span data-stu-id="56c27-349">RESEARCH-ALL</span></span>
- <span data-ttu-id="56c27-350">RESEARCH-VIEW</span><span class="sxs-lookup"><span data-stu-id="56c27-350">RESEARCH-VIEW</span></span>

<span data-ttu-id="56c27-351">Dessa grupper och deras behörigheter blir en del av konfigurationen för känslighetsetiketten RESEARCH.</span><span class="sxs-lookup"><span data-stu-id="56c27-351">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="56c27-352">För känslighetsetiketter som konfigurerats med gruppbaserade behörigheter, måste du hantera medlemskap för dessa grupper.</span><span class="sxs-lookup"><span data-stu-id="56c27-352">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="56c27-353">Din konfiguration hittills</span><span class="sxs-lookup"><span data-stu-id="56c27-353">Your configuration so far</span></span>

<span data-ttu-id="56c27-354">Här är en visuell sammanfattning av fasen för informationsskydd med nya element markerade.</span><span class="sxs-lookup"><span data-stu-id="56c27-354">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![Din organisation efter informationsskyddsfasen](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="56c27-356">De nya och markerade elementen för informationsskydd inkluderar:</span><span class="sxs-lookup"><span data-stu-id="56c27-356">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![Känslighetsetiketter för de tre säkerhetsnivåerna](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="56c27-358">Känslighetsetiketter för de tre säkerhetsnivåerna som användare kan använda för dokument och e-post.</span><span class="sxs-lookup"><span data-stu-id="56c27-358">Sensitivity labels for the three levels of security that users can apply to documents and email.</span></span> |
|||

<span data-ttu-id="56c27-359">Anpassade informationstyper och kvarhållningsetiketter visas inte.</span><span class="sxs-lookup"><span data-stu-id="56c27-359">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="56c27-360">Introduktioner</span><span class="sxs-lookup"><span data-stu-id="56c27-360">Onboarding</span></span>

<span data-ttu-id="56c27-361">Med din infrastruktur för Microsoft 365 för företag kan du enkelt introducera dina anställda.</span><span class="sxs-lookup"><span data-stu-id="56c27-361">With your Microsoft 365 for enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="56c27-362">En ny Windows 10 Enterprise-enhet</span><span class="sxs-lookup"><span data-stu-id="56c27-362">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="56c27-363">Innan du ger en anställd en ny Windows 10 Enterprise-enhet:</span><span class="sxs-lookup"><span data-stu-id="56c27-363">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="56c27-364">För hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="56c27-364">For hybrid identity</span></span>

  <span data-ttu-id="56c27-365">Anslut enheten till AD DS-domänen, anslut enheten till Azure AD-klientorganisationen och registrera sedan enheten i Intune.</span><span class="sxs-lookup"><span data-stu-id="56c27-365">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="56c27-366">För identitet endast för molnet</span><span class="sxs-lookup"><span data-stu-id="56c27-366">For cloud-only identity</span></span>

  <span data-ttu-id="56c27-367">Anslut enheten till Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="56c27-367">Join the device to your Azure AD tenant.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="56c27-368">Befintlig anställd med ett AD DS-användarkonto</span><span class="sxs-lookup"><span data-stu-id="56c27-368">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="56c27-369">Som en del av den första introduktionen för din organisation vid användning av hybrididentitet, lägger du till AD DS-användarkontot i följande Azure AD-grupper:</span><span class="sxs-lookup"><span data-stu-id="56c27-369">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="56c27-370">LICENSED</span><span class="sxs-lookup"><span data-stu-id="56c27-370">LICENSED</span></span>
- <span data-ttu-id="56c27-371">Lämpliga AD DS- eller Azure AD-säkerhetsgrupper som är medlemmar i Azure AD-grupperna BASELINE, SENSITIVE och HIGHLY-REGULATED </span><span class="sxs-lookup"><span data-stu-id="56c27-371">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="56c27-372">Grupper av känslighetsetiketter (efter behov)</span><span class="sxs-lookup"><span data-stu-id="56c27-372">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="56c27-373">En befintlig anställd ska redan ha lagts till i lämplig arbetsgrupp, avdelning och regional AD DS-grupp.</span><span class="sxs-lookup"><span data-stu-id="56c27-373">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="56c27-374">Du kan lägga till ett användarkonto i flera Azure AD-grupper i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56c27-374">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="56c27-375">Från användarkontots egenskaper klickar du på **Hantera grupper > Lägg till medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="56c27-375">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="56c27-376">Om du vill använda PowerShell kan du läsa den här [nedladdningsbara Excel-arbetsboken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-foundation-infrastructure-non-enterprises/Group-License-Mgmt-PowerShell.xlsx), som genererar PowerShell-kommandon baserat på ett specifikt användarkonto och valda gruppnamn.</span><span class="sxs-lookup"><span data-stu-id="56c27-376">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-foundation-infrastructure-non-enterprises/Group-License-Mgmt-PowerShell.xlsx), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="56c27-377">Ny anställd med ett användarkonto för endast molnet</span><span class="sxs-lookup"><span data-stu-id="56c27-377">New employee with a cloud-only user account</span></span>

<span data-ttu-id="56c27-378">Som en del av den första introduktionen för din organisation vid användning av identitet för endast molnet, lägger du till det nya användarkontot i följande grupper:</span><span class="sxs-lookup"><span data-stu-id="56c27-378">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="56c27-379">LICENSED</span><span class="sxs-lookup"><span data-stu-id="56c27-379">LICENSED</span></span>
- <span data-ttu-id="56c27-380">Lämpliga Azure AD-säkerhetsgrupper som är medlemmar i Azure AD-grupperna BASELINE, SENSITIVE och HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-380">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="56c27-381">Arbetsgrupp, avdelning och regionala grupper</span><span class="sxs-lookup"><span data-stu-id="56c27-381">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="56c27-382">Grupper av känslighetsetiketter (efter behov)</span><span class="sxs-lookup"><span data-stu-id="56c27-382">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="56c27-383">Första inloggning till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56c27-383">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="56c27-384">För första gången som medarbetarna loggar in på Microsoft 365, instruerar du dem att:</span><span class="sxs-lookup"><span data-stu-id="56c27-384">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="56c27-385">Logga in på sina enheter med användarkontouppgifterna.</span><span class="sxs-lookup"><span data-stu-id="56c27-385">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="56c27-386">Logga in på Office 365-portalen med hjälp av en webbläsare på https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="56c27-386">Using a browser, sign in to the Office 365 portal at https://portal.office.com.</span></span>
3. <span data-ttu-id="56c27-387">På **startfliken för Office 365** klickar du på **Installera Office** för att installera Microsoft 365-applikationer för företag på deras enhet.</span><span class="sxs-lookup"><span data-stu-id="56c27-387">From the **Office 365 Home** tab, click **Install Office** to install Microsoft 365 Apps for enterprise on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="56c27-388">Slutresultat</span><span class="sxs-lookup"><span data-stu-id="56c27-388">End results</span></span>

<span data-ttu-id="56c27-389">Här visas resultatet av att konfigurera den grundläggande infrastrukturen för Microsoft 365 för företag för din organisation, som inte är ett större företag.</span><span class="sxs-lookup"><span data-stu-id="56c27-389">Here are the results of configuring the Microsoft 365 for enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="56c27-390">Infrastrukturresultat</span><span class="sxs-lookup"><span data-stu-id="56c27-390">Infrastructure results</span></span>

<span data-ttu-id="56c27-391">Efter utbyggnad och konfiguration av din Microsoft 365 för företag-infrastruktur bör du ha:</span><span class="sxs-lookup"><span data-stu-id="56c27-391">After the build-out and configuration of your Microsoft 365 for enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="56c27-392">En lokal Internetanslutning för vart och ett av dina kontor med tillräcklig bandbredd som tillhandahålls av en Internetleverantör som använder en regional lokal DNS-server.</span><span class="sxs-lookup"><span data-stu-id="56c27-392">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="56c27-393">För hybrididentitet: Azure AD Connect som körs på en server som synkroniserar din lokala AD DS-domän med Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="56c27-393">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="56c27-394">Dessa grupper:</span><span class="sxs-lookup"><span data-stu-id="56c27-394">These groups:</span></span>
  - <span data-ttu-id="56c27-395">LICENSED</span><span class="sxs-lookup"><span data-stu-id="56c27-395">LICENSED</span></span>
  - <span data-ttu-id="56c27-396">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="56c27-396">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="56c27-397">Lämpliga AD DS- eller Azure AD-säkerhetsgrupper som även är medlemmar i Azure AD-grupperna BASELINE, SENSITIVE och HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="56c27-397">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="56c27-398">Arbetsgrupp, avdelning och regionala grupper</span><span class="sxs-lookup"><span data-stu-id="56c27-398">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="56c27-399">Grupper av känslighetsetiketter för Microsoft 365 (efter behov)</span><span class="sxs-lookup"><span data-stu-id="56c27-399">Sensitivity label Microsoft 365 groups (as needed)</span></span>
- <span data-ttu-id="56c27-400">Principer för villkorsstyrd åtkomst för Azure AD-inloggning som använder Azure AD-grupperna BASELINE, SENSITIVE, HIGHLY-REGULATED och COND-ACCESS-EXCLUDE.</span><span class="sxs-lookup"><span data-stu-id="56c27-400">Azure AD sign-in Conditional Access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="56c27-401">Principer för Intune-program och enhetsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="56c27-401">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="56c27-402">Vanliga typer av känslig information (efter behov).</span><span class="sxs-lookup"><span data-stu-id="56c27-402">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="56c27-403">Kvarhållningsetiketter (efter behov).</span><span class="sxs-lookup"><span data-stu-id="56c27-403">Retention labels (as needed).</span></span>
- <span data-ttu-id="56c27-404">Känslighetsetiketter (efter behov).</span><span class="sxs-lookup"><span data-stu-id="56c27-404">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="56c27-405">Här är en visuell sammanfattning av infrastrukturen om organisationen använder hybrididentitet, som inkluderar din AD DS-domän, en Azure AD Connect-server och synkroniserade AD DS-användare och -grupper.</span><span class="sxs-lookup"><span data-stu-id="56c27-405">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![Sammanfattning av infrastrukturen om organisationen använder hybrididentitet](../media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="56c27-407">Här är en visuell sammanfattning av infrastrukturen om organisationen använder helt molnbaserad identitet.</span><span class="sxs-lookup"><span data-stu-id="56c27-407">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![Sammanfattning av infrastrukturen om organisationen använder helt molnbaserad identitet](../media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="56c27-409">Resultat för personal</span><span class="sxs-lookup"><span data-stu-id="56c27-409">Employee results</span></span>

<span data-ttu-id="56c27-410">Efter introduktionen ska varje anställd ha följande:</span><span class="sxs-lookup"><span data-stu-id="56c27-410">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="56c27-411">En fungerande lokal nätverkssökväg från sin enhet till Microsoft 365-molntjänsterna i respektive region.</span><span class="sxs-lookup"><span data-stu-id="56c27-411">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="56c27-412">Ett användarkonto med följande gruppmedlemskap:</span><span class="sxs-lookup"><span data-stu-id="56c27-412">A user account with these group memberships:</span></span>
   - <span data-ttu-id="56c27-413">LICENSED</span><span class="sxs-lookup"><span data-stu-id="56c27-413">LICENSED</span></span>
   - <span data-ttu-id="56c27-414">Lämpliga AD DS- eller Azure AD-säkerhetsgrupper, som även är medlemmar i Azure AD-grupperna BASELINE, SENSITIVE och HIGHLY-REGULATED för principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="56c27-414">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for Conditional Access policies</span></span> 
   - <span data-ttu-id="56c27-415">Lämplig arbetsgrupp, avdelning och regionala grupper</span><span class="sxs-lookup"><span data-stu-id="56c27-415">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="56c27-416">Grupper av känslighetsetiketter för Microsoft 365 (efter behov)</span><span class="sxs-lookup"><span data-stu-id="56c27-416">Sensitivity label Microsoft 365 groups (as needed)</span></span>
- <span data-ttu-id="56c27-417">En Windows 10 Enterprise-enhet som:</span><span class="sxs-lookup"><span data-stu-id="56c27-417">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="56c27-418">är ansluten till Azure AD-klientorganisationen (endast molnet) eller till både Azure AD-klientorganisationen och AD DS-domänen (hybrid).</span><span class="sxs-lookup"><span data-stu-id="56c27-418">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="56c27-419">uppdateras automatiskt med de senaste produkt- och säkerhetsförbättringarna för Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="56c27-419">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="56c27-420">har Microsoft 365-applikationer för företag installerat, som automatiskt uppdateras med de senaste produkt- och säkerhetsförbättringarna för Office-produkter.</span><span class="sxs-lookup"><span data-stu-id="56c27-420">Has Microsoft 365 Apps for enterprise installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="56c27-421">är registrerad i Intune och omfattas av efterlevnads- och appskyddsprinciper för Intune-enheter.</span><span class="sxs-lookup"><span data-stu-id="56c27-421">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="56c27-422">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="56c27-422">Next step</span></span>

<span data-ttu-id="56c27-423">Distribuera dina [arbetsbelastningar och scenarier](deploy-workloads.md) så att de drar nytta av funktioner och konfigurationen i din grundläggande infrastruktur för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="56c27-423">Deploy your [workloads and scenarios](deploy-workloads.md) to take advantage of the features and configuration of your Microsoft 365 for enterprise foundation infrastructure.</span></span>
