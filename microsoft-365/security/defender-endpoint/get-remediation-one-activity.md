---
title: Få en åtgärdsaktivitet efter ID
description: Returnerar information för den angivna åtgärdsaktiviteten.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation by ID,
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
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772155"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="bdc50-104">Få en åtgärdsaktivitet efter ID</span><span class="sxs-lookup"><span data-stu-id="bdc50-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bdc50-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bdc50-105">**Applies to:**</span></span>

- [<span data-ttu-id="bdc50-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bdc50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bdc50-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdc50-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bdc50-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="bdc50-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bdc50-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="bdc50-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="bdc50-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="bdc50-110">API description</span></span>

<span data-ttu-id="bdc50-111">Returnerar information för den angivna åtgärdsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="bdc50-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="bdc50-112">Visar samma kolumner som [Hämta all åtgärdsaktivitet](get-remediation-all-activities.md), men returnerar _endast resultat för den angivna åtgärdsaktiviteten._</span><span class="sxs-lookup"><span data-stu-id="bdc50-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="bdc50-113">[Läs mer om åtgärder](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="bdc50-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="bdc50-114">Lista en angiven åtgärdsaktivitet för (id)</span><span class="sxs-lookup"><span data-stu-id="bdc50-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="bdc50-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="bdc50-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="bdc50-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="bdc50-116">Permissions</span></span>

<span data-ttu-id="bdc50-117">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="bdc50-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bdc50-118">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bdc50-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="bdc50-119">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="bdc50-119">Permission type</span></span> | <span data-ttu-id="bdc50-120">Behörighet</span><span class="sxs-lookup"><span data-stu-id="bdc50-120">Permission</span></span> | <span data-ttu-id="bdc50-121">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="bdc50-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bdc50-122">Program</span><span class="sxs-lookup"><span data-stu-id="bdc50-122">Application</span></span> | <span data-ttu-id="bdc50-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="bdc50-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="bdc50-124">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="bdc50-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="bdc50-125">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="bdc50-125">Delegated (work or school account)</span></span> | <span data-ttu-id="bdc50-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="bdc50-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="bdc50-127">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="bdc50-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="bdc50-128">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="bdc50-128">Properties</span></span>

<span data-ttu-id="bdc50-129">Egenskap (id)</span><span class="sxs-lookup"><span data-stu-id="bdc50-129">Property (id)</span></span> | <span data-ttu-id="bdc50-130">Datatyp</span><span class="sxs-lookup"><span data-stu-id="bdc50-130">Data type</span></span> | <span data-ttu-id="bdc50-131">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bdc50-131">Description</span></span> | <span data-ttu-id="bdc50-132">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="bdc50-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="bdc50-133">kategori</span><span class="sxs-lookup"><span data-stu-id="bdc50-133">category</span></span> | <span data-ttu-id="bdc50-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-134">String</span></span> | <span data-ttu-id="bdc50-135">Kategori för åtgärdsaktiviteten (konfiguration av programvara/säkerhet)</span><span class="sxs-lookup"><span data-stu-id="bdc50-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="bdc50-136">Programvara</span><span class="sxs-lookup"><span data-stu-id="bdc50-136">Software</span></span>
<span data-ttu-id="bdc50-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="bdc50-137">completerEmail</span></span> | <span data-ttu-id="bdc50-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-138">String</span></span> | <span data-ttu-id="bdc50-139">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras e-postadress</span><span class="sxs-lookup"><span data-stu-id="bdc50-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="bdc50-140">null</span><span class="sxs-lookup"><span data-stu-id="bdc50-140">null</span></span>
<span data-ttu-id="bdc50-141">completerId</span><span class="sxs-lookup"><span data-stu-id="bdc50-141">completerId</span></span> | <span data-ttu-id="bdc50-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-142">String</span></span> | <span data-ttu-id="bdc50-143">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras objekt-ID</span><span class="sxs-lookup"><span data-stu-id="bdc50-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="bdc50-144">null</span><span class="sxs-lookup"><span data-stu-id="bdc50-144">null</span></span>
<span data-ttu-id="bdc50-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="bdc50-145">completionMethod</span></span> | <span data-ttu-id="bdc50-146">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-146">String</span></span> | <span data-ttu-id="bdc50-147">En åtgärdsaktivitet kan slutföras "automatiskt" (om alla enheter är korrigerade) eller "manuellt" av en person som väljer "markera som slutförd"</span><span class="sxs-lookup"><span data-stu-id="bdc50-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="bdc50-148">Automatisk</span><span class="sxs-lookup"><span data-stu-id="bdc50-148">Automatic</span></span>
<span data-ttu-id="bdc50-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="bdc50-149">createdOn</span></span> | <span data-ttu-id="bdc50-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="bdc50-150">DateTime</span></span> | <span data-ttu-id="bdc50-151">Tidpunkten då den här åtgärdsaktiviteten skapades</span><span class="sxs-lookup"><span data-stu-id="bdc50-151">Time this remediation activity was created</span></span> | <span data-ttu-id="bdc50-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="bdc50-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="bdc50-153">beskrivning</span><span class="sxs-lookup"><span data-stu-id="bdc50-153">description</span></span> | <span data-ttu-id="bdc50-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-154">String</span></span> | <span data-ttu-id="bdc50-155">Beskrivning av den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="bdc50-155">Description of this remediation activity</span></span> | <span data-ttu-id="bdc50-156">Uppdatera Microsoft Silverlight till en senare version för att minimera kända säkerhetsproblem som påverkar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="bdc50-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="bdc50-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="bdc50-157">dueOn</span></span> | <span data-ttu-id="bdc50-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="bdc50-158">DateTime</span></span> | <span data-ttu-id="bdc50-159">Förfallodatum som skapare uppsättningen för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="bdc50-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="bdc50-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="bdc50-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="bdc50-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="bdc50-161">fixedDevices</span></span> |  | <span data-ttu-id="bdc50-162">Antalet enheter som har åtgärdats</span><span class="sxs-lookup"><span data-stu-id="bdc50-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="bdc50-163">2</span><span class="sxs-lookup"><span data-stu-id="bdc50-163">2</span></span>
<span data-ttu-id="bdc50-164">id</span><span class="sxs-lookup"><span data-stu-id="bdc50-164">id</span></span> | <span data-ttu-id="bdc50-165">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-165">String</span></span> | <span data-ttu-id="bdc50-166">ID för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="bdc50-166">ID of this remediation activity</span></span> | <span data-ttu-id="bdc50-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="bdc50-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="bdc50-168">nameId</span><span class="sxs-lookup"><span data-stu-id="bdc50-168">nameId</span></span> | <span data-ttu-id="bdc50-169">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-169">String</span></span> | <span data-ttu-id="bdc50-170">Relaterade produktnamn</span><span class="sxs-lookup"><span data-stu-id="bdc50-170">Related product name</span></span> | <span data-ttu-id="bdc50-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="bdc50-171">Microsoft Silverlight</span></span>
<span data-ttu-id="bdc50-172">prioritet</span><span class="sxs-lookup"><span data-stu-id="bdc50-172">priority</span></span> | <span data-ttu-id="bdc50-173">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-173">String</span></span> | <span data-ttu-id="bdc50-174">Prioritet för skaparuppsättningen för den här åtgärdsaktiviteten (Hög\Medel\Låg)</span><span class="sxs-lookup"><span data-stu-id="bdc50-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="bdc50-175">Högsta</span><span class="sxs-lookup"><span data-stu-id="bdc50-175">High</span></span>
<span data-ttu-id="bdc50-176">productId</span><span class="sxs-lookup"><span data-stu-id="bdc50-176">productId</span></span> | <span data-ttu-id="bdc50-177">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-177">String</span></span> | <span data-ttu-id="bdc50-178">Relaterade produkt-ID</span><span class="sxs-lookup"><span data-stu-id="bdc50-178">Related product ID</span></span> | <span data-ttu-id="bdc50-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="bdc50-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="bdc50-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="bdc50-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="bdc50-181">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-181">String</span></span> | <span data-ttu-id="bdc50-182">Några konfigurationsändringar kunde endast begäras för enheter utan påverkan från användare.</span><span class="sxs-lookup"><span data-stu-id="bdc50-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="bdc50-183">Det här värdet anger valet mellan "alla exponerade enheter" eller "endast enheter utan påverkan från användare".</span><span class="sxs-lookup"><span data-stu-id="bdc50-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="bdc50-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="bdc50-184">AllExposedAssets</span></span>
<span data-ttu-id="bdc50-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="bdc50-185">rbacGroupNames</span></span> | <span data-ttu-id="bdc50-186">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-186">String</span></span> | <span data-ttu-id="bdc50-187">Gruppnamn för relaterade enheter</span><span class="sxs-lookup"><span data-stu-id="bdc50-187">Related device group names</span></span> | <span data-ttu-id="bdc50-188">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="bdc50-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="bdc50-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="bdc50-189">recommendedProgram</span></span> | <span data-ttu-id="bdc50-190">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-190">String</span></span> | <span data-ttu-id="bdc50-191">Rekommenderat program att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="bdc50-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="bdc50-192">null</span><span class="sxs-lookup"><span data-stu-id="bdc50-192">null</span></span>
<span data-ttu-id="bdc50-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="bdc50-193">recommendedVendor</span></span> | <span data-ttu-id="bdc50-194">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-194">String</span></span> | <span data-ttu-id="bdc50-195">Rekommenderad leverantör att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="bdc50-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="bdc50-196">null</span><span class="sxs-lookup"><span data-stu-id="bdc50-196">null</span></span>
<span data-ttu-id="bdc50-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="bdc50-197">recommendedVersion</span></span> | <span data-ttu-id="bdc50-198">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-198">String</span></span> | <span data-ttu-id="bdc50-199">Rekommenderad version att uppdatera/uppgradera till</span><span class="sxs-lookup"><span data-stu-id="bdc50-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="bdc50-200">null</span><span class="sxs-lookup"><span data-stu-id="bdc50-200">null</span></span>
<span data-ttu-id="bdc50-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="bdc50-201">relatedComponent</span></span> | <span data-ttu-id="bdc50-202">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-202">String</span></span> | <span data-ttu-id="bdc50-203">Relaterad komponent i den här åtgärdsaktiviteten (som liknar den relaterade komponenten för en säkerhetsrekommendationer)</span><span class="sxs-lookup"><span data-stu-id="bdc50-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="bdc50-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="bdc50-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="bdc50-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="bdc50-205">requesterEmail</span></span> | <span data-ttu-id="bdc50-206">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-206">String</span></span> | <span data-ttu-id="bdc50-207">E-postadress skapad</span><span class="sxs-lookup"><span data-stu-id="bdc50-207">Creator email address</span></span> | <span data-ttu-id="bdc50-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bdc50-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="bdc50-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="bdc50-209">requesterId</span></span> | <span data-ttu-id="bdc50-210">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-210">String</span></span> | <span data-ttu-id="bdc50-211">Creator-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="bdc50-211">Creator object id</span></span> | <span data-ttu-id="bdc50-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="bdc50-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="bdc50-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="bdc50-213">requesterNotes</span></span> | <span data-ttu-id="bdc50-214">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-214">String</span></span> | <span data-ttu-id="bdc50-215">Anteckningarna (fri text) som skaparen har lagt till för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="bdc50-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="bdc50-216">null</span><span class="sxs-lookup"><span data-stu-id="bdc50-216">null</span></span>
<span data-ttu-id="bdc50-217">scid</span><span class="sxs-lookup"><span data-stu-id="bdc50-217">scid</span></span> | <span data-ttu-id="bdc50-218">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-218">String</span></span> | <span data-ttu-id="bdc50-219">SCID för relaterad säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="bdc50-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="bdc50-220">null</span><span class="sxs-lookup"><span data-stu-id="bdc50-220">null</span></span>
<span data-ttu-id="bdc50-221">status</span><span class="sxs-lookup"><span data-stu-id="bdc50-221">status</span></span> | <span data-ttu-id="bdc50-222">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-222">String</span></span> | <span data-ttu-id="bdc50-223">Status för åtgärdsaktivitet (Aktiv/slutförd)</span><span class="sxs-lookup"><span data-stu-id="bdc50-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="bdc50-224">Aktiv</span><span class="sxs-lookup"><span data-stu-id="bdc50-224">Active</span></span>
<span data-ttu-id="bdc50-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="bdc50-225">statusLastModifiedOn</span></span> | <span data-ttu-id="bdc50-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="bdc50-226">DateTime</span></span> | <span data-ttu-id="bdc50-227">Datum när statusfältet uppdaterades</span><span class="sxs-lookup"><span data-stu-id="bdc50-227">Date when the status field was updated</span></span> | <span data-ttu-id="bdc50-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="bdc50-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="bdc50-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="bdc50-229">targetDevices</span></span> | <span data-ttu-id="bdc50-230">Long</span><span class="sxs-lookup"><span data-stu-id="bdc50-230">Long</span></span> | <span data-ttu-id="bdc50-231">Antal exponerade enheter som denna åtgärd gäller för</span><span class="sxs-lookup"><span data-stu-id="bdc50-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="bdc50-232">43</span><span class="sxs-lookup"><span data-stu-id="bdc50-232">43</span></span>
<span data-ttu-id="bdc50-233">rubrik</span><span class="sxs-lookup"><span data-stu-id="bdc50-233">title</span></span> | <span data-ttu-id="bdc50-234">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-234">String</span></span> | <span data-ttu-id="bdc50-235">Rubrik för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="bdc50-235">Title of this remediation activity</span></span> | <span data-ttu-id="bdc50-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="bdc50-236">Microsoft Silverlight</span></span>
<span data-ttu-id="bdc50-237">skriv</span><span class="sxs-lookup"><span data-stu-id="bdc50-237">type</span></span> | <span data-ttu-id="bdc50-238">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-238">String</span></span> | <span data-ttu-id="bdc50-239">Åtgärdstyp</span><span class="sxs-lookup"><span data-stu-id="bdc50-239">Remediation type</span></span> | <span data-ttu-id="bdc50-240">Update</span><span class="sxs-lookup"><span data-stu-id="bdc50-240">Update</span></span>
<span data-ttu-id="bdc50-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="bdc50-241">vendorId</span></span> | <span data-ttu-id="bdc50-242">Sträng</span><span class="sxs-lookup"><span data-stu-id="bdc50-242">String</span></span> | <span data-ttu-id="bdc50-243">Relaterade leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="bdc50-243">Related vendor name</span></span> | <span data-ttu-id="bdc50-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="bdc50-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="bdc50-245">Exempel</span><span class="sxs-lookup"><span data-stu-id="bdc50-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="bdc50-246">Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="bdc50-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="bdc50-247">Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="bdc50-247">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bdc50-248">Se även</span><span class="sxs-lookup"><span data-stu-id="bdc50-248">See also</span></span>

- [<span data-ttu-id="bdc50-249">Åtgärdsmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="bdc50-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="bdc50-250">Lista alla åtgärdsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="bdc50-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="bdc50-251">Lista exponerade enheter av en åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="bdc50-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="bdc50-252">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="bdc50-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="bdc50-253">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="bdc50-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
