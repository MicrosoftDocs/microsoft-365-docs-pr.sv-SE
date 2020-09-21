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
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Säkra användarinloggningar till din Microsoft 365-klient

Så här ökar du säkerheten för användarinloggningar:

- Använd Azure Active Directory (Azure AD) lösenordsskydd
- Använd multifaktorautentisering (MFA)
- Distribuera identitets- och enhetsåtkomstpolicyer

## <a name="azure-ad-password-protection"></a>Azure AD-lösenordsskydd

Azure AD-lösenordsskydd upptäcker och blockerar kända svaga lösenord och deras varianter och kan också blockera ytterligare svaga termer som är specifika för din organisation. Standard globala förbjudna lösenordslistor tillämpas automatiskt på alla användare i en Azure AD-klient. Du kan definiera ytterligare poster i en anpassad förbjuden lösenordslista. När användare ändrar eller återställer sina lösenord kontrolleras dessa förbjudna lösenordslistor för att använda starka lösenord.

Mer information finns i [Konfigurera Azure AD-lösenordsskydd](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).

## <a name="mfa"></a>MFA

MFA kräver att användarinloggningar underkastas en ytterligare verifiering utöver lösenordet för användarkontot. Även om en användare som vill vålla skada bestämmer ett lösenord för ett användarkonto, måste de också kunna svara på en ytterligare verifiering, till exempel ett textmeddelande som skickas till en smartphone innan åtkomst beviljas.

