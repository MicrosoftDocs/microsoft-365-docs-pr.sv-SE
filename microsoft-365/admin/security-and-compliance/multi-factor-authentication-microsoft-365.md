---
title: Multifaktorautentisering för Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig mer om multifaktorautentisering i Microsoft 365.
ms.openlocfilehash: eba9ae38dbc17a22abb5d5ef92b8cd30a827ae11
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371458"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="5ef16-103">Multifaktorautentisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ef16-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="5ef16-104">Lösenord är den vanligaste metoden för att autentisera en inloggning till en dator eller onlinetjänst, men de är också de mest sårbara.</span><span class="sxs-lookup"><span data-stu-id="5ef16-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="5ef16-105">Människor kan välja enkla lösenord och använda samma lösenord för flera inloggningar till olika datorer och tjänster.</span><span class="sxs-lookup"><span data-stu-id="5ef16-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="5ef16-106">Om du vill ange ytterligare en säkerhetsnivå för inloggningar måste du använda MFA (Multifaktor authentication), som använder både ett lösenord, som ska vara starkt, och en ytterligare verifieringsmetod baserad på:</span><span class="sxs-lookup"><span data-stu-id="5ef16-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="5ef16-107">Något du har med dig som inte är lätt dupliceras, till exempel en smart telefon.</span><span class="sxs-lookup"><span data-stu-id="5ef16-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="5ef16-108">Något du unikt och biologiskt har, till exempel dina fingeravtryck, ansikte eller andra biometriska attribut.</span><span class="sxs-lookup"><span data-stu-id="5ef16-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="5ef16-109">Den ytterligare verifieringsmetoden används inte förrän användarens lösenord har verifierats.</span><span class="sxs-lookup"><span data-stu-id="5ef16-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="5ef16-110">Med MFA, även om ett starkt användarlösenord äventyras, har angriparen inte din smarta telefon eller ditt fingeravtryck för att slutföra inloggningen.</span><span class="sxs-lookup"><span data-stu-id="5ef16-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="5ef16-111">MFA-stöd i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ef16-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="5ef16-112">Som standard stöder både Microsoft 365 och Office 365 MFA för användarkonton med hjälp av:</span><span class="sxs-lookup"><span data-stu-id="5ef16-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="5ef16-113">Ett sms som skickas till en telefon som kräver att användaren skriver en verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="5ef16-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="5ef16-114">Ett telefonsamtal.</span><span class="sxs-lookup"><span data-stu-id="5ef16-114">A phone call.</span></span>
- <span data-ttu-id="5ef16-115">Microsoft Authenticator-appen för smarta telefoner.</span><span class="sxs-lookup"><span data-stu-id="5ef16-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="5ef16-116">I båda fallen använder MFA-inloggningen metoden "något du har med dig som inte är lätt att duplicera" för ytterligare verifiering.</span><span class="sxs-lookup"><span data-stu-id="5ef16-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="5ef16-117">Det finns flera sätt att aktivera MFA för Microsoft 365 och Office 365:</span><span class="sxs-lookup"><span data-stu-id="5ef16-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="5ef16-118">Med säkerhet standardvärden</span><span class="sxs-lookup"><span data-stu-id="5ef16-118">With security defaults</span></span>
- <span data-ttu-id="5ef16-119">Med principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="5ef16-119">With Conditional Access policies</span></span>
- <span data-ttu-id="5ef16-120">För varje enskilt användarkonto (rekommenderas inte)</span><span class="sxs-lookup"><span data-stu-id="5ef16-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="5ef16-121">De här sätten baseras på ditt Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="5ef16-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="5ef16-122">Planera</span><span class="sxs-lookup"><span data-stu-id="5ef16-122">Plan</span></span>  |<span data-ttu-id="5ef16-123">Rekommendation</span><span class="sxs-lookup"><span data-stu-id="5ef16-123">Recommendation</span></span>  | <span data-ttu-id="5ef16-124">Typ av kund</span><span class="sxs-lookup"><span data-stu-id="5ef16-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="5ef16-125">Alla Microsoft 365-abonnemang</span><span class="sxs-lookup"><span data-stu-id="5ef16-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="5ef16-126">Använd standardvärden för säkerhet, som kräver MFA för alla användarkonton.</span><span class="sxs-lookup"><span data-stu-id="5ef16-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="5ef16-127">Du kan också kräva MFA per användarkonto, men detta rekommenderas inte.</span><span class="sxs-lookup"><span data-stu-id="5ef16-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="5ef16-128">Småföretag</span><span class="sxs-lookup"><span data-stu-id="5ef16-128">Small business</span></span> |
| <span data-ttu-id="5ef16-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="5ef16-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="5ef16-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="5ef16-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="5ef16-131">Azure Active Directory (Azure AD) Premium P1-licenser</span><span class="sxs-lookup"><span data-stu-id="5ef16-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="5ef16-132">Använd principer för villkorlig åtkomst för att kräva MFA för användarkonton baserat på gruppmedlemskap, appar eller andra villkor.</span><span class="sxs-lookup"><span data-stu-id="5ef16-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="5ef16-133">Små företag till företag</span><span class="sxs-lookup"><span data-stu-id="5ef16-133">Small business to enterprise</span></span> |
| <span data-ttu-id="5ef16-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5ef16-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="5ef16-135">Azure AD Premium P2-licenser</span><span class="sxs-lookup"><span data-stu-id="5ef16-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="5ef16-136">Använd Azure AD Identity Protection för att kräva MFA baserat på inloggningsriskkriterier.</span><span class="sxs-lookup"><span data-stu-id="5ef16-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="5ef16-137">Företag</span><span class="sxs-lookup"><span data-stu-id="5ef16-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="5ef16-138">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="5ef16-138">Security defaults</span></span>

