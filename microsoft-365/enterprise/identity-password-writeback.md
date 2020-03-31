---
title: 'Steg 9: Enklare uppdatering av lösenord'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera tillbakaskrivning av lösenord för hybridmiljöer.
ms.openlocfilehash: 09679bd732e074ebedac09d1abfce53370610d0c
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42805435"
---
# <a name="step-9-simplify-password-updates"></a>Steg 9: Enklare uppdatering av lösenord

*Det här steget är valfritt för hybridmiljöer och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

I det här steget ska du ge användare möjlighet att återställa sina lösenord via Azure Active Directory (AD), som sedan replikeras till din lokala Windows Server Active Directory (AD). Processen kallas för tillbakaskrivning av lösenord. Med funktionen för tillbakaskrivning av lösenord behöver användarna inte uppdatera sina lösenord via den lokala Windows Server AD där användarkontona och tillhörande attribut lagras. Det här är värdefullt vid nätverksväxling och för fjärranvändare som inte har någon fjärråtkomstanslutning till det lokala nätverket.

Tillbakaskrivning av lösenord krävs för att fullt ut använda Identity Protection-funktioner, t.ex. för att begära att användare ska ändra sina lokala lösenord när en stor risk för kontointrång har upptäckts.

Mer information och anvisningar för konfiguration finns i [Azure AD SSPR med tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Uppgradera till den senaste versionen av Azure AD Connect för att säkerställa bästa möjliga upplevelse och nya funktioner när de släpps. Mer information finns i [Anpassad installation av Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>


|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pw-writeback) för detta steg.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [Enklare inloggning för användare](identity-single-sign-on.md) |

