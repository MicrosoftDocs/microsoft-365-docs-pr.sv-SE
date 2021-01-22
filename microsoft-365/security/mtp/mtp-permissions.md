---
title: Hantera åtkomst till Microsoft 365 Defender-data i Säkerhetscenter för Microsoft 365
description: Lär dig hur du hanterar behörigheter till data i Microsoft 365 Defender
keywords: åtkomst, behörigheter, MTP, Microsoft Threat Protection, M365, säkerhet, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, omfattning, omfattning, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930144"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="6bf3a-104">Hantera åtkomst till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bf3a-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6bf3a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6bf3a-105">**Applies to:**</span></span>
- <span data-ttu-id="6bf3a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bf3a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6bf3a-107">Konton som tilldelats följande Azure Active Directory-roller (AD) har åtkomst till funktioner och data i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="6bf3a-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="6bf3a-108">Global administratör</span><span class="sxs-lookup"><span data-stu-id="6bf3a-108">Global administrator</span></span>
- <span data-ttu-id="6bf3a-109">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="6bf3a-109">Security administrator</span></span>
- <span data-ttu-id="6bf3a-110">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="6bf3a-110">Security Operator</span></span>
- <span data-ttu-id="6bf3a-111">Global läsare</span><span class="sxs-lookup"><span data-stu-id="6bf3a-111">Global Reader</span></span>
- <span data-ttu-id="6bf3a-112">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="6bf3a-112">Security Reader</span></span>

<span data-ttu-id="6bf3a-113">Om du vill granska konton med dessa [roller kan du visa behörigheter i Säkerhetscenter för Microsoft 365.](https://security.microsoft.com/permissions)</span><span class="sxs-lookup"><span data-stu-id="6bf3a-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="6bf3a-114">Åtkomst till funktioner</span><span class="sxs-lookup"><span data-stu-id="6bf3a-114">Access to functionality</span></span>
<span data-ttu-id="6bf3a-115">Åtkomst till specifika funktioner bestäms av din [Azure AD-roll.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="6bf3a-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="6bf3a-116">Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användargrupp tilldelas en ny roll.</span><span class="sxs-lookup"><span data-stu-id="6bf3a-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="6bf3a-117">Godkänna väntande automatiserade uppgifter</span><span class="sxs-lookup"><span data-stu-id="6bf3a-117">Approve pending automated tasks</span></span>
<span data-ttu-id="6bf3a-118">[Automatiserad undersökning och åtgärd kan](mtp-autoir-actions.md) vidta åtgärder på e-postmeddelanden, regler för vidarebefordran, filer, mekanismer för beständighet och andra artefakter som påträffas under undersökningar.</span><span class="sxs-lookup"><span data-stu-id="6bf3a-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="6bf3a-119">Om du vill godkänna eller avvisa väntande åtgärder som kräver uttryckligt godkännande måste du ha vissa roller tilldelade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bf3a-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="6bf3a-120">Mer information finns i behörigheter [för Åtgärdscenter.](mtp-action-center.md#required-permissions-for-action-center-tasks)</span><span class="sxs-lookup"><span data-stu-id="6bf3a-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="6bf3a-121">Åtkomst till data</span><span class="sxs-lookup"><span data-stu-id="6bf3a-121">Access to data</span></span>
<span data-ttu-id="6bf3a-122">Åtkomst till data i Microsoft 365 Defender kan kontrolleras med hjälp av omfattningen som tilldelats användargrupper i Microsoft Defender för slutpunktsrollbaserad åtkomstkontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="6bf3a-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="6bf3a-123">Om åtkomsten inte har begränsad till en viss uppsättning enheter i Defender för Slutpunkten har du fullständig åtkomst till data i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6bf3a-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="6bf3a-124">Men när ditt konto har begränsad omfattning visas bara data om enheterna i din omfattning.</span><span class="sxs-lookup"><span data-stu-id="6bf3a-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="6bf3a-125">Om du till exempel bara tillhör en användargrupp med rollen Microsoft Defender för slutpunkt och den användargruppen endast har åtkomst till försäljningsenheter visas bara data om säljenheter i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6bf3a-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="6bf3a-126">Läs mer om RBAC-inställningar i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6bf3a-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="6bf3a-127">Åtkomstkontroller för Microsoft Cloud App-säkerhet</span><span class="sxs-lookup"><span data-stu-id="6bf3a-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="6bf3a-128">Under förhandsgranskningen tillämpar Microsoft 365 Defender inte åtkomstkontroller baserat på inställningar för molnappsäkerhet.</span><span class="sxs-lookup"><span data-stu-id="6bf3a-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="6bf3a-129">Åtkomst till data i Microsoft 365 Defender påverkas inte av de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="6bf3a-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6bf3a-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6bf3a-130">Related topics</span></span>

- [<span data-ttu-id="6bf3a-131">Azure AD-roller</span><span class="sxs-lookup"><span data-stu-id="6bf3a-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="6bf3a-132">Microsoft Defender för slutpunkt RBAC</span><span class="sxs-lookup"><span data-stu-id="6bf3a-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="6bf3a-133">Roller för molnappsäkerhet</span><span class="sxs-lookup"><span data-stu-id="6bf3a-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
