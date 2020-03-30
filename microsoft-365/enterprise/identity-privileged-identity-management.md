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
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="cb336-103">Steg 3: Konfigurera globala administratörer på begäran</span><span class="sxs-lookup"><span data-stu-id="cb336-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="cb336-104">*Det här steget är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="cb336-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="cb336-105">I det här steget konfigurerar du Azure AD Privileged Identity Management (PIM) för att minska tiden då dina globala administratörskonton är sårbara för angrepp från obehöriga användare.</span><span class="sxs-lookup"><span data-stu-id="cb336-105">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="cb336-106">I PIM kan den globala administratörsrollen bara tilldelas vid behov.</span><span class="sxs-lookup"><span data-stu-id="cb336-106">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="cb336-107">I stället för att dina globala administratörskonton ska vara en permanent administratör, blir de berättigade administratörer.</span><span class="sxs-lookup"><span data-stu-id="cb336-107">Instead of your global administrator accounts being a permanent admin, they become eligible admins.</span></span> <span data-ttu-id="cb336-108">Rollen som global administratör är inaktiv tills någon behöver den.</span><span class="sxs-lookup"><span data-stu-id="cb336-108">The global administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="cb336-109">Därefter slutför du en aktiveringsprocess för att lägga till den globala administratörsrollen på det globala administratörskontot under en angiven tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="cb336-109">You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time.</span></span> <span data-ttu-id="cb336-110">När tiden går ut tar PIM bort rollen som global administratör från det globala administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="cb336-110">When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="cb336-111">PIM finns i Azure Active Directory Premium P2, som ingår i Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="cb336-111">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5.</span></span> <span data-ttu-id="cb336-112">Alternativt kan du köpa enskilda Azure Active Directory Premium P2-licenser för dina globala administratörskonton.</span><span class="sxs-lookup"><span data-stu-id="cb336-112">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="cb336-113">Mer information om hur du aktiverar Azure PIM för Azure AD-klientorganisationen och globala administratörskonton finns i [anvisningar för att konfigurera PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="cb336-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="cb336-114">Om du vill utveckla en heltäckande översikt för att skydda privilegierad åtkomst mot cyberangripare, kan du läsa [Skydda privilegierad åtkomst för hybrid- och molndistributioner i Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="cb336-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="cb336-115">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pim) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="cb336-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="cb336-116">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="cb336-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="cb336-117">Enklare återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="cb336-117">Simplify password resets</span></span>](identity-password-reset.md) |

