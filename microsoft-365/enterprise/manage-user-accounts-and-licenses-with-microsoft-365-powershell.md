---
title: Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
description: I den här artikeln lär du dig hur du hanterar Microsoft 365-användarkonton,-licenser och-grupper med PowerShell.
ms.openlocfilehash: a262cbb62cd457e3a22550af2f773551cf67bb43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696718"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="f5734-103">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5734-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="f5734-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f5734-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f5734-105">En av de viktigaste uppgifterna hos alla Microsoft 365-administratörer är att hantera användar konton, licenser och grupper.</span><span class="sxs-lookup"><span data-stu-id="f5734-105">One of the primary tasks of any Microsoft 365 administrator is managing user accounts, licenses, and groups.</span></span> <span data-ttu-id="f5734-106">Även om du kan utföra de flesta aspekterna av dessa uppgifter i administrations centret för Microsoft 365, är det mycket snabbare och enklare med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5734-106">Although you can accomplish most aspects of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier with PowerShell.</span></span> 

<span data-ttu-id="f5734-107">Mer information finns i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f5734-107">For more information, see these topics.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="f5734-108">Användar konton</span><span class="sxs-lookup"><span data-stu-id="f5734-108">User accounts</span></span>

- [<span data-ttu-id="f5734-109">Create user accounts</span><span class="sxs-lookup"><span data-stu-id="f5734-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-110">Visa användar konton</span><span class="sxs-lookup"><span data-stu-id="f5734-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-111">Konfigurera egenskaper för användar konton</span><span class="sxs-lookup"><span data-stu-id="f5734-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-112">Tilldela roller till användar konton</span><span class="sxs-lookup"><span data-stu-id="f5734-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-113">Ta bort och återställa användar konton</span><span class="sxs-lookup"><span data-stu-id="f5734-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-114">Blockera användar konton</span><span class="sxs-lookup"><span data-stu-id="f5734-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="f5734-115">Licenser och tjänster</span><span class="sxs-lookup"><span data-stu-id="f5734-115">Licenses and services</span></span>
- [<span data-ttu-id="f5734-116">Visa licenser och tjänster</span><span class="sxs-lookup"><span data-stu-id="f5734-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-117">Visa licensierade och olicensierade användare</span><span class="sxs-lookup"><span data-stu-id="f5734-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-118">Tilldela licenser till användar konton</span><span class="sxs-lookup"><span data-stu-id="f5734-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-119">Visa information om konto licenser och tjänster</span><span class="sxs-lookup"><span data-stu-id="f5734-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-120">Inaktivera åtkomst till tjänster</span><span class="sxs-lookup"><span data-stu-id="f5734-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="f5734-121">Inaktivera åtkomst till Sway</span><span class="sxs-lookup"><span data-stu-id="f5734-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="f5734-122">Inaktivera åtkomst till tjänster när du tilldelar användar licenser</span><span class="sxs-lookup"><span data-stu-id="f5734-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="f5734-123">Ta bort licenser från användar konton</span><span class="sxs-lookup"><span data-stu-id="f5734-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="f5734-124">Grupper</span><span class="sxs-lookup"><span data-stu-id="f5734-124">Groups</span></span>
- [<span data-ttu-id="f5734-125">Underhåll grupp medlemskap</span><span class="sxs-lookup"><span data-stu-id="f5734-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f5734-126">Hantera Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="f5734-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)

