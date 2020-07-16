---
title: Få tillgång till administratörsportalen
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146277"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="77dca-103">Få tillgång till administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="77dca-103">Access the admin portal</span></span>

<span data-ttu-id="77dca-104">Din gateway till Tjänsten Microsoft Managed Desktop är Microsoft [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="77dca-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="77dca-105">Mer information om hur du använder och anpassar din Azure-portalupplevelse i allmänhet finns i [Azure-portaldokumentationen](https://docs.microsoft.com/azure/azure-portal/).</span><span class="sxs-lookup"><span data-stu-id="77dca-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> 

<span data-ttu-id="77dca-106">Ditt administrativa konto behöver särskilda behörigheter för att komma åt Microsoft Managed Desktop Admin-portalen.</span><span class="sxs-lookup"><span data-stu-id="77dca-106">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="77dca-107">Du kan hantera administratörsåtkomst till dessa funktioner i organisationen med hjälp av Rollbaserad åtkomstkontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="77dca-107">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="77dca-108">Mer information om Azure Active Directory-roller finns [i Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="77dca-108">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="77dca-109">Tilldela administratörsanvändarkontona någon av följande roller för att säkerställa åtkomst:</span><span class="sxs-lookup"><span data-stu-id="77dca-109">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="77dca-110">Azure AD-roll</span><span class="sxs-lookup"><span data-stu-id="77dca-110">Azure AD role</span></span>  |<span data-ttu-id="77dca-111">Behörigheter för Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="77dca-111">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="77dca-112">Global administratör</span><span class="sxs-lookup"><span data-stu-id="77dca-112">Global Administrator</span></span>     | <span data-ttu-id="77dca-113">Administratörer med den här rollen har **läs- och skrivbehörighet** till alla funktioner i Microsoft Managed Desktop Admin-portalen.</span><span class="sxs-lookup"><span data-stu-id="77dca-113">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="77dca-114">Global läsare</span><span class="sxs-lookup"><span data-stu-id="77dca-114">Global Reader</span></span>     | <span data-ttu-id="77dca-115">Administratörer med den här rollen har **skrivskyddade behörigheter** för alla funktioner i Microsoft Managed Desktop Admin-portalen.</span><span class="sxs-lookup"><span data-stu-id="77dca-115">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="77dca-116">Administratör för Intune-tjänsten</span><span class="sxs-lookup"><span data-stu-id="77dca-116">Intune Service Administrator</span></span>     |  <span data-ttu-id="77dca-117">Administratörer med den här rollen har **läs- och skrivbehörighet** till alla funktioner i Microsoft Managed Desktop Admin-portalen.</span><span class="sxs-lookup"><span data-stu-id="77dca-117">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="77dca-118">Administratör för servicesupport</span><span class="sxs-lookup"><span data-stu-id="77dca-118">Service Support Administrator</span></span>     | <span data-ttu-id="77dca-119">Administratörer med den här rollen har **läs- och skrivbehörighet** till alla funktioner i Microsoft Managed Desktop Admin-portalen.</span><span class="sxs-lookup"><span data-stu-id="77dca-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="77dca-120">Endast rollen Global administratör har de behörigheter som krävs för att *registrera* din organisation på Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="77dca-120">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="77dca-121">Tänk på att Azure Active Directory-roller ger användarkonton behörighet för en mängd olika Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="77dca-121">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="77dca-122">När du har slutfört registreringen hos Microsoft Managed Desktop bör du alltid använda rollen med de *lägsta* behörigheter som krävs för att utföra dina andra uppgifter.</span><span class="sxs-lookup"><span data-stu-id="77dca-122">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="77dca-123">Tilldela roller till administratörer</span><span class="sxs-lookup"><span data-stu-id="77dca-123">Assigning roles to administrators</span></span>

<span data-ttu-id="77dca-124">Om du behöver hjälp med att tilldela Azure Active Directory-roller läser du [Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="77dca-124">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
