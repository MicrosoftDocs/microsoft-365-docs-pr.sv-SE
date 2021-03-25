---
title: Använda grundläggande behörigheter för att komma åt Microsoft Defender Säkerhetscenter
description: Lär dig hur du använder grundläggande behörigheter för att komma åt Microsoft Defender för Endpoint-portalen.
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
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163677"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="f733f-104">Använda grundläggande behörigheter för åtkomst till portalen</span><span class="sxs-lookup"><span data-stu-id="f733f-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f733f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f733f-105">**Applies to:**</span></span>
- <span data-ttu-id="f733f-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f733f-106">Azure Active Directory</span></span>
- [<span data-ttu-id="f733f-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f733f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f733f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f733f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f733f-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f733f-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f733f-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f733f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="f733f-111">Använd grundläggande behörighetshantering i anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="f733f-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="f733f-112">Du kan använda någon av följande lösningar:</span><span class="sxs-lookup"><span data-stu-id="f733f-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="f733f-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f733f-113">Azure PowerShell</span></span>
- <span data-ttu-id="f733f-114">Azure Portal</span><span class="sxs-lookup"><span data-stu-id="f733f-114">Azure portal</span></span>

<span data-ttu-id="f733f-115">Om du vill ha detaljerad kontroll över behörigheter [växlar du till rollbaserad åtkomstkontroll.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="f733f-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="f733f-116">Tilldela användaråtkomst med hjälp av Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f733f-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="f733f-117">Du kan tilldela användare med någon av följande behörighetsnivåer:</span><span class="sxs-lookup"><span data-stu-id="f733f-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="f733f-118">Fullständig åtkomst (läsa och skriva)</span><span class="sxs-lookup"><span data-stu-id="f733f-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="f733f-119">Skrivskyddade åtkomst</span><span class="sxs-lookup"><span data-stu-id="f733f-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="f733f-120">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="f733f-120">Before you begin</span></span>

- <span data-ttu-id="f733f-121">Installera Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f733f-121">Install Azure PowerShell.</span></span> <span data-ttu-id="f733f-122">Mer information finns i Installera [och konfigurera Azure PowerShell.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="f733f-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="f733f-123">Du måste köra PowerShell-cmdletarna i en upphöjd kommandorad.</span><span class="sxs-lookup"><span data-stu-id="f733f-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="f733f-124">Anslut till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f733f-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="f733f-125">Mer information finns i [Connect-MsolService.](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="f733f-125">For more information, see [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="f733f-126">**Fullständig åtkomst**</span><span class="sxs-lookup"><span data-stu-id="f733f-126">**Full access**</span></span> <br>
<span data-ttu-id="f733f-127">Användare med fullständig åtkomst kan logga in, visa all systeminformation och lösa aviseringar, skicka filer för djupanalys och ladda ned onboarding-paketet.</span><span class="sxs-lookup"><span data-stu-id="f733f-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="f733f-128">Om du vill tilldela fullständiga åtkomstbehörigheter måste du lägga till användarna i de inbyggda rollerna "säkerhetsadministratör" eller "global administratör".</span><span class="sxs-lookup"><span data-stu-id="f733f-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="f733f-129">**Skrivskyddade åtkomst**</span><span class="sxs-lookup"><span data-stu-id="f733f-129">**Read-only access**</span></span> <br>
<span data-ttu-id="f733f-130">Användare med skrivskydd kan logga in, visa alla aviseringar och relaterad information.</span><span class="sxs-lookup"><span data-stu-id="f733f-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="f733f-131">De kommer inte att kunna ändra aviseringstillstånd, skicka filer för djupanalys eller utföra åtgärder som ändrar tillstånd.</span><span class="sxs-lookup"><span data-stu-id="f733f-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="f733f-132">Om du vill tilldela skrivskyddad åtkomstbehörighet måste användarna läggs till i den inbyggda rollen "Säkerhetsläsare" i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f733f-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="f733f-133">Använd följande steg för att tilldela säkerhetsroller:</span><span class="sxs-lookup"><span data-stu-id="f733f-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="f733f-134">För **läs- och skrivbehörighet** tilldelar du användare till säkerhetsadministratörsrollen med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f733f-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="f733f-135">För **skrivskyddad** åtkomst tilldelar du användare till rollen för säkerhetsläsare med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f733f-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="f733f-136">Mer information finns i Lägga [till eller ta bort gruppmedlemmar med Hjälp av Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="f733f-136">For more information, see [Add or remove group members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="f733f-137">Tilldela användaråtkomst via Azure Portal</span><span class="sxs-lookup"><span data-stu-id="f733f-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="f733f-138">Mer information finns i Tilldela [användare med Azure Active Directory administratörsroller och icke-administratörsroller.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="f733f-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="f733f-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f733f-139">Related topic</span></span>

- [<span data-ttu-id="f733f-140">Hantera portalåtkomst med RBAC</span><span class="sxs-lookup"><span data-stu-id="f733f-140">Manage portal access using RBAC</span></span>](rbac.md)
