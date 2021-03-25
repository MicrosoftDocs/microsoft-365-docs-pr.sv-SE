---
title: Anpassade roller för rollbaserad åtkomstkontroll
description: Lär dig hur du hanterar anpassade roller i Säkerhetscenter för Microsoft 365
keywords: åtkomst, behörigheter, MTP, Microsoft Threat Protection, M365, säkerhet, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, omfattning, omfattning, RBAC, rollbaserad åtkomst, anpassad rollerbaserad åtkomst, rollbaserad autentisering, RBAC i MDO, roller, rollgrupper, behörighetsarv, mer begränsade behörigheter
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 17d55a434cc0499b9b24039f19ec7ed3c94310e8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068929"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a><span data-ttu-id="4fa7e-104">Anpassade roller i rollbaserad åtkomstkontroll för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4fa7e-104">Custom roles in role-based access control for Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="4fa7e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4fa7e-105">**Applies to:**</span></span>

- <span data-ttu-id="4fa7e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4fa7e-106">Microsoft 365 Defender</span></span>
 
<span data-ttu-id="4fa7e-107">Det finns två typer av roller som kan användas för att komma åt Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-107">There are two types of roles that can be used to access to Microsoft 365 Defender:</span></span>
- <span data-ttu-id="4fa7e-108">**Globala Azure Active Directory-roller (AD)**</span><span class="sxs-lookup"><span data-stu-id="4fa7e-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="4fa7e-109">**Anpassade roller**</span><span class="sxs-lookup"><span data-stu-id="4fa7e-109">**Custom roles**</span></span>

