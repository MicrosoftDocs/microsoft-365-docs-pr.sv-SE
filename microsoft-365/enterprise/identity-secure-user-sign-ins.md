---
title: 'Steg 3: Skydda och hantera användarinloggningar'
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
description: Du kan göra användarinloggningar till Windows-enheter och Microsoft 365 säkrare.
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42805452"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="11826-103">Steg 3: Skydda och hantera användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="11826-103">Step 3: Secure and manage your user sign-ins</span></span>

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="11826-105">Använda Windows Hello för företag</span><span class="sxs-lookup"><span data-stu-id="11826-105">Use Windows Hello for Business</span></span>

<span data-ttu-id="11826-106">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="11826-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="11826-107">Windows Hello för företag i Windows 10 Enterprise ersätter lösenord med stark tvåfaktorsautentisering när du loggar in på en Windows-enhet.</span><span class="sxs-lookup"><span data-stu-id="11826-107">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="11826-108">De två faktorerna är en ny typ av användaruppgifter som är kopplade till en enhet och ett biometriskt attribut eller en PIN-kod.</span><span class="sxs-lookup"><span data-stu-id="11826-108">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="11826-109">Mer information finns i [Översikt över Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span><span class="sxs-lookup"><span data-stu-id="11826-109">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="11826-110">Konfigurera Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="11826-110">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="11826-111">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="11826-111">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="11826-112">I det här steget konfigurerar du Azure Multi-Factor Authentication (MFA) för att lägga till en andra säkerhetsnivå för användarinloggningar och transaktioner.</span><span class="sxs-lookup"><span data-stu-id="11826-112">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="11826-113">MFA kräver ytterligare en verifieringsmetod efter att användarna korrekt har angett sina lösenord.</span><span class="sxs-lookup"><span data-stu-id="11826-113">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="11826-114">Utan MFA är lösenordet den enda verifieringsmetoden.</span><span class="sxs-lookup"><span data-stu-id="11826-114">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="11826-115">Problemet med lösenord är att många av dem är enkla att gissa sig till av obehöriga personer eller omedvetet delas med parter som inte är betrodda.</span><span class="sxs-lookup"><span data-stu-id="11826-115">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="11826-116">Med MFA kan den andra säkerhetsnivån vara:</span><span class="sxs-lookup"><span data-stu-id="11826-116">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="11826-117">En personlig och betrodd enhet som inte är lätt att förfalska eller duplicera, t.ex. en smartphone.</span><span class="sxs-lookup"><span data-stu-id="11826-117">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="11826-118">Ett biometriskt attribut, t.ex. ett fingeravtryck.</span><span class="sxs-lookup"><span data-stu-id="11826-118">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="11826-119">Du ska aktivera MFA och konfigurera den sekundära autentiseringsmetoden med [principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), som gör att du kan använda Azure Active Directory-grupper (Azure AD) för att distribuera MFA till angivna uppsättningar av användare, t.ex. pilotanvändare, geografiska regioner eller avdelningar.</span><span class="sxs-lookup"><span data-stu-id="11826-119">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="11826-120">Se till att informera användarna om att MFA är aktiverat så att de förstår kraven, t.ex. obligatoriskt utnyttjande av en smartphone för att logga in, och kan logga in korrekt.</span><span class="sxs-lookup"><span data-stu-id="11826-120">Make sure to let your users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="11826-121">Mer information finns i [Planera en molnbaserad distribution av Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="11826-121">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="11826-123">Testlabbguide: Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="11826-123">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="11826-124">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-mfa) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="11826-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="11826-125">Skydda mot obehörig inloggning</span><span class="sxs-lookup"><span data-stu-id="11826-125">Protect against credential compromise</span></span>

<span data-ttu-id="11826-126">*Det här är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="11826-126">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="11826-127">I det här avsnittet får du lära dig hur du konfigurerar principer som skyddar mot obehörig inloggning, där en angripare bestämmer en användares kontonamn och lösenord för att få åtkomst till organisationens molntjänster och data.</span><span class="sxs-lookup"><span data-stu-id="11826-127">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="11826-128">Azure AD Identity Protection tillhandahåller ett antal olika sätt som förhindrar att en obehörig angripare kan kompromettera användarkontots inloggningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="11826-128">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="11826-129">Med Azure AD Identity Protection kan du:</span><span class="sxs-lookup"><span data-stu-id="11826-129">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="11826-130">Fastställa och åtgärda potentiella säkerhetsproblem i organisationens identiteter</span><span class="sxs-lookup"><span data-stu-id="11826-130">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="11826-131">I Azure AD används maskininlärning för att identifiera avvikelser och misstänkt aktivitet, till exempel inloggningar och aktiviteter efter inloggning.</span><span class="sxs-lookup"><span data-stu-id="11826-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="11826-132">Med dessa data genererar Azure AD Identity Protection rapporter och aviseringar som hjälper dig att utvärdera problem och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="11826-132">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="11826-133">Identifiera misstänkta åtgärder som är relaterade till organisationens identitet och svara på dem automatiskt</span><span class="sxs-lookup"><span data-stu-id="11826-133">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="11826-134">Du kan konfigurera riskbaserade principer som automatiskt reagerar på problem som upptäcks när en viss risknivå har uppnåtts.</span><span class="sxs-lookup"><span data-stu-id="11826-134">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="11826-135">Dessa principer, förutom andra kontroller för villkorsstyrd åtkomst i Azure AD och Microsoft Intune, kan antingen automatiskt blockera åtkomst eller utföra korrigeringsåtgärder, t.ex. återställning av lösenord och krav på multifaktorautentisering för efterföljande inloggningar.</span><span class="sxs-lookup"><span data-stu-id="11826-135">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="11826-136">Undersök misstänkta händelser och åtgärda dem med administrativa åtgärder</span><span class="sxs-lookup"><span data-stu-id="11826-136">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="11826-137">Du kan undersöka riskhändelser med hjälp av information om säkerhetshändelsen.</span><span class="sxs-lookup"><span data-stu-id="11826-137">You can investigate risk events using information about the security incident.</span></span> <span data-ttu-id="11826-138">Enkla arbetsflöden är tillgängliga för att spåra undersökningar och initiera åtgärder för reparationer, som återställning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="11826-138">Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="11826-139">Se [mer information om Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="11826-139">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="11826-140">Se [stegen för att aktivera Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="11826-140">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="11826-141">Resultatet av det här steget är att du har aktiverat Azure AD Identity Protection och att du använder det för att:</span><span class="sxs-lookup"><span data-stu-id="11826-141">The results of this step are that you've enabled Azure AD Identity Protection and you are using it to:</span></span>

- <span data-ttu-id="11826-142">Åtgärda potentiella identitetssårbarheter.</span><span class="sxs-lookup"><span data-stu-id="11826-142">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="11826-143">Upptäcka möjliga försök till intrång i autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="11826-143">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="11826-144">Undersöka och åtgärda fortlöpande misstänkta identitetstillbud.</span><span class="sxs-lookup"><span data-stu-id="11826-144">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="11826-146">Testlabbguide: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="11826-146">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="11826-147">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-ident-prot) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="11826-147">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![Steg 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="11826-149">Lägga till användarkonton</span><span class="sxs-lookup"><span data-stu-id="11826-149">Add your user accounts</span></span>](identity-add-user-accounts.md) |
