---
title: Tilldela Microsoft 365-licenser till användar konton
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beskriver hur du tilldelar Microsoft 365-licenser till användar konton, antingen individuellt eller baserat på grupp medlemskap.
ms.openlocfilehash: e132a8c2d65c401899624b9d255050385f2cb721
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417104"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="0644b-103">Tilldela Microsoft 365-licenser till användar konton</span><span class="sxs-lookup"><span data-stu-id="0644b-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="0644b-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0644b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0644b-105">För den molnbaserade identitets modellen kan du tilldela Microsoft 365-licenser till användar konton när de skapas, beroende på hur du skapar dem.</span><span class="sxs-lookup"><span data-stu-id="0644b-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="0644b-106">För Hybrid identitets modellen, när AD DS-användarkonton (Active Directory Domain Services) synkroniseras för första gången, kopplas de inte automatiskt till en Microsoft 365-licens.</span><span class="sxs-lookup"><span data-stu-id="0644b-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license.</span></span> <span data-ttu-id="0644b-107">Du måste först konfigurera varje användar konto till en användare.</span><span class="sxs-lookup"><span data-stu-id="0644b-107">You must first configure each user account with a user location.</span></span>

<span data-ttu-id="0644b-108">I båda fallen måste du tilldela en licens till användar konton så att användarna kan komma åt Microsoft 365-tjänster, till exempel e-post och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0644b-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="0644b-109">Du kan tilldela licenser till användar konton individuellt eller automatiskt via grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="0644b-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="0644b-110">Om du vill tilldela Microsoft 365-licenser till enskilda användar konton kan du använda:</span><span class="sxs-lookup"><span data-stu-id="0644b-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="0644b-111">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0644b-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="0644b-112">PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0644b-112">PowerShell for Microsoft 365</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="0644b-113">För automatisk licens tilldelning, se [gruppbaserad licensiering i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="0644b-113">For automatic license assignment, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0644b-114">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0644b-114">Next steps</span></span>

<span data-ttu-id="0644b-115">Med alla användar konton som har tilldelats licenser är du nu redo att:</span><span class="sxs-lookup"><span data-stu-id="0644b-115">With the full set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="0644b-116">Implementera säkerhet</span><span class="sxs-lookup"><span data-stu-id="0644b-116">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="0644b-117">Distribuera klient program vara, till exempel Microsoft 365-appar</span><span class="sxs-lookup"><span data-stu-id="0644b-117">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="0644b-118">Konfigurera grundläggande mobilitet och säkerhet i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0644b-118">Set up Basic Mobility and Security in Microsoft 365</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [<span data-ttu-id="0644b-119">Konfigurera tjänster och program</span><span class="sxs-lookup"><span data-stu-id="0644b-119">Configure services and applications</span></span>](configure-services-and-applications.md)
