---
title: Principer för identitets- och enhetsåtkomst för att tillåta gäst- och extern användares B2B-åtkomst – Microsoft 365 för företag| Microsoft Docs
description: Här beskrivs den rekommenderade villkorsstyrda åtkomsten och relaterade principer för att skydda åtkomst för gäster och externa användare.
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932616"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="4e750-103">Principer för att tillåta gäståtkomst och åtkomst för B2B-externa användare</span><span class="sxs-lookup"><span data-stu-id="4e750-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="4e750-104">I den här artikeln beskrivs hur du justerar rekommenderade principer för enhets- och identitetsåtkomst för att tillåta åtkomst för gäster och externa användare som har ett Azure Active Directory-konto (Azure AD) business-to-business (B2B).</span><span class="sxs-lookup"><span data-stu-id="4e750-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="4e750-105">Den här vägledningen bygger på de [gemensamma principerna för identitets- och enhetsåtkomst.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4e750-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="4e750-106">De här rekommendationerna är utformade för att gälla **baslinjenivån** för skyddet.</span><span class="sxs-lookup"><span data-stu-id="4e750-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="4e750-107">Men du kan också justera rekommendationerna utifrån dina specifika behov för **känsligt och** **starkt reglerat** skydd.</span><span class="sxs-lookup"><span data-stu-id="4e750-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="4e750-108">Att tillhandahålla en sökväg för B2B-konton för autentisering med din Azure AD-klientorganisation ger inte dessa konton åtkomst till hela miljön.</span><span class="sxs-lookup"><span data-stu-id="4e750-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="4e750-109">B2B-användare och deras konton har åtkomst till tjänster och resurser, som filer, som delas med dem genom villkorsstyrd åtkomstprincip.</span><span class="sxs-lookup"><span data-stu-id="4e750-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="4e750-110">Uppdatera vanliga principer för att tillåta och skydda gäster och åtkomst för externa användare</span><span class="sxs-lookup"><span data-stu-id="4e750-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="4e750-111">Det här diagrammet visar vilka principer som ska läggas till eller uppdateras bland vanliga principer för identitets- och enhetsåtkomst, för B2B-gäst- och extern användaråtkomst.</span><span class="sxs-lookup"><span data-stu-id="4e750-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="4e750-112">[![Sammanfattning av principuppdateringar för att skydda gäståtkomst](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="4e750-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="4e750-113">Visa en större version av den här bilden</span><span class="sxs-lookup"><span data-stu-id="4e750-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="4e750-114">I följande tabell visas de principer som du antingen behöver skapa och uppdatera.</span><span class="sxs-lookup"><span data-stu-id="4e750-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="4e750-115">De vanliga principerna länkar till de tillhörande konfigurationsanvisningarna i [artikeln Principer för gemensamma identiteter och enhetsåtkomst.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4e750-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="4e750-116">Skyddsnivå</span><span class="sxs-lookup"><span data-stu-id="4e750-116">Protection level</span></span>|<span data-ttu-id="4e750-117">Principer</span><span class="sxs-lookup"><span data-stu-id="4e750-117">Policies</span></span>|<span data-ttu-id="4e750-118">Mer information</span><span class="sxs-lookup"><span data-stu-id="4e750-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="4e750-119">**Grundläggande**</span><span class="sxs-lookup"><span data-stu-id="4e750-119">**Baseline**</span></span>|[<span data-ttu-id="4e750-120">Kräv alltid MFA för gäster och externa användare</span><span class="sxs-lookup"><span data-stu-id="4e750-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="4e750-121">Skapa den här nya principen och konfigurera:</span><span class="sxs-lookup"><span data-stu-id="4e750-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="4e750-122">För **Tilldelningar > användare** och grupper > Välj användare och grupper och välj sedan **Alla gästanvändare och externa användare.**</span><span class="sxs-lookup"><span data-stu-id="4e750-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="4e750-123">Om **det >** villkor > du logga in låter du alla alternativ vara avmarkerade för att alltid tillämpa multifaktorautentisering (MFA).</span><span class="sxs-lookup"><span data-stu-id="4e750-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="4e750-124">Kräv MFA när inloggningsrisken är *medelhög* eller *hög*</span><span class="sxs-lookup"><span data-stu-id="4e750-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="4e750-125">Ändra den här principen för att utesluta gäster och externa användare.</span><span class="sxs-lookup"><span data-stu-id="4e750-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="4e750-126">Kräv kompatibla PC-datorer</span><span class="sxs-lookup"><span data-stu-id="4e750-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="4e750-127">Ändra den här principen för att utesluta gäster och externa användare.</span><span class="sxs-lookup"><span data-stu-id="4e750-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="4e750-128">Om du vill inkludera eller exkludera gäster och externa användare i **villkorsstyrda åtkomstprinciper** markerar du, för Tilldelningar > Användare och grupper > Inkludera eller **Exkludera,** markera Alla gästanvändare och **externa användare.**</span><span class="sxs-lookup"><span data-stu-id="4e750-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![skärmdump av kontroller för att utesluta gäster och externa användare](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="4e750-130">Mer information</span><span class="sxs-lookup"><span data-stu-id="4e750-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="4e750-131">Gäster och åtkomst för externa användare med Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e750-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="4e750-132">Microsoft Teams definierar följande användare:</span><span class="sxs-lookup"><span data-stu-id="4e750-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="4e750-133">**Gäståtkomst** använder ett Azure AD B2B-konto som kan läggas till som medlem i ett team och har åtkomst till teamets kommunikation och resurser.</span><span class="sxs-lookup"><span data-stu-id="4e750-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="4e750-134">**Extern åtkomst** är för en extern användare som inte har ett B2B-konto.</span><span class="sxs-lookup"><span data-stu-id="4e750-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="4e750-135">Extern användaråtkomst omfattar inbjudningar, samtal, chattar och möten, men omfattar inte teammedlemskap och åtkomst till teamets resurser.</span><span class="sxs-lookup"><span data-stu-id="4e750-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="4e750-136">Mer information finns i [jämförelsen mellan gäster och extern användaråtkomst för team.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="4e750-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="4e750-137">Mer information om hur du skyddar identitets- och enhetsåtkomstprinciper för Teams finns i principrekommendationer för att skydda [Chattar, grupper och filer i Teams.](teams-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4e750-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="4e750-138">Kräv MFA alltid för gästanvändare och externa användare</span><span class="sxs-lookup"><span data-stu-id="4e750-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="4e750-139">Den här principen uppmanar gäster att registrera sig för MFA i din klientorganisation, oavsett om de är registrerade för MFA i sin hemklientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4e750-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="4e750-140">När du ska få åtkomst till resurser i klientorganisationen måste gäster och externa användare använda MFA för varje begäran.</span><span class="sxs-lookup"><span data-stu-id="4e750-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="4e750-141">Utesluta gäster och externa användare från riskbaserade MFA</span><span class="sxs-lookup"><span data-stu-id="4e750-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="4e750-142">Även om organisationer kan tillämpa riskbaserade principer för B2B-användare med Azure AD Identity Protection, finns det begränsningar i implementeringen av Azure AD Identity Protection för B2B-samarbetsanvändare i en resurskatalog på grund av att deras identitet finns i deras hemkatalog.</span><span class="sxs-lookup"><span data-stu-id="4e750-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="4e750-143">På grund av dessa begränsningar rekommenderar Microsoft att du undantar gäster från riskbaserade MFA-policyer och kräver att dessa användare alltid använder MFA.</span><span class="sxs-lookup"><span data-stu-id="4e750-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="4e750-144">Mer information finns i Begränsningar [av identitetsskydd för B2B-samarbetsanvändare.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="4e750-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="4e750-145">Utesluta gäster och externa användare från enhetshantering</span><span class="sxs-lookup"><span data-stu-id="4e750-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="4e750-146">Det är bara en organisation som kan hantera en enhet.</span><span class="sxs-lookup"><span data-stu-id="4e750-146">Only one organization can manage a device.</span></span> <span data-ttu-id="4e750-147">Om du inte utesluter gäster och externa användare från principer som kräver enhetsefterlevnad blockerar dessa principer dessa användare.</span><span class="sxs-lookup"><span data-stu-id="4e750-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="4e750-148">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4e750-148">Next step</span></span>

![Steg 4: Principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="4e750-150">Konfigurera villkorsstyrda åtkomstprinciper för:</span><span class="sxs-lookup"><span data-stu-id="4e750-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="4e750-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e750-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="4e750-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e750-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="4e750-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e750-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
