---
title: Lista alla åtgärder
description: Returnerar information om alla åtgärder.
keywords: apis, remediation, remediation api, get, remediation tasks,
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
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061159"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="13d5c-104">Lista alla åtgärder</span><span class="sxs-lookup"><span data-stu-id="13d5c-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="13d5c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="13d5c-105">**Applies to:**</span></span>

- [<span data-ttu-id="13d5c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="13d5c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="13d5c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13d5c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="13d5c-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="13d5c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="13d5c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="13d5c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="13d5c-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="13d5c-110">API description</span></span>

<span data-ttu-id="13d5c-111">Returnerar information om alla åtgärder.</span><span class="sxs-lookup"><span data-stu-id="13d5c-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="13d5c-112">[Läs mer om åtgärder](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="13d5c-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="13d5c-113">**URL:** HÄMTA: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="13d5c-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="13d5c-114">**Egenskapsinformation**</span><span class="sxs-lookup"><span data-stu-id="13d5c-114">**Properties** details</span></span>

<span data-ttu-id="13d5c-115">Egenskap (id)</span><span class="sxs-lookup"><span data-stu-id="13d5c-115">Property (id)</span></span> | <span data-ttu-id="13d5c-116">Datatyp</span><span class="sxs-lookup"><span data-stu-id="13d5c-116">Data type</span></span> | <span data-ttu-id="13d5c-117">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="13d5c-117">Description</span></span> | <span data-ttu-id="13d5c-118">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="13d5c-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="13d5c-119">kategori</span><span class="sxs-lookup"><span data-stu-id="13d5c-119">category</span></span> | <span data-ttu-id="13d5c-120">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-120">String</span></span> | <span data-ttu-id="13d5c-121">Kategori för åtgärdsaktiviteten (konfiguration av programvara/säkerhet)</span><span class="sxs-lookup"><span data-stu-id="13d5c-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="13d5c-122">Programvara</span><span class="sxs-lookup"><span data-stu-id="13d5c-122">Software</span></span>
<span data-ttu-id="13d5c-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="13d5c-123">completerEmail</span></span> | <span data-ttu-id="13d5c-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-124">String</span></span> | <span data-ttu-id="13d5c-125">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras e-postadress</span><span class="sxs-lookup"><span data-stu-id="13d5c-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="13d5c-126">null</span><span class="sxs-lookup"><span data-stu-id="13d5c-126">null</span></span>
<span data-ttu-id="13d5c-127">completerId</span><span class="sxs-lookup"><span data-stu-id="13d5c-127">completerId</span></span> | <span data-ttu-id="13d5c-128">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-128">String</span></span> | <span data-ttu-id="13d5c-129">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras objekt-ID</span><span class="sxs-lookup"><span data-stu-id="13d5c-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="13d5c-130">null</span><span class="sxs-lookup"><span data-stu-id="13d5c-130">null</span></span>
<span data-ttu-id="13d5c-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="13d5c-131">completionMethod</span></span> | <span data-ttu-id="13d5c-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-132">String</span></span> | <span data-ttu-id="13d5c-133">En åtgärdsaktivitet kan slutföras "automatiskt" (om alla enheter är korrigerade) eller "manuellt" av en person som väljer "markera som slutförd"</span><span class="sxs-lookup"><span data-stu-id="13d5c-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="13d5c-134">Automatisk</span><span class="sxs-lookup"><span data-stu-id="13d5c-134">Automatic</span></span>
<span data-ttu-id="13d5c-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="13d5c-135">createdOn</span></span> | <span data-ttu-id="13d5c-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="13d5c-136">DateTime</span></span> | <span data-ttu-id="13d5c-137">Tidpunkten då den här åtgärdsaktiviteten skapades</span><span class="sxs-lookup"><span data-stu-id="13d5c-137">Time this remediation activity was created</span></span> | <span data-ttu-id="13d5c-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="13d5c-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="13d5c-139">beskrivning</span><span class="sxs-lookup"><span data-stu-id="13d5c-139">description</span></span> | <span data-ttu-id="13d5c-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-140">String</span></span> | <span data-ttu-id="13d5c-141">Beskrivning av den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="13d5c-141">Description of this remediation activity</span></span> | <span data-ttu-id="13d5c-142">Uppdatera Chrome till en senare version för att minimera kända 1248 säkerhetsproblem som påverkar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="13d5c-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="13d5c-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="13d5c-143">dueOn</span></span> | <span data-ttu-id="13d5c-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="13d5c-144">DateTime</span></span> | <span data-ttu-id="13d5c-145">Förfallodatum som skapare uppsättningen för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="13d5c-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="13d5c-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="13d5c-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="13d5c-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="13d5c-147">fixedDevices</span></span> | <span data-ttu-id="13d5c-148">.</span><span class="sxs-lookup"><span data-stu-id="13d5c-148">.</span></span> | <span data-ttu-id="13d5c-149">Antalet enheter som har åtgärdats</span><span class="sxs-lookup"><span data-stu-id="13d5c-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="13d5c-150">2</span><span class="sxs-lookup"><span data-stu-id="13d5c-150">2</span></span>
<span data-ttu-id="13d5c-151">id</span><span class="sxs-lookup"><span data-stu-id="13d5c-151">id</span></span> | <span data-ttu-id="13d5c-152">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-152">String</span></span> | <span data-ttu-id="13d5c-153">ID för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="13d5c-153">ID of this remediation activity</span></span> | <span data-ttu-id="13d5c-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="13d5c-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="13d5c-155">nameId</span><span class="sxs-lookup"><span data-stu-id="13d5c-155">nameId</span></span> | <span data-ttu-id="13d5c-156">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-156">String</span></span> | <span data-ttu-id="13d5c-157">Relaterade produktnamn</span><span class="sxs-lookup"><span data-stu-id="13d5c-157">Related product name</span></span> | <span data-ttu-id="13d5c-158">chrome</span><span class="sxs-lookup"><span data-stu-id="13d5c-158">chrome</span></span>
<span data-ttu-id="13d5c-159">prioritet</span><span class="sxs-lookup"><span data-stu-id="13d5c-159">priority</span></span> | <span data-ttu-id="13d5c-160">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-160">String</span></span> | <span data-ttu-id="13d5c-161">Prioritet för skaparuppsättningen för den här åtgärdsaktiviteten (Hög\Medel\Låg)</span><span class="sxs-lookup"><span data-stu-id="13d5c-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="13d5c-162">Hög</span><span class="sxs-lookup"><span data-stu-id="13d5c-162">High</span></span>
<span data-ttu-id="13d5c-163">productId</span><span class="sxs-lookup"><span data-stu-id="13d5c-163">productId</span></span> | <span data-ttu-id="13d5c-164">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-164">String</span></span> | <span data-ttu-id="13d5c-165">Relaterade produkt-ID</span><span class="sxs-lookup"><span data-stu-id="13d5c-165">Related product ID</span></span> | <span data-ttu-id="13d5c-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="13d5c-166">google-_-chrome</span></span>
<span data-ttu-id="13d5c-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="13d5c-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="13d5c-168">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-168">String</span></span> | <span data-ttu-id="13d5c-169">Några konfigurationsändringar kunde endast begäras för enheter utan påverkan från användare.</span><span class="sxs-lookup"><span data-stu-id="13d5c-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="13d5c-170">Det här värdet anger valet mellan "alla exponerade enheter" eller "endast enheter utan påverkan från användare".</span><span class="sxs-lookup"><span data-stu-id="13d5c-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="13d5c-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="13d5c-171">AllExposedAssets</span></span>
<span data-ttu-id="13d5c-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="13d5c-172">rbacGroupNames</span></span> | <span data-ttu-id="13d5c-173">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-173">String</span></span> | <span data-ttu-id="13d5c-174">Gruppnamn för relaterade enheter</span><span class="sxs-lookup"><span data-stu-id="13d5c-174">Related device group names</span></span> | <span data-ttu-id="13d5c-175">[ "Windows-servrar", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="13d5c-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="13d5c-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="13d5c-176">recommendedProgram</span></span> | <span data-ttu-id="13d5c-177">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-177">String</span></span> | <span data-ttu-id="13d5c-178">Rekommenderat program att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="13d5c-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="13d5c-179">null</span><span class="sxs-lookup"><span data-stu-id="13d5c-179">null</span></span>
<span data-ttu-id="13d5c-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="13d5c-180">recommendedVendor</span></span> | <span data-ttu-id="13d5c-181">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-181">String</span></span> | <span data-ttu-id="13d5c-182">Rekommenderad leverantör att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="13d5c-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="13d5c-183">null</span><span class="sxs-lookup"><span data-stu-id="13d5c-183">null</span></span>
<span data-ttu-id="13d5c-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="13d5c-184">recommendedVersion</span></span> | <span data-ttu-id="13d5c-185">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-185">String</span></span> | <span data-ttu-id="13d5c-186">Rekommenderad version att uppdatera/uppgradera till</span><span class="sxs-lookup"><span data-stu-id="13d5c-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="13d5c-187">null</span><span class="sxs-lookup"><span data-stu-id="13d5c-187">null</span></span>
<span data-ttu-id="13d5c-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="13d5c-188">relatedComponent</span></span> | <span data-ttu-id="13d5c-189">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-189">String</span></span> | <span data-ttu-id="13d5c-190">Relaterad komponent i den här åtgärdsaktiviteten (som liknar den relaterade komponenten för en säkerhetsrekommendationer)</span><span class="sxs-lookup"><span data-stu-id="13d5c-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="13d5c-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="13d5c-191">Google Chrome</span></span>
<span data-ttu-id="13d5c-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="13d5c-192">requesterEmail</span></span> | <span data-ttu-id="13d5c-193">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-193">String</span></span> | <span data-ttu-id="13d5c-194">E-postadress skapad</span><span class="sxs-lookup"><span data-stu-id="13d5c-194">Creator email address</span></span> | <span data-ttu-id="13d5c-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="13d5c-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="13d5c-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="13d5c-196">requesterId</span></span> | <span data-ttu-id="13d5c-197">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-197">String</span></span> | <span data-ttu-id="13d5c-198">Creator-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="13d5c-198">Creator object id</span></span> | <span data-ttu-id="13d5c-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="13d5c-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="13d5c-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="13d5c-200">requesterNotes</span></span> | <span data-ttu-id="13d5c-201">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-201">String</span></span> | <span data-ttu-id="13d5c-202">Anteckningarna (fri text) som skaparen har lagt till för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="13d5c-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="13d5c-203">null</span><span class="sxs-lookup"><span data-stu-id="13d5c-203">null</span></span>
<span data-ttu-id="13d5c-204">scid</span><span class="sxs-lookup"><span data-stu-id="13d5c-204">scid</span></span> | <span data-ttu-id="13d5c-205">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-205">String</span></span> | <span data-ttu-id="13d5c-206">SCID för relaterad säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="13d5c-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="13d5c-207">null</span><span class="sxs-lookup"><span data-stu-id="13d5c-207">null</span></span>
<span data-ttu-id="13d5c-208">status</span><span class="sxs-lookup"><span data-stu-id="13d5c-208">status</span></span> | <span data-ttu-id="13d5c-209">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-209">String</span></span> | <span data-ttu-id="13d5c-210">Status för åtgärdsaktivitet (Aktiv/slutförd)</span><span class="sxs-lookup"><span data-stu-id="13d5c-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="13d5c-211">Aktiv</span><span class="sxs-lookup"><span data-stu-id="13d5c-211">Active</span></span>
<span data-ttu-id="13d5c-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="13d5c-212">statusLastModifiedOn</span></span> | <span data-ttu-id="13d5c-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="13d5c-213">DateTime</span></span> | <span data-ttu-id="13d5c-214">Datum när statusfältet uppdaterades</span><span class="sxs-lookup"><span data-stu-id="13d5c-214">Date when the status field was updated</span></span> | <span data-ttu-id="13d5c-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="13d5c-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="13d5c-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="13d5c-216">targetDevices</span></span> | <span data-ttu-id="13d5c-217">Long</span><span class="sxs-lookup"><span data-stu-id="13d5c-217">Long</span></span> | <span data-ttu-id="13d5c-218">Antal exponerade enheter som denna åtgärd gäller för</span><span class="sxs-lookup"><span data-stu-id="13d5c-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="13d5c-219">43</span><span class="sxs-lookup"><span data-stu-id="13d5c-219">43</span></span>
<span data-ttu-id="13d5c-220">rubrik</span><span class="sxs-lookup"><span data-stu-id="13d5c-220">title</span></span> | <span data-ttu-id="13d5c-221">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-221">String</span></span> | <span data-ttu-id="13d5c-222">Rubrik för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="13d5c-222">Title of this remediation activity</span></span> | <span data-ttu-id="13d5c-223">Uppdatera Google Chrome</span><span class="sxs-lookup"><span data-stu-id="13d5c-223">Update Google Chrome</span></span>
<span data-ttu-id="13d5c-224">skriv</span><span class="sxs-lookup"><span data-stu-id="13d5c-224">type</span></span> | <span data-ttu-id="13d5c-225">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-225">String</span></span> | <span data-ttu-id="13d5c-226">Åtgärdstyp</span><span class="sxs-lookup"><span data-stu-id="13d5c-226">Remediation type</span></span> | <span data-ttu-id="13d5c-227">Uppdatera</span><span class="sxs-lookup"><span data-stu-id="13d5c-227">Update</span></span>
<span data-ttu-id="13d5c-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="13d5c-228">vendorId</span></span> | <span data-ttu-id="13d5c-229">Sträng</span><span class="sxs-lookup"><span data-stu-id="13d5c-229">String</span></span> | <span data-ttu-id="13d5c-230">Relaterade leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="13d5c-230">Related vendor name</span></span> | <span data-ttu-id="13d5c-231">google</span><span class="sxs-lookup"><span data-stu-id="13d5c-231">google</span></span>

## <a name="example"></a><span data-ttu-id="13d5c-232">Exempel</span><span class="sxs-lookup"><span data-stu-id="13d5c-232">Example</span></span>

<span data-ttu-id="13d5c-233">**Exempel på** förfrågan</span><span class="sxs-lookup"><span data-stu-id="13d5c-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="13d5c-234">**Svarsexempel**</span><span class="sxs-lookup"><span data-stu-id="13d5c-234">**Response** example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="13d5c-235">Se även</span><span class="sxs-lookup"><span data-stu-id="13d5c-235">See also</span></span>

- [<span data-ttu-id="13d5c-236">Åtgärdsmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="13d5c-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="13d5c-237">Få en åtgärdsaktivitet efter ID</span><span class="sxs-lookup"><span data-stu-id="13d5c-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="13d5c-238">Lista över exponerade enheter med en åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="13d5c-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="13d5c-239">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="13d5c-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="13d5c-240">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="13d5c-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
