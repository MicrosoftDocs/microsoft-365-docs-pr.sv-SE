---
title: Säkra användarinloggningar till din Microsoft 365-klient
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Kräva att dina användare loggar in säkert med multifaktorautentisering (MFA) och andra funktioner.
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132251"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a><span data-ttu-id="2677e-103">Säkra användarinloggningar till din Microsoft 365-klient</span><span class="sxs-lookup"><span data-stu-id="2677e-103">Secure user sign-ins to your Microsoft 365 tenant</span></span>

<span data-ttu-id="2677e-104">Så här ökar du säkerheten för användarinloggningar:</span><span class="sxs-lookup"><span data-stu-id="2677e-104">To increase the security of user sign-ins:</span></span>

- <span data-ttu-id="2677e-105">Använd Azure Active Directory (Azure AD) lösenordsskydd</span><span class="sxs-lookup"><span data-stu-id="2677e-105">Use Azure Active Directory (Azure AD) Password Protection</span></span>
- <span data-ttu-id="2677e-106">Använd multifaktorautentisering (MFA)</span><span class="sxs-lookup"><span data-stu-id="2677e-106">Use multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="2677e-107">Distribuera identitets- och enhetsåtkomstpolicyer</span><span class="sxs-lookup"><span data-stu-id="2677e-107">Deploy identity and device access policies</span></span>

## <a name="azure-ad-password-protection"></a><span data-ttu-id="2677e-108">Azure AD-lösenordsskydd</span><span class="sxs-lookup"><span data-stu-id="2677e-108">Azure AD Password Protection</span></span>

<span data-ttu-id="2677e-109">Azure AD-lösenordsskydd upptäcker och blockerar kända svaga lösenord och deras varianter och kan också blockera ytterligare svaga termer som är specifika för din organisation.</span><span class="sxs-lookup"><span data-stu-id="2677e-109">Azure AD Password Protection detects and blocks known weak passwords and their variants, and can also block additional weak terms that are specific to your organization.</span></span> <span data-ttu-id="2677e-110">Standard globala förbjudna lösenordslistor tillämpas automatiskt på alla användare i en Azure AD-klient.</span><span class="sxs-lookup"><span data-stu-id="2677e-110">Default global banned password lists are automatically applied to all users in an Azure AD tenant.</span></span> <span data-ttu-id="2677e-111">Du kan definiera ytterligare poster i en anpassad förbjuden lösenordslista.</span><span class="sxs-lookup"><span data-stu-id="2677e-111">You can define additional entries in a custom banned password list.</span></span> <span data-ttu-id="2677e-112">När användare ändrar eller återställer sina lösenord kontrolleras dessa förbjudna lösenordslistor för att använda starka lösenord.</span><span class="sxs-lookup"><span data-stu-id="2677e-112">When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords.</span></span>

