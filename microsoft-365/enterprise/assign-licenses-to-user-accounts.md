---
title: Tilldela Microsoft 365-licenser till användar konton
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326513"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="019e6-103">Tilldela Microsoft 365-licenser till användar konton</span><span class="sxs-lookup"><span data-stu-id="019e6-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="019e6-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="019e6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="019e6-105">För den molnbaserade identitets modellen kan du tilldela Microsoft 365-licenser till användar konton när de skapas, beroende på hur du skapar dem.</span><span class="sxs-lookup"><span data-stu-id="019e6-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="019e6-106">För Hybrid identitets modellen, när AD DS-användarkonton (Active Directory Domain Services) synkroniseras för första gången, kopplas de inte automatiskt till en plats eller Microsoft 365-licens.</span><span class="sxs-lookup"><span data-stu-id="019e6-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="019e6-107">**Du måste konfigurera varje användar konto med en användar plats före eller tillsammans med tilldelningen av en licens.**</span><span class="sxs-lookup"><span data-stu-id="019e6-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="019e6-108">I båda fallen måste du tilldela en licens till användar konton så att användarna kan komma åt Microsoft 365-tjänster, till exempel e-post och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="019e6-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="019e6-109">Du kan tilldela licenser till användar konton individuellt eller automatiskt via grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="019e6-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="019e6-110">Om du vill tilldela Microsoft 365-licenser till enskilda användar konton kan du använda:</span><span class="sxs-lookup"><span data-stu-id="019e6-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="019e6-111">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="019e6-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="019e6-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="019e6-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="019e6-113">Administrations centret för Azure AD</span><span class="sxs-lookup"><span data-stu-id="019e6-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="019e6-114">Gruppbaserad licensiering</span><span class="sxs-lookup"><span data-stu-id="019e6-114">Group-based licensing</span></span>

<span data-ttu-id="019e6-115">Du kan konfigurera säkerhets grupper i Azure AD så att de automatiskt tilldelar licenser från en uppsättning prenumerationer till alla medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="019e6-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="019e6-116">Det här kallas för *gruppbaserad licensiering*.</span><span class="sxs-lookup"><span data-stu-id="019e6-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="019e6-117">Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.</span><span class="sxs-lookup"><span data-stu-id="019e6-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="019e6-118">Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="019e6-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="019e6-119">Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="019e6-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="019e6-120">Du bör inte konfigurera gruppbaserad licensiering för grupper som innehåller konton för Azure B2B.</span><span class="sxs-lookup"><span data-stu-id="019e6-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="019e6-121">Mer information finns i [gruppbaserad licensiering i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="019e6-121">For more informaion, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="019e6-122">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="019e6-122">Next steps</span></span>

<span data-ttu-id="019e6-123">Med en lämplig uppsättning användar konton som har tilldelats licenser är du nu redo att:</span><span class="sxs-lookup"><span data-stu-id="019e6-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="019e6-124">Implementera säkerhet</span><span class="sxs-lookup"><span data-stu-id="019e6-124">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="019e6-125">Distribuera klient program vara, till exempel Microsoft 365-appar</span><span class="sxs-lookup"><span data-stu-id="019e6-125">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="019e6-126">Konfigurera enhets hantering</span><span class="sxs-lookup"><span data-stu-id="019e6-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="019e6-127">Konfigurera tjänster och program</span><span class="sxs-lookup"><span data-stu-id="019e6-127">Configure services and applications</span></span>](configure-services-and-applications.md)
