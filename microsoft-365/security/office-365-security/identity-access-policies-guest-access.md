---
title: Identitets-och enhets åtkomst principer för att tillåta gäst och extern användare B2B-åtkomst-Microsoft 365 för företag | Microsoft-dok
description: Här beskrivs Rekommenderad villkorlig åtkomst och relaterade principer för att skydda åtkomst till gäster och externa användare.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845101"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="797e7-103">Principer för att tillåta gäst åtkomst och åtkomst till externa användare</span><span class="sxs-lookup"><span data-stu-id="797e7-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="797e7-104">I den här artikeln beskrivs hur du justerar Rekommenderad enhet och identitets åtkomst för att tillåta åtkomst för gäster och externa användare som har ett Azure Active Directory (Azure AD)-konto.</span><span class="sxs-lookup"><span data-stu-id="797e7-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="797e7-105">Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="797e7-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="797e7-106">Dessa rekommendationer är avsedda att tillämpas på den **ursprungliga** skydds nivån.</span><span class="sxs-lookup"><span data-stu-id="797e7-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="797e7-107">Men du kan också justera rekommendationerna baserat på dina specifika behov för **känsligt** och **starkt reglerat** skydd.</span><span class="sxs-lookup"><span data-stu-id="797e7-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="797e7-108">Om du tillhandahåller en sökväg för B2B-konton för att autentisera med din Azure AD-klient får inte dessa konton åtkomst till hela din miljö.</span><span class="sxs-lookup"><span data-stu-id="797e7-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="797e7-109">B2B-användare och deras konton har till gång till tjänster och resurser, till exempel filer, som delas med dem via princip för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="797e7-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="797e7-110">Uppdatera gemensamma principer för att tillåta och skydda gäster och åtkomst till externa användare</span><span class="sxs-lookup"><span data-stu-id="797e7-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="797e7-111">Det här diagrammet visar vilka principer du kan lägga till eller uppdatera bland de vanliga åtkomst principerna för identitet och enheter, för B2B-gäst och åtkomst via extern användare.</span><span class="sxs-lookup"><span data-stu-id="797e7-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="797e7-112">[![Sammanfattning av princip uppdateringar för att skydda gäst åtkomst](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="797e7-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="797e7-113">Visa en större version av bilden</span><span class="sxs-lookup"><span data-stu-id="797e7-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="797e7-114">I följande tabell visas de principer som du måste skapa och uppdatera.</span><span class="sxs-lookup"><span data-stu-id="797e7-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="797e7-115">Gemensamma principer-länken till de associerade konfigurations anvisningarna i artikeln om [principer för åtkomst policys för identitet och enheter](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="797e7-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="797e7-116">Skydds nivå</span><span class="sxs-lookup"><span data-stu-id="797e7-116">Protection level</span></span>|<span data-ttu-id="797e7-117">Principerna</span><span class="sxs-lookup"><span data-stu-id="797e7-117">Policies</span></span>|<span data-ttu-id="797e7-118">Mer information</span><span class="sxs-lookup"><span data-stu-id="797e7-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="797e7-119">**Grundläggande**</span><span class="sxs-lookup"><span data-stu-id="797e7-119">**Baseline**</span></span>|[<span data-ttu-id="797e7-120">Kräv MFA alltid för gäster och externa användare</span><span class="sxs-lookup"><span data-stu-id="797e7-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="797e7-121">Skapa den här nya principen och konfigurera:</span><span class="sxs-lookup"><span data-stu-id="797e7-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="797e7-122">För **uppgifter > användare och grupper > inkludera** väljer **du Välj användare och grupper** och sedan **alla gäst-och externa användare**.</span><span class="sxs-lookup"><span data-stu-id="797e7-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="797e7-123">För **tilldelningar > villkor > inloggning** ska du låta alla alternativ vara avmarkerade så att multifaktorautentisering alltid används (MFA).</span><span class="sxs-lookup"><span data-stu-id="797e7-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="797e7-124">Kräv MFA när en inloggnings risk är *mellan* eller *hög*</span><span class="sxs-lookup"><span data-stu-id="797e7-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="797e7-125">Ändra den här principen för att exkludera gäster och externa användare.</span><span class="sxs-lookup"><span data-stu-id="797e7-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="797e7-126">Kräv kompatibla PC-datorer</span><span class="sxs-lookup"><span data-stu-id="797e7-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="797e7-127">Ändra den här principen för att exkludera gäster och externa användare.</span><span class="sxs-lookup"><span data-stu-id="797e7-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="797e7-128">Om du vill inkludera eller exkludera gäster och externa användare i principer för villkorsstyrd åtkomst för **uppgifter > användare och grupper > inkludera** eller **exkludera** markerar du **alla gäster och externa användare**.</span><span class="sxs-lookup"><span data-stu-id="797e7-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![skärm bild av kontroller för att exkludera gäster och externa användare](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="797e7-130">Mer information</span><span class="sxs-lookup"><span data-stu-id="797e7-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="797e7-131">Gäster och åtkomst till externa användare med Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="797e7-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="797e7-132">Microsoft Teams definierar följande användare:</span><span class="sxs-lookup"><span data-stu-id="797e7-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="797e7-133">**Gäst åtkomst** använder ett Azure AD B2B-konto som kan läggas till som medlem i ett team och ha åtkomst till kommunikationen och resurserna i teamet.</span><span class="sxs-lookup"><span data-stu-id="797e7-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="797e7-134">**Extern åtkomst** är för en extern användare som inte har ett B2B-konto.</span><span class="sxs-lookup"><span data-stu-id="797e7-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="797e7-135">Åtkomst till externa användare inkluderar inbjudningar, samtal, chattar och möten, men inkluderar inte grupp medlemskap och åtkomst till teamens resurser.</span><span class="sxs-lookup"><span data-stu-id="797e7-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="797e7-136">Mer information finns i [jämförelsen mellan gäster och externa användar åtkomst för Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="797e7-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="797e7-137">Mer information om hur du skyddar identitets-och åtkomst principer för grupper finns i [Policy rekommendationer för att skydda Teams, grupper och filer](teams-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="797e7-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="797e7-138">Kräv MFA alltid för gäst-och externa användare</span><span class="sxs-lookup"><span data-stu-id="797e7-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="797e7-139">Den här principen ber dig registrera gäster för MFA i klient organisationen, oavsett om de är registrerade för MFA i sin hem klient organisation.</span><span class="sxs-lookup"><span data-stu-id="797e7-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="797e7-140">När du får åtkomst till resurser i klient organisationen måste gäster och externa användare använda MFA för varje begäran.</span><span class="sxs-lookup"><span data-stu-id="797e7-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="797e7-141">Exkludera gäster och externa användare från riskfyllda MFA</span><span class="sxs-lookup"><span data-stu-id="797e7-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="797e7-142">Trots att organisationer kan använda riskbaserade principer för B2B-användare som använder Azure AD Identity Protection finns det begränsningar i implementeringen av Azure AD Identity Protection för B2B-samarbets användare i en resurs katalog på grund av deras identitet i sin Hem Katalog.</span><span class="sxs-lookup"><span data-stu-id="797e7-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="797e7-143">På grund av dessa begränsningar rekommenderar Microsoft att du exkluderar gäster från riskfyllda MFA-principer och kräver att dessa användare alltid använder MFA.</span><span class="sxs-lookup"><span data-stu-id="797e7-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="797e7-144">Mer information finns i [begränsningar för identitets skydd för B2B-samarbets användare](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="797e7-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="797e7-145">Exkludera gäster och externa användare från enhets hantering</span><span class="sxs-lookup"><span data-stu-id="797e7-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="797e7-146">Endast en organisation kan hantera en enhet.</span><span class="sxs-lookup"><span data-stu-id="797e7-146">Only one organization can manage a device.</span></span> <span data-ttu-id="797e7-147">Om du inte utesluter gäster och externa användare från principer som kräver att enheter efterlevs blockerar dessa användare.</span><span class="sxs-lookup"><span data-stu-id="797e7-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="797e7-148">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="797e7-148">Next step</span></span>

![Steg 4: principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="797e7-150">Konfigurera principer för villkorsstyrd åtkomst för:</span><span class="sxs-lookup"><span data-stu-id="797e7-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="797e7-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="797e7-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="797e7-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="797e7-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="797e7-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="797e7-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
