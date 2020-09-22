---
title: Hantera åtkomst till Microsoft Threat Protection data i Microsoft 365 säkerhets Center
description: Lär dig hur du hanterar behörigheter till data i Microsoft Threat Protection
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
ms.openlocfilehash: 96a8694f5cbc7c27d27acbd5ec0aabe8712c6f06
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201081"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="d78a5-104">Hantera åtkomst till skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="d78a5-104">Manage access to Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d78a5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d78a5-105">**Applies to:**</span></span>
- <span data-ttu-id="d78a5-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="d78a5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d78a5-107">Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt funktioner och data för Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="d78a5-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="d78a5-108">Global administratör</span><span class="sxs-lookup"><span data-stu-id="d78a5-108">Global administrator</span></span>
- <span data-ttu-id="d78a5-109">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="d78a5-109">Security administrator</span></span>
- <span data-ttu-id="d78a5-110">Säkerhets ansvarig</span><span class="sxs-lookup"><span data-stu-id="d78a5-110">Security Operator</span></span>
- <span data-ttu-id="d78a5-111">Global läsare</span><span class="sxs-lookup"><span data-stu-id="d78a5-111">Global Reader</span></span>
- <span data-ttu-id="d78a5-112">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="d78a5-112">Security Reader</span></span>

<span data-ttu-id="d78a5-113">[Visa behörigheter i säkerhets Center för Microsoft 365](https://security.microsoft.com/permissions)för att granska konton med de här rollerna.</span><span class="sxs-lookup"><span data-stu-id="d78a5-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="d78a5-114">Till gång till funktioner</span><span class="sxs-lookup"><span data-stu-id="d78a5-114">Access to functionality</span></span>
<span data-ttu-id="d78a5-115">Åtkomsten till specifika funktioner bestäms av din [Azure AD-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="d78a5-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="d78a5-116">Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användar grupp är tilldelad en ny roll.</span><span class="sxs-lookup"><span data-stu-id="d78a5-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="d78a5-117">Godkänn väntande automatiska uppgifter</span><span class="sxs-lookup"><span data-stu-id="d78a5-117">Approve pending automated tasks</span></span>
<span data-ttu-id="d78a5-118">[Automatisk undersökning och reparation](mtp-autoir-actions.md) kan utföra åtgärder på e-post, vidarebefordrings regler, filer, beständiga mekanismer och andra artefakter under undersökningar.</span><span class="sxs-lookup"><span data-stu-id="d78a5-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="d78a5-119">För att godkänna eller avvisa väntande åtgärder som kräver explicit godkännande måste du ha vissa roller tilldelade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d78a5-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="d78a5-120">Mer information finns i [behörigheter för åtgärds Center](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="d78a5-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="d78a5-121">Till gång till data</span><span class="sxs-lookup"><span data-stu-id="d78a5-121">Access to data</span></span>
<span data-ttu-id="d78a5-122">Åtkomst till Microsoft Threat Protection data kan styras med det scope som tilldelats till användar grupper i Microsoft Defender ATP-baserad åtkomst kontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="d78a5-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="d78a5-123">Om din åtkomst inte har beställts till en viss uppsättning enheter i Microsoft Defender ATP får du fullständig åtkomst till data i Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d78a5-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="d78a5-124">Men när ditt konto har begränsad räckvidd visas bara data om enheterna i ditt område.</span><span class="sxs-lookup"><span data-stu-id="d78a5-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="d78a5-125">Om du till exempel tillhör bara en användar grupp med en Microsoft Defender ATP-roll och den användar gruppen endast har åtkomst till försäljnings enheter kan du endast se data om försäljnings enheter i Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d78a5-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="d78a5-126">Läs mer om RBAC-inställningar i Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d78a5-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="d78a5-127">Kontroller för säkerhets åtkomst för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="d78a5-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="d78a5-128">Under förhands granskningen upprätthålls inte åtkomst kontroller baserade på säkerhets inställningar för moln programmet.</span><span class="sxs-lookup"><span data-stu-id="d78a5-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="d78a5-129">Åtkomst till Microsoft Threat Protection data påverkas inte av de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="d78a5-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d78a5-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d78a5-130">Related topics</span></span>

- [<span data-ttu-id="d78a5-131">Azure AD-roller</span><span class="sxs-lookup"><span data-stu-id="d78a5-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="d78a5-132">Microsoft Defender ATP-RBAC</span><span class="sxs-lookup"><span data-stu-id="d78a5-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="d78a5-133">Säkerhets roller för Cloud App</span><span class="sxs-lookup"><span data-stu-id="d78a5-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