<span data-ttu-id="5ef16-139">Standardinställningar för säkerhet är en ny funktion för Microsoft 365 och Office 365, betalade eller utvärderingsprenumerationer skapade efter den 21 oktober 2019.</span><span class="sxs-lookup"><span data-stu-id="5ef16-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="5ef16-140">Dessa prenumerationer har aktiverat säkerhetsstandarder, vilket:</span><span class="sxs-lookup"><span data-stu-id="5ef16-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="5ef16-141">Kräver att alla användare använder MFA med Microsoft Authenticator-appen.</span><span class="sxs-lookup"><span data-stu-id="5ef16-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="5ef16-142">Blockerar äldre autentisering.</span><span class="sxs-lookup"><span data-stu-id="5ef16-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="5ef16-143">Användare har 14 dagar på sig att registrera sig för MFA med Microsoft Authenticator-appen från sina smartphones, som börjar från första gången de loggar in efter att standardinställningar för säkerhet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="5ef16-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="5ef16-144">Efter 14 dagar kommer användaren inte att kunna logga in förrän MFA-registreringen är klar.</span><span class="sxs-lookup"><span data-stu-id="5ef16-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="5ef16-145">Standardinställningar för säkerhet säkerställer att alla organisationer har en grundläggande säkerhetsnivå för användarinloggning som är aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="5ef16-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="5ef16-146">Du kan inaktivera säkerhetsstandarder till förmån för MFA med principer för villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="5ef16-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="5ef16-147">Du aktiverar eller inaktiverar säkerhetsstandarder från **fönstret Egenskaper** för Azure AD i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="5ef16-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="5ef16-148">Du kan använda säkerhetsstandarder med alla Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="5ef16-148">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="5ef16-149">Mer information finns i den här [översikten över standardinställningar för säkerhet](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="5ef16-149">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="5ef16-150">Principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="5ef16-150">Conditional Access policies</span></span>

