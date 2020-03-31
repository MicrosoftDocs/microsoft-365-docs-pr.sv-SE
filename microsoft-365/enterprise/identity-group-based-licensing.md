---
title: 'Steg 12: Konfigurera automatisk licensiering'
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
description: Förstå och konfigurera gruppbaserad licensiering för Azure AD-grupper.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42808587"
---
# <a name="step-12-set-up-automatic-licensing"></a>Steg 12: Konfigurera automatisk licensiering

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

I det här steget konfigurerar du att säkerhetsgrupper i Azure AD automatiskt tilldelar licenser från en uppsättning prenumerationer till alla medlemmar i gruppen. Det här kallas för *gruppbaserad licensiering*. Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.

För Microsoft 365 Enterprise konfigurerar du att Azure AD-säkerhetsgrupperna ska tilldela båda dessa licenser:

- Office 365 Enterprise E3 eller E5
- Enterprise Mobility + Security (EMS) E3 eller E5

Utgå från de grupper du identifierade i steg 2 och leta efter grupper som innehåller en lista med konton där alla användare i gruppen måste ha båda licenserna för Office 365 och EMS. Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar. Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.

>[!Note]
>Du bör inte konfigurera *gruppbaserad licensiering* för grupper som innehåller konton för Azure B2B.
>

Se mer information om [Grunderna i gruppbaserad licensiering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Se [stegen för att konfigurera gruppbaserad licensiering för en Azure-säkerhetsgrupp](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Resultatet från det här steget är:

- Du har identifierat vilka säkerhetsgrupper som är lämpliga för gruppbaserad licensiering.
- Du har konfigurerat dessa grupper för gruppbaserad licensiering.

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Automatisera licenser och gruppmedlemskap](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-group-license) för det här steget.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [Övervaka klientorganisationen och inloggningsaktivitet](identity-azure-ad-access-usage-reporting.md) |

