---
title: Identitets- och enhetsåtkomstpolicyer för att tillåta gäst och extern B2B-åtkomst – Microsoft 365 Enterprise | Microsoft Dokument
description: Beskriver den rekommenderade villkorligåtkomst och relaterade principer för att skydda åtkomsten för gäst och externa användare.
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8276dcf85f6c5fd61e01e67deee4fea35c1a15c4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807657"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="74ba1-103">Policyer för att tillåta gäst och extern B2B-åtkomst</span><span class="sxs-lookup"><span data-stu-id="74ba1-103">Policies for allowing guest and external B2B access</span></span>
<span data-ttu-id="74ba1-104">I den här artikeln beskrivs hur du justerar de rekommenderade vanliga identitets- och enhetsåtkomstprinciperna så att B2B-kontoåtkomst (gäst och externa användare) kan justeras.</span><span class="sxs-lookup"><span data-stu-id="74ba1-104">This article describes how to adjust the recommended common identity and device access policies to allow B2B account access (guest and external users).</span></span> <span data-ttu-id="74ba1-105">Den här vägledningen bygger på principerna [för gemensam identitet och enhetsåtkomst](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="74ba1-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="74ba1-106">Dessa rekommendationer är utformade för att gälla **för baslinjenivån** för skydd.</span><span class="sxs-lookup"><span data-stu-id="74ba1-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="74ba1-107">Du kan dock justera rekommendationerna baserat på granulariteten i dina behov av **känsligt** och **starkt reglerat** skydd.</span><span class="sxs-lookup"><span data-stu-id="74ba1-107">However, you can adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="74ba1-108">Att tillhandahålla en sökväg för B2B-användare att autentisera med din Azure AD-klient ger inte dessa användare åtkomst till hela din miljö.</span><span class="sxs-lookup"><span data-stu-id="74ba1-108">Providing a path for B2B users to authenticate with your Azure AD tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="74ba1-109">B2B-användare har bara tillgång till resurser som delas med dem (t.ex. filer) inom de tjänster som beviljas i principerna för villkorsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="74ba1-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the conditional access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="74ba1-110">Uppdatera de gemensamma principerna för att tillåta och skydda gäst och extern åtkomst</span><span class="sxs-lookup"><span data-stu-id="74ba1-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="74ba1-111">Följande diagram illustrerar principerna för gemensam identitet och enhetsåtkomst och anger (med en pennikon) vilka principer som ska läggas till eller uppdateras för att skydda gäst och extern åtkomst.</span><span class="sxs-lookup"><span data-stu-id="74ba1-111">The following diagram illustrates the common identity and device access policies and indicates (with a pencil icon) which policies to add or update to protect guest and external access.</span></span> 

![Sammanfattning av principuppdateringar för att skydda gäståtkomst](../media/identity-access-ruleset-guest.png)

<span data-ttu-id="74ba1-113">I följande tabell visas de principer som du antingen behöver uppdatera eller skapa nya.</span><span class="sxs-lookup"><span data-stu-id="74ba1-113">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="74ba1-114">De gemensamma principerna länkar till de associerade konfigurationsinstruktionerna i artikeln [Gemensamma identitets- och enhetsåtkomstprinciper.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="74ba1-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="74ba1-115">Skyddsnivå</span><span class="sxs-lookup"><span data-stu-id="74ba1-115">Protection level</span></span>|<span data-ttu-id="74ba1-116">Politik</span><span class="sxs-lookup"><span data-stu-id="74ba1-116">Policies</span></span>|<span data-ttu-id="74ba1-117">Mer information</span><span class="sxs-lookup"><span data-stu-id="74ba1-117">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="74ba1-118">**Originalplan**</span><span class="sxs-lookup"><span data-stu-id="74ba1-118">**Baseline**</span></span>|[<span data-ttu-id="74ba1-119">Kräv MFA alltid för gäst- och externa användare</span><span class="sxs-lookup"><span data-stu-id="74ba1-119">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="74ba1-120">Skapa den här nya regeln och tillämpa den endast för gäster och externa användare.</span><span class="sxs-lookup"><span data-stu-id="74ba1-120">Create this new rule and apply it only to guests and external users.</span></span> <span data-ttu-id="74ba1-121">Under inloggningsrisk lämnar du alla alternativ omarkerade för att alltid genomdriva MFA.</span><span class="sxs-lookup"><span data-stu-id="74ba1-121">Under sign-in risk, leave all options unchecked to always enforce MFA.</span></span>|
|        |[<span data-ttu-id="74ba1-122">Kräv MFA när inloggningsrisken är *medelhög* eller *hög*</span><span class="sxs-lookup"><span data-stu-id="74ba1-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="74ba1-123">Ändra den här regeln om du vill utesluta gästanvändare och externa användare.</span><span class="sxs-lookup"><span data-stu-id="74ba1-123">Modify this rule to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="74ba1-124">Kräv kompatibla datorer</span><span class="sxs-lookup"><span data-stu-id="74ba1-124">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="74ba1-125">Ändra den här regeln om du vill utesluta gästanvändare och externa användare.</span><span class="sxs-lookup"><span data-stu-id="74ba1-125">Modify this rule to exclude guest and external users.</span></span>|

<span data-ttu-id="74ba1-126">Om du vill inkludera eller utesluta gäster och externa användare i regler för villkorlig åtkomst klickar du på fliken Inkludera eller uteslut och kontrollerar **Alla gäster och externa användare**.</span><span class="sxs-lookup"><span data-stu-id="74ba1-126">To include or exclude guests and external users in conditional access rules, click the include or exclude tab and check **All guests and external users**.</span></span>

![skärminspelning av kontroller för att utesluta gäster](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="74ba1-128">Mer information</span><span class="sxs-lookup"><span data-stu-id="74ba1-128">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="74ba1-129">Gäster kontra externa användare</span><span class="sxs-lookup"><span data-stu-id="74ba1-129">Guests vs. external users</span></span>
<span data-ttu-id="74ba1-130">I Azure AD är gäst och externa användare desamma.</span><span class="sxs-lookup"><span data-stu-id="74ba1-130">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="74ba1-131">Användartypen för båda dessa är Gäst.</span><span class="sxs-lookup"><span data-stu-id="74ba1-131">The user type for both of these is Guest.</span></span> <span data-ttu-id="74ba1-132">Gästanvändare är B2B-användare.</span><span class="sxs-lookup"><span data-stu-id="74ba1-132">Guest users are B2B users.</span></span>

<span data-ttu-id="74ba1-133">Microsoft Teams skiljer mellan gästanvändare och externa användare i appen, men dessa är båda B2B-användare när de autentiseras.</span><span class="sxs-lookup"><span data-stu-id="74ba1-133">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="74ba1-134">Mer information om Teams-gäst och externa användare finns i [Aktivera gäst och extern åtkomst för Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span><span class="sxs-lookup"><span data-stu-id="74ba1-134">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="74ba1-135">Kräv MFA alltid för gäst- och externa användare</span><span class="sxs-lookup"><span data-stu-id="74ba1-135">Require MFA always for guest and external users</span></span>
<span data-ttu-id="74ba1-136">Den här regeln uppmanar gästerna att registrera dig för MFA i din klientorganisation, oavsett om de är registrerade för MFA i sin hemklient.</span><span class="sxs-lookup"><span data-stu-id="74ba1-136">This rule prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="74ba1-137">När du använder resurser i din klientmåste gäster och externa användare använda MFA för varje begäran.</span><span class="sxs-lookup"><span data-stu-id="74ba1-137">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="74ba1-138">Exklusive gäst- och externa användare från riskbaserad MFA</span><span class="sxs-lookup"><span data-stu-id="74ba1-138">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="74ba1-139">Organisationer kan tillämpa riskbaserade principer för B2B-användare som använder identitetsskydd, men det finns begränsningar i implementeringen av användare av identitetsskydd för B2B-samarbete i en resurskatalog på grund av deras identitet som finns i deras hem Katalog.</span><span class="sxs-lookup"><span data-stu-id="74ba1-139">While organizations can enforce risk-based policies for B2B users using Identity Protection, there are limitations in the implementation of Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="74ba1-140">På grund av dessa begränsningar rekommenderar Microsoft att du utesluter gästanvändare från riskbaserade MFA-principer och kräver att dessa användare alltid använder MFA.</span><span class="sxs-lookup"><span data-stu-id="74ba1-140">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="74ba1-141">Mer information finns i [Begränsningar av identitetsskydd för B2B-samarbetsanvändare](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="74ba1-141">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="74ba1-142">Exklusive gäst- och externa användare från enhetshantering</span><span class="sxs-lookup"><span data-stu-id="74ba1-142">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="74ba1-143">Endast en organisation kan hantera en enhet.</span><span class="sxs-lookup"><span data-stu-id="74ba1-143">Only one organization can manage a device.</span></span> <span data-ttu-id="74ba1-144">Om du inte utesluter gästanvändare och externa användare från principer som kräver enhetsefterlevnad blockerar dessa principer dessa användare.</span><span class="sxs-lookup"><span data-stu-id="74ba1-144">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="74ba1-145">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="74ba1-145">Next steps</span></span>

[<span data-ttu-id="74ba1-146">Läs om hur du aktiverar teams villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="74ba1-146">Learn how to enable Teams conditional access</span></span>](teams-access-policies.md)

