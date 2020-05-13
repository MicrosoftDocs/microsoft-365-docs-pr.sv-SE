---
title: 'Steg 2: Skydda dina lösenord'
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
description: Se till att skapa starka och lätthanterliga lösenord i hela organisationen.
ms.openlocfilehash: 6e5c2567ee2027be2a84121fdad10ba873ec1c43
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214656"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="5d7fa-103">Steg 2: Skydda dina lösenord</span><span class="sxs-lookup"><span data-stu-id="5d7fa-103">Step 2: Secure your passwords</span></span>

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="5d7fa-105">Förhindra svaga lösenord</span><span class="sxs-lookup"><span data-stu-id="5d7fa-105">Prevent bad passwords</span></span>

<span data-ttu-id="5d7fa-106">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="5d7fa-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="5d7fa-107">Alla dina användare bör följa [Microsofts lösenordsvägledning](https://www.microsoft.com/research/publication/password-guidance) när de skapar lösenord till sina användarkonton.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="5d7fa-108">Hindra användarna från att skapa svaga lösenord genom att använda Azure AD-lösenordsskydd, som tillämpar både en global lista med blockerade lösenord och en valfri lista med blockerade lösenord som du väljer.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="5d7fa-109">Du kan till exempel välja ord som gäller specifikt för din organisation, som:</span><span class="sxs-lookup"><span data-stu-id="5d7fa-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="5d7fa-110">Varumärken</span><span class="sxs-lookup"><span data-stu-id="5d7fa-110">Brand names</span></span>
- <span data-ttu-id="5d7fa-111">Produktnamn</span><span class="sxs-lookup"><span data-stu-id="5d7fa-111">Product names</span></span>
- <span data-ttu-id="5d7fa-112">Platser (till exempel företagets huvudkontor)</span><span class="sxs-lookup"><span data-stu-id="5d7fa-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="5d7fa-113">Företagsspecifik, intern terminologi</span><span class="sxs-lookup"><span data-stu-id="5d7fa-113">Company-specific internal terms</span></span>
- <span data-ttu-id="5d7fa-114">Förkortningar med särskild betydelse för företaget</span><span class="sxs-lookup"><span data-stu-id="5d7fa-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="5d7fa-115">Du kan förbjuda svaga lösenord [i molnet](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) och för din [lokala AD DS (Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="5d7fa-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="5d7fa-116">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-password-prot) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="5d7fa-117">Enklare återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="5d7fa-117">Simplify password resets</span></span>

<span data-ttu-id="5d7fa-118">*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="5d7fa-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="5d7fa-119">I det här avsnittet aktiverar du självbetjäning för återställning av lösenord (SSPR) så att användarna kan återställa eller låsa upp sina lösenord eller konton.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="5d7fa-120">Du kan få varningar om missbruk eller felanvändning genom att använda den detaljerade rapporteringen som spårar när användare har åtkomst till systemet, tillsammans med meddelanden.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="5d7fa-121">Du måste aktivera tillbakaskrivning av lösenord innan du kan distribuera återställning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="5d7fa-122">Se [anvisningarna för att distribuera återställning av lösenord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="5d7fa-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5d7fa-124">Testlabbguide: återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="5d7fa-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="5d7fa-125">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pw-reset) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="5d7fa-126">Enklare inloggning för användare</span><span class="sxs-lookup"><span data-stu-id="5d7fa-126">Simplify user sign-in</span></span>

<span data-ttu-id="5d7fa-127">*Det här är valfritt för hybridversioner och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5d7fa-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5d7fa-128">I det här avsnittet konfigurerar du enkel inloggning med Azure Active Directory (Azure AD Seamless SSO), som fungerar med synkronisering av lösenordshash och direktautentisering, så att användare kan logga in på tjänster som använder Azure AD-användarkonton utan att behöva ange lösenord, och i många fall användarnamn.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="5d7fa-129">Det gör att användarna lättare kommer åt molnbaserade program, till exempel Office 365, utan att behöva några ytterligare lokala komponenter som identitetsservrar.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="5d7fa-130">Du konfigurerar Azure AD Seamless SSO med Azure AD Connect-verktyget.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="5d7fa-131">Se [anvisningarna för att konfigurera Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="5d7fa-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5d7fa-133">Testlabbguide: enkel inloggning med Azure AD Seamless</span><span class="sxs-lookup"><span data-stu-id="5d7fa-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="5d7fa-134">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-sso) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-sign-in-page"></a><span data-ttu-id="5d7fa-135">Anpassa inloggningssidan</span><span class="sxs-lookup"><span data-stu-id="5d7fa-135">Customize the sign-in page</span></span>

<span data-ttu-id="5d7fa-136">*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5d7fa-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5d7fa-137">I det här avsnittet kan du hjälpa användarna att identifiera din organisations inloggningssida genom att lägga till företagets namn, logotyp och andra bekanta element.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="5d7fa-138">Med Microsoft 365 Enterprise kan du anpassa utseendet på sidorna för inloggning och åtkomstpaneler så att de innehåller företagets logotyp, färgschema och anpassad användarinformation.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="5d7fa-139">Mer information finns i [Lägga till din företagsanpassning på inloggningssidan i Microsoft 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="5d7fa-139">For more information, see [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="5d7fa-140">Instruktioner för konfigurering finns i [Lägga till företagsanpassning på din inloggningssida och åtkomstpanelsidorna](https://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="5d7fa-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="5d7fa-141">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-custom-sign-in) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5d7fa-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="5d7fa-142">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5d7fa-142">Next step</span></span>

|||
|:-------|:-----|
|![Steg 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="5d7fa-144">Skydda och hantera användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="5d7fa-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
