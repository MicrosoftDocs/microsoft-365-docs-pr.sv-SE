---
title: 'Fas 2: Avslutsvillkor för identitetsinfrastruktur'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Kontrollera att din konfiguration uppfyller Microsoft 365 Enterprise-villkoren för identitetsbaserade tjänster och infrastruktur.
ms.openlocfilehash: 3706cd84a722e68a8b75274544630719e510345a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632547"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="ca46f-103">Fas 2: Avslutsvillkor för identitetsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="ca46f-103">Phase 2: Identity infrastructure exit criteria</span></span>

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="ca46f-105">Kontrollera att identitetsinfrastrukturen uppfyller följande krav och att du har övervägt de som är valfria.</span><span class="sxs-lookup"><span data-stu-id="ca46f-105">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="ca46f-106">Se också [Krav](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) för ytterligare rekommendationer om identitetsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="ca46f-106">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="ca46f-107">Obligatoriskt: dina globala administratörskonton skyddas</span><span class="sxs-lookup"><span data-stu-id="ca46f-107">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="ca46f-108">Du har [skyddat dina globala administratörskonton](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) för att hindra att autentiseringsuppgifter komprometteras av angripare, vilket kan leda till intrång i din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ca46f-108">You've [protected your global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="ca46f-109">Om du hoppar över det här kravet kan dina globala administratörskonton vara sårbara för attacker och intrång, vilket gör det möjligt för en angripare att få tillgång till dina data i hela systemet och hämta, förstöra eller använda dina data i utpressningssyfte.</span><span class="sxs-lookup"><span data-stu-id="ca46f-109">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="ca46f-110">Vid behov kan [Steg 1](identity-create-protect-global-admins.md#identity-global-admin) hjälpa dig att uppfylla detta krav.</span><span class="sxs-lookup"><span data-stu-id="ca46f-110">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-111">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-111">How to test</span></span>