<span data-ttu-id="4fa7e-110">Åtkomst till Microsoft 365 Defender kan hanteras gemensamt med hjälp av [globala roller i Azure Active Directory (AAD)](m365d-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-110">Access to Microsoft 365 Defender can be managed collectively by using [Global roles in Azure Active Directory (AAD)](m365d-permissions.md)</span></span>

<span data-ttu-id="4fa7e-111">Om du behöver mer flexibilitet och kontroll över åtkomsten till specifika produktdata kan du även hantera Microsoft 365 Defender-åtkomst genom att skapa anpassade roller via respektive säkerhetsportal.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-111">If you need greater flexibility and control over access to specific product data, Microsoft 365 Defender access can also be managed with the creation of Custom roles through each respective security portal.</span></span>  

<span data-ttu-id="4fa7e-112">En anpassad roll som skapats via Microsoft Defender för Endpoint skulle till exempel ge åtkomst till relevanta produktdata, inklusive Slutpunktsdata i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-112">For example, a Custom role created through Microsoft Defender for Endpoint would allow access to the relevant product data, including Endpoint data within the Microsoft 365 security center.</span></span> <span data-ttu-id="4fa7e-113">På samma sätt ger en anpassad roll som skapats via Microsoft Defender för Office 365 åtkomst till relevanta produktdata, till exempel e-& och samarbetsdata i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-113">Similarly, a Custom role created through Microsoft Defender for Office 365 would allow access to the relevant product data, including Email & collaboration data within the Microsoft 365 security center.</span></span>

<span data-ttu-id="4fa7e-114">Användare med befintliga anpassade roller kan komma åt data i Microsoft 365 säkerhetscenter enligt deras befintliga behörigheter för arbetsbelastning utan ytterligare konfiguration krävs.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-114">Users with existing Custom roles may access data in the Microsoft 365 security center according to their existing workload permissions with no additional configuration required.</span></span>

## <a name="create-and-manage-custom-roles"></a><span data-ttu-id="4fa7e-115">Skapa och hantera anpassade roller</span><span class="sxs-lookup"><span data-stu-id="4fa7e-115">Create and manage custom roles</span></span>
<span data-ttu-id="4fa7e-116">Anpassade roller och behörigheter kan skapas och hanteras individuellt via följande säkerhetsportaler:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-116">Custom roles and permissions can be created and individually managed through each of the following security portals:</span></span> 

- <span data-ttu-id="4fa7e-117">Microsoft Defender för slutpunkt – [Redigera roller i Microsoft Defender för Slutpunkt](../defender-endpoint/user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-117">Microsoft Defender for Endpoint – [Edit roles in Microsoft Defender for Endpoint](../defender-endpoint/user-roles.md)</span></span>
- <span data-ttu-id="4fa7e-118">Microsoft Defender för Office 365 – [behörigheter i säkerhets- & säkerhets- och efterlevnadscenter](../defender-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-118">Microsoft Defender for Office 365 – [Permissions in the Security & Compliance Center](../defender-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)</span></span>
- <span data-ttu-id="4fa7e-119">Microsoft Cloud App Security – [Hantera administratörsåtkomst](/cloud-app-security/manage-admins)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-119">Microsoft Cloud App Security – [Manage admin access](/cloud-app-security/manage-admins)</span></span>

<span data-ttu-id="4fa7e-120">Varje anpassad roll som skapas via en enskild portal ger tillgång till data i relevant produktportal.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-120">Each custom role created through an individual portal allows access to the data of the relevant product portal.</span></span> <span data-ttu-id="4fa7e-121">Till exempel tillåter en anpassad roll som skapats via Microsoft Defender för Endpoint endast åtkomst till Defender för slutpunktsdata.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-121">For example, a custom role created through Microsoft Defender for Endpoint will only allow access to Defender for Endpoint data.</span></span>

> [!TIP]
> <span data-ttu-id="4fa7e-122">Behörigheter och roller kan också nås via Säkerhetscenter för Microsoft 365 genom att välja Behörigheter & roller i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-122">Permissions and roles can also be accessed through the Microsoft 365 security center by selecting Permissions & roles from the navigation pane.</span></span> <span data-ttu-id="4fa7e-123">Åtkomst till Microsoft Cloud App Security (MCAS) hanteras via MCAS-portalen och styr även åtkomsten till Microsoft Defender för identitet.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-123">Access to Microsoft Cloud App Security (MCAS) is managed through the MCAS portal and controls access to Microsoft Defender for Identity as well.</span></span>  <span data-ttu-id="4fa7e-124">Se [Microsoft Cloud App Security](/cloud-app-security/manage-admins)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-124">See [Microsoft Cloud App Security](/cloud-app-security/manage-admins)</span></span>

> [!NOTE]
> <span data-ttu-id="4fa7e-125">Anpassade roller som skapats i Microsoft Cloud App Security har även åtkomst till Microsoft Defender för identitetsdata.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-125">Custom roles created in Microsoft Cloud App Security have access to Microsoft Defender for Identity data as well.</span></span> <span data-ttu-id="4fa7e-126">Användare med användargruppsadministratör eller App-/instansadministratörEr för Microsoft Cloud App-säkerhetsroller kan inte komma åt data om Microsoft Cloud App Security via Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-126">Users with User group admin, or App/instance admin Microsoft Cloud App Security roles are not able to access Microsoft Cloud App Security data through the Microsoft 365 security center.</span></span>

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a><span data-ttu-id="4fa7e-127">Hantera behörigheter och roller i Säkerhetscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4fa7e-127">Manage permissions and roles in the Microsoft 365 security center</span></span>
<span data-ttu-id="4fa7e-128">Behörigheter och roller kan också hanteras i Säkerhetscenter för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-128">Permissions and roles can also be managed in the Microsoft 365 security center:</span></span>

1. <span data-ttu-id="4fa7e-129">Logga in på Säkerhetscenter för Microsoft 365 security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-129">Sign in to the Microsoft 365 security center at security.microsoft.com.</span></span>
2. <span data-ttu-id="4fa7e-130">I navigeringsfönstret väljer du Behörigheter **& roller**.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-130">In the navigation pane, select **Permissions & roles**.</span></span>
3. <span data-ttu-id="4fa7e-131">Under rubriken **Behörigheter** väljer du **Roller**.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-131">Under the **Permissions** header, select **Roles**.</span></span>

> [!NOTE]
> <span data-ttu-id="4fa7e-132">Det här gäller endast Defender för Office 365 och Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-132">This only applies to Defender for Office 365 and Defender for Endpoint.</span></span> <span data-ttu-id="4fa7e-133">Åtkomst till andra arbetsbelastningar måste göras i relevanta portaler.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-133">Access for other workloads must be done in their relevant portals.</span></span>


## <a name="required-roles-and-permissions"></a><span data-ttu-id="4fa7e-134">Roller och behörigheter som krävs</span><span class="sxs-lookup"><span data-stu-id="4fa7e-134">Required roles and permissions</span></span>
<span data-ttu-id="4fa7e-135">I följande tabell beskrivs de roller och behörigheter som krävs för att få åtkomst till varje enhetlig upplevelse i varje arbetsfördelning.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-135">The following table outlines the roles and permissions required to access each unified experience in each workload.</span></span> <span data-ttu-id="4fa7e-136">Roller som har definierats i tabellen nedan refererar till anpassade roller i enskilda portaler och är inte anslutna till globala roller i Azure AD, även om de har liknande namn.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-136">Roles defined in the table below refer to custom roles in individual portals and are not connected to global roles in Azure AD, even if similarly named.</span></span>

> [!NOTE]
> <span data-ttu-id="4fa7e-137">Hantering av incidenter kräver behörighet för hantering av alla produkter som är en del av incidenten.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-137">Incident management requires management permissions for all products that are part of the incident.</span></span>
 
| <span data-ttu-id="4fa7e-138">**En av följande roller krävs för Microsoft 365 Defender**</span><span class="sxs-lookup"><span data-stu-id="4fa7e-138">**One of the following roles are required for Microsoft 365 Defender**</span></span>  | <span data-ttu-id="4fa7e-139">**En av följande roller krävs för Defender för Slutpunkt**</span><span class="sxs-lookup"><span data-stu-id="4fa7e-139">**One of the following roles are required for Defender for Endpoint**</span></span>  | <span data-ttu-id="4fa7e-140">**En av följande roller krävs för Defender för Office 365**</span><span class="sxs-lookup"><span data-stu-id="4fa7e-140">**One of the following roles are required for Defender for Office 365**</span></span> | <span data-ttu-id="4fa7e-141">**En av följande roller krävs för Cloud App Security**</span><span class="sxs-lookup"><span data-stu-id="4fa7e-141">**One of the following roles are required for Cloud App Security**</span></span> | 
|---------|---------|---------|---------|
| <span data-ttu-id="4fa7e-142">Visa undersökningsdata:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-142">Viewing investigation data:</span></span> <ul><li><span data-ttu-id="4fa7e-143">Aviseringssida</span><span class="sxs-lookup"><span data-stu-id="4fa7e-143">Alert page</span></span></li> <li><span data-ttu-id="4fa7e-144">Kön Aviseringar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-144">Alerts queue</span></span></li> <li><span data-ttu-id="4fa7e-145">Incidenter</span><span class="sxs-lookup"><span data-stu-id="4fa7e-145">Incidents</span></span></li>  <li><span data-ttu-id="4fa7e-146">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="4fa7e-146">Incident queue</span></span></li> <li><span data-ttu-id="4fa7e-147">Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="4fa7e-147">Action center</span></span></li></ul>| <span data-ttu-id="4fa7e-148">Visa datasäkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="4fa7e-148">View data- security operations</span></span> | <ul><li><span data-ttu-id="4fa7e-149">Endast visa Hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-149">View-only Manage alerts</span></span> </li> <li><span data-ttu-id="4fa7e-150">Organisationskonfiguration</span><span class="sxs-lookup"><span data-stu-id="4fa7e-150">Organization configuration</span></span></li><li><span data-ttu-id="4fa7e-151">Granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-151">Audit logs</span></span></li> <li><span data-ttu-id="4fa7e-152">Visningsbaserade granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-152">View-only audit logs</span></span></li> <li><span data-ttu-id="4fa7e-153">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-153">Security reader</span></span></li> <li><span data-ttu-id="4fa7e-154">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-154">Security admin</span></span></li><li><span data-ttu-id="4fa7e-155">Endast visa-mottagare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-155">View-only recipients</span></span></li></ul>  | <ul><li><span data-ttu-id="4fa7e-156">Global administratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-156">Global admin</span></span></li> <li><span data-ttu-id="4fa7e-157">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-157">Security admin</span></span></li> <li><span data-ttu-id="4fa7e-158">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-158">Compliance admin</span></span></li> <li><span data-ttu-id="4fa7e-159">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-159">Security operator</span></span></li> <li><span data-ttu-id="4fa7e-160">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-160">Security reader</span></span></li> <li><span data-ttu-id="4fa7e-161">Global läsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-161">Global reader</span></span></li></ul> |
| <span data-ttu-id="4fa7e-162">Visa data om du vill ta del av dina data</span><span class="sxs-lookup"><span data-stu-id="4fa7e-162">Viewing hunting data</span></span> | <span data-ttu-id="4fa7e-163">Visa datasäkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="4fa7e-163">View data- security operations</span></span> | <ul><li><span data-ttu-id="4fa7e-164">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-164">Security reader</span></span></li> <li><span data-ttu-id="4fa7e-165">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-165">Security admin</span></span></li> <li><span data-ttu-id="4fa7e-166">Endast visa-mottagare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-166">View-only recipients</span></span></li> | <ul><li><span data-ttu-id="4fa7e-167">Global administratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-167">Global admin</span></span></li> <li><span data-ttu-id="4fa7e-168">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-168">Security admin</span></span></li> <li><span data-ttu-id="4fa7e-169">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-169">Compliance admin</span></span></li> <li><span data-ttu-id="4fa7e-170">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-170">Security operator</span></span></li> <li><span data-ttu-id="4fa7e-171">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-171">Security reader</span></span></li> <li><span data-ttu-id="4fa7e-172">Global läsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-172">Global reader</span></span></li></ul> |
| <span data-ttu-id="4fa7e-173">Hantera aviseringar och incidenter</span><span class="sxs-lookup"><span data-stu-id="4fa7e-173">Managing alerts and incidents</span></span> | <span data-ttu-id="4fa7e-174">Undersökning av aviseringar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-174">Alerts investigation</span></span> | <ul><li><span data-ttu-id="4fa7e-175">Hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-175">Manage alerts</span></span></li> <li><span data-ttu-id="4fa7e-176">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-176">Security admin</span></span></li> | <ul><li><span data-ttu-id="4fa7e-177">Global administratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-177">Global admin</span></span></li> <li><span data-ttu-id="4fa7e-178">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-178">Security admin</span></span></li> <li><span data-ttu-id="4fa7e-179">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-179">Compliance admin</span></span></li> <li><span data-ttu-id="4fa7e-180">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-180">Security operator</span></span></li> <li><span data-ttu-id="4fa7e-181">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-181">Security reader</span></span></li></ul> |
| <span data-ttu-id="4fa7e-182">Åtgärdscenteråtgärd</span><span class="sxs-lookup"><span data-stu-id="4fa7e-182">Action center remediation</span></span> | <span data-ttu-id="4fa7e-183">Aktiva åtgärdsåtgärder – säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="4fa7e-183">Active remediation actions – security operations</span></span> | <span data-ttu-id="4fa7e-184">Sök och rensa</span><span class="sxs-lookup"><span data-stu-id="4fa7e-184">Search and purge</span></span> | |
| <span data-ttu-id="4fa7e-185">Ställa in anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-185">Setting custom detections</span></span> | <span data-ttu-id="4fa7e-186">Hantera säkerhetsinställningar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-186">Manage security settings</span></span> |<ul><li><span data-ttu-id="4fa7e-187">Hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-187">Manage alerts</span></span></li> <li><span data-ttu-id="4fa7e-188">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-188">Security admin</span></span></li></ul> | <ul><li><span data-ttu-id="4fa7e-189">Global administratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-189">Global admin</span></span></li> <li><span data-ttu-id="4fa7e-190">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-190">Security admin</span></span></li> <li><span data-ttu-id="4fa7e-191">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-191">Compliance admin</span></span></li> <li><span data-ttu-id="4fa7e-192">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-192">Security operator</span></span></li> <li><span data-ttu-id="4fa7e-193">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-193">Security reader</span></span></li> <li><span data-ttu-id="4fa7e-194">Global läsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-194">Global reader</span></span></li></ul> |
| <span data-ttu-id="4fa7e-195">Analys av hot</span><span class="sxs-lookup"><span data-stu-id="4fa7e-195">Threat Analytics</span></span> | <span data-ttu-id="4fa7e-196">Information om aviseringar och incidenter:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-196">Alerts and incidents data:</span></span> <ul><li><span data-ttu-id="4fa7e-197">Visa datasäkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="4fa7e-197">View data- security operations</span></span></li></ul><span data-ttu-id="4fa7e-198">Minskningar av TVM:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-198">TVM mitigations:</span></span><ul><li><span data-ttu-id="4fa7e-199">Visa data – hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="4fa7e-199">View data - Threat and vulnerability management</span></span></li></ul> | <span data-ttu-id="4fa7e-200">Information om aviseringar och incidenter:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-200">Alerts and incidents data:</span></span><ul> <li><span data-ttu-id="4fa7e-201">Endast visa Hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-201">View-only Manage alerts</span></span></li> <li><span data-ttu-id="4fa7e-202">Hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-202">Manage alerts</span></span></li> <li><span data-ttu-id="4fa7e-203">Organisationskonfiguration</span><span class="sxs-lookup"><span data-stu-id="4fa7e-203">Organization configuration</span></span></li><li><span data-ttu-id="4fa7e-204">Granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-204">Audit logs</span></span></li> <li><span data-ttu-id="4fa7e-205">Visningsbaserade granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="4fa7e-205">View-only audit logs</span></span></li><li><span data-ttu-id="4fa7e-206">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-206">Security reader</span></span></li> <li><span data-ttu-id="4fa7e-207">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-207">Security admin</span></span></li><li><span data-ttu-id="4fa7e-208">Endast visa-mottagare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-208">View-only recipients</span></span></li> </ul> <span data-ttu-id="4fa7e-209">Förhindrade e-postförsök:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-209">Prevented email attempts:</span></span> <ul><li><span data-ttu-id="4fa7e-210">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-210">Security reader</span></span></li> <li><span data-ttu-id="4fa7e-211">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-211">Security admin</span></span></li><li><span data-ttu-id="4fa7e-212">Endast visa-mottagare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-212">View-only recipients</span></span></li> | <span data-ttu-id="4fa7e-213">Inte tillgängligt för MCAS- eller MDI-användare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-213">Not available for MCAS or MDI users</span></span> |

<span data-ttu-id="4fa7e-214">Om du till exempel vill visa letar efter data från Microsoft Defender för Endpoint krävs behörigheten Visa datasäkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="4fa7e-214">For example, to view hunting data from Microsoft Defender for Endpoint, View data security operations permissions are required.</span></span>  

<span data-ttu-id="4fa7e-215">För att kunna visa data på visning från Microsoft Defender för Office 365 behöver användarna på samma sätt en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="4fa7e-215">Similarly, to view hunting data from Microsoft Defender for Office 365, users would require one of the following roles:</span></span>  

- <span data-ttu-id="4fa7e-216">Visa datasäkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="4fa7e-216">View data security operations</span></span>
- <span data-ttu-id="4fa7e-217">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-217">Security reader</span></span>
- <span data-ttu-id="4fa7e-218">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4fa7e-218">Security admin</span></span>
- <span data-ttu-id="4fa7e-219">Endast visa-mottagare</span><span class="sxs-lookup"><span data-stu-id="4fa7e-219">View-only recipients</span></span>

## <a name="related-topics"></a><span data-ttu-id="4fa7e-220">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4fa7e-220">Related topics</span></span>
- [<span data-ttu-id="4fa7e-221">Hantera åtkomst till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4fa7e-221">Manage access to Microsoft 365 Defender</span></span>](m365d-permissions.md)
- [<span data-ttu-id="4fa7e-222">Hantera administratörsåtkomst för MCAS</span><span class="sxs-lookup"><span data-stu-id="4fa7e-222">Manage admin access for MCAS</span></span>](/cloud-app-security/manage-admins)