---
title: Säkra användarinloggningar till din Microsoft 365-klient
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365initiative-coredeploy
ms.custom: ''
description: Kräva att dina användare loggar in säkert med multifaktorautentisering (MFA) och andra funktioner.
ms.openlocfilehash: a3a63dfc06f5470c2151cd2ff140ad5dee19b0ce
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446083"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Säkra användarinloggningar till din Microsoft 365-klient

Så här ökar du säkerheten för användarinloggningar:

- Använda Windows Hello för företag
- Använd Azure Active Directory (Azure AD) lösenordsskydd
- Använd multifaktorautentisering (MFA)
- Distribuera identitet och enhetsåtkomst konfigurationer
- Skydda mot referens kompromiss med Azure AD Identity Protection

## <a name="windows-hello-for-business"></a>Windows Hello för företag

Windows Hello för företag i Windows 10 Enterprise ersätter lösenord med stark tvåfaktorsautentisering när du loggar in på en Windows-enhet. De två faktorerna är en ny typ av användaruppgifter som är kopplade till en enhet och ett biometriskt attribut eller en PIN-kod.

Mer information finns i [Översikt över Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).


## <a name="azure-ad-password-protection"></a>Azure AD-lösenordsskydd

Azure AD Password Protection upptäcker och blockerar kända svaga lösenord och deras varianter och kan också blockera ytterligare svaga termer som är specifika för din organisation. Standard globala förbjudna lösenordslistor tillämpas automatiskt på alla användare i en Azure AD-klient. Du kan definiera ytterligare poster i en anpassad förbjuden lösenordslista. När användare ändrar eller återställer sina lösenord kontrolleras dessa förbjudna lösenordslistor för att använda starka lösenord.

Mer information finns i [Konfigurera Azure AD-lösenordsskydd](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).

## <a name="mfa"></a>MFA

MFA kräver att användarinloggningar underkastas en ytterligare verifiering utöver lösenordet för användarkontot. Även om en användare som vill vålla skada bestämmer ett lösenord för ett användarkonto, måste de också kunna svara på en ytterligare verifiering, till exempel ett textmeddelande som skickas till en smartphone innan åtkomst beviljas.