<span data-ttu-id="ca46f-112">Använd följande steg för att kontrollera att du har skyddat dina globala administratörskonton:</span><span class="sxs-lookup"><span data-stu-id="ca46f-112">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="ca46f-113">Kör det här kommandot i Azure Active Directory PowerShell för Graph vid kommandotolken i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca46f-113">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="ca46f-114">Du bör bara se listan med dedikerade globala administratörskonton.</span><span class="sxs-lookup"><span data-stu-id="ca46f-114">You should see only the list of dedicated global administrator accounts.</span></span>
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="ca46f-115">Logga in med vart och ett av kontona från steg 1.</span><span class="sxs-lookup"><span data-stu-id="ca46f-115">Sign in using each of the accounts from step 1.</span></span> <span data-ttu-id="ca46f-116">Varje inloggning bör kräva Azure-multifaktorautentisering och den starkaste formen av sekundär autentisering som finns tillgänglig i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ca46f-116">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="ca46f-117">Mer information om hur du installerar Azure Active Directory PowerShell för Graph-moduler och loggar in på Office 365 finns under [Ansluta till Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="ca46f-117">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="ca46f-118">Valfritt: du har konfigurerat privilegierad identitetshantering så att den globala administratörsrollen kan användas på begäran</span><span class="sxs-lookup"><span data-stu-id="ca46f-118">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="ca46f-119">Du har använt anvisningarna i [Konfigurera Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) för att aktivera PIM i din Azure AD-klientorganisation och konfigurera dina globala administratörskonton som giltiga administratörer.</span><span class="sxs-lookup"><span data-stu-id="ca46f-119">You've used the instructions in [Configure Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="ca46f-120">Du har också använt rekommendationerna i [Säkrare åtkomst för hybrid- och molndistributioner i Azure AD ](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)för att utveckla en roadmap som säkrar att behörig åtkomst skyddas mot cyberangrepp.</span><span class="sxs-lookup"><span data-stu-id="ca46f-120">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="ca46f-121">Om du hoppar över det här alternativet är dina globala administratörskonton sårbara för fortlöpande online-angrepp, och om de komprometteras kan det innebära att en angripare kan hämta, förstöra eller använda dina känsliga uppgifter i utpressningssyfte.</span><span class="sxs-lookup"><span data-stu-id="ca46f-121">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="ca46f-122">Vid behov kan [Steg 1](identity-create-protect-global-admins.md#identity-pim) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-122">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="ca46f-123">Valfritt: Du har konfigurerat behörighetshantering i Office 365</span><span class="sxs-lookup"><span data-stu-id="ca46f-123">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="ca46f-124">Du har använt informationen i [Konfigurera behörighetshantering i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) för att aktivera behörighet och skapa en eller flera policyer för behörig åtkomst inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-124">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="ca46f-125">Du har konfigurerat dessa principer och just-in-time-åtkomst är aktiverad för åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="ca46f-125">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="ca46f-126">Vid behov kan [Steg 1](identity-create-protect-global-admins.md#identity-pam) hjälpa dig att uppfylla detta krav.</span><span class="sxs-lookup"><span data-stu-id="ca46f-126">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="ca46f-127">Valfritt: Azure AD-lösenordsskydd förbjuder användning av svaga lösenord</span><span class="sxs-lookup"><span data-stu-id="ca46f-127">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="ca46f-128">Du har aktiverat förbudet mot svaga lösenord [i molnet](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) och för dina [lokala AD DS (Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) för globalt blockerade lösenord och, om du vill, anpassade termer.</span><span class="sxs-lookup"><span data-stu-id="ca46f-128">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="ca46f-129">Vid behov kan [Steg 2](identity-secure-your-passwords.md#identity-password-prot) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-129">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="ca46f-130">Valfritt: Användare kan återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="ca46f-130">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="ca46f-131">Du har använt [snabbdistribution av självbetjäning av lösenordsåterställning för Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) för att konfigurera återställning av lösenord för dina användare.</span><span class="sxs-lookup"><span data-stu-id="ca46f-131">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="ca46f-132">Om du inte uppfyller det här villkoret kommer användare att vara beroende av administratörer av användarkonton för att återställa sina lösenord, vilket innebär ytterligare framtida IT-administration.</span><span class="sxs-lookup"><span data-stu-id="ca46f-132">If you don't meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="ca46f-133">Vid behov kan [Steg 2](identity-secure-your-passwords.md#identity-pw-reset) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-133">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="ca46f-134">Valfritt: användare kan logga in med sömlös enkel inloggning i Azure AD</span><span class="sxs-lookup"><span data-stu-id="ca46f-134">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="ca46f-135">Du har aktiverat [Azure AD Connect: sömlös enkel inloggning](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) för organisationen för att förenkla användarnas inloggning i molnbaserade program, till exempel Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca46f-135">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="ca46f-136">Om du hoppar över det här alternativet kan användarna bli ombedda att uppge autentiseringsuppgifter när de får åtkomst till fler program som använder Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-136">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use you Azure AD tenant.</span></span>

