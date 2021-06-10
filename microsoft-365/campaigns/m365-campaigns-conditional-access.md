---
title: Aktivera säkerhetsstandarder
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur säkerhetsstandarder kan skydda organisationen från identitetsrelaterade attacker genom att ange förkonfigurerade säkerhetsinställningar.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398302"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="24b16-103">Aktivera säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="24b16-103">Turn on security defaults</span></span>

<span data-ttu-id="24b16-104">Säkerhetsstandarder hjälper till att skydda organisationen från identitetsrelaterade attacker genom att tillhandahålla förkonfigurerade säkerhetsinställningar som Microsoft hanterar för din organisations räkning.</span><span class="sxs-lookup"><span data-stu-id="24b16-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="24b16-105">De här inställningarna omfattar aktivering av multifaktorautentisering (MFA) för alla administratörer och användarkonton.</span><span class="sxs-lookup"><span data-stu-id="24b16-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="24b16-106">För de flesta organisationer erbjuder säkerhetsstandarder en bra nivå av ytterligare inloggningssäkerhet.</span><span class="sxs-lookup"><span data-stu-id="24b16-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="24b16-107">Mer information om säkerhetsstandarder och de principer de tillämpar finns i [Vad är standardinställningar för säkerhet?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="24b16-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="24b16-108">Om prenumerationen skapades den 22 oktober 2019 eller efter den 22 oktober 2019 kan säkerhetsstandarder ha aktiverats automatiskt. Kontrollera inställningarna &mdash; för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="24b16-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="24b16-109">Så här aktiverar du säkerhetsstandardvärden i Azure Active Directory (Azure AD) eller kontrollerar om de redan är aktiverade:</span><span class="sxs-lookup"><span data-stu-id="24b16-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="24b16-110">Logga in på Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">med autentiseringsuppgifterna</a> för global administratör.</span><span class="sxs-lookup"><span data-stu-id="24b16-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="24b16-111">I den vänstra rutan väljer **du Visa alla och** under **Administrationscenter** väljer du **sedan Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="24b16-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="24b16-112">I det vänstra fönstret i **Azure Active Directory väljer du** **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="24b16-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="24b16-113">I den vänstra menyn på Instrumentpanelen går du till **avsnittet Hantera** och väljer **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="24b16-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Skärmbild av Azure Active Directory administrationscenter som visar platsen för menyobjektet Egenskaper.":::

5. <span data-ttu-id="24b16-115">Längst ned på sidan **Egenskaper** väljer du **Hantera säkerhetsstandarder.**</span><span class="sxs-lookup"><span data-stu-id="24b16-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="24b16-116">I det högra fönstret visas standardinställningen **Aktivera** säkerhet.</span><span class="sxs-lookup"><span data-stu-id="24b16-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="24b16-117">Om **Ja** har valts är säkerhetsstandardvärden redan aktiverade och inga ytterligare åtgärder krävs.</span><span class="sxs-lookup"><span data-stu-id="24b16-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="24b16-118">Om säkerhetsstandarder inte är aktiverade, väljer du **Ja** för att aktivera dem och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="24b16-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="24b16-119">Om du har använt villkorsstyrda åtkomstprinciper måste du inaktivera dem innan du använder säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="24b16-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="24b16-120">Du kan använda antingen säkerhetsstandarder eller villkorsstyrda åtkomstprinciper, men du kan inte använda båda samtidigt.</span><span class="sxs-lookup"><span data-stu-id="24b16-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="24b16-121">Överväg att använda villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="24b16-121">Consider using Conditional Access</span></span>

<span data-ttu-id="24b16-122">Om organisationen har komplexa säkerhetskrav eller om du behöver mer detaljerad kontroll över dina säkerhetsprinciper bör du överväga att använda villkorsstyrd åtkomst i stället för säkerhetsstandarder för att uppnå ett liknande eller högre säkerhetsbeteende.</span><span class="sxs-lookup"><span data-stu-id="24b16-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="24b16-123">Med villkorsstyrd åtkomst kan du skapa och definiera principer som reagerar på inloggningshändelser och begär ytterligare åtgärder innan en användare beviljas åtkomst till ett program eller en tjänst.</span><span class="sxs-lookup"><span data-stu-id="24b16-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="24b16-124">Villkorsstyrda principer kan vara detaljerade och specifika så att användarna kan vara produktiva var och när som helst, men även skydda organisationen.</span><span class="sxs-lookup"><span data-stu-id="24b16-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="24b16-125">Standardinställningar för säkerhet är tillgängliga för alla kunder, medan villkorsstyrd åtkomst kräver en licens för något av följande abonnemang:</span><span class="sxs-lookup"><span data-stu-id="24b16-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="24b16-126">Azure Active Directory Premium P1 eller P2</span><span class="sxs-lookup"><span data-stu-id="24b16-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="24b16-127">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="24b16-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="24b16-128">Microsoft 365 E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="24b16-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="24b16-129">Enterprise Mobility & Security E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="24b16-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="24b16-130">Om du vill använda villkorsstyrd åtkomst för att konfigurera principer som motsvarar dem som aktiverats som säkerhetsstandard tar du en del av följande steg-för-steg-guider:</span><span class="sxs-lookup"><span data-stu-id="24b16-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="24b16-131">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="24b16-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="24b16-132">Kräv MFA för Azure-hantering</span><span class="sxs-lookup"><span data-stu-id="24b16-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="24b16-133">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="24b16-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="24b16-134">Kräv MFA för alla användare</span><span class="sxs-lookup"><span data-stu-id="24b16-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="24b16-135">[Kräv Azure AD MFA-registrering](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) – kräver Azure AD Identity Protection, som är en del av Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="24b16-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="24b16-136">Mer information om villkorsstyrd åtkomst finns i [Vad är villkorsstyrd åtkomst?](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="24b16-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="24b16-137">Mer information om hur du skapar principer för villkorsstyrd åtkomst finns [i Skapa en princip för villkorsstyrd åtkomst.](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)</span><span class="sxs-lookup"><span data-stu-id="24b16-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="24b16-138">Om du har ett abonnemang eller en licens som tillhandahåller villkorsstyrd åtkomst men ännu inte har skapat några principer för villkorsstyrd åtkomst får du använda säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="24b16-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="24b16-139">Du måste dock inaktivera säkerhetsstandarder innan du kan använda villkorsstyrda åtkomstprinciper.</span><span class="sxs-lookup"><span data-stu-id="24b16-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
