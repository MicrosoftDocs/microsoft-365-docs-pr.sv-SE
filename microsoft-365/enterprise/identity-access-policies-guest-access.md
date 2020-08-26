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
ms.openlocfilehash: ad1203543db1c2bd0ea9e9bdd3433aad58db320b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898110"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="6b4e0-103">Principer för att tillåta gäst-och extern B2B-åtkomst</span><span class="sxs-lookup"><span data-stu-id="6b4e0-103">Policies for allowing guest and external B2B access</span></span>
<span data-ttu-id="6b4e0-104">I den här artikeln beskrivs hur du justerar de rekommenderade vanliga principer för identitet och enheter för att tillåta B2B-konto åtkomst (gäst-och externa användare).</span><span class="sxs-lookup"><span data-stu-id="6b4e0-104">This article describes how to adjust the recommended common identity and device access policies to allow B2B account access (guest and external users).</span></span> <span data-ttu-id="6b4e0-105">Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6b4e0-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="6b4e0-106">Dessa rekommendationer är avsedda att tillämpas på den **ursprungliga** skydds nivån.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="6b4e0-107">Men du kan ändra rekommendationerna baserat på hur **känsligt** och **starkt reglerade** skydd du behöver.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-107">However, you can adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="6b4e0-108">Om du tillhandahåller en sökväg för B2B-användare som autentiseras med din Azure AD-klient ger dessa användare åtkomst till hela din miljö.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-108">Providing a path for B2B users to authenticate with your Azure AD tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="6b4e0-109">B2B-användare har till gång till resurser som delas med dem (till exempel filer) inom de tjänster som beviljats i principer för villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the conditional access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="6b4e0-110">Uppdatera vanliga principer för att tillåta och skydda gäst och extern åtkomst</span><span class="sxs-lookup"><span data-stu-id="6b4e0-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="6b4e0-111">I följande diagram visas den vanliga policyn för identitets-och enhets åtkomst och visar (med en penna-ikon) vilka principer som du kan använda för att lägga till eller uppdatera för att skydda gäst och extern åtkomst.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-111">The following diagram illustrates the common identity and device access policies and indicates (with a pencil icon) which policies to add or update to protect guest and external access.</span></span> 

![Sammanfattning av princip uppdateringar för att skydda gäst åtkomst](../media/identity-access-ruleset-guest.png)

