---
title: 'Steg 2: Skydda dina lösenord'
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
description: Se till att skapa starka och lätthanterliga lösenord i hela organisationen.
ms.openlocfilehash: 6e5c2567ee2027be2a84121fdad10ba873ec1c43
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214656"
---
# <a name="step-2-secure-your-passwords"></a>Steg 2: Skydda dina lösenord

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Förhindra svaga lösenord

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*

Alla dina användare bör följa [Microsofts lösenordsvägledning](https://www.microsoft.com/research/publication/password-guidance) när de skapar lösenord till sina användarkonton.

Hindra användarna från att skapa svaga lösenord genom att använda Azure AD-lösenordsskydd, som tillämpar både en global lista med blockerade lösenord och en valfri lista med blockerade lösenord som du väljer. Du kan till exempel välja ord som gäller specifikt för din organisation, som:

- Varumärken
- Produktnamn
- Platser (till exempel företagets huvudkontor)
- Företagsspecifik, intern terminologi
- Förkortningar med särskild betydelse för företaget

Du kan förbjuda svaga lösenord [i molnet](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) och för din [lokala AD DS (Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-password-prot) för det här avsnittet.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Enklare återställning av lösenord

*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*

I det här avsnittet aktiverar du självbetjäning för återställning av lösenord (SSPR) så att användarna kan återställa eller låsa upp sina lösenord eller konton. Du kan få varningar om missbruk eller felanvändning genom att använda den detaljerade rapporteringen som spårar när användare har åtkomst till systemet, tillsammans med meddelanden. Du måste aktivera tillbakaskrivning av lösenord innan du kan distribuera återställning av lösenord.

Se [anvisningarna för att distribuera återställning av lösenord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: återställa lösenord](password-reset-m365-ent-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pw-reset) för det här avsnittet.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Enklare inloggning för användare

*Det här är valfritt för hybridversioner och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

I det här avsnittet konfigurerar du enkel inloggning med Azure Active Directory (Azure AD Seamless SSO), som fungerar med synkronisering av lösenordshash och direktautentisering, så att användare kan logga in på tjänster som använder Azure AD-användarkonton utan att behöva ange lösenord, och i många fall användarnamn. Det gör att användarna lättare kommer åt molnbaserade program, till exempel Office 365, utan att behöva några ytterligare lokala komponenter som identitetsservrar.

Du konfigurerar Azure AD Seamless SSO med Azure AD Connect-verktyget.

Se [anvisningarna för att konfigurera Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: enkel inloggning med Azure AD Seamless](single-sign-on-m365-ent-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-sso) för det här avsnittet.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-sign-in-page"></a>Anpassa inloggningssidan

*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

I det här avsnittet kan du hjälpa användarna att identifiera din organisations inloggningssida genom att lägga till företagets namn, logotyp och andra bekanta element. 

Med Microsoft 365 Enterprise kan du anpassa utseendet på sidorna för inloggning och åtkomstpaneler så att de innehåller företagets logotyp, färgschema och anpassad användarinformation. 

Mer information finns i [Lägga till din företagsanpassning på inloggningssidan i Microsoft 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Instruktioner för konfigurering finns i [Lägga till företagsanpassning på din inloggningssida och åtkomstpanelsidorna](https://aka.ms/aadpaddbranding).

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-custom-sign-in) för det här avsnittet.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 3](../media/stepnumbers/Step3.png)| [Skydda och hantera användarinloggningar](identity-secure-user-sign-ins.md) |
