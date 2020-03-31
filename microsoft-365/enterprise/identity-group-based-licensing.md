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
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="c8561-103">Steg 12: Konfigurera automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="c8561-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="c8561-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c8561-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="c8561-105">I det här steget konfigurerar du att säkerhetsgrupper i Azure AD automatiskt tilldelar licenser från en uppsättning prenumerationer till alla medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="c8561-105">In this step, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="c8561-106">Det här kallas för *gruppbaserad licensiering*.</span><span class="sxs-lookup"><span data-stu-id="c8561-106">This is known as *group-based licensing*.</span></span> <span data-ttu-id="c8561-107">Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.</span><span class="sxs-lookup"><span data-stu-id="c8561-107">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="c8561-108">För Microsoft 365 Enterprise konfigurerar du att Azure AD-säkerhetsgrupperna ska tilldela båda dessa licenser:</span><span class="sxs-lookup"><span data-stu-id="c8561-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="c8561-109">Office 365 Enterprise E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="c8561-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="c8561-110">Enterprise Mobility + Security (EMS) E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="c8561-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="c8561-111">Utgå från de grupper du identifierade i steg 2 och leta efter grupper som innehåller en lista med konton där alla användare i gruppen måste ha båda licenserna för Office 365 och EMS.</span><span class="sxs-lookup"><span data-stu-id="c8561-111">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses.</span></span> <span data-ttu-id="c8561-112">Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="c8561-112">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="c8561-113">Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="c8561-113">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="c8561-114">Du bör inte konfigurera *gruppbaserad licensiering* för grupper som innehåller konton för Azure B2B.</span><span class="sxs-lookup"><span data-stu-id="c8561-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="c8561-115">Se mer information om [Grunderna i gruppbaserad licensiering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c8561-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="c8561-116">Se [stegen för att konfigurera gruppbaserad licensiering för en Azure-säkerhetsgrupp](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c8561-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="c8561-117">Resultatet från det här steget är:</span><span class="sxs-lookup"><span data-stu-id="c8561-117">The results of this step are:</span></span>

- <span data-ttu-id="c8561-118">Du har identifierat vilka säkerhetsgrupper som är lämpliga för gruppbaserad licensiering.</span><span class="sxs-lookup"><span data-stu-id="c8561-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="c8561-119">Du har konfigurerat dessa grupper för gruppbaserad licensiering.</span><span class="sxs-lookup"><span data-stu-id="c8561-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c8561-121">Testlabbguide: Automatisera licenser och gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="c8561-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="c8561-122">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-group-license) för det här steget.</span><span class="sxs-lookup"><span data-stu-id="c8561-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c8561-123">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c8561-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="c8561-124">Övervaka klientorganisationen och inloggningsaktivitet</span><span class="sxs-lookup"><span data-stu-id="c8561-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