<span data-ttu-id="ca46f-137">Vid behov kan [Steg 2](identity-secure-your-passwords.md#identity-sso) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-137">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="ca46f-138">Valfritt: Inloggningsskärmen anpassas för din organisation</span><span class="sxs-lookup"><span data-stu-id="ca46f-138">Optional: The sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="ca46f-139">Du har använt anvisningarna i artikeln om att [lägga till företagsanpassning på sidorna för inloggning och åtkomstpanelen](https://aka.ms/aadpaddbranding) för att lägga till organisationens varumärke på inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="ca46f-139">You have used [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding) to add your organization's branding to the sign-in page.</span></span>

<span data-ttu-id="ca46f-140">Om du hoppar över det här alternativet visas en allmän inloggningsskärm för dina användare vilket kan leda till att de blir osäkra på om de verkligen loggar in på organisationens webbplats.</span><span class="sxs-lookup"><span data-stu-id="ca46f-140">If you skip this option, your users will see a generic sign-in screen and might not be confident that they're signing into your organization's site.</span></span>

<span data-ttu-id="ca46f-141">Vid behov kan [Steg 2](identity-secure-your-passwords.md#identity-custom-sign-in) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-141">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="ca46f-142">Valfritt: Azure multifaktorautentisering har aktiverats för dina användare</span><span class="sxs-lookup"><span data-stu-id="ca46f-142">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="ca46f-143">Du har använt [Planera för Azure multifaktorautentisering](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) och [Principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) för att aktivera Azure multifaktorautentisering (MFA) för dina användarkonton.</span><span class="sxs-lookup"><span data-stu-id="ca46f-143">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="ca46f-144">Om du hoppar över det här alternativet kommer dina användarkonton att vara sårbara för kompromettering av autentiseringsuppgifter genom cyberangrepp.</span><span class="sxs-lookup"><span data-stu-id="ca46f-144">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers.</span></span> <span data-ttu-id="ca46f-145">Om lösenordet till ett användarkonto har komprometterats är alla resurser och funktioner för kontot, till exempel administratörsroller, tillgängliga för angriparen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-145">If a user account's password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker.</span></span> <span data-ttu-id="ca46f-146">Det gör det möjligt för angriparen att kopiera, förstöra eller använda interna dokument och andra data i utpressningssyfte.</span><span class="sxs-lookup"><span data-stu-id="ca46f-146">This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="ca46f-147">Vid behov kan [Steg 3](identity-secure-user-sign-ins.md#identity-mfa) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-147">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-148">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-148">How to test</span></span>

1.    <span data-ttu-id="ca46f-149">Skapa ett testanvändarkonto och tilldela dem en licens.</span><span class="sxs-lookup"><span data-stu-id="ca46f-149">Create a test user account and assign them a license.</span></span> 
2.    <span data-ttu-id="ca46f-150">Konfigurera multifaktorautentisering med Azure för testanvändarkontot med den extra verifieringsmetoden som du använder för verkliga användarkonton, t. ex. att skicka textmeddelanden till telefonen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-150">Configure Azure Multi-Factor Authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a text message to your phone.</span></span> 
3.    <span data-ttu-id="ca46f-151">Logga in på Office 365-portalen med ditt testanvändarkonto.</span><span class="sxs-lookup"><span data-stu-id="ca46f-151">Sign in to the Office 365 portal with the test user account.</span></span>
4.    <span data-ttu-id="ca46f-152">Kontrollera att MFA uppmanar dig om ytterligare verifieringsinformation och -resultat i en lyckad autentisering.</span><span class="sxs-lookup"><span data-stu-id="ca46f-152">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.    <span data-ttu-id="ca46f-153">Ta bort testanvändarkontot.</span><span class="sxs-lookup"><span data-stu-id="ca46f-153">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a><span data-ttu-id="ca46f-154">Valfritt: Azure AD-identitetsskydd är aktiverat för att skydda mot kompromettering av autentiseringsuppgifter (endast Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="ca46f-154">Optional: Azure AD Identity Protection is enabled to protect against credential compromise (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="ca46f-155">Du har aktiverat Azure AD Identity Protection för:</span><span class="sxs-lookup"><span data-stu-id="ca46f-155">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="ca46f-156">Åtgärda potentiella identitetssårbarheter.</span><span class="sxs-lookup"><span data-stu-id="ca46f-156">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="ca46f-157">Upptäcka möjliga försök till intrång i autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ca46f-157">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="ca46f-158">Undersöka och åtgärda fortlöpande misstänkta identitetstillbud.</span><span class="sxs-lookup"><span data-stu-id="ca46f-158">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="ca46f-159">Om du hoppar över det här alternativet kan du inte upptäcka eller automatiskt bekämpa försök till kompromettering av autentiseringsuppgifter eller undersöka identitetsrelaterade incidenter.</span><span class="sxs-lookup"><span data-stu-id="ca46f-159">If you skip this option, you won't be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents.</span></span> <span data-ttu-id="ca46f-160">Detta gör din organisation potentiellt utsatt för kompromettering av autentiseringsuppgifter och innebär ett hot mot organisationens känsliga data.</span><span class="sxs-lookup"><span data-stu-id="ca46f-160">This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization's sensitive data.</span></span>

<span data-ttu-id="ca46f-161">Vid behov kan [Steg 3](identity-secure-user-sign-ins.md#identity-ident-prot) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-161">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="ca46f-162">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-162">How to test</span></span>

1. <span data-ttu-id="ca46f-163">Skapa ett testanvändarkonto med ett första lösenord.</span><span class="sxs-lookup"><span data-stu-id="ca46f-163">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="ca46f-164">Använd anvisningarna i [Låt användare återställa sina egna lösenord i Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) för att återställa lösenordet för testanvändarkontot.</span><span class="sxs-lookup"><span data-stu-id="ca46f-164">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="ca46f-165">Logga ut och logga sedan in på testanvändarkontot med hjälp av lösenordsåterställning.</span><span class="sxs-lookup"><span data-stu-id="ca46f-165">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="ca46f-166">Ta bort testanvändarkontot.</span><span class="sxs-lookup"><span data-stu-id="ca46f-166">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="ca46f-167">Obligatoriskt för hybrididentiteter: användare och grupper synkroniseras med Azure AD</span><span class="sxs-lookup"><span data-stu-id="ca46f-167">Required for hybrid identity: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="ca46f-168">Om du har en befintlig lokal AD DS (Active Directory Domain Services) har du använt Azure AD Connect för att synkronisera användarkonton och -grupper från din lokala AD DS till Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-168">If you have an existing on-premises Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises AD DS to your Azure AD tenant.</span></span>

<span data-ttu-id="ca46f-169">Med katalogsynkronisering kan användarna logga in på Microsoft 365 och andra Microsoft-molntjänster med samma autentiseringsuppgifter som de använder för att logga in på sina datorer och komma åt lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="ca46f-169">With directory synchronization, your users can sign in to Microsoft 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="ca46f-170">Vid behov kan [Steg 4](identity-add-user-accounts.md#identity-sync) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="ca46f-170">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="ca46f-171">Om du hoppar över det här kravet kommer du att ha två uppsättningar användarkonton och grupper:</span><span class="sxs-lookup"><span data-stu-id="ca46f-171">If you skip this requirement, you'll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="ca46f-172">Användarkonton och -grupper som finns i din lokala AD DS</span><span class="sxs-lookup"><span data-stu-id="ca46f-172">User accounts and groups that exist in your on-premises AD DS</span></span>
- <span data-ttu-id="ca46f-173">Användarkonton och -grupper som finns i din Azure AD-klientorganisation</span><span class="sxs-lookup"><span data-stu-id="ca46f-173">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="ca46f-174">I det här läget måste de två uppsättningarna användarkonton och -grupper hanteras manuellt av både IT-administratörer och användare.</span><span class="sxs-lookup"><span data-stu-id="ca46f-174">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users.</span></span> <span data-ttu-id="ca46f-175">Detta kommer oundvikligen att leda till osynkroniserade konton, deras lösenord och grupper.</span><span class="sxs-lookup"><span data-stu-id="ca46f-175">This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-176">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-176">How to test</span></span>
<span data-ttu-id="ca46f-177">Verifiera att autentisering med lokala autentiseringsuppgifter fungerar korrekt genom att logga in på Office-portalen med dina lokala autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ca46f-177">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="ca46f-178">Du kontrollerar att katalogsynkronisering fungerar genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="ca46f-178">To verify that directory synchronization is working correctly, do the following:</span></span>

1.    <span data-ttu-id="ca46f-179">Skapa en ny testgrupp i AD DS.</span><span class="sxs-lookup"><span data-stu-id="ca46f-179">Create a new test group in AD DS.</span></span>
2.    <span data-ttu-id="ca46f-180">Vänta på synkroniseringstid.</span><span class="sxs-lookup"><span data-stu-id="ca46f-180">Wait for the synchronization time.</span></span>
3.    <span data-ttu-id="ca46f-181">Kontrollera att namnet på den nya testgruppen visas i Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-181">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="ca46f-182">Valfritt: Active Directory-synkroniseringen övervakas</span><span class="sxs-lookup"><span data-stu-id="ca46f-182">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="ca46f-183">Du har använt [Azure AD Connect Health med synkronisering](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (för lösenordssynkronisering) eller [Med Azure AD Connect Health med AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (för federerad autentisering) och har distribuerat Azure AD Connect Health, vilket inbegriper:</span><span class="sxs-lookup"><span data-stu-id="ca46f-183">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="ca46f-184">Installera Azure AD Connect Health-agenten på var och en av dina lokala identitetsservrar.</span><span class="sxs-lookup"><span data-stu-id="ca46f-184">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="ca46f-185">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span><span class="sxs-lookup"><span data-stu-id="ca46f-185">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="ca46f-186">Om du hoppar över det här alternativet kan du bättre utvärdera tillståndet för den molnbaserade identitetsinfrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-186">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="ca46f-187">Vid behov kan [Steg 4](identity-add-user-accounts.md#identity-sync-health) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-187">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-188">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-188">How to test</span></span>
<span data-ttu-id="ca46f-189">Azure AD Connect Health-portalen visar aktuell och korrekt status för lokala domänkontrollanter och pågående synkronisering.</span><span class="sxs-lookup"><span data-stu-id="ca46f-189">The Azure AD Connect Health portal shows the current and correct state of your on-premises domain controllers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="ca46f-190">Valfritt: tillbakaskrivning av lösenord är aktiverat för dina användare</span><span class="sxs-lookup"><span data-stu-id="ca46f-190">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="ca46f-191">Du har använt anvisningarna i [Azure AD-SSPR med tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) för att aktivera tillbakaskrivning av lösenord för Azure AD-klientorganisationen för Microsoft 365 Enterprise-abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="ca46f-191">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="ca46f-192">Om du hoppar över det här alternativet måste användare som inte är anslutna till ditt lokala nätverk återställa eller låsa upp AD DS-lösenordet via en IT-administratör.</span><span class="sxs-lookup"><span data-stu-id="ca46f-192">If you skip this option, users who aren't connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="ca46f-193">Vid behov kan [Steg 4](identity-add-user-accounts.md#identity-pw-writeback) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-193">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="ca46f-194">Tillbakaskrivning av lösenord krävs för att fullt ut använda skyddsfunktioner för Azure AD, t. ex. för att begära att användare ska ändra sina lokala lösenord när Azure AD har upptäckt en stor risk för kontointrång.</span><span class="sxs-lookup"><span data-stu-id="ca46f-194">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-195">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-195">How to test</span></span>

<span data-ttu-id="ca46f-196">Du testar tillbakaskrivning av lösenord genom att ändra ditt lösenord i Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca46f-196">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="ca46f-197">Du bör kunna använda kontot och det nya lösenordet för att komma åt lokala AD DS-resurser.</span><span class="sxs-lookup"><span data-stu-id="ca46f-197">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="ca46f-198">Skapa ett testanvändarkonto i din lokala AD DS, tillåt att katalogsynkroniseringen utförs och ge den sedan en Microsoft 365 Enterprise-licens i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca46f-198">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it a Microsoft 365 Enterprise license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="ca46f-199">Logga in på datorn och Office-portalen med hjälp av autentiseringsuppgifterna för testanvändarkontot från en fjärransluten dator som är ansluten till din lokala AD DS-domän.</span><span class="sxs-lookup"><span data-stu-id="ca46f-199">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="ca46f-200">Välj **Inställningar > Inställningar för Office 365 > Lösenord > Ändra lösenord**.</span><span class="sxs-lookup"><span data-stu-id="ca46f-200">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="ca46f-201">Skriv ditt nuvarande lösenord, skriv ett nytt lösenord och bekräfta det.</span><span class="sxs-lookup"><span data-stu-id="ca46f-201">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="ca46f-202">Logga ut från Office-portalen och fjärrdatorn och logga sedan in på datorn med testanvändarkontot och det nya lösenordet.</span><span class="sxs-lookup"><span data-stu-id="ca46f-202">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="ca46f-203">Detta bekräftar att du kunde ändra lösenordet för ett lokalt AD DS-användarkonto med Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-203">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-204">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-204">How to test</span></span>

<span data-ttu-id="ca46f-205">Logga in på portalen med ditt användarkontonamn och Azure Multi-Factor Authentication.</span><span class="sxs-lookup"><span data-stu-id="ca46f-205">Sign in to the portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="ca46f-206">Du bör se dina anpassade varumärkeselement på inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="ca46f-206">You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-microsoft-365-groups"></a><span data-ttu-id="ca46f-207">Valfritt: Självbetjäning av grupphantering har aktiverats för vissa Azure AD-säkerhetsgrupper och Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="ca46f-207">Optional: Self-service group management is enabled for specific Azure AD security and Microsoft 365 Groups</span></span>

<span data-ttu-id="ca46f-208">Du har fastställt vilka grupper som är lämpliga för självbetjäningshantering, instruerat deras ägare i arbetsflöden och ansvarsområden för grupphantering, och [konfigurerat självbetjäningshantering i Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) för dessa grupper.</span><span class="sxs-lookup"><span data-stu-id="ca46f-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="ca46f-209">Om du hoppar över det här alternativet måste alla uppgifter för Azure AD-grupphantering utföras av IT-administratörer.</span><span class="sxs-lookup"><span data-stu-id="ca46f-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="ca46f-210">Vid behov kan [Steg 5](identity-use-group-management.md#identity-self-service-groups) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-210">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-211">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-211">How to test</span></span>
1.    <span data-ttu-id="ca46f-212">Skapa ett testanvändarkonto för Azure AD med Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.    <span data-ttu-id="ca46f-213">Logga in med testanvändarkontot och skapa en säkerhetstestgrupp för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ca46f-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.    <span data-ttu-id="ca46f-214">Logga ut och logga sedan in med ditt IT-administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="ca46f-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.    <span data-ttu-id="ca46f-215">Konfigurera säkerhetstestgruppen för självbetjäningshantering för testanvändarkontot.</span><span class="sxs-lookup"><span data-stu-id="ca46f-215">Configure the test security group for self-service management for the test user account.</span></span>
5.    <span data-ttu-id="ca46f-216">Logga ut och logga sedan in med ditt testanvändarkonto.</span><span class="sxs-lookup"><span data-stu-id="ca46f-216">Sign out and then sign-in with your test user account.</span></span>
6.    <span data-ttu-id="ca46f-217">Använd Azure-portalen för att lägga till medlemmar i säkerhetstestgruppen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-217">Use the Azure portal to add members to the test security group.</span></span>
7.    <span data-ttu-id="ca46f-218">Ta bort säkerhetstestgruppen och testanvändarkontot.</span><span class="sxs-lookup"><span data-stu-id="ca46f-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="ca46f-219">Valfritt: inställningar för dynamiska gruppmedlemskap lägger automatiskt till användarkonton i grupper baserat på användarkontons attribut</span><span class="sxs-lookup"><span data-stu-id="ca46f-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="ca46f-220">Du har fastställt uppsättningen av dynamiska grupper i Azure AD och använt anvisningarna i [Attributbaserade dynamiska gruppmedlemskap i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) för att skapa grupperna och reglerna som avgör uppsättningen användarkontoattribut och värdena för gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="ca46f-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="ca46f-221">Om du hoppar över det här alternativet måste gruppmedlemskap göras manuellt när nya konton läggs till eller när attribut för användarkonton ändras med tiden.</span><span class="sxs-lookup"><span data-stu-id="ca46f-221">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time.</span></span> <span data-ttu-id="ca46f-222">Om någon till exempel flyttas från försäljningsavdelningen till ekonomiavdelningen blir du tvungen att:</span><span class="sxs-lookup"><span data-stu-id="ca46f-222">For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="ca46f-223">Uppdatera värdet för det användarkontots avdelningsattribut.</span><span class="sxs-lookup"><span data-stu-id="ca46f-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="ca46f-224">Manuellt ta bort dem från försäljningsgruppen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="ca46f-225">Manuellt lägga till dem till ekonomigruppen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="ca46f-226">Om försäljnings- och redovisningsgrupperna var dynamiska skulle du bara behöva ändra användarkontots avdelningsvärde.</span><span class="sxs-lookup"><span data-stu-id="ca46f-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account's Department value.</span></span>

<span data-ttu-id="ca46f-227">Vid behov kan [Steg 5](identity-use-group-management.md#identity-dyn-groups) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-227">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-228">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-228">How to test</span></span>

1. <span data-ttu-id="ca46f-229">Skapa en dynamisk testgrupp i Azure AD med Azure-portalen och konfigurera en regel för avdelningen motsvarande ”test1”.</span><span class="sxs-lookup"><span data-stu-id="ca46f-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals "test1".</span></span>
2. <span data-ttu-id="ca46f-230">Skapa ett testanvändarkonto i Azure AD och ställ in egenskapen för avdelningen till ”test1”.</span><span class="sxs-lookup"><span data-stu-id="ca46f-230">Create a test user account in Azure AD and set the Department property to "test1".</span></span>
3. <span data-ttu-id="ca46f-231">Kontrollera egenskaperna för användarkontot för att säkerställa att det har blivit medlem i den dynamiska testgruppen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="ca46f-232">Ändra värdet på avdelningsegenskapen för testanvändarkontot till ”test2”.</span><span class="sxs-lookup"><span data-stu-id="ca46f-232">Change the value of the Department property for the test user account to "test2".</span></span>
5. <span data-ttu-id="ca46f-233">Kontrollera egenskaperna för användarkontot för att säkerställa att det har inte längre är medlem i den dynamiska testgruppen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="ca46f-234">Ta bort den dynamiska testgruppen och testanvändarkontot.</span><span class="sxs-lookup"><span data-stu-id="ca46f-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="ca46f-235">Valfritt: Gruppbaserad licensiering för att automatiskt tilldela och ta bort licenser till användarkonton baserat på gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="ca46f-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="ca46f-236">Du har [aktiverat gruppbaserad licensiering](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) för lämpliga Azure AD-säkerhetsgrupper, så att dina Microsoft 365 Enterprise-licenser tilldelas eller tas bort automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ca46f-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that your Microsoft 365 Enterprise licenses are automatically assigned or unassigned.</span></span>

<span data-ttu-id="ca46f-237">Om du hoppar över det här alternativet blir du tvungen att manuellt:</span><span class="sxs-lookup"><span data-stu-id="ca46f-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="ca46f-238">Tilldela licenser till nya användare som du vill ska ha åtkomst.</span><span class="sxs-lookup"><span data-stu-id="ca46f-238">Assign licenses to new users whom you intend to have access.</span></span>
- <span data-ttu-id="ca46f-239">Ta bort licenser från användare som inte längre finns i din organisation eller som inte längre har åtkomst.</span><span class="sxs-lookup"><span data-stu-id="ca46f-239">Unassign licenses from users who are no longer with your organization or do not have access.</span></span>

<span data-ttu-id="ca46f-240">Vid behov kan [Steg 5](identity-use-group-management.md#identity-group-license) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-240">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ca46f-241">Så testar man</span><span class="sxs-lookup"><span data-stu-id="ca46f-241">How to test</span></span>

1. <span data-ttu-id="ca46f-242">Skapa en säkerhetstestgrupp i Azure AD med Azure-portalen och konfigurera gruppbaserad licensering för att tilldela Microsoft 365 Enterprise-licens.</span><span class="sxs-lookup"><span data-stu-id="ca46f-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Microsoft 365 Enterprise license.</span></span>
2. <span data-ttu-id="ca46f-243">Skapa ett testanvändarkonto i Azure AD och lägg till det i säkerhetstestgruppen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="ca46f-244">Kontrollera egenskaperna för användarkontot i administrationscentret för Microsoft 365 för att säkerställa att det har tilldelats Microsoft 365 Enterprise-licensen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Microsoft 365 Enterprise license.</span></span>
4. <span data-ttu-id="ca46f-245">Ta bort testanvändarkontot från säkerhetstestgruppen.</span><span class="sxs-lookup"><span data-stu-id="ca46f-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="ca46f-246">Kontrollera egenskaperna för användarkontot för att säkerställa att det har inte har Microsoft 365 Enterprise-licensen tilldelad längre.</span><span class="sxs-lookup"><span data-stu-id="ca46f-246">Examine the properties of the user account to ensure that it no longer has the Microsoft 365 Enterprise license assigned.</span></span>
6. <span data-ttu-id="ca46f-247">Ta bort säkerhetstestgruppen och testanvändarkontot.</span><span class="sxs-lookup"><span data-stu-id="ca46f-247">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="ca46f-248">Valfritt: åtkomstgranskningar som konfigurerats och används för att övervaka åtkomst</span><span class="sxs-lookup"><span data-stu-id="ca46f-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="ca46f-249">Du har använt de här artiklarna för att konfigurera olika typer av åtkomstgranskningar och övervaka gruppmedlemskap, åtkomst till företagsprogram och rolluppgifter:</span><span class="sxs-lookup"><span data-stu-id="ca46f-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="ca46f-250">Grupper och appar</span><span class="sxs-lookup"><span data-stu-id="ca46f-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="ca46f-251">Azure AD-roller</span><span class="sxs-lookup"><span data-stu-id="ca46f-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="ca46f-252">Azure-resursroller</span><span class="sxs-lookup"><span data-stu-id="ca46f-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="ca46f-253">Vid behov kan [Steg 6](identity-configure-identity-governance.md#identity-access-reviews) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="ca46f-253">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="ca46f-254">Resultat och nästa steg</span><span class="sxs-lookup"><span data-stu-id="ca46f-254">Results and next steps</span></span>

<span data-ttu-id="ca46f-255">Din identitetsinfrastruktur i Microsoft 365-molnet använder stark autentisering, skyddade administratörskonton och förenklad användaråtkomst och -hantering.</span><span class="sxs-lookup"><span data-stu-id="ca46f-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="ca46f-257">Om du följer stegen för slutpunkt till slutpunkt-distribution av Microsoft 365 Enterprise, är nästa fas [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="ca46f-257">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

