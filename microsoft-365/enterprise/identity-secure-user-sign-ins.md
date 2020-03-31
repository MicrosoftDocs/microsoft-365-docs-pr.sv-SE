---
title: 'Steg 3: Skydda och hantera användarinloggningar'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Du kan göra användarinloggningar till Windows-enheter och Microsoft 365 säkrare.
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42805452"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>Steg 3: Skydda och hantera användarinloggningar

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>Använda Windows Hello för företag

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*

Windows Hello för företag i Windows 10 Enterprise ersätter lösenord med stark tvåfaktorsautentisering när du loggar in på en Windows-enhet. De två faktorerna är en ny typ av användaruppgifter som är kopplade till en enhet och ett biometriskt attribut eller en PIN-kod.

Mer information finns i [Översikt över Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>Konfigurera Azure Multi-Factor Authentication

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*

I det här steget konfigurerar du Azure Multi-Factor Authentication (MFA) för att lägga till en andra säkerhetsnivå för användarinloggningar och transaktioner. MFA kräver ytterligare en verifieringsmetod efter att användarna korrekt har angett sina lösenord. Utan MFA är lösenordet den enda verifieringsmetoden. Problemet med lösenord är att många av dem är enkla att gissa sig till av obehöriga personer eller omedvetet delas med parter som inte är betrodda.

Med MFA kan den andra säkerhetsnivån vara:

- En personlig och betrodd enhet som inte är lätt att förfalska eller duplicera, t.ex. en smartphone.
- Ett biometriskt attribut, t.ex. ett fingeravtryck.

Du ska aktivera MFA och konfigurera den sekundära autentiseringsmetoden med [principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), som gör att du kan använda Azure Active Directory-grupper (Azure AD) för att distribuera MFA till angivna uppsättningar av användare, t.ex. pilotanvändare, geografiska regioner eller avdelningar. Se till att informera användarna om att MFA är aktiverat så att de förstår kraven, t.ex. obligatoriskt utnyttjande av en smartphone för att logga in, och kan logga in korrekt. 

Mer information finns i [Planera en molnbaserad distribution av Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Azure Multi-Factor Authentication](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-mfa) för det här avsnittet.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Skydda mot obehörig inloggning

*Det här är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*

I det här avsnittet får du lära dig hur du konfigurerar principer som skyddar mot obehörig inloggning, där en angripare bestämmer en användares kontonamn och lösenord för att få åtkomst till organisationens molntjänster och data. Azure AD Identity Protection tillhandahåller ett antal olika sätt som förhindrar att en obehörig angripare kan kompromettera användarkontots inloggningsuppgifter.

Med Azure AD Identity Protection kan du:

|||
|:---------|:---------|
|Fastställa och åtgärda potentiella säkerhetsproblem i organisationens identiteter|I Azure AD används maskininlärning för att identifiera avvikelser och misstänkt aktivitet, till exempel inloggningar och aktiviteter efter inloggning. Med dessa data genererar Azure AD Identity Protection rapporter och aviseringar som hjälper dig att utvärdera problem och vidta åtgärder.|
|Identifiera misstänkta åtgärder som är relaterade till organisationens identitet och svara på dem automatiskt|Du kan konfigurera riskbaserade principer som automatiskt reagerar på problem som upptäcks när en viss risknivå har uppnåtts. Dessa principer, förutom andra kontroller för villkorsstyrd åtkomst i Azure AD och Microsoft Intune, kan antingen automatiskt blockera åtkomst eller utföra korrigeringsåtgärder, t.ex. återställning av lösenord och krav på multifaktorautentisering för efterföljande inloggningar.|
|Undersök misstänkta händelser och åtgärda dem med administrativa åtgärder|Du kan undersöka riskhändelser med hjälp av information om säkerhetshändelsen. Enkla arbetsflöden är tillgängliga för att spåra undersökningar och initiera åtgärder för reparationer, som återställning av lösenord.|

Se [mer information om Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Se [stegen för att aktivera Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Resultatet av det här steget är att du har aktiverat Azure AD Identity Protection och att du använder det för att:

- Åtgärda potentiella identitetssårbarheter.
- Upptäcka möjliga försök till intrång i autentiseringsuppgifter.
- Undersöka och åtgärda fortlöpande misstänkta identitetstillbud.

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-ident-prot) för det här avsnittet.

|||
|:-------|:-----|
|![Steg 4](../media/stepnumbers/Step4.png)| [Lägga till användarkonton](identity-add-user-accounts.md) |
