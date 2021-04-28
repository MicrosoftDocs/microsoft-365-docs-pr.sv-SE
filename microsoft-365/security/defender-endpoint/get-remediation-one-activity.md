---
title: Få en åtgärdsaktivitet efter ID
description: Returnerar information för den angivna åtgärdsaktiviteten.
keywords: apis, remediation, remediation api, get, remediation tasks, list
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061169"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="2a637-104">Få en åtgärdsaktivitet efter ID</span><span class="sxs-lookup"><span data-stu-id="2a637-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a637-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2a637-105">**Applies to:**</span></span>

- [<span data-ttu-id="2a637-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2a637-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a637-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a637-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a637-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2a637-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a637-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2a637-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2a637-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="2a637-110">API description</span></span>

<span data-ttu-id="2a637-111">Returnerar information för den angivna åtgärdsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="2a637-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="2a637-112">Visar samma kolumner som [Hämta all åtgärdsaktivitet](get-remediation-all-activities.md), men returnerar _endast resultat för den angivna åtgärdsaktiviteten._</span><span class="sxs-lookup"><span data-stu-id="2a637-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="2a637-113">[Läs mer om åtgärder](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="2a637-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="2a637-114">Lista en angiven åtgärdsaktivitet för (id)</span><span class="sxs-lookup"><span data-stu-id="2a637-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="2a637-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="2a637-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="2a637-116">**Egenskapsinformation**</span><span class="sxs-lookup"><span data-stu-id="2a637-116">**Properties** details</span></span>

<span data-ttu-id="2a637-117">Egenskap (id)</span><span class="sxs-lookup"><span data-stu-id="2a637-117">Property (id)</span></span> | <span data-ttu-id="2a637-118">Datatyp</span><span class="sxs-lookup"><span data-stu-id="2a637-118">Data type</span></span> | <span data-ttu-id="2a637-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2a637-119">Description</span></span> | <span data-ttu-id="2a637-120">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="2a637-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2a637-121">kategori</span><span class="sxs-lookup"><span data-stu-id="2a637-121">category</span></span> | <span data-ttu-id="2a637-122">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-122">String</span></span> | <span data-ttu-id="2a637-123">Kategori för åtgärdsaktiviteten (konfiguration av programvara/säkerhet)</span><span class="sxs-lookup"><span data-stu-id="2a637-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="2a637-124">Programvara</span><span class="sxs-lookup"><span data-stu-id="2a637-124">Software</span></span>
<span data-ttu-id="2a637-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="2a637-125">completerEmail</span></span> | <span data-ttu-id="2a637-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-126">String</span></span> | <span data-ttu-id="2a637-127">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras e-postadress</span><span class="sxs-lookup"><span data-stu-id="2a637-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="2a637-128">null</span><span class="sxs-lookup"><span data-stu-id="2a637-128">null</span></span>
<span data-ttu-id="2a637-129">completerId</span><span class="sxs-lookup"><span data-stu-id="2a637-129">completerId</span></span> | <span data-ttu-id="2a637-130">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-130">String</span></span> | <span data-ttu-id="2a637-131">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras objekt-ID</span><span class="sxs-lookup"><span data-stu-id="2a637-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="2a637-132">null</span><span class="sxs-lookup"><span data-stu-id="2a637-132">null</span></span>
<span data-ttu-id="2a637-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="2a637-133">completionMethod</span></span> | <span data-ttu-id="2a637-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-134">String</span></span> | <span data-ttu-id="2a637-135">En åtgärdsaktivitet kan slutföras "automatiskt" (om alla enheter är korrigerade) eller "manuellt" av en person som väljer "markera som slutförd"</span><span class="sxs-lookup"><span data-stu-id="2a637-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="2a637-136">Automatisk</span><span class="sxs-lookup"><span data-stu-id="2a637-136">Automatic</span></span>
<span data-ttu-id="2a637-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="2a637-137">createdOn</span></span> | <span data-ttu-id="2a637-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="2a637-138">DateTime</span></span> | <span data-ttu-id="2a637-139">Tidpunkten då den här åtgärdsaktiviteten skapades</span><span class="sxs-lookup"><span data-stu-id="2a637-139">Time this remediation activity was created</span></span> | <span data-ttu-id="2a637-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="2a637-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="2a637-141">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2a637-141">description</span></span> | <span data-ttu-id="2a637-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-142">String</span></span> | <span data-ttu-id="2a637-143">Beskrivning av den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="2a637-143">Description of this remediation activity</span></span> | <span data-ttu-id="2a637-144">Uppdatera Chrome till en senare version för att minimera kända 1248 säkerhetsproblem som påverkar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="2a637-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="2a637-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="2a637-145">dueOn</span></span> | <span data-ttu-id="2a637-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="2a637-146">DateTime</span></span> | <span data-ttu-id="2a637-147">Förfallodatum som skapare uppsättningen för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="2a637-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="2a637-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="2a637-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="2a637-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="2a637-149">fixedDevices</span></span> |  | <span data-ttu-id="2a637-150">Antalet enheter som har åtgärdats</span><span class="sxs-lookup"><span data-stu-id="2a637-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="2a637-151">2</span><span class="sxs-lookup"><span data-stu-id="2a637-151">2</span></span>
<span data-ttu-id="2a637-152">id</span><span class="sxs-lookup"><span data-stu-id="2a637-152">id</span></span> | <span data-ttu-id="2a637-153">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-153">String</span></span> | <span data-ttu-id="2a637-154">ID för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="2a637-154">ID of this remediation activity</span></span> | <span data-ttu-id="2a637-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="2a637-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="2a637-156">nameId</span><span class="sxs-lookup"><span data-stu-id="2a637-156">nameId</span></span> | <span data-ttu-id="2a637-157">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-157">String</span></span> | <span data-ttu-id="2a637-158">Relaterade produktnamn</span><span class="sxs-lookup"><span data-stu-id="2a637-158">Related product name</span></span> | <span data-ttu-id="2a637-159">chrome</span><span class="sxs-lookup"><span data-stu-id="2a637-159">chrome</span></span>
<span data-ttu-id="2a637-160">prioritet</span><span class="sxs-lookup"><span data-stu-id="2a637-160">priority</span></span> | <span data-ttu-id="2a637-161">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-161">String</span></span> | <span data-ttu-id="2a637-162">Prioritet för skaparuppsättningen för den här åtgärdsaktiviteten (Hög\Medel\Låg)</span><span class="sxs-lookup"><span data-stu-id="2a637-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="2a637-163">Hög</span><span class="sxs-lookup"><span data-stu-id="2a637-163">High</span></span>
<span data-ttu-id="2a637-164">productId</span><span class="sxs-lookup"><span data-stu-id="2a637-164">productId</span></span> | <span data-ttu-id="2a637-165">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-165">String</span></span> | <span data-ttu-id="2a637-166">Relaterade produkt-ID</span><span class="sxs-lookup"><span data-stu-id="2a637-166">Related product ID</span></span> | <span data-ttu-id="2a637-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="2a637-167">google-_-chrome</span></span>
<span data-ttu-id="2a637-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="2a637-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="2a637-169">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-169">String</span></span> | <span data-ttu-id="2a637-170">Några konfigurationsändringar kunde endast begäras för enheter utan påverkan från användare.</span><span class="sxs-lookup"><span data-stu-id="2a637-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="2a637-171">Det här värdet anger valet mellan "alla exponerade enheter" eller "endast enheter utan påverkan från användare".</span><span class="sxs-lookup"><span data-stu-id="2a637-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="2a637-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="2a637-172">AllExposedAssets</span></span>
<span data-ttu-id="2a637-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="2a637-173">rbacGroupNames</span></span> | <span data-ttu-id="2a637-174">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-174">String</span></span> | <span data-ttu-id="2a637-175">Gruppnamn för relaterade enheter</span><span class="sxs-lookup"><span data-stu-id="2a637-175">Related device group names</span></span> | <span data-ttu-id="2a637-176">[ "Windows-servrar", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="2a637-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="2a637-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="2a637-177">recommendedProgram</span></span> | <span data-ttu-id="2a637-178">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-178">String</span></span> | <span data-ttu-id="2a637-179">Rekommenderat program att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="2a637-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="2a637-180">null</span><span class="sxs-lookup"><span data-stu-id="2a637-180">null</span></span>
<span data-ttu-id="2a637-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="2a637-181">recommendedVendor</span></span> | <span data-ttu-id="2a637-182">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-182">String</span></span> | <span data-ttu-id="2a637-183">Rekommenderad leverantör att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="2a637-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="2a637-184">null</span><span class="sxs-lookup"><span data-stu-id="2a637-184">null</span></span>
<span data-ttu-id="2a637-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="2a637-185">recommendedVersion</span></span> | <span data-ttu-id="2a637-186">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-186">String</span></span> | <span data-ttu-id="2a637-187">Rekommenderad version att uppdatera/uppgradera till</span><span class="sxs-lookup"><span data-stu-id="2a637-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="2a637-188">null</span><span class="sxs-lookup"><span data-stu-id="2a637-188">null</span></span>
<span data-ttu-id="2a637-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="2a637-189">relatedComponent</span></span> | <span data-ttu-id="2a637-190">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-190">String</span></span> | <span data-ttu-id="2a637-191">Relaterad komponent i den här åtgärdsaktiviteten (som liknar den relaterade komponenten för en säkerhetsrekommendationer)</span><span class="sxs-lookup"><span data-stu-id="2a637-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="2a637-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="2a637-192">Google Chrome</span></span>
<span data-ttu-id="2a637-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="2a637-193">requesterEmail</span></span> | <span data-ttu-id="2a637-194">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-194">String</span></span> | <span data-ttu-id="2a637-195">E-postadress skapad</span><span class="sxs-lookup"><span data-stu-id="2a637-195">Creator email address</span></span> | <span data-ttu-id="2a637-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a637-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="2a637-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="2a637-197">requesterId</span></span> | <span data-ttu-id="2a637-198">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-198">String</span></span> | <span data-ttu-id="2a637-199">Creator-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="2a637-199">Creator object id</span></span> | <span data-ttu-id="2a637-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="2a637-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="2a637-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="2a637-201">requesterNotes</span></span> | <span data-ttu-id="2a637-202">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-202">String</span></span> | <span data-ttu-id="2a637-203">Anteckningarna (fri text) som skaparen har lagt till för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="2a637-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="2a637-204">null</span><span class="sxs-lookup"><span data-stu-id="2a637-204">null</span></span>
<span data-ttu-id="2a637-205">scid</span><span class="sxs-lookup"><span data-stu-id="2a637-205">scid</span></span> | <span data-ttu-id="2a637-206">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-206">String</span></span> | <span data-ttu-id="2a637-207">SCID för relaterad säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="2a637-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="2a637-208">null</span><span class="sxs-lookup"><span data-stu-id="2a637-208">null</span></span>
<span data-ttu-id="2a637-209">status</span><span class="sxs-lookup"><span data-stu-id="2a637-209">status</span></span> | <span data-ttu-id="2a637-210">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-210">String</span></span> | <span data-ttu-id="2a637-211">Status för åtgärdsaktivitet (Aktiv/slutförd)</span><span class="sxs-lookup"><span data-stu-id="2a637-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="2a637-212">Aktiv</span><span class="sxs-lookup"><span data-stu-id="2a637-212">Active</span></span>
<span data-ttu-id="2a637-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="2a637-213">statusLastModifiedOn</span></span> | <span data-ttu-id="2a637-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="2a637-214">DateTime</span></span> | <span data-ttu-id="2a637-215">Datum när statusfältet uppdaterades</span><span class="sxs-lookup"><span data-stu-id="2a637-215">Date when the status field was updated</span></span> | <span data-ttu-id="2a637-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="2a637-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="2a637-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="2a637-217">targetDevices</span></span> | <span data-ttu-id="2a637-218">Long</span><span class="sxs-lookup"><span data-stu-id="2a637-218">Long</span></span> | <span data-ttu-id="2a637-219">Antal exponerade enheter som denna åtgärd gäller för</span><span class="sxs-lookup"><span data-stu-id="2a637-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="2a637-220">43</span><span class="sxs-lookup"><span data-stu-id="2a637-220">43</span></span>
<span data-ttu-id="2a637-221">rubrik</span><span class="sxs-lookup"><span data-stu-id="2a637-221">title</span></span> | <span data-ttu-id="2a637-222">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-222">String</span></span> | <span data-ttu-id="2a637-223">Rubrik för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="2a637-223">Title of this remediation activity</span></span> | <span data-ttu-id="2a637-224">Uppdatera Google Chrome</span><span class="sxs-lookup"><span data-stu-id="2a637-224">Update Google Chrome</span></span>
<span data-ttu-id="2a637-225">skriv</span><span class="sxs-lookup"><span data-stu-id="2a637-225">type</span></span> | <span data-ttu-id="2a637-226">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-226">String</span></span> | <span data-ttu-id="2a637-227">Åtgärdstyp</span><span class="sxs-lookup"><span data-stu-id="2a637-227">Remediation type</span></span> | <span data-ttu-id="2a637-228">Uppdatera</span><span class="sxs-lookup"><span data-stu-id="2a637-228">Update</span></span>
<span data-ttu-id="2a637-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="2a637-229">vendorId</span></span> | <span data-ttu-id="2a637-230">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a637-230">String</span></span> | <span data-ttu-id="2a637-231">Relaterade leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="2a637-231">Related vendor name</span></span> | <span data-ttu-id="2a637-232">google</span><span class="sxs-lookup"><span data-stu-id="2a637-232">google</span></span>

## <a name="example"></a><span data-ttu-id="2a637-233">Exempel</span><span class="sxs-lookup"><span data-stu-id="2a637-233">Example</span></span>

<span data-ttu-id="2a637-234">**Exempel på** förfrågan</span><span class="sxs-lookup"><span data-stu-id="2a637-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="2a637-235">**Svarsexempel**</span><span class="sxs-lookup"><span data-stu-id="2a637-235">**Response** example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a><span data-ttu-id="2a637-236">Se även</span><span class="sxs-lookup"><span data-stu-id="2a637-236">See also</span></span>

- [<span data-ttu-id="2a637-237">Åtgärdsmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="2a637-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="2a637-238">Lista alla åtgärder</span><span class="sxs-lookup"><span data-stu-id="2a637-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="2a637-239">Lista över exponerade enheter med en åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="2a637-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="2a637-240">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="2a637-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="2a637-241">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="2a637-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