<span data-ttu-id="6b4e0-113">I följande tabell visas de principer som du måste uppdatera eller skapa nya.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-113">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="6b4e0-114">Gemensamma principer-länken till de associerade konfigurations anvisningarna i artikeln om [principer för åtkomst policys för identitet och enheter](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="6b4e0-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="6b4e0-115">Skydds nivå</span><span class="sxs-lookup"><span data-stu-id="6b4e0-115">Protection level</span></span>|<span data-ttu-id="6b4e0-116">Principerna</span><span class="sxs-lookup"><span data-stu-id="6b4e0-116">Policies</span></span>|<span data-ttu-id="6b4e0-117">Mer information</span><span class="sxs-lookup"><span data-stu-id="6b4e0-117">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="6b4e0-118">**Grundläggande**</span><span class="sxs-lookup"><span data-stu-id="6b4e0-118">**Baseline**</span></span>|[<span data-ttu-id="6b4e0-119">Kräv MFA alltid för gäst-och externa användare</span><span class="sxs-lookup"><span data-stu-id="6b4e0-119">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="6b4e0-120">Skapa den nya regeln och Använd den bara för gäster och externa användare.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-120">Create this new rule and apply it only to guests and external users.</span></span> <span data-ttu-id="6b4e0-121">Låt alla alternativ vara avmarkerade om du inte vill använda MFA.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-121">Under sign-in risk, leave all options unchecked to always enforce MFA.</span></span>|
|        |[<span data-ttu-id="6b4e0-122">Kräv MFA när en inloggnings risk är *mellan* eller *hög*</span><span class="sxs-lookup"><span data-stu-id="6b4e0-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="6b4e0-123">Ändra regeln så att den exkluderar gäst-och externa användare.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-123">Modify this rule to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="6b4e0-124">Kräv kompatibla PC-datorer</span><span class="sxs-lookup"><span data-stu-id="6b4e0-124">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="6b4e0-125">Ändra regeln så att den exkluderar gäst-och externa användare.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-125">Modify this rule to exclude guest and external users.</span></span>|

<span data-ttu-id="6b4e0-126">Om du vill inkludera eller exkludera gäster och externa användare i regler för villkorsstyrd åtkomst klickar du på fliken inkludera eller exkludera och markerar **alla gäster och externa användare**.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-126">To include or exclude guests and external users in conditional access rules, click the include or exclude tab and check **All guests and external users**.</span></span>

![skärm bild av kontroller för att exkludera gäster](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="6b4e0-128">Mer information</span><span class="sxs-lookup"><span data-stu-id="6b4e0-128">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="6b4e0-129">Gäster kontra externa användare</span><span class="sxs-lookup"><span data-stu-id="6b4e0-129">Guests vs. external users</span></span>
<span data-ttu-id="6b4e0-130">I Azure AD är gäst och externa användare desamma.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-130">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="6b4e0-131">Användar typen för båda dessa är gäster.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-131">The user type for both of these is Guest.</span></span> <span data-ttu-id="6b4e0-132">Gäst användare är B2B-användare.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-132">Guest users are B2B users.</span></span>

<span data-ttu-id="6b4e0-133">Microsoft Teams skiljer sig mellan gäst användare och externa användare inom programmet, men dessa båda är båda B2B-användare vid autentisering.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-133">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="6b4e0-134">Mer information om Teams gäst och externa användare finns i [Aktivera gäst och extern åtkomst till Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span><span class="sxs-lookup"><span data-stu-id="6b4e0-134">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="6b4e0-135">Kräv MFA alltid för gäst-och externa användare</span><span class="sxs-lookup"><span data-stu-id="6b4e0-135">Require MFA always for guest and external users</span></span>
<span data-ttu-id="6b4e0-136">Den här regeln ber dig registrera sig för MFA i klient organisationen, oavsett om de är registrerade för MFA i sin hem klient organisation.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-136">This rule prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="6b4e0-137">När du får åtkomst till resurser i klient organisationen måste gäster och externa användare använda MFA för varje begäran.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-137">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="6b4e0-138">Exkluderar gäst och externa användare från riskfyllda MFA</span><span class="sxs-lookup"><span data-stu-id="6b4e0-138">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="6b4e0-139">Även om organisationer kan tvinga fram riskbaserade principer för B2B-användare som använder identitets skydd finns det begränsningar i implementeringen av identitets skydd för B2B-samarbets användare i en resurs katalog på grund av deras identitet i sin Hem Katalog.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-139">While organizations can enforce risk-based policies for B2B users using Identity Protection, there are limitations in the implementation of Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="6b4e0-140">På grund av dessa begränsningar rekommenderar Microsoft att du exkluderar gäst användare från riskfyllda principer och kräver att dessa användare alltid använder MFA.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-140">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="6b4e0-141">Mer information finns i [begränsningar för identitets skydd för B2B-samarbets användare](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="6b4e0-141">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="6b4e0-142">Exkludera gäst-och externa användare från enhets hantering</span><span class="sxs-lookup"><span data-stu-id="6b4e0-142">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="6b4e0-143">Endast en organisation kan hantera en enhet.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-143">Only one organization can manage a device.</span></span> <span data-ttu-id="6b4e0-144">Om du inte utesluter gäst-och externa användare från principer som kräver att enheter efterlevs blockerar dessa användare.</span><span class="sxs-lookup"><span data-stu-id="6b4e0-144">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="6b4e0-145">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6b4e0-145">Next steps</span></span>

[<span data-ttu-id="6b4e0-146">Lär dig hur du aktiverar Teams villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="6b4e0-146">Learn how to enable Teams conditional access</span></span>](teams-access-policies.md)

