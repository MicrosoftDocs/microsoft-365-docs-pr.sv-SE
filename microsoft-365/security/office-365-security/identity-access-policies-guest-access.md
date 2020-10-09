---
title: Identitets-och enhets åtkomst principer för att tillåta gäst och extern B2B-åtkomst-Microsoft 365 för företag | Microsoft-dok
description: Här beskrivs rekommenderade villkor för villkorlig åtkomst och relaterade principer för att skydda gäst-och externa användare.
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
ms.openlocfilehash: 2e81b17b96b532f8ae26ae1750e884988f116203
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399735"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="de3a9-103">Principer för att tillåta gäst-och extern B2B-åtkomst</span><span class="sxs-lookup"><span data-stu-id="de3a9-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="de3a9-104">I den här artikeln beskrivs hur du justerar de rekommenderade vanliga principer för identitets-och enhets åtkomst för att tillåta åtkomst för gäst och externa användare som har ett Azure Active Directory (Azure AD)-konto.</span><span class="sxs-lookup"><span data-stu-id="de3a9-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="de3a9-105">Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="de3a9-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="de3a9-106">Dessa rekommendationer är avsedda att tillämpas på den **ursprungliga** skydds nivån.</span><span class="sxs-lookup"><span data-stu-id="de3a9-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="de3a9-107">Men du kan också justera rekommendationerna baserat på hur många olika behov du har för **känsligt** och **starkt reglerat** skydd.</span><span class="sxs-lookup"><span data-stu-id="de3a9-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="de3a9-108">Om du tillhandahåller en sökväg för B2B-konton för att autentisera med din Azure AD-klient får inte dessa konton åtkomst till hela din miljö.</span><span class="sxs-lookup"><span data-stu-id="de3a9-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="de3a9-109">B2B-användare och deras konton har till gång till resurser som delas med dem (till exempel filer) inom de tjänster som beviljats i principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="de3a9-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="de3a9-110">Uppdatera vanliga principer för att tillåta och skydda gäst och extern åtkomst</span><span class="sxs-lookup"><span data-stu-id="de3a9-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="de3a9-111">För att skydda gäst-och extern åtkomst med Azure AD B2B-konton illustrerar följande diagram vilka principer du kan lägga till eller uppdatera från principer för åtkomst till gemensam identitet och enhet.</span><span class="sxs-lookup"><span data-stu-id="de3a9-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span> 