![Rätt lösenord plus extra verifiering gör att inloggningen lyckas](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Ditt första steg i att använda MFA är att ***kräva det för alla administratörskonton***, även kända som privilegierade konton.

Utöver detta första steg rekommenderar Microsoft starkt MFA för alla användare.

Det finns tre sätt att kräva att dina administratörer eller användare använder MFA baserat på din Microsoft 365-plan.

| Planera | Rekommendation |
|---------|---------|
|Alla Microsoft 365-abonnemang (utan Azure Active Directory Premium P1- eller P2-licenser)     |[Aktivera standardinställningar för säkerhet i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Standardinställningar för säkerhet i Azure AD inkluderar MFA för användare och administratörer.   |
|Microsoft 365 E3 (inkluderar Azure Active Directory Premium P1-licenser)     | Använd [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer: <br>- [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (inkluderar Azure Active Directory Premium P2-licenser)     | Dra nytta av Azure AD Identity Protection och börja implementera Microsofts [rekommenderade uppsättning av villkorsstyrd åtkomst och relaterade principer](../enterprise/identity-access-policies.md) genom att skapa de två principerna:<br> - [Kräv MFA när inloggningsrisker är medel eller hög](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Användare med hög risk måste byta lösenord](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Standardinställningar för säkerhet är en ny funktion för Microsoft 365 och Office 365, betalade eller utvärderingsprenumerationer skapade efter den 21 oktober 2019. De här prenumerationerna har aktiverat standardinställningar för säkerhet som ***kräver att alla dina användare ska använda MFA med programmet Microsoft Authenticator-appen***.
 
Användare har 14 dagar på sig att registrera sig för MFA med Microsoft Authenticator-appen från sina smartphones, som börjar från första gången de loggar in efter att standardinställningar för säkerhet har aktiverats. Efter 14 dagar kommer användaren inte att kunna logga in förrän MFA-registreringen är klar.

Standardinställningar för säkerhet säkerställer att alla organisationer har en grundläggande säkerhetsnivå för användarinloggning som är aktiverad som standard. Du kan inaktivera standardinställningar för säkerhet till förmån för MFA med Principer för villkorsstyrd åtkomst eller för enskilda konton.

Mer information finns i den här [översikten över standardinställningar för säkerhet](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Policyer för villkorlig åtkomst är en uppsättning regler som anger villkoren för att inloggningar utvärderas och åtkomst beviljas. Du kan till exempel skapa en princip för villkorsstyrd åtkomst som anger:

- Om namnet på användarkontot är medlem i en grupp för användare som är tilldelade rollerna Exchange, användare, lösenord, säkerhet, SharePoint eller global administratör krävs MFA innan åtkomst tillåts.

Med den här principen kan du kräva MFA baserat på gruppmedlemskap, i stället för att försöka konfigurera enskilda användarkonton för MFA när de tilldelas eller tas bort från dessa administratörsroller.

Du kan också använda principer för villkorsstyrd åtkomst för mer avancerade funktioner, t. ex. krav på att inloggningen görs från en kompatibel enhet, t. ex. en bärbar dator med Windows 10.

Villkorsstyrd åtkomst kräver Azure Active Directory Premium P1-licens som ingår i Microsoft 365 E3 och E5.

Mer information finns i den här [översikt av villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="using-these-methods-together"></a>Använda dessa metoder tillsammans

Tänk på följande:

- Du kan inte aktivera standardinställningar för säkerhet om du har aktiverat principer för villkorsstyrd åtkomst.
- Du kan inte aktivera principer för villkorsstyrd åtkomst om du har aktiverat standardinställningar för säkerhet.

Om standardinställningar för säkerhet är aktiverade, blir alla nya användare ombedda att registrera sig och använda Microsoft Authenticator-appen. 

I den här tabellen visas resultatet av att aktivera MFA med standardinställningar för säkerhet och principer för villkorsstyrd åtkomst.

| Metod | Aktiverad | Inaktiverad | Ytterligare autentiseringsmetod |
|:-------|:-----|:-------|:-------|
| **Standardinställningar för säkerhet**  | Det går inte att använda principer för villkorsstyrd åtkomst | Det går att använda principer för villkorsstyrd åtkomst | Microsoft Authenticator-appen |
| **Principer för villkorsstyrd åtkomst** | Om några är aktiverade kan du inte aktivera standardinställningar för säkerhet | Om alla är inaktiverade kan du aktivera standardinställningar för säkerhet  | Användare anger under MFA-registrering  |
||||

## <a name="identity-and-device-access-policies"></a>Policyer för identitets- och enhetsåtkomst

Identitets- och enhetsåtkomstinställningar och policyer rekommenderas förutsättningsfunktioner och deras inställningar i kombination med villkorlig åtkomst, Intune och Azure AD Identity Protection-principer som avgör om en given åtkomstbegäran ska beviljas och under vilka villkor. Denna bestämning baseras på användarkontot för inloggningen, den enhet som används, appen som användaren använder för åtkomst, platsen från vilken begäran om åtkomst görs och en bedömning av risken för begäran. Denna funktion hjälper till att säkerställa att endast godkända användare och enheter kan komma åt dina kritiska resurser.

>[!Note]
>För Azure Active Directory Identity Protection krävs Azure Active Directory Premium P2-licenser, som ingår i Microsoft 365 E5.
>

Policyer för identitets- och enhetsåtkomst definieras för att användas i tre nivåer: 

- Baslinjeskydd är en minsta säkerhetsnivå för dina identiteter och enheter som har åtkomst till dina appar och data.
- Känsligt skydd ger ytterligare säkerhet för specifika data. Identiteter och enheter är föremål för högre säkerhetsnivåer och krav på enhetens hälsa.
- Skydd för miljöer med högt reglerad eller sekretessbelagd information gäller typiskt små mängder data som är mycket klassificerade, innehåller affärshemligheter eller är föremål för dataregler. Identiteter och enheter är föremål för mycket högre säkerhetsnivåer och krav på enhetens hälsa. 

Dessa nivåer och deras motsvarande konfigurationer ger konsekventa skyddsnivåer för dina data, identiteter och enheter.

Microsoft rekommenderar starkt att du konfigurerar och rullar ut policyer för identitets- och enhetsåtkomst i din organisation, inklusive specifika inställningar för Microsoft Teams, Exchange Online och SharePoint. Mer information finns i konfigurationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md).

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

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>Administrera tekniska resurser för MFA och säkra inloggningar

- [MFA för Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Identitets översikt för Microsoft 365](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD-utbildningsvideor](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Tillämpa registreringspolicy för Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Konfigurationer för identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md)

