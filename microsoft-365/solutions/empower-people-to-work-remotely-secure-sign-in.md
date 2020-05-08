---
title: Steg 1. Öka inloggningssäkerheten för distansarbetare med MFA
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Kräv att dina distansarbetare loggar in med multi-factor authentication (MFA).
ms.openlocfilehash: 2cb16c78f7fb0b1f9f48559c61a6200d6adcf470
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166143"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>Steg 1. Öka inloggningssäkerheten för distansarbetare med MFA

Använd multi-factor authentication (MFA) om du vill öka inloggningssäkerheten för distansarbetare. MFA kräver att användarinloggningar underkastas en ytterligare verifiering utöver lösenordet för användarkontot. Även om en användare som vill vålla skada bestämmer ett lösenord för ett användarkonto, måste de också kunna svara på en ytterligare verifiering, till exempel ett textmeddelande som skickas till en smartphone innan åtkomst beviljas.

![Rätt lösenord plus extra verifiering gör att inloggningen lyckas](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

För alla användare, inklusive distansarbetare och särskilt administratörer, rekommenderar Microsoft starkt MFA.

Det finns tre sätt till att kräva att dina användare ska använda MFA baserat på ditt Microsoft 365-abonnemang.

|Planera  |Rekommendation  |
|---------|---------|
|Microsoft 365-abonnemang (utan Azure AD Premium P1 eller P2)     |[Aktivera standardinställningar för säkerhet i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Standardinställningar för säkerhet i Azure AD inkluderar MFA för användare och administratörer.   |
|Microsoft 365 E3 (med Azure AD Premium P1)     | Använd [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer: <br>- [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (med Azure AD Premium P2)     | Dra nytta av Azure AD Identity Protection och börja implementera Microsofts [rekommenderade uppsättning av villkorsstyrd åtkomst och relaterade principer](../enterprise/identity-access-policies.md) genom att skapa de två principerna:<br> - [Kräv MFA när inloggningsrisker är medel eller hög](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Blockera klienter som inte har stöd för modern autentisering](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Användare med hög risk måste byta lösenord](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Standardinställningar för säkerhet

Standardinställningar för säkerhet är en ny funktion för Microsoft 365 och Office 365, betalade eller utvärderingsprenumerationer skapade efter den 21 oktober 2019. De här prenumerationerna har aktiverat standardinställningar för säkerhet som ***kräver att alla dina användare ska använda MFA med programmet Microsoft Authenticator-appen***.
 
Användare har 14 dagar på sig att registrera sig för MFA med Microsoft Authenticator-appen från sina smartphones, som börjar från första gången de loggar in efter att standardinställningar för säkerhet har aktiverats. Efter 14 dagar kommer användaren inte att kunna logga in förrän MFA-registreringen är klar.

Standardinställningar för säkerhet säkerställer att alla organisationer har en grundläggande säkerhetsnivå för användarinloggning som är aktiverad som standard. Du kan inaktivera standardinställningar för säkerhet till förmån för MFA med Principer för villkorsstyrd åtkomst eller för enskilda konton.

Mer information finns i den här [översikten över standardinställningar för säkerhet](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

## <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Principer för villkorsstyrd åtkomst är en uppsättning regler som anger villkoren under vilka inloggningar utvärderas och tillåts. Du kan till exempel skapa en princip för villkorsstyrd åtkomst som anger:

- Om namnet på användarkontot är för en användare som är en Exchange-, användar-, lösen ords-, säkerhets- eller SharePoint-administratör eller global administratör, så måste du tillåta MFA innan åtkomst tillåts.

Med den här principen blir det enklare än att försöka komma ihåg att konfigurera enskilda användarkonton för MFA när de läggs till i eller tas bort från dessa administratörsroller.

Du kan också använda principer för villkorsstyrd åtkomst för mer avancerade funktioner, t. ex. krav på att inloggningen görs från en kompatibel enhet, t. ex. en bärbar dator med Windows 10.

För villkorsstyrd åtkomst krävs Azure AD Premium P1, som ingår i Microsoft 365 E3 och E5.

Mer information finns i den här [översikt över villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

## <a name="azure-ad-identity-protection-policies"></a>Principer för Azure AD Identity Protection

Principer för Azure AD Identity Protection är regler som anger villkoren under vilka inloggningar utvärderas och tillåts. Du kan till exempel skapa en princip för Azure AD Identity Protection som anger:

- Om risken för inloggningen fastställs som medel eller hög risk måste användaren använda MFA för att logga in.

För Azure AD Identity Protection krävs Azure AD Premium P2, som ingår i Microsoft 365 E5.

Mer information finns i den här [översikt över Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

## <a name="using-these-methods-together"></a>Använda dessa metoder tillsammans

Tänk på följande:

- Du kan inte aktivera standardinställningar för säkerhet om du har aktiverat principer för villkorsstyrd åtkomst.
- Du kan inte aktivera principer för villkorsstyrd åtkomst om du har aktiverat standardinställningar för säkerhet.

Om standardinställningar för säkerhet är aktiverade, blir alla nya användare ombedda att registrera sig och använda Microsoft Authenticator-appen. 

I den här tabellen visas resultatet av att aktivera MFA med standardinställningar för säkerhet, principer för villkorsstyrd åtkomst och användarspecifika kontoinställningar.

|| Aktiverat | Inaktiverad | Metod för sekundär autentisering |
|:-------|:-----|:-------|:-------|
| **Standardinställningar för säkerhet**  | Det går inte att använda principer för villkorsstyrd åtkomst | Det går att använda principer för villkorsstyrd åtkomst | Microsoft Authenticator-appen |
| **Principer för villkorsstyrd åtkomst** | Om några är aktiverade kan du inte aktivera standardinställningar för säkerhet | Om alla inte är aktiverade kan du inte aktivera standardinställningar för säkerhet  | Användardefinierad under MFA-registrering  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>Administrationsutbildning och tekniska resurser för MFA och identitet

- [MFA-planering för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [De 5 bästa sätten på vilka Azure AD kan hjälpa dig att aktivera distansarbete](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Planera och distribuera din identitetsinfrastruktur för Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Azure Academy Azure AD-utbildningsvideor](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Tillämpa registreringspolicy för Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>Resultat i steg 1

När du har distribuerat MFA måste dina användare:

- Använda MFA för-inloggning.
- Ha genomfört processen för MFA-registrering och använda MFA för alla inloggningar.

## <a name="next-step"></a>Nästa steg

Fortsätt med [Steg 2](empower-people-to-work-remotely-remote-access.md) om du vill tillhandahålla fjärråtkomst till lokala appar och tjänster.
