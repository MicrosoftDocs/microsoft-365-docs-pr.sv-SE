---
title: 'Steg 15: Konfigurera dynamiskt gruppmedlemskap'
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
description: Förstå och konfigurera automatiska gruppmedlemskap baserat på kontoattribut.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42809676"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>Steg 15: Konfigurera dynamiskt gruppmedlemskap

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

I det här steget kan du skapa en serie regler som automatiskt lägger till eller tar bort användarkonton som är medlemmar i en Azure AD-grupp. Detta kallas för ett *dynamiskt gruppmedlemskap*. Reglerna baseras på användarkontonas attribut, till exempel Avdelning eller Land.

Så här tillämpas reglerna:

- Om ett nytt användarkonto matchar alla regler för gruppen, blir det en medlem.
- Om ett användarkonto inte är medlem i gruppen, men dess attribut ändras så att det matchar alla regler för gruppen, blir det medlem i gruppen.
- Om ett användarkonto inte matchar alla regler för gruppen, läggs det inte till i gruppen.
- Om ett användarkonto är medlem i gruppen, men dess attribut ändras så att det inte längre matchar alla regler för gruppen, tas det bort som medlem i gruppen.

Om du vill använda dynamiskt medlemskap, måste du först bestämma vilka grupper som ska ha en gemensam uppsättning av användarkontoattribut. Alla medlemmar på säljavdelningen kan t.ex. ingå i gruppen Azure AD-försäljning, baserat på användarkontoattributet Avdelning som är inställd på ”Försäljning”.

I [anvisningarna finns information om hur du skapar och konfigurerar reglerna för en dynamisk Azure AD-grupp](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

Resultatet från det här steget är:

- En uppsättning Azure AD-grupper som kan konfigureras för dynamiskt medlemskap
- En uppsättning regler för varje dynamisk grupp

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Automatisera licenser och gruppmedlemskap](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-dyn-groups) för det här steget.

## <a name="next-step"></a>Nästa steg

[Avslutsvillkor för identitetsinfrastruktur](identity-exit-criteria.md)
