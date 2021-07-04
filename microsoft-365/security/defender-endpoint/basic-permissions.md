---
title: Använda grundläggande behörigheter för att komma Microsoft Defender Säkerhetscenter
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
ms.openlocfilehash: e7c208998e436245c53b90905858b7cf7ebe91d6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290201"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="72ee2-104">Använda grundläggande behörigheter för att komma åt portalen</span><span class="sxs-lookup"><span data-stu-id="72ee2-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72ee2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="72ee2-105">**Applies to:**</span></span>
- <span data-ttu-id="72ee2-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="72ee2-106">Azure Active Directory</span></span>
- [<span data-ttu-id="72ee2-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="72ee2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="72ee2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72ee2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="72ee2-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="72ee2-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="72ee2-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="72ee2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="72ee2-111">Använd grundläggande behörighetshantering i anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="72ee2-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="72ee2-112">Du kan använda någon av följande lösningar:</span><span class="sxs-lookup"><span data-stu-id="72ee2-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="72ee2-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="72ee2-113">Azure PowerShell</span></span>
- <span data-ttu-id="72ee2-114">Azure Portal</span><span class="sxs-lookup"><span data-stu-id="72ee2-114">Azure portal</span></span>

<span data-ttu-id="72ee2-115">Om du vill ha detaljerad kontroll över behörigheter [växlar du till rollbaserad åtkomstkontroll.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="72ee2-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="72ee2-116">Tilldela användaråtkomst via Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="72ee2-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="72ee2-117">Du kan tilldela användare med någon av följande behörighetsnivåer:</span><span class="sxs-lookup"><span data-stu-id="72ee2-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="72ee2-118">Fullständig åtkomst (läsa och skriva)</span><span class="sxs-lookup"><span data-stu-id="72ee2-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="72ee2-119">Skrivskyddade åtkomst</span><span class="sxs-lookup"><span data-stu-id="72ee2-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="72ee2-120">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="72ee2-120">Before you begin</span></span>

- <span data-ttu-id="72ee2-121">Installera Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72ee2-121">Install Azure PowerShell.</span></span> <span data-ttu-id="72ee2-122">Mer information finns i Installera [och konfigurera Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span><span class="sxs-lookup"><span data-stu-id="72ee2-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="72ee2-123">Du måste köra PowerShell-cmdletarna i en upphöjd kommandorad.</span><span class="sxs-lookup"><span data-stu-id="72ee2-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="72ee2-124">Anslut på Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="72ee2-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="72ee2-125">Mer information finns i [Anslut-MsolService.](/powershell/module/msonline/connect-msolservice)</span><span class="sxs-lookup"><span data-stu-id="72ee2-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice).</span></span>

<span data-ttu-id="72ee2-126">**Fullständig åtkomst**</span><span class="sxs-lookup"><span data-stu-id="72ee2-126">**Full access**</span></span> <br>
<span data-ttu-id="72ee2-127">Användare med fullständig åtkomst kan logga in, visa all systeminformation och lösa aviseringar, skicka filer för djupanalys och ladda ned onboarding-paketet.</span><span class="sxs-lookup"><span data-stu-id="72ee2-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="72ee2-128">Om du vill tilldela fullständiga åtkomstbehörigheter måste du lägga till användarna i de inbyggda rollerna "säkerhetsadministratör" eller "global administratör".</span><span class="sxs-lookup"><span data-stu-id="72ee2-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="72ee2-129">**Skrivskyddade åtkomst**</span><span class="sxs-lookup"><span data-stu-id="72ee2-129">**Read-only access**</span></span> <br>
<span data-ttu-id="72ee2-130">Användare med skrivskydd kan logga in, visa alla aviseringar och relaterad information.</span><span class="sxs-lookup"><span data-stu-id="72ee2-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="72ee2-131">De kommer inte att kunna ändra aviseringstillstånd, skicka filer för djupanalys eller utföra åtgärder som ändrar tillstånd.</span><span class="sxs-lookup"><span data-stu-id="72ee2-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="72ee2-132">Om du vill tilldela skrivskyddad åtkomstbehörighet måste användarna läggs till i den inbyggda rollen "Säkerhetsläsare" i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72ee2-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="72ee2-133">Använd följande steg för att tilldela säkerhetsroller:</span><span class="sxs-lookup"><span data-stu-id="72ee2-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="72ee2-134">För **läs- och skrivbehörighet** tilldelar du användare till säkerhetsadministratörsrollen med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="72ee2-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="72ee2-135">För **skrivskyddad** åtkomst tilldelar du användare till rollen för säkerhetsläsare med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="72ee2-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="72ee2-136">Mer information finns i Lägga [till eller ta bort gruppmedlemmar med hjälp av Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="72ee2-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="72ee2-137">Tilldela användaråtkomst via Azure Portal</span><span class="sxs-lookup"><span data-stu-id="72ee2-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="72ee2-138">Mer information finns i Tilldela [administratörs- och icke-administratörsroller till användare med Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="72ee2-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="72ee2-139">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="72ee2-139">Related topic</span></span>

- [<span data-ttu-id="72ee2-140">Hantera portalåtkomst med RBAC</span><span class="sxs-lookup"><span data-stu-id="72ee2-140">Manage portal access using RBAC</span></span>](rbac.md)