<span data-ttu-id="2677e-113">Mer information finns i [Konfigurera Azure AD-lösenordsskydd](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span><span class="sxs-lookup"><span data-stu-id="2677e-113">For more information, see [Configure Azure AD password protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span></span>

## <a name="mfa"></a><span data-ttu-id="2677e-114">MFA</span><span class="sxs-lookup"><span data-stu-id="2677e-114">MFA</span></span>

<span data-ttu-id="2677e-115">MFA kräver att användarinloggningar underkastas en ytterligare verifiering utöver lösenordet för användarkontot.</span><span class="sxs-lookup"><span data-stu-id="2677e-115">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="2677e-116">Även om en användare som vill vålla skada bestämmer ett lösenord för ett användarkonto, måste de också kunna svara på en ytterligare verifiering, till exempel ett textmeddelande som skickas till en smartphone innan åtkomst beviljas.</span><span class="sxs-lookup"><span data-stu-id="2677e-116">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![Rätt lösenord plus extra verifiering gör att inloggningen lyckas](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="2677e-118">Ditt första steg i att använda MFA är att ***kräva det för alla administratörskonton***, även kända som privilegierade konton.</span><span class="sxs-lookup"><span data-stu-id="2677e-118">Your first step in using MFA is to ***require it for all administrator accounts***, also known as privileged accounts.</span></span>

<span data-ttu-id="2677e-119">Utöver detta första steg rekommenderar Microsoft starkt MFA för alla användare.</span><span class="sxs-lookup"><span data-stu-id="2677e-119">Beyond this first step, Microsoft strongly recommends MFA For all users.</span></span>

<span data-ttu-id="2677e-120">Det finns tre sätt att kräva att dina administratörer eller användare använder MFA baserat på din Microsoft 365-plan.</span><span class="sxs-lookup"><span data-stu-id="2677e-120">There are three ways to require your administrators or users to use MFA based on your Microsoft 365 plan.</span></span>

| <span data-ttu-id="2677e-121">Planera</span><span class="sxs-lookup"><span data-stu-id="2677e-121">Plan</span></span> | <span data-ttu-id="2677e-122">Rekommendation</span><span class="sxs-lookup"><span data-stu-id="2677e-122">Recommendation</span></span> |
|---------|---------|
|<span data-ttu-id="2677e-123">Alla Microsoft 365-abonnemang (utan Azure Active Directory Premium P1- eller P2-licenser)</span><span class="sxs-lookup"><span data-stu-id="2677e-123">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="2677e-124">[Aktivera standardinställningar för säkerhet i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="2677e-124">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="2677e-125">Standardinställningar för säkerhet i Azure AD inkluderar MFA för användare och administratörer.</span><span class="sxs-lookup"><span data-stu-id="2677e-125">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="2677e-126">Microsoft 365 E3 (inkluderar Azure Active Directory Premium P1-licenser)</span><span class="sxs-lookup"><span data-stu-id="2677e-126">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="2677e-127">Använd [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer:</span><span class="sxs-lookup"><span data-stu-id="2677e-127">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="2677e-128">- [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="2677e-128">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="2677e-129">- [Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="2677e-129">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="2677e-130">- [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="2677e-130">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="2677e-131">Microsoft 365 E5 (inkluderar Azure Active Directory Premium P2-licenser)</span><span class="sxs-lookup"><span data-stu-id="2677e-131">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="2677e-132">Dra nytta av Azure AD Identity Protection och börja implementera Microsofts [rekommenderade uppsättning av villkorsstyrd åtkomst och relaterade principer](../enterprise/identity-access-policies.md) genom att skapa de två principerna:</span><span class="sxs-lookup"><span data-stu-id="2677e-132">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../enterprise/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="2677e-133">- [Kräv MFA när inloggningsrisker är medel eller hög](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="2677e-133">- [Require MFA when sign-in risk is medium or high](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="2677e-134">- [Användare med hög risk måste byta lösenord](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="2677e-134">- [High risk users must change password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

### <a name="security-defaults"></a><span data-ttu-id="2677e-135">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="2677e-135">Security defaults</span></span>

<span data-ttu-id="2677e-136">Standardinställningar för säkerhet är en ny funktion för Microsoft 365 och Office 365, betalade eller utvärderingsprenumerationer skapade efter den 21 oktober 2019.</span><span class="sxs-lookup"><span data-stu-id="2677e-136">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="2677e-137">De här prenumerationerna har aktiverat standardinställningar för säkerhet som ***kräver att alla dina användare ska använda MFA med programmet Microsoft Authenticator-appen***.</span><span class="sxs-lookup"><span data-stu-id="2677e-137">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="2677e-138">Användare har 14 dagar på sig att registrera sig för MFA med Microsoft Authenticator-appen från sina smartphones, som börjar från första gången de loggar in efter att standardinställningar för säkerhet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="2677e-138">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="2677e-139">Efter 14 dagar kommer användaren inte att kunna logga in förrän MFA-registreringen är klar.</span><span class="sxs-lookup"><span data-stu-id="2677e-139">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="2677e-140">Standardinställningar för säkerhet säkerställer att alla organisationer har en grundläggande säkerhetsnivå för användarinloggning som är aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="2677e-140">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="2677e-141">Du kan inaktivera standardinställningar för säkerhet till förmån för MFA med Principer för villkorsstyrd åtkomst eller för enskilda konton.</span><span class="sxs-lookup"><span data-stu-id="2677e-141">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="2677e-142">Mer information finns i den här [översikten över standardinställningar för säkerhet](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="2677e-142">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="2677e-143">Principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="2677e-143">Conditional Access policies</span></span>

<span data-ttu-id="2677e-144">Policyer för villkorlig åtkomst är en uppsättning regler som anger villkoren för att inloggningar utvärderas och åtkomst beviljas.</span><span class="sxs-lookup"><span data-stu-id="2677e-144">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and access is granted.</span></span> <span data-ttu-id="2677e-145">Du kan till exempel skapa en princip för villkorsstyrd åtkomst som anger:</span><span class="sxs-lookup"><span data-stu-id="2677e-145">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="2677e-146">Om namnet på användarkontot är medlem i en grupp för användare som är tilldelade rollerna Exchange, användare, lösenord, säkerhet, SharePoint eller global administratör krävs MFA innan åtkomst tillåts.</span><span class="sxs-lookup"><span data-stu-id="2677e-146">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="2677e-147">Med den här principen kan du kräva MFA baserat på gruppmedlemskap, i stället för att försöka konfigurera enskilda användarkonton för MFA när de tilldelas eller tas bort från dessa administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="2677e-147">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="2677e-148">Du kan också använda principer för villkorsstyrd åtkomst för mer avancerade funktioner, t. ex. krav på att inloggningen görs från en kompatibel enhet, t. ex. en bärbar dator med Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2677e-148">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="2677e-149">Villkorsstyrd åtkomst kräver Azure Active Directory Premium P1-licens som ingår i Microsoft 365 E3 och E5.</span><span class="sxs-lookup"><span data-stu-id="2677e-149">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="2677e-150">Mer information finns i den här [översikt av villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="2677e-150">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="2677e-151">Använda dessa metoder tillsammans</span><span class="sxs-lookup"><span data-stu-id="2677e-151">Using these methods together</span></span>

<span data-ttu-id="2677e-152">Tänk på följande:</span><span class="sxs-lookup"><span data-stu-id="2677e-152">Keep the following in mind:</span></span>

- <span data-ttu-id="2677e-153">Du kan inte aktivera standardinställningar för säkerhet om du har aktiverat principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="2677e-153">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="2677e-154">Du kan inte aktivera principer för villkorsstyrd åtkomst om du har aktiverat standardinställningar för säkerhet.</span><span class="sxs-lookup"><span data-stu-id="2677e-154">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="2677e-155">Om standardinställningar för säkerhet är aktiverade, blir alla nya användare ombedda att registrera sig och använda Microsoft Authenticator-appen.</span><span class="sxs-lookup"><span data-stu-id="2677e-155">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="2677e-156">I den här tabellen visas resultatet av att aktivera MFA med standardinställningar för säkerhet och principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="2677e-156">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="2677e-157">Metod</span><span class="sxs-lookup"><span data-stu-id="2677e-157">Method</span></span> | <span data-ttu-id="2677e-158">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="2677e-158">Enabled</span></span> | <span data-ttu-id="2677e-159">Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="2677e-159">Disabled</span></span> | <span data-ttu-id="2677e-160">Ytterligare autentiseringsmetod</span><span class="sxs-lookup"><span data-stu-id="2677e-160">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="2677e-161">**Standardinställningar för säkerhet**</span><span class="sxs-lookup"><span data-stu-id="2677e-161">**Security defaults**</span></span>  | <span data-ttu-id="2677e-162">Det går inte att använda principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="2677e-162">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="2677e-163">Det går att använda principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="2677e-163">Can use Conditional Access policies</span></span> | <span data-ttu-id="2677e-164">Microsoft Authenticator-appen</span><span class="sxs-lookup"><span data-stu-id="2677e-164">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="2677e-165">**Principer för villkorsstyrd åtkomst**</span><span class="sxs-lookup"><span data-stu-id="2677e-165">**Conditional Access policies**</span></span> | <span data-ttu-id="2677e-166">Om några är aktiverade kan du inte aktivera standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="2677e-166">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="2677e-167">Om alla är inaktiverade kan du aktivera standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="2677e-167">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="2677e-168">Användare anger under MFA-registrering</span><span class="sxs-lookup"><span data-stu-id="2677e-168">User specifies during MFA registration</span></span>  |
||||

## <a name="identity-and-device-access-policies"></a><span data-ttu-id="2677e-169">Policyer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="2677e-169">Identity and device access policies</span></span>

<span data-ttu-id="2677e-170">Identitets- och enhetsåtkomstinställningar och policyer rekommenderas förutsättningsfunktioner och deras inställningar i kombination med villkorlig åtkomst, Intune och Azure AD Identity Protection-principer som avgör om en given åtkomstbegäran ska beviljas och under vilka villkor.</span><span class="sxs-lookup"><span data-stu-id="2677e-170">Identity and device access settings and policies are recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span> <span data-ttu-id="2677e-171">Denna bestämning baseras på användarkontot för inloggningen, den enhet som används, appen som användaren använder för åtkomst, platsen från vilken begäran om åtkomst görs och en bedömning av risken för begäran.</span><span class="sxs-lookup"><span data-stu-id="2677e-171">This determination is based on the user account of the sign-in, the device being used, the app the user is using for access, the location from which the access request is made, and an assessment of the risk of the request.</span></span> <span data-ttu-id="2677e-172">Denna funktion hjälper till att säkerställa att endast godkända användare och enheter kan komma åt dina kritiska resurser.</span><span class="sxs-lookup"><span data-stu-id="2677e-172">This capability helps ensure that only approved users and devices can access your critical resources.</span></span>

>[!Note]
><span data-ttu-id="2677e-173">För Azure Active Directory Identity Protection krävs Azure Active Directory Premium P2-licenser, som ingår i Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2677e-173">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>
>

<span data-ttu-id="2677e-174">Policyer för identitets- och enhetsåtkomst definieras för att användas i tre nivåer:</span><span class="sxs-lookup"><span data-stu-id="2677e-174">Identity and device access policies are defined to be used in three tiers:</span></span> 

- <span data-ttu-id="2677e-175">Baslinjeskydd är en minsta säkerhetsnivå för dina identiteter och enheter som har åtkomst till dina appar och data.</span><span class="sxs-lookup"><span data-stu-id="2677e-175">Baseline protection is a minimum level of security for your identities and devices that access your apps and data.</span></span>
- <span data-ttu-id="2677e-176">Känsligt skydd ger ytterligare säkerhet för specifika data.</span><span class="sxs-lookup"><span data-stu-id="2677e-176">Sensitive protection provides additional security for specific data.</span></span> <span data-ttu-id="2677e-177">Identiteter och enheter är föremål för högre säkerhetsnivåer och krav på enhetens hälsa.</span><span class="sxs-lookup"><span data-stu-id="2677e-177">Identities and devices are subject to higher levels of security and device health requirements.</span></span>
- <span data-ttu-id="2677e-178">Skydd för miljöer med högt reglerad eller sekretessbelagd information gäller typiskt små mängder data som är mycket klassificerade, innehåller affärshemligheter eller är föremål för dataregler.</span><span class="sxs-lookup"><span data-stu-id="2677e-178">Protection for environments with highly regulated or classified data is for typically small amounts of data that are highly classified, contain trade secrets, or is subject to data regulations.</span></span> <span data-ttu-id="2677e-179">Identiteter och enheter är föremål för mycket högre säkerhetsnivåer och krav på enhetens hälsa.</span><span class="sxs-lookup"><span data-stu-id="2677e-179">Identities and devices are subject to much higher levels of security and device health requirements.</span></span> 

<span data-ttu-id="2677e-180">Dessa nivåer och deras motsvarande konfigurationer ger konsekventa skyddsnivåer för dina data, identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="2677e-180">These tiers and their corresponding configurations provide consistent levels of protection across your data, identities, and devices.</span></span>

<span data-ttu-id="2677e-181">Microsoft rekommenderar starkt att du konfigurerar och rullar ut policyer för identitets- och enhetsåtkomst i din organisation, inklusive specifika inställningar för Microsoft Teams, Exchange Online och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2677e-181">Microsoft highly recommends configuring and rolling out identity and device access policies in your organization, including specific settings for Microsoft Teams, Exchange Online, and SharePoint.</span></span> <span data-ttu-id="2677e-182">Mer information finns i konfigurationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2677e-182">For more information, see [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a><span data-ttu-id="2677e-183">Administrera tekniska resurser för MFA och säkra inloggningar</span><span class="sxs-lookup"><span data-stu-id="2677e-183">Admin technical resources for MFA and secure sign-ins</span></span>

- [<span data-ttu-id="2677e-184">MFA för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2677e-184">MFA for Microsoft 365</span></span>](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [<span data-ttu-id="2677e-185">Identitets översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2677e-185">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="2677e-186">Azure Academy Azure AD-utbildningsvideor</span><span class="sxs-lookup"><span data-stu-id="2677e-186">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="2677e-187">Tillämpa registreringspolicy för Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="2677e-187">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [<span data-ttu-id="2677e-188">Konfigurationer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="2677e-188">Identity and device access configurations</span></span>](microsoft-365-policies-configurations.md)