<span data-ttu-id="de3a9-112">[![Sammanfattning av princip uppdateringar för att skydda gäst åtkomst](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="de3a9-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="de3a9-113">Visa en större version av bilden</span><span class="sxs-lookup"><span data-stu-id="de3a9-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="de3a9-114">I följande tabell visas de principer som du måste skapa och uppdatera.</span><span class="sxs-lookup"><span data-stu-id="de3a9-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="de3a9-115">Gemensamma principer-länken till de associerade konfigurations anvisningarna i artikeln om [principer för åtkomst policys för identitet och enheter](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="de3a9-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="de3a9-116">Skydds nivå</span><span class="sxs-lookup"><span data-stu-id="de3a9-116">Protection level</span></span>|<span data-ttu-id="de3a9-117">Principerna</span><span class="sxs-lookup"><span data-stu-id="de3a9-117">Policies</span></span>|<span data-ttu-id="de3a9-118">Mer information</span><span class="sxs-lookup"><span data-stu-id="de3a9-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="de3a9-119">**Grundläggande**</span><span class="sxs-lookup"><span data-stu-id="de3a9-119">**Baseline**</span></span>|[<span data-ttu-id="de3a9-120">Kräv MFA alltid för gäst-och externa användare</span><span class="sxs-lookup"><span data-stu-id="de3a9-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="de3a9-121">Skapa den här nya principen och konfigurera:</span><span class="sxs-lookup"><span data-stu-id="de3a9-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="de3a9-122">För **uppgifter > användare och grupper > inkludera**väljer **du Välj användare och grupper**och sedan **alla gäst-och externa användare**.</span><span class="sxs-lookup"><span data-stu-id="de3a9-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="de3a9-123">För **tilldelningar > villkor > inloggning**ska du låta alla alternativ vara avmarkerade så att multifaktorautentisering alltid används (MFA).</span><span class="sxs-lookup"><span data-stu-id="de3a9-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
|        |[<span data-ttu-id="de3a9-124">Kräv MFA när en inloggnings risk är *mellan* eller *hög*</span><span class="sxs-lookup"><span data-stu-id="de3a9-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="de3a9-125">Ändra den här principen så att den exkluderar gäst-och externa användare.</span><span class="sxs-lookup"><span data-stu-id="de3a9-125">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="de3a9-126">Kräv kompatibla PC-datorer</span><span class="sxs-lookup"><span data-stu-id="de3a9-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="de3a9-127">Ändra den här principen så att den exkluderar gäst-och externa användare.</span><span class="sxs-lookup"><span data-stu-id="de3a9-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="de3a9-128">Om du vill inkludera eller exkludera gäst-och externa användare i principer för villkorsstyrd åtkomst för **uppgifter > användare och grupper > inkludera** eller **exkludera**markerar du **alla gäst-och externa användare**.</span><span class="sxs-lookup"><span data-stu-id="de3a9-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![skärm bild av kontroller för att exkludera gäst och externa användare](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="de3a9-130">Mer information</span><span class="sxs-lookup"><span data-stu-id="de3a9-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="de3a9-131">Gäst och extern åtkomst med Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de3a9-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="de3a9-132">Microsoft Teams definierar följande:</span><span class="sxs-lookup"><span data-stu-id="de3a9-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="de3a9-133">**Gäst åtkomst** använder ett Azure AD B2B-konto som kan läggas till som medlem i ett team och få åtkomst till kommunikationen och resurserna i teamet.</span><span class="sxs-lookup"><span data-stu-id="de3a9-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="de3a9-134">**Extern åtkomst** är för en extern användare som inte har ett B2B-konto.</span><span class="sxs-lookup"><span data-stu-id="de3a9-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="de3a9-135">Extern åtkomst kan inkludera inbjudningar och deltagande i samtal, chattar och möten, men inte grupp medlemskap och åtkomst till teamens resurser.</span><span class="sxs-lookup"><span data-stu-id="de3a9-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="de3a9-136">Mer information finns i [jämförelsen mellan gäst och extern åtkomst för Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="de3a9-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="de3a9-137">Principer för villkorsstyrd åtkomst gäller endast för gäst åtkomst i Teams eftersom det finns ett motsvarande Azure AD B2B-konto.</span><span class="sxs-lookup"><span data-stu-id="de3a9-137">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<span data-ttu-id="de3a9-138">Se [Policy rekommendationer för att skydda Teams, grupper och filer](teams-access-policies.md) för att få mer information om att skydda identitets-och enhets åtkomst principer för Teams.</span><span class="sxs-lookup"><span data-stu-id="de3a9-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="de3a9-139">Kräv MFA alltid för gäst-och externa användare</span><span class="sxs-lookup"><span data-stu-id="de3a9-139">Require MFA always for guest and external users</span></span>
<span data-ttu-id="de3a9-140">Den här principen ber dig registrera gäster för MFA i klient organisationen, oavsett om de är registrerade för MFA i sin hem klient organisation.</span><span class="sxs-lookup"><span data-stu-id="de3a9-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="de3a9-141">När du får åtkomst till resurser i klient organisationen måste gäst och externa användare använda MFA för varje begäran.</span><span class="sxs-lookup"><span data-stu-id="de3a9-141">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="de3a9-142">Exkluderar gäst och externa användare från riskfyllda MFA</span><span class="sxs-lookup"><span data-stu-id="de3a9-142">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="de3a9-143">Trots att organisationer kan använda riskbaserade principer för B2B-användare som använder Azure AD Identity Protection finns det begränsningar i implementeringen av Azure AD Identity Protection för B2B-samarbets användare i en resurs katalog på grund av deras identitet i sin Hem Katalog.</span><span class="sxs-lookup"><span data-stu-id="de3a9-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="de3a9-144">På grund av dessa begränsningar rekommenderar Microsoft att du exkluderar gäst användare från riskfyllda principer och kräver att dessa användare alltid använder MFA.</span><span class="sxs-lookup"><span data-stu-id="de3a9-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="de3a9-145">Mer information finns i [begränsningar för identitets skydd för B2B-samarbets användare](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="de3a9-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="de3a9-146">Exkludera gäst-och externa användare från enhets hantering</span><span class="sxs-lookup"><span data-stu-id="de3a9-146">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="de3a9-147">Endast en organisation kan hantera en enhet.</span><span class="sxs-lookup"><span data-stu-id="de3a9-147">Only one organization can manage a device.</span></span> <span data-ttu-id="de3a9-148">Om du inte utesluter gäst-och externa användare från principer som kräver att enheter efterlevs blockerar dessa användare.</span><span class="sxs-lookup"><span data-stu-id="de3a9-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="de3a9-149">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="de3a9-149">Next step</span></span>

![Steg 4: principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="de3a9-151">Konfigurera principer för villkorsstyrd åtkomst för:</span><span class="sxs-lookup"><span data-stu-id="de3a9-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="de3a9-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de3a9-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="de3a9-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="de3a9-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="de3a9-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="de3a9-154">SharePoint</span></span>](sharepoint-file-access-policies.md)

