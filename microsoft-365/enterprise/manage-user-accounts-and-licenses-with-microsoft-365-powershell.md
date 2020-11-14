---
title: Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/13/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: Lär dig hur du hanterar Microsoft 365-användarkonton,-licenser och-grupper med PowerShell.
ms.openlocfilehash: ec60fcfe3c3d2c0e26cb2cca6a56741067d154c0
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073131"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="3e0b7-103">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e0b7-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="3e0b7-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3e0b7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3e0b7-105">Microsoft 365-administratörer måste hantera användar konton, licenser och grupper.</span><span class="sxs-lookup"><span data-stu-id="3e0b7-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="3e0b7-106">Även om du kan göra de flesta av dessa uppgifter i administrations centret för Microsoft 365 är det enklare att i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e0b7-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="3e0b7-107">Mer information finns i följande artiklar.</span><span class="sxs-lookup"><span data-stu-id="3e0b7-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="3e0b7-108">Användarkonton</span><span class="sxs-lookup"><span data-stu-id="3e0b7-108">User accounts</span></span>

- [<span data-ttu-id="3e0b7-109">Create user accounts</span><span class="sxs-lookup"><span data-stu-id="3e0b7-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-110">Visa användar konton</span><span class="sxs-lookup"><span data-stu-id="3e0b7-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-111">Konfigurera egenskaper för användar konton</span><span class="sxs-lookup"><span data-stu-id="3e0b7-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-112">Tilldela roller till användar konton</span><span class="sxs-lookup"><span data-stu-id="3e0b7-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-113">Ta bort och återställa användar konton</span><span class="sxs-lookup"><span data-stu-id="3e0b7-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-114">Blockera användar konton</span><span class="sxs-lookup"><span data-stu-id="3e0b7-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-115">Lösenord</span><span class="sxs-lookup"><span data-stu-id="3e0b7-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="3e0b7-116">Licenser och tjänster</span><span class="sxs-lookup"><span data-stu-id="3e0b7-116">Licenses and services</span></span>
- [<span data-ttu-id="3e0b7-117">Visa licenser och tjänster</span><span class="sxs-lookup"><span data-stu-id="3e0b7-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-118">Visa licensierade och olicensierade användare</span><span class="sxs-lookup"><span data-stu-id="3e0b7-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-119">Tilldela licenser till användarkonton</span><span class="sxs-lookup"><span data-stu-id="3e0b7-119">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-120">Visa information om kontolicenser och-tjänster</span><span class="sxs-lookup"><span data-stu-id="3e0b7-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-121">Inaktivera åtkomst till tjänster</span><span class="sxs-lookup"><span data-stu-id="3e0b7-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="3e0b7-122">Inaktivera åtkomst till Sway</span><span class="sxs-lookup"><span data-stu-id="3e0b7-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="3e0b7-123">Inaktivera åtkomst till tjänster när du tilldelar användarlicenser</span><span class="sxs-lookup"><span data-stu-id="3e0b7-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="3e0b7-124">Ta bort licenser från användarkonton</span><span class="sxs-lookup"><span data-stu-id="3e0b7-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="3e0b7-125">Grupper</span><span class="sxs-lookup"><span data-stu-id="3e0b7-125">Groups</span></span>
- [<span data-ttu-id="3e0b7-126">Hantera gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="3e0b7-126">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3e0b7-127">Hantera Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="3e0b7-127">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
