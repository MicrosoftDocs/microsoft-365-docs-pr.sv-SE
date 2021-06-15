---
title: Multifaktorautentisering för Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Multifaktorautentisering (MFA) använder både ett lösenord, som bör vara starkt, och en ytterligare verifieringsmetod.
ms.openlocfilehash: d9af486cf5e53609557b519612f185a20729cf76
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924737"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="239da-103">Multifaktorautentisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="239da-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="239da-104">Lösenord är den vanligaste metoden för att autentisera en inloggning på en dator eller onlinetjänst, men de är också de mest sårbara.</span><span class="sxs-lookup"><span data-stu-id="239da-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="239da-105">Användare kan välja enkla lösenord och använda samma lösenord för flera inloggningar till olika datorer och tjänster.</span><span class="sxs-lookup"><span data-stu-id="239da-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="239da-106">För att ge ytterligare säkerhetsnivå för inloggningar måste du använda multifaktorautentisering (MFA), som använder både ett lösenord, som bör vara starkt, och en ytterligare verifieringsmetod baserat på:</span><span class="sxs-lookup"><span data-stu-id="239da-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="239da-107">En sak som du har med dig är inte enkelt att duplicera, till exempel en smartphone.</span><span class="sxs-lookup"><span data-stu-id="239da-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="239da-108">Ett objekt som du är unikt och som finns i ens namn, som ditt fingeravtryck, ansikte eller annat biometriskt attribut.</span><span class="sxs-lookup"><span data-stu-id="239da-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="239da-109">Den ytterligare verifieringsmetoden används inte förrän användarens lösenord har verifierats.</span><span class="sxs-lookup"><span data-stu-id="239da-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="239da-110">Med MFA har attacker inte din smartphone eller ditt fingeravtryck för att slutföra inloggningen, även om ett starkt användarlösenord har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="239da-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="239da-111">MFA-stöd i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="239da-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="239da-112">Som standard stöder både Microsoft 365 och Office 365 MFA för användarkonton med:</span><span class="sxs-lookup"><span data-stu-id="239da-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="239da-113">Ett SMS som skickas till en telefon där användaren måste ange en verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="239da-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="239da-114">Ett telefonsamtal.</span><span class="sxs-lookup"><span data-stu-id="239da-114">A phone call.</span></span>
- <span data-ttu-id="239da-115">Appen Microsoft Authenticator smartphone.</span><span class="sxs-lookup"><span data-stu-id="239da-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="239da-116">I båda fallen använder MFA-inloggningsmetoden "något du har med dig som inte är lätt att duplicera" för den ytterligare verifieringen.</span><span class="sxs-lookup"><span data-stu-id="239da-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="239da-117">Du kan aktivera MFA för e-Microsoft 365 och Office 365 på flera Office 365:</span><span class="sxs-lookup"><span data-stu-id="239da-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="239da-118">Med standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="239da-118">With security defaults</span></span>
- <span data-ttu-id="239da-119">Med villkorsstyrda åtkomstprinciper</span><span class="sxs-lookup"><span data-stu-id="239da-119">With Conditional Access policies</span></span>
- <span data-ttu-id="239da-120">För varje enskilt användarkonto (rekommenderas inte)</span><span class="sxs-lookup"><span data-stu-id="239da-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="239da-121">Dessa sätt baseras på ditt Microsoft 365 plan.</span><span class="sxs-lookup"><span data-stu-id="239da-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="239da-122">Planera</span><span class="sxs-lookup"><span data-stu-id="239da-122">Plan</span></span>|<span data-ttu-id="239da-123">Rekommendation</span><span class="sxs-lookup"><span data-stu-id="239da-123">Recommendation</span></span>|<span data-ttu-id="239da-124">Typ av kund</span><span class="sxs-lookup"><span data-stu-id="239da-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="239da-125">Alla Microsoft 365 abonnemang</span><span class="sxs-lookup"><span data-stu-id="239da-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="239da-126">Använd säkerhetsstandarder, som kräver MFA för alla användarkonton.</span><span class="sxs-lookup"><span data-stu-id="239da-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="239da-127">Du kan också konfigurera MFA per användare för enskilda användarkonton, men det rekommenderas inte.</span><span class="sxs-lookup"><span data-stu-id="239da-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="239da-128">Småföretag</span><span class="sxs-lookup"><span data-stu-id="239da-128">Small business</span></span>|
|<span data-ttu-id="239da-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="239da-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="239da-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="239da-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="239da-131">Azure Active Directory (Azure AD) Premium P1-licenser</span><span class="sxs-lookup"><span data-stu-id="239da-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="239da-132">Använd villkorsstyrda åtkomstprinciper om du vill kräva MFA för användarkonton baserat på gruppmedlemskap, appar eller andra villkor.</span><span class="sxs-lookup"><span data-stu-id="239da-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="239da-133">Småföretag till företag</span><span class="sxs-lookup"><span data-stu-id="239da-133">Small business to enterprise</span></span>|
|<span data-ttu-id="239da-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="239da-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="239da-135">Azure AD Premium P2-licenser</span><span class="sxs-lookup"><span data-stu-id="239da-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="239da-136">Använd Azure AD Identity Protection om du vill kräva MFA baserat på villkor för inloggningsrisk.</span><span class="sxs-lookup"><span data-stu-id="239da-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="239da-137">Enterprise</span><span class="sxs-lookup"><span data-stu-id="239da-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="239da-138">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="239da-138">Security defaults</span></span>

