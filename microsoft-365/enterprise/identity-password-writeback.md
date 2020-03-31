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
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="477d1-103">Steg 9: Enklare uppdatering av lösenord</span><span class="sxs-lookup"><span data-stu-id="477d1-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="477d1-104">*Det här steget är valfritt för hybridmiljöer och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="477d1-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="477d1-105">I det här steget ska du ge användare möjlighet att återställa sina lösenord via Azure Active Directory (AD), som sedan replikeras till din lokala Windows Server Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="477d1-105">In this step, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD).</span></span> <span data-ttu-id="477d1-106">Processen kallas för tillbakaskrivning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="477d1-106">This process is known as password writeback.</span></span> <span data-ttu-id="477d1-107">Med funktionen för tillbakaskrivning av lösenord behöver användarna inte uppdatera sina lösenord via den lokala Windows Server AD där användarkontona och tillhörande attribut lagras.</span><span class="sxs-lookup"><span data-stu-id="477d1-107">With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored.</span></span> <span data-ttu-id="477d1-108">Det här är värdefullt vid nätverksväxling och för fjärranvändare som inte har någon fjärråtkomstanslutning till det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="477d1-108">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="477d1-109">Tillbakaskrivning av lösenord krävs för att fullt ut använda Identity Protection-funktioner, t.ex. för att begära att användare ska ändra sina lokala lösenord när en stor risk för kontointrång har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="477d1-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="477d1-110">Mer information och anvisningar för konfiguration finns i [Azure AD SSPR med tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="477d1-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="477d1-111">Uppgradera till den senaste versionen av Azure AD Connect för att säkerställa bästa möjliga upplevelse och nya funktioner när de släpps.</span><span class="sxs-lookup"><span data-stu-id="477d1-111">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="477d1-112">Mer information finns i [Anpassad installation av Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="477d1-112">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>


|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="477d1-114">Testlabbguide: Tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="477d1-114">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="477d1-115">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pw-writeback) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="477d1-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="477d1-116">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="477d1-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="477d1-117">Enklare inloggning för användare</span><span class="sxs-lookup"><span data-stu-id="477d1-117">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

