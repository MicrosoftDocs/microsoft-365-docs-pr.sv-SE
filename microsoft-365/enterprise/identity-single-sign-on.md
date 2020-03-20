---
title: 'Steg 10: förenkla inloggning för användare'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Mer information om hur du förstår och konfigurerar enkel inloggning med Azure AD.
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42810030"
---
# <a name="step-10-simplify-user-sign-in"></a>Steg 10: förenkla inloggning för användare

*Det här steget är valfritt för hybridversioner och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

I det här steget konfigurerar du enkel inloggning med Azure Active Directory (Azure AD Seamless SSO) så att användare kan logga in på tjänster som använder Azure AD-användarkonton utan att behöva ange lösenord, och i många fall användarnamn. Det gör att användarna lättare kommer åt molnbaserade program, till exempel Office 365, utan att behöva några ytterligare lokala komponenter som identitetsservrar.

Du konfigurerar Azure AD Seamless SSO med Azure AD Connect-verktyget.

Se [anvisningarna för att konfigurera Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Testlabbsguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbsguide: enkel inloggning med Azure AD Seamless](single-sign-on-m365-ent-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-sso) för detta steg.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [Anpassa inloggningssidan för Office 365](identity-customize-office-365-sign-in.md) |

