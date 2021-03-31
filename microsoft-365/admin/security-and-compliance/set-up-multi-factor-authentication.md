---
title: Konfigurera multifaktorautentisering för användare
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Lär dig hur du konfigurerar multifaktorautentisering för din organisation.
monikerRange: o365-worldwide
ms.openlocfilehash: de5f8ffbc5c26015f6ff0eb2863b622273f96ca1
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408519"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="eb2bf-103">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="eb2bf-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="eb2bf-104">Eftersom du har kunskap om [multifaktorautentisering (MFA) och dess stöd i Microsoft 365](multi-factor-authentication-microsoft-365.md) är det dags att konfigurera och distribuera det i din organisation.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb2bf-105">Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och uppmanas att använda MFA när du loggar in, betyder det att [standardinställningar för säkerhet](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) har aktiverats automatiskt för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="eb2bf-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="eb2bf-106">Before you begin</span></span>

- <span data-ttu-id="eb2bf-107">Du måste vara en global administratör för att hantera MFA.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="eb2bf-108">Mer information finns i [Om administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="eb2bf-109">Om du har aktiverat föråldrad MFA per person, [inaktivera föråldrad MFA per person](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="eb2bf-110">Om du har Office 2013-klienter på Windows-enheter kan du [aktivera modern autentisering för Office 2013-kunder](./enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](./enable-modern-authentication.md).</span></span>
- <span data-ttu-id="eb2bf-111">Avancerat: Om du har katalogtjänster från tredje part med Active Directory Federation Services (AD FS) konfigurerar du Microsoft Azure Multi-Factor Authentication-server.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="eb2bf-112">Mer information finns i [avancerade scenarier med Azure multifaktorautentisering och VPN-lösningar från tredje part](/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="eb2bf-113">Aktivera eller inaktivera standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="eb2bf-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="eb2bf-114">För de flesta organisationer tillhandahåller standardinställningar för säkerhet en god nivå av ytterligare inloggningssäkerhet.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="eb2bf-115">Mer information finns i [Vad är standardinställningar för säkerhet?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="eb2bf-115">For more information, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="eb2bf-116">Om prenumerationen är ny kan standardinställningar för säkerhet redan vara aktiverat för dig automatiskt.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="eb2bf-117">Du aktiverar eller inaktiverar säkerhetsinställningar för Azure Active Directory (Azure AD) i Microsoft Azure-portalen från fönstret **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="eb2bf-118">Logga in som global administratör på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="eb2bf-119">I det vänstra navigeringsfältet väljer du **Visa alla** och under **Administratörscenter** väljer du **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="eb2bf-120">I **Azure Active Directory administrationscenter** väljer du **Azure Active Directory** \> **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="eb2bf-121">Längst ner på sidan väljer du **Hantera standardinställningar för säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="eb2bf-122">Välj **Ja** för att aktivera standardinställningar för säkerhet eller **Nej** för att inaktivera dem och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="eb2bf-123">Om du har använt [originalprinciper för villkorsstyrd åtkomst](/azure/active-directory/conditional-access/concept-baseline-protection) blir du ombedd att inaktivera dem innan du går över till att använda säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-123">If you have been using [baseline Conditional Access policies](/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="eb2bf-124">Gå till sidan [principer för villkorsstyrd åtkomst](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="eb2bf-125">Välj alla originalprinciper som är **På** och ändra **Aktivera princip** till **Av**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="eb2bf-126">Gå till sidan [Azure Active Directory – Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="eb2bf-127">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="eb2bf-128">Välj **Ja** för att aktivera standardinställningar för säkerhet och **Nej** för att inaktivera dem och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="eb2bf-129">Använd principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="eb2bf-129">Use Conditional Access policies</span></span>

<span data-ttu-id="eb2bf-130">Om din organisation har mer detaljerade säkerhetsbehov kan villkorsstyrd åtkomst ge dig större kontroll.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="eb2bf-131">Med villkorsstyrd åtkomst kan du skapa och definiera principer som reagerar på inloggningshändelser och kan begära ytterligare åtgärder innan en användare beviljas åtkomst till ett program eller en tjänst.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb2bf-132">Inaktivera både MFA-och säkerhets inställningar per användare innan du aktiverar principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="eb2bf-133">Villkorsstyrd åtkomst är tillgänglig för kunder som har köpt Azure AD Premium P1, och licenser som inkluderar detta, t. ex. Microsoft 365 Business Premium och Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="eb2bf-134">Mer information finns i [skapa en princip för villkorsstyrd åtkomst](/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-134">For more information, see [create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="eb2bf-135">Riskbaserad villkorlig åtkomst är tillgänglig via Azure AD Premium P2-licens eller licenser som inkluderar detta, till exempel Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="eb2bf-136">Mer information finns i [Riskbaserad villkorsstyrd åtkomst](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-136">For more information, see [risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="eb2bf-137">Mer information om Azure AD P1 och P2 finns i [Azure Active Directory-priserna](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="eb2bf-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="eb2bf-138">Aktivera modern autentisering för din organisation</span><span class="sxs-lookup"><span data-stu-id="eb2bf-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="eb2bf-139">För de flesta prenumerationer är modern autentisering aktiverad automatiskt, men om du köpte prenumerationen före augusti 2017 måste du förmodligen aktivera modern autentisering för att få funktioner som multifaktorautentisering att fungera i Windows-klienter som Outlook.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription before August 2017, it is likely that you will need to turn on Modern Authentication in order to get features like Multi-Factor Authentication to work in Windows clients like Outlook.</span></span>


1. <span data-ttu-id="eb2bf-140">I Administrationscenter för Microsoft 365 väljer du **Inställningar** \> **Organisationsinställningar i det vänstra navigeringsfältet**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-140">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
2. <span data-ttu-id="eb2bf-141">Under fliken **Tjänster** väljer du **Modern autentisering** och kontrollerar att **Aktivera modern autentisering** är markerad i fönstret **Modern autentisering**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-141">Under the **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="eb2bf-142">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-142">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="eb2bf-143">Inaktivera föråldrad MFA för alla användare</span><span class="sxs-lookup"><span data-stu-id="eb2bf-143">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="eb2bf-144">Om du tidigare har aktiverat MFA för enskilda användare måste du inaktivera det innan du aktiverar säkerhetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-144">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="eb2bf-145">I Administrationscenter för Microsoft 365, i det vänstra navigeringsfältet, väljer du **Användare** \> **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-145">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="eb2bf-146">På sidan **Aktiva användare** väljer du **Multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-146">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="eb2bf-147">På sidan multifaktorautentisering väljer du varje användare och konfigurerar deras multifaktorstatus till **Inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="eb2bf-147">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eb2bf-148">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="eb2bf-148">Next steps</span></span>

- [<span data-ttu-id="eb2bf-149">Så här registrerar du dig för den extra autentiseringsmetoden</span><span class="sxs-lookup"><span data-stu-id="eb2bf-149">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="eb2bf-150">Vad är: multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="eb2bf-150">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="eb2bf-151">Så här loggar du in efter registrering</span><span class="sxs-lookup"><span data-stu-id="eb2bf-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="eb2bf-152">Så här ändrar du den extra autentiseringsmetoden</span><span class="sxs-lookup"><span data-stu-id="eb2bf-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a><span data-ttu-id="eb2bf-153">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="eb2bf-153">Related content</span></span>

<span data-ttu-id="eb2bf-154">[Aktivera multifaktorautentisering](../../business-video/turn-on-mfa.md) (video)</span><span class="sxs-lookup"><span data-stu-id="eb2bf-154">[Turn on multi-factor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>

<span data-ttu-id="eb2bf-155">[Aktivera multifaktorautentisering för telefonen](../../business-video/set-up-mfa.md) (video)</span><span class="sxs-lookup"><span data-stu-id="eb2bf-155">[Turn on multi-factor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>