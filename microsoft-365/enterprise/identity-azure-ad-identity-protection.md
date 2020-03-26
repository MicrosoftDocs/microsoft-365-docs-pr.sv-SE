---
title: 'Steg 6: skydda mot obehörig inloggning'
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
description: Förstå och konfigurera Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42812933"
---
# <a name="step-6-protect-against-credential-compromise"></a>Steg 6: skydda mot obehörig inloggning

*Det här steget är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

I det här steget får du lära dig hur du konfigurerar principer som skyddar mot obehörig inloggning, där en angripare bestämmer en användares kontonamn och lösenord för att få åtkomst till organisationens molntjänster och -data. Med Azure AD Identity Protection får du ett antal olika sätt att förhindra att en angripare kan röra sig lateralt genom dina konton och grupper, och sedan till dina mest värdefulla data.

Med Azure AD Identity Protection kan du:

|||
|:---------|:---------|
|Fastställa och åtgärda potentiella säkerhetsproblem i organisationens identiteter|I Azure AD används maskininlärning för att identifiera avvikelser och misstänkt aktivitet, till exempel inloggningar och aktiviteter efter inloggning. Med dessa data genererar Identity Protection rapporter och aviseringar som hjälper dig att utvärdera problem och vidta åtgärder.|
|Identifiera misstänkta åtgärder som är relaterade till organisationens identitet och svara på dem automatiskt|Du kan konfigurera riskfyllda principer som automatiskt reagerar på problem som upptäcks när en viss risknivå har uppnåtts. Dessa principer, förutom andra kontroller för villkorlig åtkomst i Azure Active Directory och Enterprise Mobility + Security (EMS), kan antingen automatiskt blockera åtkomst eller utföra korrigeringsåtgärder, t. ex. återställning av lösenord och krav på multifaktorautentisering för efterföljande inloggningar.|
|Undersök misstänkta händelser och åtgärda dem med administrativa åtgärder|Du kan undersöka riskhändelser med hjälp av information om säkerhetshändelsen. Enkla arbetsflöden är tillgängliga för att spåra undersökningar och initiera åtgärder för reparationer, som återställning av lösenord.|

Se [More information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) (Mer information om Azure AD Identity Protection).

Se [stegen för att aktivera Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Resultatet av det här steget är att du har aktiverat Azure AD Identity Protection och att du använder det för att:

- Åtgärda potentiella identitetssårbarheter.
- Upptäck möjliga försök till intrång i autentiseringsuppgifter.
- Undersök och åtgärda fortlöpande misstänkta identitetstillbud.

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-ident-prot) för detta steg.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [Synkronisera kataloger](identity-azure-ad-connect.md) |


