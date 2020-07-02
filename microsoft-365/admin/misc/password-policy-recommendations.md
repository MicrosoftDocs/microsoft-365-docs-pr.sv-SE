---
title: Policyrekommendationer för lösenord
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Lär dig hur du gör organisationen säkrare mot lösenordsattacker och varför du bör förbjuda vanliga lösenord och aktivera riskbaserad multifaktorautentisering.
ms.openlocfilehash: 1d6e399acb83751ec6a45eb0c811dedec394127e
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015929"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="87f11-103">Policyrekommendationer för lösenord</span><span class="sxs-lookup"><span data-stu-id="87f11-103">Password policy recommendations</span></span>
 
<span data-ttu-id="87f11-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="87f11-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="87f11-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span><span class="sxs-lookup"><span data-stu-id="87f11-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="87f11-106">Information om hur du anger hur ofta Microsoft 365-lösenord ska upphöra att gälla i organisationen finns i [Ange förfalloprincip för lösenord för Microsoft 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="87f11-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="87f11-107">Mer information om Microsoft 365-lösenord finns i följande [relaterade artiklar](#related-articles).</span><span class="sxs-lookup"><span data-stu-id="87f11-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="87f11-108">Förstå rekommendationer om lösenord</span><span class="sxs-lookup"><span data-stu-id="87f11-108">Understanding password recommendations</span></span>

<span data-ttu-id="87f11-109">Bra metoder för lösenord delas in i några breda kategorier:</span><span class="sxs-lookup"><span data-stu-id="87f11-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="87f11-110">**Motarbeta vanliga attacker** Här ingår valet av var användarna kan ange lösenord (kända och betrodda enheter med bra identifiering av skadlig kod, verifierade webbplatser) och valet av vilka lösenord de kan välja (längd och unikhet).</span><span class="sxs-lookup"><span data-stu-id="87f11-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="87f11-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span><span class="sxs-lookup"><span data-stu-id="87f11-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="87f11-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span><span class="sxs-lookup"><span data-stu-id="87f11-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="87f11-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span><span class="sxs-lookup"><span data-stu-id="87f11-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="87f11-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span><span class="sxs-lookup"><span data-stu-id="87f11-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="87f11-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span><span class="sxs-lookup"><span data-stu-id="87f11-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="87f11-116">Riktlinjer om lösenord för administratörer</span><span class="sxs-lookup"><span data-stu-id="87f11-116">Password guidelines for administrators</span></span>

<span data-ttu-id="87f11-117">The primary goal of a more secure password system is password diversity.</span><span class="sxs-lookup"><span data-stu-id="87f11-117">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="87f11-118">You want your password policy to contain lots of different and hard to guess passwords.</span><span class="sxs-lookup"><span data-stu-id="87f11-118">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="87f11-119">Here are a few recommendations for keeping your organization as secure as possible.</span><span class="sxs-lookup"><span data-stu-id="87f11-119">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="87f11-120">Ha ett krav om minimilängd på 8 tecken (längre är inte nödvändigtvis bättre)</span><span class="sxs-lookup"><span data-stu-id="87f11-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="87f11-121">Don't require character composition requirements.</span><span class="sxs-lookup"><span data-stu-id="87f11-121">Don't require character composition requirements.</span></span> <span data-ttu-id="87f11-122">For example, \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="87f11-122">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="87f11-123">Kräv inte regelbundna lösenordsåterställningar för användarkonton</span><span class="sxs-lookup"><span data-stu-id="87f11-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="87f11-124">Förbjud vanliga lösenord, för att undvika de mest sårbara lösenorden i systemet</span><span class="sxs-lookup"><span data-stu-id="87f11-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="87f11-125">Utbilda användarna så att de inte återanvänder sina organisationslösenord utanför arbetet</span><span class="sxs-lookup"><span data-stu-id="87f11-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="87f11-126">Tillämpa registrering för [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="87f11-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="87f11-127">Aktivera riskbaserade multifaktorautentiseringskontroller</span><span class="sxs-lookup"><span data-stu-id="87f11-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="87f11-128">Hjälp om lösenord för användare</span><span class="sxs-lookup"><span data-stu-id="87f11-128">Password guidance for your users</span></span>

<span data-ttu-id="87f11-129">Here's some password guidance for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="87f11-129">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="87f11-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span><span class="sxs-lookup"><span data-stu-id="87f11-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="87f11-131">Använd inte ett lösenord som är samma som eller liknar ett du använder på andra webbplatser</span><span class="sxs-lookup"><span data-stu-id="87f11-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="87f11-132">Använd inte ett enskilt ord, till exempel **lösenord**, eller en vanlig fras, till exempel **jagälskardig**</span><span class="sxs-lookup"><span data-stu-id="87f11-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="87f11-133">Gör lösenord svåra att gissa sig till, även för personer som vet mycket om dig, till exempel namn och födelsedagar för dina vänner och din familj, din favoritartist och fraser som du använder ofta</span><span class="sxs-lookup"><span data-stu-id="87f11-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="87f11-134">Några vanliga metoder och deras negativa följder</span><span class="sxs-lookup"><span data-stu-id="87f11-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="87f11-135">Det här är några av de vanligaste metoderna för lösenordshantering, men forskning varnar oss för deras negativa följder.</span><span class="sxs-lookup"><span data-stu-id="87f11-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="87f11-136">Krav på giltighetstid för lösenord för användare</span><span class="sxs-lookup"><span data-stu-id="87f11-136">Password expiration requirements for users</span></span>

<span data-ttu-id="87f11-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span><span class="sxs-lookup"><span data-stu-id="87f11-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="87f11-138">In these cases, the next password can be predicted based on the previous password.</span><span class="sxs-lookup"><span data-stu-id="87f11-138">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="87f11-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span><span class="sxs-lookup"><span data-stu-id="87f11-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="87f11-140">Krav på långa lösenord</span><span class="sxs-lookup"><span data-stu-id="87f11-140">Requiring long passwords</span></span>

<span data-ttu-id="87f11-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span><span class="sxs-lookup"><span data-stu-id="87f11-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="87f11-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span><span class="sxs-lookup"><span data-stu-id="87f11-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="87f11-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span><span class="sxs-lookup"><span data-stu-id="87f11-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="87f11-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span><span class="sxs-lookup"><span data-stu-id="87f11-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span> 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="87f11-145">Krav på användning av flera teckenuppsättningar</span><span class="sxs-lookup"><span data-stu-id="87f11-145">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="87f11-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span><span class="sxs-lookup"><span data-stu-id="87f11-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="87f11-147">Most systems enforce some level of password complexity requirements.</span><span class="sxs-lookup"><span data-stu-id="87f11-147">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="87f11-148">For example, passwords need characters from all three of the following categories:</span><span class="sxs-lookup"><span data-stu-id="87f11-148">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="87f11-149">versaler</span><span class="sxs-lookup"><span data-stu-id="87f11-149">uppercase characters</span></span>

- <span data-ttu-id="87f11-150">gemener</span><span class="sxs-lookup"><span data-stu-id="87f11-150">lowercase characters</span></span>

- <span data-ttu-id="87f11-151">icke-alfanumeriska tecken</span><span class="sxs-lookup"><span data-stu-id="87f11-151">non-alphanumeric characters</span></span>

<span data-ttu-id="87f11-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span><span class="sxs-lookup"><span data-stu-id="87f11-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="87f11-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span><span class="sxs-lookup"><span data-stu-id="87f11-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="87f11-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span><span class="sxs-lookup"><span data-stu-id="87f11-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="87f11-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span><span class="sxs-lookup"><span data-stu-id="87f11-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="87f11-156">Lyckade mönster</span><span class="sxs-lookup"><span data-stu-id="87f11-156">Successful Patterns</span></span>

<span data-ttu-id="87f11-157">Här finns däremot några rekommendationer om hur du uppmuntrar lösenordsvariation.</span><span class="sxs-lookup"><span data-stu-id="87f11-157">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="87f11-158">Förbjud vanliga lösenord</span><span class="sxs-lookup"><span data-stu-id="87f11-158">Ban common passwords</span></span>

<span data-ttu-id="87f11-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span><span class="sxs-lookup"><span data-stu-id="87f11-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="87f11-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span><span class="sxs-lookup"><span data-stu-id="87f11-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="87f11-161">Utbilda användare så att de inte återanvänder organisationslösenord någon annanstans</span><span class="sxs-lookup"><span data-stu-id="87f11-161">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="87f11-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span><span class="sxs-lookup"><span data-stu-id="87f11-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="87f11-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span><span class="sxs-lookup"><span data-stu-id="87f11-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="87f11-164">Tillämpa registrering för multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="87f11-164">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="87f11-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span><span class="sxs-lookup"><span data-stu-id="87f11-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="87f11-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span><span class="sxs-lookup"><span data-stu-id="87f11-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="87f11-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span><span class="sxs-lookup"><span data-stu-id="87f11-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="87f11-168">Mer information finns i [Konfigurera multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="87f11-168">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="87f11-169">Aktivera riskbaserad multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="87f11-169">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="87f11-170">Med riskbaserad multifaktorautentisering går det att kontrollera att användaren är den riktiga kontoägaren när misstänkt aktivitet identifieras av systemet.</span><span class="sxs-lookup"><span data-stu-id="87f11-170">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="87f11-171">Vill du veta mer?</span><span class="sxs-lookup"><span data-stu-id="87f11-171">Want to know more?</span></span> <span data-ttu-id="87f11-172">Rekommenderad läsning</span><span class="sxs-lookup"><span data-stu-id="87f11-172">Recommended reading</span></span>

- [<span data-ttu-id="87f11-173">Fyller starka webblösenord någon funktion?</span><span class="sxs-lookup"><span data-stu-id="87f11-173">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="87f11-174">Lösenordsportföljer och användare med begränsad insats</span><span class="sxs-lookup"><span data-stu-id="87f11-174">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="87f11-175">Förhindra svaga lösenord genom att läsa användarnas tankar</span><span class="sxs-lookup"><span data-stu-id="87f11-175">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="87f11-176">Välja säkra lösenord</span><span class="sxs-lookup"><span data-stu-id="87f11-176">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="87f11-177">Dags att ompröva obligatoriska lösenordsändringar</span><span class="sxs-lookup"><span data-stu-id="87f11-177">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="87f11-178">2015 års sämsta lösenord</span><span class="sxs-lookup"><span data-stu-id="87f11-178">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [<span data-ttu-id="87f11-179">Ladda ned filer från webben</span><span class="sxs-lookup"><span data-stu-id="87f11-179">Download files from the web</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a><span data-ttu-id="87f11-180">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="87f11-180">Related articles</span></span>

[<span data-ttu-id="87f11-181">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="87f11-181">Reset passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[<span data-ttu-id="87f11-182">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="87f11-182">Set an individual user's password to never expire</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[<span data-ttu-id="87f11-183">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="87f11-183">Let users reset their own passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[<span data-ttu-id="87f11-184">Skicka om en användares lösenord – hjälp för administratörer</span><span class="sxs-lookup"><span data-stu-id="87f11-184">Resend a user's password - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