![Rätt lösenord plus extra verifiering gör att inloggningen lyckas](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Ditt första steg i att använda MFA är att ***kräva det för alla administratörskonton***, även kända som privilegierade konton.

Utöver detta första steg rekommenderar Microsoft MFA för alla användare.

Det finns tre sätt att kräva att dina administratörer eller användare använder MFA baserat på din Microsoft 365-plan.

| Planera | Rekommendation |
|---------|---------|
|Alla Microsoft 365-abonnemang (utan Azure Active Directory Premium P1- eller P2-licenser)     |[Aktivera standardinställningar för säkerhet i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Standardinställningar för säkerhet i Azure AD inkluderar MFA för användare och administratörer.   |
|Microsoft 365 E3 (inkluderar Azure Active Directory Premium P1-licenser)     | Använd [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer: <br>- [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (inkluderar Azure Active Directory Premium P2-licenser)     | Dra nytta av Azure AD Identity Protection och börja implementera Microsofts [rekommenderade uppsättning av villkorsstyrd åtkomst och relaterade principer](../security/office-365-security/identity-access-policies.md) genom att skapa de två principerna:<br> - [Kräv MFA när inloggningsrisker är medel eller hög](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Användare med hög risk måste byta lösenord](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Standardinställningar för säkerhet är en ny funktion för Microsoft 365 och Office 365, betalade eller utvärderingsprenumerationer skapade efter den 21 oktober 2019. De här prenumerationerna har aktiverat standardinställningar för säkerhet som ***kräver att alla dina användare ska använda MFA med programmet Microsoft Authenticator-appen***.
 
Användare har 14 dagar på sig att registrera sig för MFA med Microsoft Authenticator-appen från sina smartphones, som börjar från första gången de loggar in efter att standardinställningar för säkerhet har aktiverats. Efter 14 dagar kommer användaren inte att kunna logga in förrän MFA-registreringen är klar.

Standardinställningar för säkerhet säkerställer att alla organisationer har en grundläggande säkerhetsnivå för användarinloggning som är aktiverad som standard. Du kan inaktivera standardinställningar för säkerhet till förmån för MFA med Principer för villkorsstyrd åtkomst eller för enskilda konton.

Mer information finns i [översikt av säkerhetsstandarder](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Policyer för villkorlig åtkomst är en uppsättning regler som anger villkoren för att inloggningar utvärderas och åtkomst beviljas. Du kan till exempel skapa en princip för villkorsstyrd åtkomst som anger:

- Om namnet på användarkontot är medlem i en grupp för användare som är tilldelade rollerna Exchange, användare, lösenord, säkerhet, SharePoint eller global administratör krävs MFA innan åtkomst tillåts.

Med den här principen kan du kräva MFA baserat på gruppmedlemskap, i stället för att försöka konfigurera enskilda användarkonton för MFA när de tilldelas eller tas bort från dessa administratörsroller.

Du kan också använda principer för villkorsstyrd åtkomst för mer avancerade funktioner, t. ex. krav på att inloggningen görs från en kompatibel enhet, t. ex. en bärbar dator med Windows 10.

Villkorsstyrd åtkomst kräver Azure Active Directory Premium P1-licens som ingår i Microsoft 365 E3 och E5.

Mer information finns i [översikt av villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

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

## <a name="identity-and-device-access-configurations"></a>Konfigurationer av identiteter och enhetsåtkomst

Identitets- och enhetsåtkomstinställningar och policyer rekommenderas förutsättningsfunktioner och deras inställningar i kombination med villkorlig åtkomst, Intune och Azure AD Identity Protection-principer som avgör om en given åtkomstbegäran ska beviljas och under vilka villkor. Denna bestämning baseras på användarkontot för inloggningen, den enhet som används, appen som användaren använder för åtkomst, platsen från vilken begäran om åtkomst görs och en bedömning av risken för begäran. Denna funktion hjälper till att säkerställa att endast godkända användare och enheter kan komma åt dina kritiska resurser.

>[!Note]
>För Azure Active Directory Identity Protection krävs Azure Active Directory Premium P2-licenser, som ingår i Microsoft 365 E5.
>

Policyer för identitets- och enhetsåtkomst definieras för att användas i tre nivåer: 

- Baslinjeskydd är en minsta säkerhetsnivå för dina identiteter och enheter som har åtkomst till dina appar och data.
- Känsligt skydd ger ytterligare säkerhet för specifika data. Identiteter och enheter är föremål för högre säkerhetsnivåer och krav på enhetens hälsa.
- Skydd för miljöer med högt reglerad eller sekretessbelagd information gäller typiskt små mängder data som är mycket klassificerade, innehåller affärshemligheter eller är föremål för dataregler. Identiteter och enheter är föremål för mycket högre säkerhetsnivåer och krav på enhetens hälsa. 

Dessa nivåer och deras motsvarande konfigurationer ger konsekventa skyddsnivåer för dina data, identiteter och enheter.

Microsoft rekommenderar starkt att du konfigurerar och rullar ut policyer för identitets- och enhetsåtkomst i din organisation, inklusive specifika inställningar för Microsoft Teams, Exchange Online och SharePoint. Mer information finns i konfigurationer för [identitets- och enhetsåtkomst](../security/office-365-security/microsoft-365-policies-configurations.md).

## <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

I det här avsnittet får du lära dig hur du konfigurerar principer som skyddar mot obehörig inloggning, där en angripare bestämmer en användares kontonamn och lösenord för att få åtkomst till organisationens molntjänster och data. Azure AD Identity Protection tillhandahåller ett antal olika sätt som förhindrar att en obehörig angripare kan kompromettera användarkontots inloggningsuppgifter.

Med Azure AD Identity Protection kan du:

|Funktion|Beskrivning|
|:---------|:---------|
| Fastställa och åtgärda potentiella säkerhetsproblem i organisationens identiteter | I Azure AD används maskininlärning för att identifiera avvikelser och misstänkt aktivitet, till exempel inloggningar och aktiviteter efter inloggning. Med dessa data genererar Azure AD Identity Protection rapporter och aviseringar som hjälper dig att utvärdera problem och vidta åtgärder.|
|Identifiera misstänkta åtgärder som är relaterade till organisationens identitet och svara på dem automatiskt|Du kan konfigurera riskbaserade principer som automatiskt reagerar på problem som upptäcks när en viss risknivå har uppnåtts. Dessa principer, förutom andra kontroller för villkorsstyrd åtkomst i Azure AD och Microsoft Intune, kan antingen automatiskt blockera åtkomst eller utföra korrigeringsåtgärder, t.ex. återställning av lösenord och krav på multifaktorautentisering för efterföljande inloggningar. |
| Undersök misstänkta händelser och åtgärda dem med administrativa åtgärder | Du kan undersöka riskhändelser med hjälp av information om säkerhetshändelsen. Enkla arbetsflöden är tillgängliga för att spåra undersökningar och initiera åtgärder för reparationer, som återställning av lösenord. |
|||

Se [mer information om Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Se [stegen för att aktivera Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>Administrera tekniska resurser för MFA och säkra inloggningar

- [MFA för Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Identitets översikt för Microsoft 365](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD-utbildningsvideor](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Tillämpa registreringspolicy för Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Konfigurationer för identitets- och enhetsåtkomst](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="next-step"></a>Nästa steg

[Hantera dina användarkonton](manage-microsoft-365-accounts.md)