---
title: Hantera åtkomst till Microsoft Threat Protection-data i Microsoft 365-säkerhetscentret
description: Lär dig hur du hanterar behörigheter till data i Microsoft Threat Protection
keywords: åtkomst, behörigheter, MTP, Microsoft Threat Protection, M365, säkerhet, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, omfattning, omfattning, omfattning, RBAC
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
ms.openlocfilehash: f747737fc94241ca5f65ad9881715f517d5fbe3c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773845"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="80e8d-104">Hantera åtkomst till Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="80e8d-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="80e8d-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="80e8d-105">**Applies to:**</span></span>
- <span data-ttu-id="80e8d-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="80e8d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="80e8d-107">Konton som tilldelats följande Azure Active Directory-roller (AD) kan komma åt Microsoft Threat Protection-funktioner och data:</span><span class="sxs-lookup"><span data-stu-id="80e8d-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="80e8d-108">Global administratör</span><span class="sxs-lookup"><span data-stu-id="80e8d-108">Global administrator</span></span>
- <span data-ttu-id="80e8d-109">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="80e8d-109">Security administrator</span></span>
- <span data-ttu-id="80e8d-110">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="80e8d-110">Security Operator</span></span>
- <span data-ttu-id="80e8d-111">Global läsare</span><span class="sxs-lookup"><span data-stu-id="80e8d-111">Global Reader</span></span>
- <span data-ttu-id="80e8d-112">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="80e8d-112">Security Reader</span></span>

<span data-ttu-id="80e8d-113">Om du vill granska konton med dessa roller [visar du Behörigheter i Microsoft 365-säkerhetscentret](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="80e8d-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="80e8d-114">Tillgång till funktioner</span><span class="sxs-lookup"><span data-stu-id="80e8d-114">Access to functionality</span></span>
<span data-ttu-id="80e8d-115">Åtkomst till specifika funktioner bestäms av din [Azure AD-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="80e8d-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="80e8d-116">Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användargrupp tilldelas en ny roll.</span><span class="sxs-lookup"><span data-stu-id="80e8d-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="80e8d-117">Godkänna väntande automatiserade uppgifter</span><span class="sxs-lookup"><span data-stu-id="80e8d-117">Approve pending automated tasks</span></span>
<span data-ttu-id="80e8d-118">[Automatiserad undersökning och reparation](mtp-autoir-actions.md) kan vidta åtgärder för e-post, vidarebefordran regler, filer, uthållighet mekanismer och andra artefakter som finns under undersökningar.</span><span class="sxs-lookup"><span data-stu-id="80e8d-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="80e8d-119">Om du vill godkänna eller avvisa väntande åtgärder som kräver uttryckligt godkännande måste du ha vissa roller tilldelade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80e8d-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="80e8d-120">Mer information finns i [Behörigheter för Åtgärdscenter](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="80e8d-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="80e8d-121">Tillgång till data</span><span class="sxs-lookup"><span data-stu-id="80e8d-121">Access to data</span></span>
<span data-ttu-id="80e8d-122">Åtkomst till Microsoft Threat Protection-data kan styras med hjälp av det scope som tilldelats användargrupper i Microsoft Defender ATP-rollbaserad åtkomstkontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="80e8d-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="80e8d-123">Om din åtkomst inte har begränsats till en viss uppsättning enheter i Microsoft Defender ATP har du full åtkomst till data i Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="80e8d-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="80e8d-124">När ditt konto har scoped visas dock bara data om enheterna i ditt omfång.</span><span class="sxs-lookup"><span data-stu-id="80e8d-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="80e8d-125">Om du till exempel bara tillhör en användargrupp med en Microsoft Defender ATP-roll och den användargruppen endast har fått åtkomst till försäljningsenheter, visas bara data om försäljningsenheter i Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="80e8d-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="80e8d-126">Läs mer om RBAC-inställningar i Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="80e8d-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="80e8d-127">Åtkomstkontroller för Microsoft Cloud App-säkerhet</span><span class="sxs-lookup"><span data-stu-id="80e8d-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="80e8d-128">Under förhandsversionen framtvingar Microsoft Threat Protection inte åtkomstkontroller baserat på säkerhetsinställningar för Cloud App.</span><span class="sxs-lookup"><span data-stu-id="80e8d-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="80e8d-129">Åtkomst till Microsoft Threat Protection-data påverkas inte av dessa inställningar.</span><span class="sxs-lookup"><span data-stu-id="80e8d-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="80e8d-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="80e8d-130">Related topics</span></span>

- [<span data-ttu-id="80e8d-131">Azure AD-roller</span><span class="sxs-lookup"><span data-stu-id="80e8d-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="80e8d-132">Microsoft Defender ATP RBAC</span><span class="sxs-lookup"><span data-stu-id="80e8d-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="80e8d-133">Säkerhetsroller för molnappar</span><span class="sxs-lookup"><span data-stu-id="80e8d-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
