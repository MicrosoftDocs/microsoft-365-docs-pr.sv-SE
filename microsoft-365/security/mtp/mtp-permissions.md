---
title: Hantera åtkomst till Microsoft 365 Defender-data i Microsoft 365 säkerhets Center
description: Lär dig hur du hanterar behörigheter till data i Microsoft 365 Defender
keywords: åtkomst, behörigheter, MTP, Microsoft Threat Protection, M365, säkerhet, MCAS, MDATP, Cloud App Security, Microsoft Defender Avancerat skydd, scope, omfattning, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847254"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="3ca03-104">Hantera åtkomst till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ca03-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3ca03-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3ca03-105">**Applies to:**</span></span>
- <span data-ttu-id="3ca03-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ca03-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3ca03-107">Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt Microsoft 365 Defender-funktioner och-data:</span><span class="sxs-lookup"><span data-stu-id="3ca03-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="3ca03-108">Global administratör</span><span class="sxs-lookup"><span data-stu-id="3ca03-108">Global administrator</span></span>
- <span data-ttu-id="3ca03-109">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="3ca03-109">Security administrator</span></span>
- <span data-ttu-id="3ca03-110">Säkerhets ansvarig</span><span class="sxs-lookup"><span data-stu-id="3ca03-110">Security Operator</span></span>
- <span data-ttu-id="3ca03-111">Global läsare</span><span class="sxs-lookup"><span data-stu-id="3ca03-111">Global Reader</span></span>
- <span data-ttu-id="3ca03-112">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="3ca03-112">Security Reader</span></span>

<span data-ttu-id="3ca03-113">[Visa behörigheter i säkerhets Center för Microsoft 365](https://security.microsoft.com/permissions)för att granska konton med de här rollerna.</span><span class="sxs-lookup"><span data-stu-id="3ca03-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="3ca03-114">Till gång till funktioner</span><span class="sxs-lookup"><span data-stu-id="3ca03-114">Access to functionality</span></span>
<span data-ttu-id="3ca03-115">Åtkomsten till specifika funktioner bestäms av din [Azure AD-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="3ca03-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="3ca03-116">Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användar grupp är tilldelad en ny roll.</span><span class="sxs-lookup"><span data-stu-id="3ca03-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="3ca03-117">Godkänn väntande automatiska uppgifter</span><span class="sxs-lookup"><span data-stu-id="3ca03-117">Approve pending automated tasks</span></span>
<span data-ttu-id="3ca03-118">[Automatisk undersökning och reparation](mtp-autoir-actions.md) kan utföra åtgärder på e-post, vidarebefordrings regler, filer, beständiga mekanismer och andra artefakter under undersökningar.</span><span class="sxs-lookup"><span data-stu-id="3ca03-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="3ca03-119">För att godkänna eller avvisa väntande åtgärder som kräver explicit godkännande måste du ha vissa roller tilldelade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ca03-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="3ca03-120">Mer information finns i [behörigheter för åtgärds Center](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="3ca03-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="3ca03-121">Till gång till data</span><span class="sxs-lookup"><span data-stu-id="3ca03-121">Access to data</span></span>
<span data-ttu-id="3ca03-122">Åtkomst till Microsoft 365 Defender-data kan styras med det scope som är tilldelat till användar grupper i Microsoft Defender för slut punkts rollbaserad åtkomst kontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="3ca03-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="3ca03-123">Om din åtkomst inte har beställts till en viss uppsättning enheter i Defender för slut punkt får du fullständig åtkomst till data i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3ca03-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="3ca03-124">Men när ditt konto har begränsad räckvidd visas bara data om enheterna i ditt område.</span><span class="sxs-lookup"><span data-stu-id="3ca03-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="3ca03-125">Om du till exempel tillhör bara en användar grupp med en Microsoft Defender för slut punkts roll och den användar gruppen endast har åtkomst till försäljnings enheter kan du endast se data om försäljnings enheter i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3ca03-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="3ca03-126">Läs mer om RBAC-inställningar i Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="3ca03-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="3ca03-127">Kontroller för säkerhets åtkomst för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="3ca03-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="3ca03-128">Under förhands granskningen upprätthåller inte Microsoft 365 Defender åtkomst kontroller baserade på säkerhets inställningar för Cloud App.</span><span class="sxs-lookup"><span data-stu-id="3ca03-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="3ca03-129">Åtkomst till Microsoft 365 Defender-data påverkas inte av de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="3ca03-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ca03-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3ca03-130">Related topics</span></span>

- [<span data-ttu-id="3ca03-131">Azure AD-roller</span><span class="sxs-lookup"><span data-stu-id="3ca03-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="3ca03-132">Microsoft Defender för slut punkts RBAC</span><span class="sxs-lookup"><span data-stu-id="3ca03-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="3ca03-133">Säkerhets roller för Cloud App</span><span class="sxs-lookup"><span data-stu-id="3ca03-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
