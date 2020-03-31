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
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="9cd34-103">Steg 15: Konfigurera dynamiskt gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="9cd34-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="9cd34-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9cd34-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="9cd34-105">I det här steget kan du skapa en serie regler som automatiskt lägger till eller tar bort användarkonton som är medlemmar i en Azure AD-grupp.</span><span class="sxs-lookup"><span data-stu-id="9cd34-105">In this step, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="9cd34-106">Detta kallas för ett *dynamiskt gruppmedlemskap*.</span><span class="sxs-lookup"><span data-stu-id="9cd34-106">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="9cd34-107">Reglerna baseras på användarkontonas attribut, till exempel Avdelning eller Land.</span><span class="sxs-lookup"><span data-stu-id="9cd34-107">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="9cd34-108">Så här tillämpas reglerna:</span><span class="sxs-lookup"><span data-stu-id="9cd34-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="9cd34-109">Om ett nytt användarkonto matchar alla regler för gruppen, blir det en medlem.</span><span class="sxs-lookup"><span data-stu-id="9cd34-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="9cd34-110">Om ett användarkonto inte är medlem i gruppen, men dess attribut ändras så att det matchar alla regler för gruppen, blir det medlem i gruppen.</span><span class="sxs-lookup"><span data-stu-id="9cd34-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="9cd34-111">Om ett användarkonto inte matchar alla regler för gruppen, läggs det inte till i gruppen.</span><span class="sxs-lookup"><span data-stu-id="9cd34-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="9cd34-112">Om ett användarkonto är medlem i gruppen, men dess attribut ändras så att det inte längre matchar alla regler för gruppen, tas det bort som medlem i gruppen.</span><span class="sxs-lookup"><span data-stu-id="9cd34-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="9cd34-113">Om du vill använda dynamiskt medlemskap, måste du först bestämma vilka grupper som ska ha en gemensam uppsättning av användarkontoattribut.</span><span class="sxs-lookup"><span data-stu-id="9cd34-113">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes.</span></span> <span data-ttu-id="9cd34-114">Alla medlemmar på säljavdelningen kan t.ex. ingå i gruppen Azure AD-försäljning, baserat på användarkontoattributet Avdelning som är inställd på ”Försäljning”.</span><span class="sxs-lookup"><span data-stu-id="9cd34-114">For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="9cd34-115">I [anvisningarna finns information om hur du skapar och konfigurerar reglerna för en dynamisk Azure AD-grupp](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9cd34-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="9cd34-116">Resultatet från det här steget är:</span><span class="sxs-lookup"><span data-stu-id="9cd34-116">The results of this step are:</span></span>

- <span data-ttu-id="9cd34-117">En uppsättning Azure AD-grupper som kan konfigureras för dynamiskt medlemskap</span><span class="sxs-lookup"><span data-stu-id="9cd34-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="9cd34-118">En uppsättning regler för varje dynamisk grupp</span><span class="sxs-lookup"><span data-stu-id="9cd34-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9cd34-120">Testlabbguide: Automatisera licenser och gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="9cd34-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="9cd34-121">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-dyn-groups) för det här steget.</span><span class="sxs-lookup"><span data-stu-id="9cd34-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="9cd34-122">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9cd34-122">Next step</span></span>

[<span data-ttu-id="9cd34-123">Avslutsvillkor för identitetsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="9cd34-123">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)
