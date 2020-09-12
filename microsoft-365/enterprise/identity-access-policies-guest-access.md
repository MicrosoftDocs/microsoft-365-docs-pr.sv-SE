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
ms.openlocfilehash: a88fc5f46a6dafda72a24ba5e80587b24a216955
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546494"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="40dae-103">Principer för att tillåta gäst-och extern B2B-åtkomst</span><span class="sxs-lookup"><span data-stu-id="40dae-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="40dae-104">I den här artikeln beskrivs hur du justerar de rekommenderade vanliga principerna för identitets-och enhets åtkomst för att tillåta åtkomst till konton för företag-till-företag (gäst-och externa användare).</span><span class="sxs-lookup"><span data-stu-id="40dae-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="40dae-105">Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="40dae-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="40dae-106">Dessa rekommendationer är avsedda att tillämpas på den **ursprungliga** skydds nivån.</span><span class="sxs-lookup"><span data-stu-id="40dae-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="40dae-107">Men du kan också justera rekommendationerna baserat på hur många olika behov du har för **känsligt** och **starkt reglerat** skydd.</span><span class="sxs-lookup"><span data-stu-id="40dae-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="40dae-108">Om du tillhandahåller en väg för B2B-användare att autentisera med Azure Active Directory-klienten (Azure AD) ger dessa användare åtkomst till hela din miljö.</span><span class="sxs-lookup"><span data-stu-id="40dae-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="40dae-109">B2B-användare har till gång till resurser som delas med dem (till exempel filer) inom de tjänster som beviljats i principer för villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="40dae-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="40dae-110">Uppdatera vanliga principer för att tillåta och skydda gäst och extern åtkomst</span><span class="sxs-lookup"><span data-stu-id="40dae-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="40dae-111">För att skydda gäst och extern åtkomst illustrerar följande diagram vilka principer du kan lägga till eller uppdatera från principer för åtkomst till identitet och enheter.</span><span class="sxs-lookup"><span data-stu-id="40dae-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="40dae-112">[![Sammanfattning av princip uppdateringar för att skydda gäst åtkomst](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="40dae-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="40dae-113">Visa en större version av bilden</span><span class="sxs-lookup"><span data-stu-id="40dae-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="40dae-114">I följande tabell visas de principer som du måste uppdatera eller skapa nya.</span><span class="sxs-lookup"><span data-stu-id="40dae-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="40dae-115">Gemensamma principer-länken till de associerade konfigurations anvisningarna i artikeln om [principer för åtkomst policys för identitet och enheter](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="40dae-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="40dae-116">Skydds nivå</span><span class="sxs-lookup"><span data-stu-id="40dae-116">Protection level</span></span>|<span data-ttu-id="40dae-117">Principerna</span><span class="sxs-lookup"><span data-stu-id="40dae-117">Policies</span></span>|<span data-ttu-id="40dae-118">Mer information</span><span class="sxs-lookup"><span data-stu-id="40dae-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="40dae-119">**Grundläggande**</span><span class="sxs-lookup"><span data-stu-id="40dae-119">**Baseline**</span></span>|[<span data-ttu-id="40dae-120">Kräv MFA alltid för gäst-och externa användare</span><span class="sxs-lookup"><span data-stu-id="40dae-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="40dae-121">Skapa den nya principen och Använd den bara för gäster och externa användare.</span><span class="sxs-lookup"><span data-stu-id="40dae-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="40dae-122">Låt alla alternativ vara avmarkerade under **inloggnings risker**så att multifaktorautentisering alltid upprätthålls (MFA).</span><span class="sxs-lookup"><span data-stu-id="40dae-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="40dae-123">Kräv MFA när en inloggnings risk är *mellan* eller *hög*</span><span class="sxs-lookup"><span data-stu-id="40dae-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="40dae-124">Ändra den här principen så att den exkluderar gäst-och externa användare.</span><span class="sxs-lookup"><span data-stu-id="40dae-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="40dae-125">Kräv kompatibla PC-datorer</span><span class="sxs-lookup"><span data-stu-id="40dae-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="40dae-126">Ändra den här principen så att den exkluderar gäst-och externa användare.</span><span class="sxs-lookup"><span data-stu-id="40dae-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="40dae-127">Om du vill inkludera eller exkludera gäster och externa användare i principer för villkorsstyrd åtkomst klickar du på fliken **Inkludera** eller **exkludera** och markerar **alla gäster och externa användare**.</span><span class="sxs-lookup"><span data-stu-id="40dae-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![skärm bild av kontroller för att exkludera gäster](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="40dae-129">Mer information</span><span class="sxs-lookup"><span data-stu-id="40dae-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="40dae-130">Gäster kontra externa användare</span><span class="sxs-lookup"><span data-stu-id="40dae-130">Guests vs. external users</span></span>
<span data-ttu-id="40dae-131">I Azure AD är gäst och externa användare desamma.</span><span class="sxs-lookup"><span data-stu-id="40dae-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="40dae-132">Användar typen för båda dessa är gäster.</span><span class="sxs-lookup"><span data-stu-id="40dae-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="40dae-133">Gäst användare är B2B-användare.</span><span class="sxs-lookup"><span data-stu-id="40dae-133">Guest users are B2B users.</span></span>

<span data-ttu-id="40dae-134">Microsoft Teams skiljer sig mellan gäst användare och externa användare inom programmet, men dessa båda är båda B2B-användare vid autentisering.</span><span class="sxs-lookup"><span data-stu-id="40dae-134">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="40dae-135">Mer information om Teams gäst och externa användare finns i [Aktivera gäst och extern åtkomst till Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span><span class="sxs-lookup"><span data-stu-id="40dae-135">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="40dae-136">Kräv MFA alltid för gäst-och externa användare</span><span class="sxs-lookup"><span data-stu-id="40dae-136">Require MFA always for guest and external users</span></span>
<span data-ttu-id="40dae-137">Den här principen ber dig registrera gäster för MFA i klient organisationen, oavsett om de är registrerade för MFA i sin hem klient organisation.</span><span class="sxs-lookup"><span data-stu-id="40dae-137">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="40dae-138">När du får åtkomst till resurser i klient organisationen måste gäster och externa användare använda MFA för varje begäran.</span><span class="sxs-lookup"><span data-stu-id="40dae-138">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="40dae-139">Exkluderar gäst och externa användare från riskfyllda MFA</span><span class="sxs-lookup"><span data-stu-id="40dae-139">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="40dae-140">Trots att organisationer kan använda riskbaserade principer för B2B-användare som använder Azure AD Identity Protection finns det begränsningar i implementeringen av Azure AD Identity Protection för B2B-samarbets användare i en resurs katalog på grund av deras identitet i sin Hem Katalog.</span><span class="sxs-lookup"><span data-stu-id="40dae-140">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="40dae-141">På grund av dessa begränsningar rekommenderar Microsoft att du exkluderar gäst användare från riskfyllda principer och kräver att dessa användare alltid använder MFA.</span><span class="sxs-lookup"><span data-stu-id="40dae-141">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="40dae-142">Mer information finns i [begränsningar för identitets skydd för B2B-samarbets användare](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="40dae-142">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="40dae-143">Exkludera gäst-och externa användare från enhets hantering</span><span class="sxs-lookup"><span data-stu-id="40dae-143">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="40dae-144">Endast en organisation kan hantera en enhet.</span><span class="sxs-lookup"><span data-stu-id="40dae-144">Only one organization can manage a device.</span></span> <span data-ttu-id="40dae-145">Om du inte utesluter gäst-och externa användare från principer som kräver att enheter efterlevs blockerar dessa användare.</span><span class="sxs-lookup"><span data-stu-id="40dae-145">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="40dae-146">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="40dae-146">Next step</span></span>

![Steg 4: principer för Microsoft 365-molnappar](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="40dae-148">Konfigurera principer för villkorsstyrd åtkomst för:</span><span class="sxs-lookup"><span data-stu-id="40dae-148">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="40dae-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40dae-149">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="40dae-150">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="40dae-150">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="40dae-151">SharePoint</span><span class="sxs-lookup"><span data-stu-id="40dae-151">SharePoint</span></span>](secure-email-recommended-policies.md)

