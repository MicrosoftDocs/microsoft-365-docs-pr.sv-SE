---
title: Hantera åtkomst till Microsoft 365 Defender-data i Säkerhetscenter för Microsoft 365
description: Lär dig hur du hanterar behörigheter till data i Microsoft 365 Defender
keywords: åtkomst, behörigheter, Microsoft 365 Defender, M365, säkerhet, MCAS, Cloud App Security, Microsoft Defender för slutpunkt, omfattning, omfattning, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 52e4e9fc8c73d1adca0c24c5bebb50f9dcf7ac6f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935635"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="49cfb-104">Hantera åtkomst till Microsoft 365 Defender med globala roller i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="49cfb-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="49cfb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="49cfb-105">**Applies to:**</span></span>
- <span data-ttu-id="49cfb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49cfb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="49cfb-107">Det finns två sätt att hantera åtkomst till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49cfb-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="49cfb-108">**Globala Azure Active Directory-roller (AD)**</span><span class="sxs-lookup"><span data-stu-id="49cfb-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="49cfb-109">**Anpassad rollåtkomst**</span><span class="sxs-lookup"><span data-stu-id="49cfb-109">**Custom role access**</span></span>

<span data-ttu-id="49cfb-110">Konton som tilldelats följande **globala Azure Active Directory-roller (AD)** har åtkomst till funktioner och data i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="49cfb-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="49cfb-111">Global administratör</span><span class="sxs-lookup"><span data-stu-id="49cfb-111">Global administrator</span></span>
- <span data-ttu-id="49cfb-112">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="49cfb-112">Security administrator</span></span>
- <span data-ttu-id="49cfb-113">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="49cfb-113">Security Operator</span></span>
- <span data-ttu-id="49cfb-114">Global läsare</span><span class="sxs-lookup"><span data-stu-id="49cfb-114">Global Reader</span></span>
- <span data-ttu-id="49cfb-115">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="49cfb-115">Security Reader</span></span>

<span data-ttu-id="49cfb-116">Om du vill granska konton med de här [rollerna visar du Behörigheter i Säkerhetscenter för Microsoft 365.](https://security.microsoft.com/permissions)</span><span class="sxs-lookup"><span data-stu-id="49cfb-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="49cfb-117">**Anpassad rollåtkomst** är en ny funktion i Microsoft 365 Defender och gör att du kan hantera åtkomst till specifika data, uppgifter och funktioner i Microsoft Defender 365.</span><span class="sxs-lookup"><span data-stu-id="49cfb-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="49cfb-118">Anpassade roller ger mer kontroll än globala Azure AD-roller, vilket ger användarna bara den åtkomst de behöver med de minst tillåtande rollerna som krävs.</span><span class="sxs-lookup"><span data-stu-id="49cfb-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="49cfb-119">Anpassade roller kan skapas utöver globala Azure AD-roller.</span><span class="sxs-lookup"><span data-stu-id="49cfb-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="49cfb-120">[Läs mer om anpassade roller.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="49cfb-120">[Learn more about custom roles](custom-roles.md).</span></span>

> <span data-ttu-id="49cfb-121">! [OBS] Den här artikeln gäller endast för hantering av globala Azure Active Directory-roller.</span><span class="sxs-lookup"><span data-stu-id="49cfb-121">![NOTE] This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="49cfb-122">Mer information om hur du använder en anpassad rollbaserad åtkomstkontroll finns i [Anpassade roller för rollbaserad åtkomstkontroll](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="49cfb-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="49cfb-123">Åtkomst till funktioner</span><span class="sxs-lookup"><span data-stu-id="49cfb-123">Access to functionality</span></span>
<span data-ttu-id="49cfb-124">Åtkomst till specifika funktioner bestäms av din [Azure AD-roll.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="49cfb-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="49cfb-125">Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användargrupp tilldelas en ny roll.</span><span class="sxs-lookup"><span data-stu-id="49cfb-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="49cfb-126">Godkänna väntande automatiserade uppgifter</span><span class="sxs-lookup"><span data-stu-id="49cfb-126">Approve pending automated tasks</span></span>
<span data-ttu-id="49cfb-127">[Automatisk undersökning och åtgärder kan](m365d-autoir-actions.md) vidta åtgärder för e-postmeddelanden, regler för vidarebefordran, filer, beständighetsmetoder och andra artefakter som påträffades under undersökningar.</span><span class="sxs-lookup"><span data-stu-id="49cfb-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="49cfb-128">Om du vill godkänna eller avvisa väntande åtgärder som kräver uttryckligt godkännande måste du ha vissa roller tilldelade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49cfb-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="49cfb-129">Mer information finns i Behörigheter [för Åtgärdscenter](m365d-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="49cfb-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="49cfb-130">Tillgång till data</span><span class="sxs-lookup"><span data-stu-id="49cfb-130">Access to data</span></span>
<span data-ttu-id="49cfb-131">Åtkomst till Microsoft 365 Defender-data kan kontrolleras med hjälp av omfattningen som tilldelats användargrupper i Microsoft Defender för rollbaserad åtkomstkontroll för slutpunkt (RBAC).</span><span class="sxs-lookup"><span data-stu-id="49cfb-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="49cfb-132">Om din åtkomst inte har begränsad till en viss uppsättning enheter i Defender för Slutpunkt har du fullständig åtkomst till data i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="49cfb-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="49cfb-133">Men när kontot har begränsad omfattning kan du bara se data om enheterna i din omfattning.</span><span class="sxs-lookup"><span data-stu-id="49cfb-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="49cfb-134">Om du till exempel bara tillhör en användargrupp med rollen Microsoft Defender för slutpunkt och den användargruppen endast har åtkomst till säljenheter, visas endast data om säljenheter i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="49cfb-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="49cfb-135">Läs mer om RBAC-inställningar i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="49cfb-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="49cfb-136">Säkerhetsåtkomstkontroller för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="49cfb-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="49cfb-137">Under förhandsversionen tillämpar Microsoft 365 Defender inte åtkomstkontroller baserat på säkerhetsinställningar för molnappen.</span><span class="sxs-lookup"><span data-stu-id="49cfb-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="49cfb-138">Åtkomst till data i Microsoft 365 Defender påverkas inte av de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="49cfb-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="49cfb-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="49cfb-139">Related topics</span></span>
- [<span data-ttu-id="49cfb-140">Anpassade roller i rollbaserad åtkomstkontroll för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49cfb-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="49cfb-141">Azure AD-roller</span><span class="sxs-lookup"><span data-stu-id="49cfb-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="49cfb-142">Microsoft Defender för slutpunkt RBAC</span><span class="sxs-lookup"><span data-stu-id="49cfb-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="49cfb-143">Säkerhetsroller i molnappen</span><span class="sxs-lookup"><span data-stu-id="49cfb-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)