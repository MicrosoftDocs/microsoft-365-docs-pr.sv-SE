---
title: Tilldela Microsoft 365 licenser till användarkonton
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
description: Här beskrivs hur du tilldelar Microsoft 365 licenser till användarkonton, antingen individuellt eller baserat på gruppmedlemskap.
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051538"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="d38f9-103">Tilldela Microsoft 365 licenser till användarkonton</span><span class="sxs-lookup"><span data-stu-id="d38f9-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="d38f9-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d38f9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d38f9-105">För den molnbaserade identitetsmodellen kan du tilldela licenser Microsoft 365 till användarkonton när de skapas, beroende på hur du skapar dem.</span><span class="sxs-lookup"><span data-stu-id="d38f9-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="d38f9-106">När AD DS-användarkonton (Active Directory Domain Services) synkroniseras för första gången för hybrididentitetsmodellen tilldelas de inte automatiskt en plats eller en Microsoft 365 licens.</span><span class="sxs-lookup"><span data-stu-id="d38f9-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="d38f9-107">**Du måste konfigurera varje användarkonto med en användarplats innan eller tillsammans med en licens.**</span><span class="sxs-lookup"><span data-stu-id="d38f9-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="d38f9-108">I båda fallen måste du tilldela en licens till användarkonton så att användarna kan komma åt Microsoft 365 tjänster, till exempel e-post och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d38f9-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="d38f9-109">Du kan tilldela licenser till användarkonton antingen individuellt eller automatiskt genom gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="d38f9-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="d38f9-110">Om du Microsoft 365 licenser till enskilda användarkonton kan du använda:</span><span class="sxs-lookup"><span data-stu-id="d38f9-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="d38f9-111">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d38f9-111">The Microsoft 365 admin center</span></span>](../admin/manage/assign-licenses-to-users.md)
- [<span data-ttu-id="d38f9-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d38f9-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="d38f9-113">Administrationscentret för Azure AD</span><span class="sxs-lookup"><span data-stu-id="d38f9-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="d38f9-114">Gruppbaserad licensiering</span><span class="sxs-lookup"><span data-stu-id="d38f9-114">Group-based licensing</span></span>

<span data-ttu-id="d38f9-115">Du kan konfigurera säkerhetsgrupper i Azure AD för att automatiskt tilldela licenser från en uppsättning prenumerationer till alla medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="d38f9-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="d38f9-116">Det här kallas för *gruppbaserad licensiering*.</span><span class="sxs-lookup"><span data-stu-id="d38f9-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="d38f9-117">Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.</span><span class="sxs-lookup"><span data-stu-id="d38f9-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="d38f9-118">Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="d38f9-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="d38f9-119">Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="d38f9-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="d38f9-120">Du bör inte konfigurera gruppbaserad licensiering för grupper som innehåller konton för Azure B2B.</span><span class="sxs-lookup"><span data-stu-id="d38f9-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="d38f9-121">Mer information finns i [gruppbaserad licensiering i Azure AD.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="d38f9-121">For more informaion, see [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d38f9-122">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d38f9-122">Next steps</span></span>

<span data-ttu-id="d38f9-123">Med rätt uppsättning användarkonton som har tilldelats licenser är du nu redo att:</span><span class="sxs-lookup"><span data-stu-id="d38f9-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="d38f9-124">Implementera säkerhet</span><span class="sxs-lookup"><span data-stu-id="d38f9-124">Implement security</span></span>](../security/defender-365-security/security-roadmap.md)
- [<span data-ttu-id="d38f9-125">Distribuera klientprogramvara, till exempel Microsoft 365 program</span><span class="sxs-lookup"><span data-stu-id="d38f9-125">Deploy client software, such as Microsoft 365 Apps</span></span>](/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="d38f9-126">Konfigurera enhetshantering</span><span class="sxs-lookup"><span data-stu-id="d38f9-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="d38f9-127">Konfigurera tjänster och program</span><span class="sxs-lookup"><span data-stu-id="d38f9-127">Configure services and applications</span></span>](configure-services-and-applications.md)