<span data-ttu-id="5ef16-151">Principer för villkorsstyrd åtkomst är en uppsättning regler som anger villkoren under vilka inloggningar utvärderas och tillåts.</span><span class="sxs-lookup"><span data-stu-id="5ef16-151">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="5ef16-152">Du kan till exempel skapa en princip för villkorsstyrd åtkomst som anger:</span><span class="sxs-lookup"><span data-stu-id="5ef16-152">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="5ef16-153">Om namnet på användarkontot är medlem i en grupp för användare som är tilldelade rollerna Exchange, användare, lösenord, säkerhet, SharePoint eller global administratör krävs MFA innan åtkomst tillåts.</span><span class="sxs-lookup"><span data-stu-id="5ef16-153">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="5ef16-154">Med den här principen kan du kräva MFA baserat på gruppmedlemskap, i stället för att försöka konfigurera enskilda användarkonton för MFA när de tilldelas eller tas bort från dessa administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="5ef16-154">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="5ef16-155">Du kan också använda principer för villkorlig åtkomst för mer avancerade funktioner, till exempel att kräva MFA för specifika appar eller att inloggningen görs från en kompatibel enhet, till exempel din bärbara dator som kör Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5ef16-155">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="5ef16-156">Du konfigurerar principer för villkorlig åtkomst från **säkerhetsfönstret** för Azure AD i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="5ef16-156">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="5ef16-157">Du kan använda principer för villkorlig åtkomst med:</span><span class="sxs-lookup"><span data-stu-id="5ef16-157">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="5ef16-158">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="5ef16-158">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="5ef16-159">Microsoft 365 E3 och E5</span><span class="sxs-lookup"><span data-stu-id="5ef16-159">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="5ef16-160">Azure AD Premium P1- och Azure AD Premium P2-licenser</span><span class="sxs-lookup"><span data-stu-id="5ef16-160">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="5ef16-161">För småföretag med Microsoft 365 Business Premium kan du enkelt använda principer för villkorlig åtkomst med följande steg:</span><span class="sxs-lookup"><span data-stu-id="5ef16-161">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="5ef16-162">Skapa en grupp som innehåller användarkonton som kräver MFA.</span><span class="sxs-lookup"><span data-stu-id="5ef16-162">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="5ef16-163">Aktivera principen **Kräv MFA för globala administratörer.**</span><span class="sxs-lookup"><span data-stu-id="5ef16-163">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="5ef16-164">Skapa en gruppbaserad princip för villkorlig åtkomst med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="5ef16-164">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="5ef16-165">Tilldelningar > användare och grupper: Namnet på din grupp från steg 1 ovan.</span><span class="sxs-lookup"><span data-stu-id="5ef16-165">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="5ef16-166">Tilldelningar > Cloud-appar eller -åtgärder: Alla molnappar.</span><span class="sxs-lookup"><span data-stu-id="5ef16-166">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="5ef16-167">Åtkomstkontroller > bevilja > bevilja åtkomst > kräver multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="5ef16-167">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="5ef16-168">Aktivera principen.</span><span class="sxs-lookup"><span data-stu-id="5ef16-168">Enable the policy.</span></span>
5. <span data-ttu-id="5ef16-169">Lägg till ett användarkonto i gruppen som skapats i steg 1 ovan och testa.</span><span class="sxs-lookup"><span data-stu-id="5ef16-169">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="5ef16-170">Om du vill kräva MFA för ytterligare användarkonton lägger du till dem i gruppen som skapats i steg 1.</span><span class="sxs-lookup"><span data-stu-id="5ef16-170">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="5ef16-171">Med den här principen för villkorlig åtkomst kan du distribuera MFA-kravet till användarna i din egen takt.</span><span class="sxs-lookup"><span data-stu-id="5ef16-171">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="5ef16-172">Företag bör använda [common conditional access-principer](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer:</span><span class="sxs-lookup"><span data-stu-id="5ef16-172">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="5ef16-173">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="5ef16-173">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="5ef16-174">Kräv MFA för alla användare</span><span class="sxs-lookup"><span data-stu-id="5ef16-174">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="5ef16-175">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="5ef16-175">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="5ef16-176">Mer information finns i den här [översikt över villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="5ef16-176">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="5ef16-177">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5ef16-177">Azure AD Identity Protection</span></span>

<span data-ttu-id="5ef16-178">Med Azure AD Identity Protection kan du skapa ytterligare en princip för villkorlig åtkomst för att [kräva MFA när inloggningsrisken är medelhög eller hög](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="5ef16-178">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="5ef16-179">Du kan använda Azure AD Identity Protection och riskbaserade principer för villkorlig åtkomst med:</span><span class="sxs-lookup"><span data-stu-id="5ef16-179">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="5ef16-180">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5ef16-180">Microsoft 365 E5</span></span>
- <span data-ttu-id="5ef16-181">Azure AD Premium P2-licenser</span><span class="sxs-lookup"><span data-stu-id="5ef16-181">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="5ef16-182">Mer information finns i den här [översikt över Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="5ef16-182">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="5ef16-183">MFA för ett enskilt användarkonto (rekommenderas inte)</span><span class="sxs-lookup"><span data-stu-id="5ef16-183">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="5ef16-184">Du bör använda antingen säkerhetsstandarder eller principer för villkorlig åtkomst för att kräva MFA för dina inloggningar för användarkontot. Om något av dessa inte kan användas rekommenderar Microsoft dock starkt MFA för användarkonton som har administratörsroller, särskilt den globala administratörsrollen, för alla storleksprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="5ef16-184">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="5ef16-185">Du aktiverar MFA för enskilda användarkonton från fönstret **Aktiv användare** i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ef16-185">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="5ef16-186">När användaren har aktiverats uppmanas de att registrera sig för MFA och att välja och testa den ytterligare verifieringsmetoden nästa gång användaren loggar in.</span><span class="sxs-lookup"><span data-stu-id="5ef16-186">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="5ef16-187">Använda dessa metoder tillsammans</span><span class="sxs-lookup"><span data-stu-id="5ef16-187">Using these methods together</span></span>

<span data-ttu-id="5ef16-188">I den här tabellen visas resultatet av att aktivera MFA med standardinställningar för säkerhet, principer för villkorsstyrd åtkomst och användarspecifika kontoinställningar.</span><span class="sxs-lookup"><span data-stu-id="5ef16-188">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="5ef16-189">Aktiverat</span><span class="sxs-lookup"><span data-stu-id="5ef16-189">Enabled</span></span> | <span data-ttu-id="5ef16-190">Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="5ef16-190">Disabled</span></span> | <span data-ttu-id="5ef16-191">Metod för sekundär autentisering</span><span class="sxs-lookup"><span data-stu-id="5ef16-191">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="5ef16-192">**Standardinställningar för säkerhet**</span><span class="sxs-lookup"><span data-stu-id="5ef16-192">**Security defaults**</span></span> | <span data-ttu-id="5ef16-193">Det går inte att använda principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="5ef16-193">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="5ef16-194">Det går att använda principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="5ef16-194">Can use Conditional Access policies</span></span> | <span data-ttu-id="5ef16-195">Microsoft Authenticator-appen</span><span class="sxs-lookup"><span data-stu-id="5ef16-195">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="5ef16-196">**Principer för villkorsstyrd åtkomst**</span><span class="sxs-lookup"><span data-stu-id="5ef16-196">**Conditional Access policies**</span></span> |<span data-ttu-id="5ef16-197">Om några är aktiverade kan du inte aktivera standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="5ef16-197">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="5ef16-198">Om alla är inaktiverade kan du aktivera standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="5ef16-198">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="5ef16-199">Användardefinierad under MFA-registrering</span><span class="sxs-lookup"><span data-stu-id="5ef16-199">User-specified during MFA registration</span></span> |
| <span data-ttu-id="5ef16-200">**Inställning per användarkonto (rekommenderas inte)**</span><span class="sxs-lookup"><span data-stu-id="5ef16-200">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="5ef16-201">Åsidosätter säkerhetsstandarder och principer för villkorlig åtkomst som kräver MFA vid varje inloggning</span><span class="sxs-lookup"><span data-stu-id="5ef16-201">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span> | <span data-ttu-id="5ef16-202">Åsidosätts efter säkerhetsstandarder och principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="5ef16-202">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="5ef16-203">Användardefinierad under MFA-registrering</span><span class="sxs-lookup"><span data-stu-id="5ef16-203">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="5ef16-204">Om standardinställningarna för säkerhet är aktiverade uppmanas alla nya användare att registrera MFA och använda Microsoft Authenticator-appen vid nästa inloggning.</span><span class="sxs-lookup"><span data-stu-id="5ef16-204">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="5ef16-205">Olika sätt att hantera MFA-inställningar</span><span class="sxs-lookup"><span data-stu-id="5ef16-205">Ways to manage MFA settings</span></span>

<span data-ttu-id="5ef16-206">Det finns två sätt att hantera MFA-inställningar.</span><span class="sxs-lookup"><span data-stu-id="5ef16-206">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="5ef16-207">I Azure-portalen kan du:</span><span class="sxs-lookup"><span data-stu-id="5ef16-207">In the Azure portal, you can:</span></span>

- <span data-ttu-id="5ef16-208">Aktivera och inaktivera säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="5ef16-208">Enable and disable security defaults</span></span>
- <span data-ttu-id="5ef16-209">Konfigurera principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="5ef16-209">Configure Conditional Access policies</span></span>

<span data-ttu-id="5ef16-210">I administrationscentret för Microsoft 365 kan du konfigurera MFA-inställningar per användare och tjänst.</span><span class="sxs-lookup"><span data-stu-id="5ef16-210">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="5ef16-211">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5ef16-211">Your next step</span></span>

[<span data-ttu-id="5ef16-212">Konfigurera MFA för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ef16-212">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

