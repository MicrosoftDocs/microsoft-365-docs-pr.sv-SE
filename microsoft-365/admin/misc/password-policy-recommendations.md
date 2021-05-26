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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Gör organisationen säkrare mot lösenordsattacker och förbjud vanliga lösenord och aktivera riskbaserad multifaktorautentisering.
ms.openlocfilehash: f42905c6bf7769e558581338fd122f26d530423e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635980"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="01aea-103">Policyrekommendationer för lösenord</span><span class="sxs-lookup"><span data-stu-id="01aea-103">Password policy recommendations</span></span>

<span data-ttu-id="01aea-p101">Som administratör för en organisation är du ansvarig för att bestämma policyn för användarnas lösenord. Det kan vara komplicerat och förvirrande att ange en lösenordspolicy och den här artikeln innehåller rekommendationer för att skydda organisationen mot lösenordsattacker.</span><span class="sxs-lookup"><span data-stu-id="01aea-p101">As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="01aea-106">Information om hur du anger hur ofta Microsoft 365-lösenord ska upphöra att gälla i organisationen finns i [Ange förfalloprincip för lösenord för Microsoft 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="01aea-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="01aea-107">För mer information om Microsoft 365-lösenord se:</span><span class="sxs-lookup"><span data-stu-id="01aea-107">For more information about Microsoft 365 passwords, see:</span></span>

<span data-ttu-id="01aea-108">[Återställ lösenord](../add-users/reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="01aea-108">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>

<span data-ttu-id="01aea-109">[Ange att en enskild användares lösenord aldrig ska förfalla](../add-users/set-password-to-never-expire.md)(artikel)</span><span class="sxs-lookup"><span data-stu-id="01aea-109">[Set an individual user's password to never expire](../add-users/set-password-to-never-expire.md) (article)</span></span>

<span data-ttu-id="01aea-110">[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="01aea-110">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="01aea-111">[Skicka om en användares lösenord – hjälp för administratörer](../add-users/resend-user-password.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="01aea-111">[Resend a user's password - Admin Help](../add-users/resend-user-password.md) (article)</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="01aea-112">Förstå rekommendationer om lösenord</span><span class="sxs-lookup"><span data-stu-id="01aea-112">Understanding password recommendations</span></span>

<span data-ttu-id="01aea-113">Bra metoder för lösenord delas in i några breda kategorier:</span><span class="sxs-lookup"><span data-stu-id="01aea-113">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="01aea-114">**Motarbeta vanliga attacker** Här ingår valet av var användarna kan ange lösenord (kända och betrodda enheter med bra identifiering av skadlig kod, verifierade webbplatser) och valet av vilka lösenord de kan välja (längd och unikhet).</span><span class="sxs-lookup"><span data-stu-id="01aea-114">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="01aea-p102">**Begränsa lyckade attacker** Att begränsa lyckade hackarattacker handlar om att begränsa exponering till en viss tjänst, eller förhindra skadan helt och hållet, om en användares lösenord stjäls. Till exempel att se till att ett avslöjande av din inloggningsinformation för sociala nätverk inte gör ditt bankkonto sårbart, eller att se till att ett konto med svagt skydd inte tar emot återställningslänkar för ett viktigt konto.</span><span class="sxs-lookup"><span data-stu-id="01aea-p102">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="01aea-p103">**Förstå människans natur** Många giltiga lösenordsmetoder misslyckas på grund av naturliga mänskliga beteenden. Det är avgörande att förstå människans natur eftersom forskning visar att nästan alla regler som du tillämpar för användarna leder till svagare lösenord. Krav gällande längd, specialtecken och lösenordsändring leder till normalisering av lösenord, vilket gör det enklare för attackerare att gissa eller knäcka lösenord.</span><span class="sxs-lookup"><span data-stu-id="01aea-p103">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="01aea-120">Riktlinjer om lösenord för administratörer</span><span class="sxs-lookup"><span data-stu-id="01aea-120">Password guidelines for administrators</span></span>

<span data-ttu-id="01aea-p104">Det primära målet med ett säkrare lösenordssystem är lösenordsvariation. Lösenordsprincipen bör innehålla många olika och svårgissade lösenord. Här är några rekommendationer för att skydda organisationen.</span><span class="sxs-lookup"><span data-stu-id="01aea-p104">The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="01aea-124">Ha ett krav om minimilängd på 8 tecken (längre är inte nödvändigtvis bättre)</span><span class="sxs-lookup"><span data-stu-id="01aea-124">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="01aea-p105">Ha inte krav på teckensammansättning. Exempel: \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="01aea-p105">Don't require character composition requirements. For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="01aea-127">Kräv inte regelbundna lösenordsåterställningar för användarkonton</span><span class="sxs-lookup"><span data-stu-id="01aea-127">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="01aea-128">Förbjud vanliga lösenord, för att undvika de mest sårbara lösenorden i systemet</span><span class="sxs-lookup"><span data-stu-id="01aea-128">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="01aea-129">Utbilda användarna så att de inte återanvänder sina organisationslösenord utanför arbetet</span><span class="sxs-lookup"><span data-stu-id="01aea-129">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="01aea-130">Tillämpa registrering för [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="01aea-130">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="01aea-131">Aktivera riskbaserade multifaktorautentiseringskontroller</span><span class="sxs-lookup"><span data-stu-id="01aea-131">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="01aea-132">Hjälp om lösenord för användare</span><span class="sxs-lookup"><span data-stu-id="01aea-132">Password guidance for your users</span></span>

<span data-ttu-id="01aea-p106">Här är lite hjälp om lösenord för användarna i organisationen. Se till att informera användarna om de här rekommendationerna och tillämpa rekommenderade lösenordsprinciper på organisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="01aea-p106">Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="01aea-135">Använd inte ett lösenord som är samma som eller liknar ett du använder på andra webbplatser</span><span class="sxs-lookup"><span data-stu-id="01aea-135">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="01aea-136">Använd inte ett enskilt ord, till exempel **lösenord**, eller en vanlig fras, till exempel **jagälskardig**</span><span class="sxs-lookup"><span data-stu-id="01aea-136">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="01aea-137">Gör lösenord svåra att gissa sig till, även för personer som vet mycket om dig, till exempel namn och födelsedagar för dina vänner och din familj, din favoritartist och fraser som du använder ofta</span><span class="sxs-lookup"><span data-stu-id="01aea-137">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="01aea-138">Några vanliga metoder och deras negativa följder</span><span class="sxs-lookup"><span data-stu-id="01aea-138">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="01aea-139">Det här är några av de vanligaste metoderna för lösenordshantering, men forskning varnar oss för deras negativa följder.</span><span class="sxs-lookup"><span data-stu-id="01aea-139">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="01aea-140">Krav på giltighetstid för lösenord för användare</span><span class="sxs-lookup"><span data-stu-id="01aea-140">Password expiration requirements for users</span></span>

<span data-ttu-id="01aea-p107">Lösenordets utgångskrav gör mer skada än nytta, eftersom dessa krav får användarna att välja förutsägbara lösenord, sammansatta av ord och nummer som är nära relaterade till varandra. I dessa fall kan nästa lösenord förutsägas baserat på föregående lösenord. Lösenordens utgångskrav erbjuder inga fördelar för inneslutning eftersom cyberbrottslingar nästan alltid använder referenser så fort de äventyrar dem. Kolla in [tid att ompröva obligatoriska lösenordsändringar ](https://go.microsoft.com/fwlink/p/?linkid=861018)för mer information.</span><span class="sxs-lookup"><span data-stu-id="01aea-p107">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them. Check out [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) for more info.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="01aea-145">Krav på långa lösenord</span><span class="sxs-lookup"><span data-stu-id="01aea-145">Requiring long passwords</span></span>

<span data-ttu-id="01aea-p108">Krav på lösenordslängd (fler än cirka 10 tecken) kan leda till förutsägbara och oönskade användarbeteenden. Användare som måste ha ett lösenord med minst 16 tecken kan till exempel välja upprepade mönster som **fyrafyrafyrafyra** eller **lösenordlösenord** som uppfyller kravet på teckenlängd men inte är svåra att gissa sig till. Längdkrav ökar dessutom risken för att användare använder sig av andra osäkra metoder, till exempel att skriva ned sina lösenord, använda dem igen eller lagra dem okrypterade i sina dokument. För att uppmuntra användare att komma på ett unikt lösenord rekommenderar vi att ha ett rimligt krav om minimilängd på 8 tecken.</span><span class="sxs-lookup"><span data-stu-id="01aea-p108">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span>
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="01aea-150">Krav på användning av flera teckenuppsättningar</span><span class="sxs-lookup"><span data-stu-id="01aea-150">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="01aea-p109">Krav på lösenordskomplexitet minskar nyckelutrymmet och leder till förutsägbart användarbeteende, vilket gör mer skada än nytta. I de flesta system tillämpas någon nivå av krav på lösenordskomplexitet. Till exempel måste lösenord innehålla tecken från samtliga av följande tre kategorier:</span><span class="sxs-lookup"><span data-stu-id="01aea-p109">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="01aea-154">versaler</span><span class="sxs-lookup"><span data-stu-id="01aea-154">uppercase characters</span></span>

- <span data-ttu-id="01aea-155">gemener</span><span class="sxs-lookup"><span data-stu-id="01aea-155">lowercase characters</span></span>

- <span data-ttu-id="01aea-156">icke-alfanumeriska tecken</span><span class="sxs-lookup"><span data-stu-id="01aea-156">non-alphanumeric characters</span></span>

<span data-ttu-id="01aea-p110">De flesta använder liknande mönster, till exempel en versal i den första positionen, en symbol i den sista och en siffra i de sista två. Cyberbrottslingar vet om det, så de kör sina ordlisteattacker med de vanligaste ersättningarna, ”$” för ”s”, ”@” för ”a”, ”1” för ”l”. Att tvinga användare att välja en kombination av versaler, gemener, siffror och specialtecken har en negativ effekt. Vissa komplexitetskrav hindrar till och med användare från att använda säkra lösenord som de kommer ihåg, och tvingar dem att komma på mindre säkra lösenord som är svårare att komma ihåg.</span><span class="sxs-lookup"><span data-stu-id="01aea-p110">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="01aea-161">Lyckade mönster</span><span class="sxs-lookup"><span data-stu-id="01aea-161">Successful Patterns</span></span>

<span data-ttu-id="01aea-162">Här finns däremot några rekommendationer om hur du uppmuntrar lösenordsvariation.</span><span class="sxs-lookup"><span data-stu-id="01aea-162">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="01aea-163">Förbjud vanliga lösenord</span><span class="sxs-lookup"><span data-stu-id="01aea-163">Ban common passwords</span></span>

<span data-ttu-id="01aea-p111">Det viktigaste lösenordskravet du bör tillämpa när användarna skapar lösenord är att förbjuda användning av vanliga lösenord för att minska organisationens känslighet för råstyrkeattacker. Vanliga användarlösenord är bland annat **abcdefg**, **lösenord** och **sommar**.</span><span class="sxs-lookup"><span data-stu-id="01aea-p111">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abcdefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="01aea-166">Utbilda användare så att de inte återanvänder organisationslösenord någon annanstans</span><span class="sxs-lookup"><span data-stu-id="01aea-166">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="01aea-p112">Ett av de viktigaste budskapen att få fram till organisationens användare är att de inte ska återanvända sitt organisationslösenord någon annanstans. Användning av organisationslösenord på externa webbplatser ökar kraftigt risken för att cyberbrottslingar får tag på lösenorden.</span><span class="sxs-lookup"><span data-stu-id="01aea-p112">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="01aea-169">Tillämpa registrering för multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="01aea-169">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="01aea-p113">Se till att användarna uppdaterar kontakt- och säkerhetsinformation, till exempel en alternativ e-postadress, telefonnummer eller en enhet som är registrerad för push-meddelanden, så att de kan svara på säkerhetskontroller och meddelas om säkerhetshändelser. Uppdaterad kontakt- och säkerhetsinformation hjälper användarna att bekräfta sin identitet om de någonsin glömmer sitt lösenord eller om någon annan försöker ta över deras konto. Det ger också en alternativ meddelandekanal vid säkerhetshändelser, till exempel inloggningsförsök eller ändrade lösenord.</span><span class="sxs-lookup"><span data-stu-id="01aea-p113">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="01aea-173">Mer information finns i [Konfigurera multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="01aea-173">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="01aea-174">Aktivera riskbaserad multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="01aea-174">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="01aea-175">Med riskbaserad multifaktorautentisering går det att kontrollera att användaren är den riktiga kontoägaren när misstänkt aktivitet identifieras av systemet.</span><span class="sxs-lookup"><span data-stu-id="01aea-175">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="01aea-176">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="01aea-176">Next steps</span></span>

<span data-ttu-id="01aea-177">Vill du veta mer om hur du hanterar lösenord?</span><span class="sxs-lookup"><span data-stu-id="01aea-177">Want to know more about managing passwords?</span></span> <span data-ttu-id="01aea-178">Här är några rekommenderade artiklar att läsa:</span><span class="sxs-lookup"><span data-stu-id="01aea-178">Here is some recommended reading:</span></span>

- [<span data-ttu-id="01aea-179">Fyller starka webblösenord någon funktion?</span><span class="sxs-lookup"><span data-stu-id="01aea-179">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="01aea-180">Lösenordsportföljer och användare med begränsad insats</span><span class="sxs-lookup"><span data-stu-id="01aea-180">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="01aea-181">Förhindra svaga lösenord genom att läsa användarnas tankar</span><span class="sxs-lookup"><span data-stu-id="01aea-181">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="01aea-182">Välja säkra lösenord</span><span class="sxs-lookup"><span data-stu-id="01aea-182">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="01aea-183">Dags att ompröva obligatoriska lösenordsändringar</span><span class="sxs-lookup"><span data-stu-id="01aea-183">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="01aea-184">2015 års sämsta lösenord</span><span class="sxs-lookup"><span data-stu-id="01aea-184">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-content"></a><span data-ttu-id="01aea-185">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="01aea-185">Related content</span></span>

<span data-ttu-id="01aea-186">[Återställa lösenord](../add-users/reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="01aea-186">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="01aea-187">[Ställa in en enskild användares lösenord för att aldrig ska förfalla](../add-users/set-password-to-never-expire.md)(artikel)</span><span class="sxs-lookup"><span data-stu-id="01aea-187">[Set an individual user's password to never expire](../add-users/set-password-to-never-expire.md) (article)</span></span>\
<span data-ttu-id="01aea-188">[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="01aea-188">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="01aea-189">[Skicka om en användares lösenord – hjälp för administratörer](../add-users/resend-user-password.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="01aea-189">[Resend a user's password - Admin Help](../add-users/resend-user-password.md) (article)</span></span>
