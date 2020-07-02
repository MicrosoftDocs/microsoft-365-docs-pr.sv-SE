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
# <a name="password-policy-recommendations"></a>Policyrekommendationer för lösenord
 
As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.
  
Information om hur du anger hur ofta Microsoft 365-lösenord ska upphöra att gälla i organisationen finns i [Ange förfalloprincip för lösenord för Microsoft 365](../manage/set-password-expiration-policy.md).

Mer information om Microsoft 365-lösenord finns i följande [relaterade artiklar](#related-articles).
  
## <a name="understanding-password-recommendations"></a>Förstå rekommendationer om lösenord

Bra metoder för lösenord delas in i några breda kategorier:
  
- **Motarbeta vanliga attacker** Här ingår valet av var användarna kan ange lösenord (kända och betrodda enheter med bra identifiering av skadlig kod, verifierade webbplatser) och valet av vilka lösenord de kan välja (längd och unikhet).

- **Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.

- **Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.

## <a name="password-guidelines-for-administrators"></a>Riktlinjer om lösenord för administratörer

The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.
  
- Ha ett krav om minimilängd på 8 tecken (längre är inte nödvändigtvis bättre)

- Don't require character composition requirements. For example, \*&amp;(^%$

- Kräv inte regelbundna lösenordsåterställningar för användarkonton

- Förbjud vanliga lösenord, för att undvika de mest sårbara lösenorden i systemet

- Utbilda användarna så att de inte återanvänder sina organisationslösenord utanför arbetet

- Tillämpa registrering för [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md)

- Aktivera riskbaserade multifaktorautentiseringskontroller

### <a name="password-guidance-for-your-users"></a>Hjälp om lösenord för användare

Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.
  
- Använd inte ett lösenord som är samma som eller liknar ett du använder på andra webbplatser

- Använd inte ett enskilt ord, till exempel **lösenord**, eller en vanlig fras, till exempel **jagälskardig**

- Gör lösenord svåra att gissa sig till, även för personer som vet mycket om dig, till exempel namn och födelsedagar för dina vänner och din familj, din favoritartist och fraser som du använder ofta

## <a name="some-common-approaches-and-their-negative-impacts"></a>Några vanliga metoder och deras negativa följder

Det här är några av de vanligaste metoderna för lösenordshantering, men forskning varnar oss för deras negativa följder.
  
### <a name="password-expiration-requirements-for-users"></a>Krav på giltighetstid för lösenord för användare

Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.
  
### <a name="requiring-long-passwords"></a>Krav på långa lösenord

Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Krav på användning av flera teckenuppsättningar

Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:
  
- versaler

- gemener

- icke-alfanumeriska tecken

Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.
  
## <a name="successful-patterns"></a>Lyckade mönster

Här finns däremot några rekommendationer om hur du uppmuntrar lösenordsvariation.
  
### <a name="ban-common-passwords"></a>Förbjud vanliga lösenord

The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abdcefg**, **password**, **monkey**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Utbilda användare så att de inte återanvänder organisationslösenord någon annanstans

One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Tillämpa registrering för multifaktorautentisering

Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords. 
  
Mer information finns i [Konfigurera multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Aktivera riskbaserad multifaktorautentisering

Med riskbaserad multifaktorautentisering går det att kontrollera att användaren är den riktiga kontoägaren när misstänkt aktivitet identifieras av systemet. 
  
## <a name="want-to-know-more-recommended-reading"></a>Vill du veta mer? Rekommenderad läsning

- [Fyller starka webblösenord någon funktion?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Lösenordsportföljer och användare med begränsad insats](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Förhindra svaga lösenord genom att läsa användarnas tankar](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Välja säkra lösenord](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Dags att ompröva obligatoriska lösenordsändringar](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [2015 års sämsta lösenord](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [Ladda ned filer från webben](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a>Relaterade artiklar

[Återställa lösenord](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[Ange att en enskild användares lösenord aldrig ska förfalla](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[Låt användare återställa sina egna lösenord](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[Skicka om en användares lösenord – hjälp för administratörer](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
