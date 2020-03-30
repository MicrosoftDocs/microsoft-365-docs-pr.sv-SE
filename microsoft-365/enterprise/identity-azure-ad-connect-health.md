---
title: 'Steg 8: Övervaka synkroniseringshälsa'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera Azure AD Connect Health.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42811823"
---
# <a name="step-8-monitor-synchronization-health"></a>Steg 8: Övervaka synkroniseringshälsa

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

I det här steget installerar du en Azure AD Connect Health-agent på var och en av dina lokala identitetsservrar för att övervaka din identitetsinfrastruktur och de synkroniseringstjänster som tillhandahålls av Azure AD Connect. Övervakningsinformationen visas i en Azure AD Connect Health-portal, där du kan se varningar, prestandaövervakning, användningsanalys och annan information.

![Komponenter i Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

Det viktiga beslutet för hur du ska använda Azure AD Connect Health, baseras på hur du använder Azure AD Connect:

- Om du använder **hanterad autentisering** börjar du med [Använda Azure AD Connect Health med synkronisering](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) för att förstå och konfigurera Azure AD Connect Health.
- Om du bara synkroniserar namnen på de konton och grupper som använder **federerad autentisering** med Active Directory Federation Services (AD FS), börjar du med [Använda Azure AD Connect Health med AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) för att förstå och konfigurera Azure AD Connect Health.

När du har slutfört det här steget har du:

- Azure AD Connect Health-agenten installerad på dina lokala identitetsproviderservrar.
- Azure AD Connect Health-portalen visar aktuell status för lokal infrastruktur och synkronisering med Azure AD-klientorganisationen för dina Office 365- och EMS-prenumerationer.

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-sync-health) för detta steg.


## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [Enklare uppdatering av lösenord](identity-password-writeback.md) |

