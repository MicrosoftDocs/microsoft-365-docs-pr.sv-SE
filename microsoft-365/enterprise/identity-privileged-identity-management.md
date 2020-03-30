---
title: 'Steg 3: Konfigurera globala administratörer på begäran'
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
description: Förstå och konfigurera Azure AD Privileged Identity Management.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42807493"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>Steg 3: Konfigurera globala administratörer på begäran

*Det här steget är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

I det här steget konfigurerar du Azure AD Privileged Identity Management (PIM) för att minska tiden då dina globala administratörskonton är sårbara för angrepp från obehöriga användare. I PIM kan den globala administratörsrollen bara tilldelas vid behov.  

I stället för att dina globala administratörskonton ska vara en permanent administratör, blir de berättigade administratörer. Rollen som global administratör är inaktiv tills någon behöver den. Därefter slutför du en aktiveringsprocess för att lägga till den globala administratörsrollen på det globala administratörskontot under en angiven tidsperiod. När tiden går ut tar PIM bort rollen som global administratör från det globala administratörskontot.

PIM finns i Azure Active Directory Premium P2, som ingår i Microsoft 365 Enterprise E5. Alternativt kan du köpa enskilda Azure Active Directory Premium P2-licenser för dina globala administratörskonton.

Mer information om hur du aktiverar Azure PIM för Azure AD-klientorganisationen och globala administratörskonton finns i [anvisningar för att konfigurera PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Om du vill utveckla en heltäckande översikt för att skydda privilegierad åtkomst mot cyberangripare, kan du läsa [Skydda privilegierad åtkomst för hybrid- och molndistributioner i Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pim) för detta steg.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [Enklare återställning av lösenord](identity-password-reset.md) |