<span data-ttu-id="239da-139">Standardinställningar för säkerhet är en ny funktion för Microsoft 365 och Office 365, betalade eller utvärderingsprenumerationer skapade efter den 21 oktober 2019.</span><span class="sxs-lookup"><span data-stu-id="239da-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="239da-140">De här prenumerationerna har aktiverat säkerhetsstandarder, som:</span><span class="sxs-lookup"><span data-stu-id="239da-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="239da-141">Kräver att alla användare använder MFA med Microsoft Authenticator program.</span><span class="sxs-lookup"><span data-stu-id="239da-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="239da-142">Blockerar äldre autentisering.</span><span class="sxs-lookup"><span data-stu-id="239da-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="239da-143">Användare har 14 dagar på sig att registrera sig för MFA med Microsoft Authenticator-appen från sina smartphones, som börjar från första gången de loggar in efter att standardinställningar för säkerhet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="239da-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="239da-144">Efter 14 dagar kommer användaren inte att kunna logga in förrän MFA-registreringen är klar.</span><span class="sxs-lookup"><span data-stu-id="239da-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="239da-145">Standardinställningar för säkerhet säkerställer att alla organisationer har en grundläggande säkerhetsnivå för användarinloggning som är aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="239da-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="239da-146">Du kan inaktivera säkerhetsstandarder till att använda MFA med villkorsstyrda åtkomstprinciper.</span><span class="sxs-lookup"><span data-stu-id="239da-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="239da-147">Du aktiverar eller inaktiverar säkerhetsstandarder i **fönstret** Egenskaper för Azure AD i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="239da-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Bild av sidan Katalogegenskaper.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="239da-149">Du kan använda säkerhetsstandarder i alla Microsoft 365 abonnemang.</span><span class="sxs-lookup"><span data-stu-id="239da-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="239da-150">Mer information finns i den här [översikten över standardinställningar för säkerhet](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="239da-150">For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="239da-151">Principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="239da-151">Conditional Access policies</span></span>

<span data-ttu-id="239da-152">Principer för villkorsstyrd åtkomst är en uppsättning regler som anger villkoren under vilka inloggningar utvärderas och tillåts.</span><span class="sxs-lookup"><span data-stu-id="239da-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="239da-153">Du kan till exempel skapa en princip för villkorsstyrd åtkomst som anger:</span><span class="sxs-lookup"><span data-stu-id="239da-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="239da-154">Om namnet på användarkontot är medlem i en grupp för användare som är tilldelade rollerna Exchange, användare, lösenord, säkerhet, SharePoint eller global administratör krävs MFA innan åtkomst tillåts.</span><span class="sxs-lookup"><span data-stu-id="239da-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="239da-155">Med den här principen kan du kräva MFA baserat på gruppmedlemskap, i stället för att försöka konfigurera enskilda användarkonton för MFA när de tilldelas eller tas bort från dessa administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="239da-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="239da-156">Du kan också använda villkorsstyrda åtkomstprinciper för mer avancerade funktioner, till exempel krav på MFA för specifika appar eller att inloggningen görs från en kompatibel enhet, till exempel en bärbar dator som kör Windows 10.</span><span class="sxs-lookup"><span data-stu-id="239da-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="239da-157">Du konfigurerar principer för villkorsstyrd **åtkomst från** säkerhetsfönstret för Azure AD i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="239da-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Bild av menyalternativet Villkorsstyrd åtkomst](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="239da-159">Du kan använda villkorsstyrda åtkomstprinciper med:</span><span class="sxs-lookup"><span data-stu-id="239da-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="239da-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="239da-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="239da-161">Microsoft 365 E3 och E5</span><span class="sxs-lookup"><span data-stu-id="239da-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="239da-162">Azure AD Premium P1- och Azure AD Premium P2-licenser</span><span class="sxs-lookup"><span data-stu-id="239da-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="239da-163">För småföretag med Microsoft 365 Business Premium kan du enkelt använda villkorsstyrda principer med följande steg:</span><span class="sxs-lookup"><span data-stu-id="239da-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="239da-164">Skapa en grupp som innehåller användarkonton som kräver MFA.</span><span class="sxs-lookup"><span data-stu-id="239da-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="239da-165">Aktivera principen **Kräv MFA för globala** administratörer.</span><span class="sxs-lookup"><span data-stu-id="239da-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="239da-166">Skapa en gruppbaserad villkorsstyrd åtkomstprincip med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="239da-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="239da-167">Uppgifter > Användare och grupper: Namnet på gruppen från steg 1 ovan.</span><span class="sxs-lookup"><span data-stu-id="239da-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="239da-168">Uppgifter > Molnappar eller åtgärder: Alla molnappar.</span><span class="sxs-lookup"><span data-stu-id="239da-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="239da-169">Access-> bevilja > åtkomst > Kräv multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="239da-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="239da-170">Aktivera principen.</span><span class="sxs-lookup"><span data-stu-id="239da-170">Enable the policy.</span></span>
5. <span data-ttu-id="239da-171">Lägg till ett användarkonto i gruppen som skapades i steg 1 ovan och testa.</span><span class="sxs-lookup"><span data-stu-id="239da-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="239da-172">Om du vill kräva MFA för ytterligare användarkonton lägger du till dem i gruppen som skapades i steg 1.</span><span class="sxs-lookup"><span data-stu-id="239da-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="239da-173">Med den här principen för villkorsstyrd åtkomst kan du distribuera MFA-kravet till användarna i din egen takt.</span><span class="sxs-lookup"><span data-stu-id="239da-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="239da-174">Företag bör använda [vanliga principer för villkorsstyrd](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) åtkomst för att konfigurera följande principer:</span><span class="sxs-lookup"><span data-stu-id="239da-174">Enterprises should use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="239da-175">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="239da-175">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="239da-176">Kräv MFA för alla användare</span><span class="sxs-lookup"><span data-stu-id="239da-176">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="239da-177">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="239da-177">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="239da-178">Mer information finns i den här [översikt över villkorsstyrd åtkomst](/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="239da-178">For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="239da-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="239da-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="239da-180">Med Azure AD Identity Protection kan du skapa ytterligare en villkorsstyrd åtkomstprincip som kräver [MFA när inloggningsrisken är medium eller hög.](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="239da-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="239da-181">Du kan använda Azure AD Identity Protection och riskbaserade villkorsstyrda åtkomstpolicyer med:</span><span class="sxs-lookup"><span data-stu-id="239da-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="239da-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="239da-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="239da-183">Azure AD Premium P2-licenser</span><span class="sxs-lookup"><span data-stu-id="239da-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="239da-184">Mer information finns i den här [översikt över Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="239da-184">For more information, see this [overview of Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="239da-185">Äldre MFA per användare (rekommenderas inte)</span><span class="sxs-lookup"><span data-stu-id="239da-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="239da-186">Du bör använda antingen säkerhetsstandarder eller villkorsstyrda åtkomstprinciper för att kräva MFA för inloggningar för användarkonton. Men om någon av dessa inte kan användas rekommenderar Microsoft starkt MFA för användarkonton som har administratörsroller, särskilt den globala administratörsrollen, för alla storleksprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="239da-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="239da-187">Du aktiverar MFA för enskilda användarkonton i **fönstret** Aktiv användare Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="239da-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Bild av alternativet Multifaktorautentisering på sidan Aktiva användare](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="239da-189">När funktionen är aktiverad uppmanas användaren nästa gång att registrera sig för MFA samt välja och testa den ytterligare verifieringsmetoden.</span><span class="sxs-lookup"><span data-stu-id="239da-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="239da-190">Använda dessa metoder tillsammans</span><span class="sxs-lookup"><span data-stu-id="239da-190">Using these methods together</span></span>

<span data-ttu-id="239da-191">I den här tabellen visas resultatet av att aktivera MFA med standardinställningar för säkerhet, principer för villkorsstyrd åtkomst och användarspecifika kontoinställningar.</span><span class="sxs-lookup"><span data-stu-id="239da-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|<span data-ttu-id="239da-192">*Objekt*</span><span class="sxs-lookup"><span data-stu-id="239da-192">*Item*</span></span>|<span data-ttu-id="239da-193">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="239da-193">Enabled</span></span>|<span data-ttu-id="239da-194">Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="239da-194">Disabled</span></span>|<span data-ttu-id="239da-195">Metod för sekundär autentisering</span><span class="sxs-lookup"><span data-stu-id="239da-195">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="239da-196">**Standardinställningar för säkerhet**</span><span class="sxs-lookup"><span data-stu-id="239da-196">**Security defaults**</span></span>|<span data-ttu-id="239da-197">Det går inte att använda villkorsstyrda åtkomstprinciper</span><span class="sxs-lookup"><span data-stu-id="239da-197">Can't use Conditional Access policies</span></span>|<span data-ttu-id="239da-198">Det går att använda principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="239da-198">Can use Conditional Access policies</span></span>|<span data-ttu-id="239da-199">Microsoft Authenticator-appen</span><span class="sxs-lookup"><span data-stu-id="239da-199">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="239da-200">**Principer för villkorsstyrd åtkomst**</span><span class="sxs-lookup"><span data-stu-id="239da-200">**Conditional Access policies**</span></span>|<span data-ttu-id="239da-201">Om några är aktiverade kan du inte aktivera säkerhetsstandardvärden</span><span class="sxs-lookup"><span data-stu-id="239da-201">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="239da-202">Om alla är inaktiverade kan du aktivera standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="239da-202">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="239da-203">Användardefinierad under MFA-registrering</span><span class="sxs-lookup"><span data-stu-id="239da-203">User-specified during MFA registration</span></span>|
|<span data-ttu-id="239da-204">**Äldre MFA per användare (rekommenderas inte)**</span><span class="sxs-lookup"><span data-stu-id="239da-204">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="239da-205">Åsidosätter säkerhetsstandarder och villkorsstyrda åtkomstprinciper som kräver MFA vid varje inloggning</span><span class="sxs-lookup"><span data-stu-id="239da-205">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="239da-206">Åsidosätts av säkerhetsstandarder och villkorsstyrda åtkomstprinciper</span><span class="sxs-lookup"><span data-stu-id="239da-206">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="239da-207">Användardefinierad under MFA-registrering</span><span class="sxs-lookup"><span data-stu-id="239da-207">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="239da-208">Om säkerhetsstandarder är aktiverade uppmanas alla nya användare att registrera sig för MFA och att appen Microsoft Authenticator vid nästa inloggning.</span><span class="sxs-lookup"><span data-stu-id="239da-208">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="239da-209">Olika sätt att hantera MFA-inställningar</span><span class="sxs-lookup"><span data-stu-id="239da-209">Ways to manage MFA settings</span></span>

<span data-ttu-id="239da-210">Det finns två sätt att hantera MFA-inställningar.</span><span class="sxs-lookup"><span data-stu-id="239da-210">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="239da-211">I Azure Portal kan du:</span><span class="sxs-lookup"><span data-stu-id="239da-211">In the Azure portal, you can:</span></span>

- <span data-ttu-id="239da-212">Aktivera och inaktivera säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="239da-212">Enable and disable security defaults</span></span>
- <span data-ttu-id="239da-213">Konfigurera principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="239da-213">Configure Conditional Access policies</span></span>

<span data-ttu-id="239da-214">I Microsoft 365 kan du konfigurera MFA-inställningar per användare och tjänst.</span><span class="sxs-lookup"><span data-stu-id="239da-214">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="239da-215">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="239da-215">Next steps</span></span>

[<span data-ttu-id="239da-216">Konfigurera MFA för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="239da-216">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-content"></a><span data-ttu-id="239da-217">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="239da-217">Related content</span></span>

<span data-ttu-id="239da-218">[Aktivera multifaktorautentisering](../../business-video/turn-on-mfa.md) (video)</span><span class="sxs-lookup"><span data-stu-id="239da-218">[Turn on multi-factor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>\
<span data-ttu-id="239da-219">[Aktivera multifaktorautentisering för telefonen](../../business-video/set-up-mfa.md) (video)</span><span class="sxs-lookup"><span data-stu-id="239da-219">[Turn on multi-factor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>