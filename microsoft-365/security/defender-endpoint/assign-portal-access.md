---
title: Tilldela användaråtkomst till Microsoft Defender Säkerhetscenter
description: Tilldela läs- och skrivskyddad åtkomst till Microsoft Defender för Endpoint-portalen.
keywords: tilldela användarroller, tilldela läs- och skrivåtkomst, tilldela skrivskyddsåtkomst, användare, användarroller, roller
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164783"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="2d062-104">Tilldela användaråtkomst till Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="2d062-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2d062-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2d062-105">**Applies to:**</span></span>
- <span data-ttu-id="2d062-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2d062-106">Azure Active Directory</span></span>
- <span data-ttu-id="2d062-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="2d062-107">Office 365</span></span>
- [<span data-ttu-id="2d062-108">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2d062-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2d062-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d062-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="2d062-110">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2d062-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2d062-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2d062-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2d062-112">Defender för Endpoint har stöd för två sätt att hantera behörigheter:</span><span class="sxs-lookup"><span data-stu-id="2d062-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="2d062-113">**Grundläggande behörighetshantering:** Ange behörighet till antingen fullständig åtkomst eller skrivskydd.</span><span class="sxs-lookup"><span data-stu-id="2d062-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="2d062-114">**Rollbaserad åtkomstkontroll (RBAC):** Ange detaljerade behörigheter genom att definiera roller, tilldela Azure AD-användargrupper till rollerna och ge användargrupper åtkomst till enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="2d062-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="2d062-115">Mer information om RBAC finns i Hantera [portalåtkomst med rollbaserad åtkomstkontroll.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="2d062-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2d062-116">Om du redan har tilldelat grundläggande behörigheter kan du när som helst byta till RBAC.</span><span class="sxs-lookup"><span data-stu-id="2d062-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="2d062-117">Tänk på följande innan du byter:</span><span class="sxs-lookup"><span data-stu-id="2d062-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="2d062-118">Användare med fullständig åtkomst (användare som har tilldelats rollen Global administratör eller Säkerhetsadministratör i Azure AD) tilldelas automatiskt standardrollen Defender för slutpunktsadministratör, som också har fullständig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="2d062-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="2d062-119">Ytterligare Azure AD-användargrupper kan tilldelas rollen Defender för slutpunktsadministratör när du har växlat till RBAC.</span><span class="sxs-lookup"><span data-stu-id="2d062-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="2d062-120">Endast användare som tilldelats rollen Defender för slutpunktsadministratör kan hantera behörigheter med RBAC.</span><span class="sxs-lookup"><span data-stu-id="2d062-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="2d062-121">Användare som har skrivskyddade åtkomst (säkerhetsläsare) förlorar åtkomsten till portalen tills de har tilldelats en roll.</span><span class="sxs-lookup"><span data-stu-id="2d062-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="2d062-122">Observera att endast Azure AD-användargrupper kan tilldelas en roll under RBAC.</span><span class="sxs-lookup"><span data-stu-id="2d062-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="2d062-123">När du har bytt till RBAC kan du inte växla tillbaka till att använda grundläggande behörighetshantering.</span><span class="sxs-lookup"><span data-stu-id="2d062-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d062-124">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2d062-124">Related topics</span></span>

- [<span data-ttu-id="2d062-125">Använda grundläggande behörigheter för åtkomst till portalen</span><span class="sxs-lookup"><span data-stu-id="2d062-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="2d062-126">Hantera portalåtkomst med RBAC</span><span class="sxs-lookup"><span data-stu-id="2d062-126">Manage portal access using RBAC</span></span>](rbac.md)
