---
title: Lista alla åtgärdsaktiviteter
description: Returnerar information om alla åtgärder.
keywords: apis, remediation, remediation api, get, remediation tasks, all remediation,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 60f80e78a5f5c7da44a218c30f4b0173d4ecc829
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845144"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="1d805-104">Lista alla åtgärdsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="1d805-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d805-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1d805-105">**Applies to:**</span></span>

- [<span data-ttu-id="1d805-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d805-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d805-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d805-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1d805-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1d805-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d805-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1d805-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1d805-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="1d805-110">API description</span></span>

<span data-ttu-id="1d805-111">Returnerar information om alla åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1d805-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="1d805-112">[Läs mer om åtgärder](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="1d805-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="1d805-113">**URL:** HÄMTA: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="1d805-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="1d805-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="1d805-114">Permissions</span></span>

<span data-ttu-id="1d805-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="1d805-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d805-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1d805-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="1d805-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="1d805-117">Permission type</span></span> | <span data-ttu-id="1d805-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="1d805-118">Permission</span></span> | <span data-ttu-id="1d805-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="1d805-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1d805-120">Program</span><span class="sxs-lookup"><span data-stu-id="1d805-120">Application</span></span> | <span data-ttu-id="1d805-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="1d805-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="1d805-122">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="1d805-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="1d805-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="1d805-123">Delegated (work or school account)</span></span> | <span data-ttu-id="1d805-124">RemediationTask.Read</span><span class="sxs-lookup"><span data-stu-id="1d805-124">RemediationTask.Read</span></span> | <span data-ttu-id="1d805-125">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="1d805-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="1d805-126">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="1d805-126">Properties</span></span>

<span data-ttu-id="1d805-127">Egenskap (id)</span><span class="sxs-lookup"><span data-stu-id="1d805-127">Property (id)</span></span> | <span data-ttu-id="1d805-128">Datatyp</span><span class="sxs-lookup"><span data-stu-id="1d805-128">Data type</span></span> | <span data-ttu-id="1d805-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1d805-129">Description</span></span> | <span data-ttu-id="1d805-130">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="1d805-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="1d805-131">kategori</span><span class="sxs-lookup"><span data-stu-id="1d805-131">category</span></span> | <span data-ttu-id="1d805-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-132">String</span></span> | <span data-ttu-id="1d805-133">Kategori för åtgärdsaktiviteten (konfiguration av programvara/säkerhet)</span><span class="sxs-lookup"><span data-stu-id="1d805-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="1d805-134">Programvara</span><span class="sxs-lookup"><span data-stu-id="1d805-134">Software</span></span>
<span data-ttu-id="1d805-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="1d805-135">completerEmail</span></span> | <span data-ttu-id="1d805-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-136">String</span></span> | <span data-ttu-id="1d805-137">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras e-postadress</span><span class="sxs-lookup"><span data-stu-id="1d805-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="1d805-138">null</span><span class="sxs-lookup"><span data-stu-id="1d805-138">null</span></span>
<span data-ttu-id="1d805-139">completerId</span><span class="sxs-lookup"><span data-stu-id="1d805-139">completerId</span></span> | <span data-ttu-id="1d805-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-140">String</span></span> | <span data-ttu-id="1d805-141">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras objekt-ID</span><span class="sxs-lookup"><span data-stu-id="1d805-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="1d805-142">null</span><span class="sxs-lookup"><span data-stu-id="1d805-142">null</span></span>
<span data-ttu-id="1d805-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="1d805-143">completionMethod</span></span> | <span data-ttu-id="1d805-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-144">String</span></span> | <span data-ttu-id="1d805-145">En åtgärdsaktivitet kan slutföras "automatiskt" (om alla enheter är korrigerade) eller "manuellt" av en person som väljer "markera som slutförd"</span><span class="sxs-lookup"><span data-stu-id="1d805-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="1d805-146">Automatisk</span><span class="sxs-lookup"><span data-stu-id="1d805-146">Automatic</span></span>
<span data-ttu-id="1d805-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="1d805-147">createdOn</span></span> | <span data-ttu-id="1d805-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d805-148">DateTime</span></span> | <span data-ttu-id="1d805-149">Tidpunkten då den här åtgärdsaktiviteten skapades</span><span class="sxs-lookup"><span data-stu-id="1d805-149">Time this remediation activity was created</span></span> | <span data-ttu-id="1d805-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="1d805-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="1d805-151">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1d805-151">description</span></span> | <span data-ttu-id="1d805-152">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-152">String</span></span> | <span data-ttu-id="1d805-153">Beskrivning av den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="1d805-153">Description of this remediation activity</span></span> | <span data-ttu-id="1d805-154">Uppdatera Microsoft Silverlight till en senare version för att minimera kända säkerhetsproblem som påverkar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="1d805-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="1d805-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="1d805-155">dueOn</span></span> | <span data-ttu-id="1d805-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d805-156">DateTime</span></span> | <span data-ttu-id="1d805-157">Förfallodatum som skapare uppsättningen för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="1d805-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="1d805-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="1d805-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="1d805-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="1d805-159">fixedDevices</span></span> | <span data-ttu-id="1d805-160">.</span><span class="sxs-lookup"><span data-stu-id="1d805-160">.</span></span> | <span data-ttu-id="1d805-161">Antalet enheter som har åtgärdats</span><span class="sxs-lookup"><span data-stu-id="1d805-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="1d805-162">2</span><span class="sxs-lookup"><span data-stu-id="1d805-162">2</span></span>
<span data-ttu-id="1d805-163">id</span><span class="sxs-lookup"><span data-stu-id="1d805-163">id</span></span> | <span data-ttu-id="1d805-164">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-164">String</span></span> | <span data-ttu-id="1d805-165">ID för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="1d805-165">ID of this remediation activity</span></span> | <span data-ttu-id="1d805-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="1d805-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="1d805-167">nameId</span><span class="sxs-lookup"><span data-stu-id="1d805-167">nameId</span></span> | <span data-ttu-id="1d805-168">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-168">String</span></span> | <span data-ttu-id="1d805-169">Relaterade produktnamn</span><span class="sxs-lookup"><span data-stu-id="1d805-169">Related product name</span></span> | <span data-ttu-id="1d805-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1d805-170">Microsoft Silverlight</span></span>
<span data-ttu-id="1d805-171">prioritet</span><span class="sxs-lookup"><span data-stu-id="1d805-171">priority</span></span> | <span data-ttu-id="1d805-172">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-172">String</span></span> | <span data-ttu-id="1d805-173">Prioritet för skaparuppsättningen för den här åtgärdsaktiviteten (Hög\Medel\Låg)</span><span class="sxs-lookup"><span data-stu-id="1d805-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="1d805-174">Högsta</span><span class="sxs-lookup"><span data-stu-id="1d805-174">High</span></span>
<span data-ttu-id="1d805-175">productId</span><span class="sxs-lookup"><span data-stu-id="1d805-175">productId</span></span> | <span data-ttu-id="1d805-176">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-176">String</span></span> | <span data-ttu-id="1d805-177">Relaterade produkt-ID</span><span class="sxs-lookup"><span data-stu-id="1d805-177">Related product ID</span></span> | <span data-ttu-id="1d805-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="1d805-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="1d805-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="1d805-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="1d805-180">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-180">String</span></span> | <span data-ttu-id="1d805-181">Några konfigurationsändringar kunde endast begäras för enheter utan påverkan från användare.</span><span class="sxs-lookup"><span data-stu-id="1d805-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="1d805-182">Det här värdet anger valet mellan "alla exponerade enheter" eller "endast enheter utan påverkan från användare".</span><span class="sxs-lookup"><span data-stu-id="1d805-182">This value indicates the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="1d805-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="1d805-183">AllExposedAssets</span></span>
<span data-ttu-id="1d805-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="1d805-184">rbacGroupNames</span></span> | <span data-ttu-id="1d805-185">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-185">String</span></span> | <span data-ttu-id="1d805-186">Gruppnamn för relaterade enheter</span><span class="sxs-lookup"><span data-stu-id="1d805-186">Related device group names</span></span> | <span data-ttu-id="1d805-187">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="1d805-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="1d805-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="1d805-188">recommendedProgram</span></span> | <span data-ttu-id="1d805-189">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-189">String</span></span> | <span data-ttu-id="1d805-190">Rekommenderat program att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="1d805-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="1d805-191">null</span><span class="sxs-lookup"><span data-stu-id="1d805-191">null</span></span>
<span data-ttu-id="1d805-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="1d805-192">recommendedVendor</span></span> | <span data-ttu-id="1d805-193">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-193">String</span></span> | <span data-ttu-id="1d805-194">Rekommenderad leverantör att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="1d805-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="1d805-195">null</span><span class="sxs-lookup"><span data-stu-id="1d805-195">null</span></span>
<span data-ttu-id="1d805-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="1d805-196">recommendedVersion</span></span> | <span data-ttu-id="1d805-197">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-197">String</span></span> | <span data-ttu-id="1d805-198">Rekommenderad version att uppdatera/uppgradera till</span><span class="sxs-lookup"><span data-stu-id="1d805-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="1d805-199">null</span><span class="sxs-lookup"><span data-stu-id="1d805-199">null</span></span>
<span data-ttu-id="1d805-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="1d805-200">relatedComponent</span></span> | <span data-ttu-id="1d805-201">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-201">String</span></span> | <span data-ttu-id="1d805-202">Relaterad komponent i den här åtgärdsaktiviteten (som liknar den relaterade komponenten för en säkerhetsrekommendationer)</span><span class="sxs-lookup"><span data-stu-id="1d805-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="1d805-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1d805-203">Microsoft Silverlight</span></span>
<span data-ttu-id="1d805-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="1d805-204">requesterEmail</span></span> | <span data-ttu-id="1d805-205">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-205">String</span></span> | <span data-ttu-id="1d805-206">E-postadress skapad</span><span class="sxs-lookup"><span data-stu-id="1d805-206">Creator email address</span></span> | <span data-ttu-id="1d805-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d805-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="1d805-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="1d805-208">requesterId</span></span> | <span data-ttu-id="1d805-209">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-209">String</span></span> | <span data-ttu-id="1d805-210">Creator-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="1d805-210">Creator object id</span></span> | <span data-ttu-id="1d805-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="1d805-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="1d805-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="1d805-212">requesterNotes</span></span> | <span data-ttu-id="1d805-213">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-213">String</span></span> | <span data-ttu-id="1d805-214">Anteckningarna (fri text) som skaparen har lagt till för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="1d805-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="1d805-215">null</span><span class="sxs-lookup"><span data-stu-id="1d805-215">null</span></span>
<span data-ttu-id="1d805-216">scid</span><span class="sxs-lookup"><span data-stu-id="1d805-216">scid</span></span> | <span data-ttu-id="1d805-217">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-217">String</span></span> | <span data-ttu-id="1d805-218">SCID för relaterad säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="1d805-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="1d805-219">null</span><span class="sxs-lookup"><span data-stu-id="1d805-219">null</span></span>
<span data-ttu-id="1d805-220">status</span><span class="sxs-lookup"><span data-stu-id="1d805-220">status</span></span> | <span data-ttu-id="1d805-221">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-221">String</span></span> | <span data-ttu-id="1d805-222">Status för åtgärdsaktivitet (Aktiv/slutförd)</span><span class="sxs-lookup"><span data-stu-id="1d805-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="1d805-223">Aktiv</span><span class="sxs-lookup"><span data-stu-id="1d805-223">Active</span></span>
<span data-ttu-id="1d805-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="1d805-224">statusLastModifiedOn</span></span> | <span data-ttu-id="1d805-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d805-225">DateTime</span></span> | <span data-ttu-id="1d805-226">Datum när statusfältet uppdaterades</span><span class="sxs-lookup"><span data-stu-id="1d805-226">Date when the status field was updated</span></span> | <span data-ttu-id="1d805-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="1d805-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="1d805-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="1d805-228">targetDevices</span></span> | <span data-ttu-id="1d805-229">Long</span><span class="sxs-lookup"><span data-stu-id="1d805-229">Long</span></span> | <span data-ttu-id="1d805-230">Antal exponerade enheter som denna åtgärd gäller för</span><span class="sxs-lookup"><span data-stu-id="1d805-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="1d805-231">43</span><span class="sxs-lookup"><span data-stu-id="1d805-231">43</span></span>
<span data-ttu-id="1d805-232">rubrik</span><span class="sxs-lookup"><span data-stu-id="1d805-232">title</span></span> | <span data-ttu-id="1d805-233">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-233">String</span></span> | <span data-ttu-id="1d805-234">Rubrik för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="1d805-234">Title of this remediation activity</span></span> | <span data-ttu-id="1d805-235">Uppdatera Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1d805-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="1d805-236">skriv</span><span class="sxs-lookup"><span data-stu-id="1d805-236">type</span></span> | <span data-ttu-id="1d805-237">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-237">String</span></span> | <span data-ttu-id="1d805-238">Åtgärdstyp</span><span class="sxs-lookup"><span data-stu-id="1d805-238">Remediation type</span></span> | <span data-ttu-id="1d805-239">Update</span><span class="sxs-lookup"><span data-stu-id="1d805-239">Update</span></span>
<span data-ttu-id="1d805-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="1d805-240">vendorId</span></span> | <span data-ttu-id="1d805-241">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d805-241">String</span></span> | <span data-ttu-id="1d805-242">Relaterade leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="1d805-242">Related vendor name</span></span> | <span data-ttu-id="1d805-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="1d805-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="1d805-244">Exempel</span><span class="sxs-lookup"><span data-stu-id="1d805-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="1d805-245">Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="1d805-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="1d805-246">Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="1d805-246">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="1d805-247">Se även</span><span class="sxs-lookup"><span data-stu-id="1d805-247">See also</span></span>

- [<span data-ttu-id="1d805-248">Åtgärdsmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="1d805-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="1d805-249">Få en åtgärdsaktivitet efter ID</span><span class="sxs-lookup"><span data-stu-id="1d805-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="1d805-250">Lista exponerade enheter av en åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="1d805-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="1d805-251">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="1d805-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="1d805-252">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="1d805-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
