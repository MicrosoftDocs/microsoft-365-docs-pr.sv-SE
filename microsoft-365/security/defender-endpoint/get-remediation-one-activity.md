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
ms.technology: mde
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244449"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="69f37-104">Få en åtgärdsaktivitet efter ID</span><span class="sxs-lookup"><span data-stu-id="69f37-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="69f37-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="69f37-105">**Applies to:**</span></span>

- [<span data-ttu-id="69f37-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="69f37-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="69f37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69f37-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="69f37-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="69f37-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="69f37-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="69f37-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="69f37-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="69f37-110">API description</span></span>

<span data-ttu-id="69f37-111">Returnerar information för den angivna åtgärdsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="69f37-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="69f37-112">Visar samma kolumner som [Hämta all åtgärdsaktivitet](get-remediation-all-activities.md), men returnerar _endast resultat för den angivna åtgärdsaktiviteten._</span><span class="sxs-lookup"><span data-stu-id="69f37-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="69f37-113">[Läs mer om åtgärder](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="69f37-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="69f37-114">Lista en angiven åtgärdsaktivitet för (id)</span><span class="sxs-lookup"><span data-stu-id="69f37-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="69f37-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="69f37-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="69f37-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="69f37-116">Permissions</span></span>

<span data-ttu-id="69f37-117">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="69f37-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="69f37-118">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="69f37-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="69f37-119">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="69f37-119">Permission type</span></span> | <span data-ttu-id="69f37-120">Behörighet</span><span class="sxs-lookup"><span data-stu-id="69f37-120">Permission</span></span> | <span data-ttu-id="69f37-121">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="69f37-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="69f37-122">Program</span><span class="sxs-lookup"><span data-stu-id="69f37-122">Application</span></span> | <span data-ttu-id="69f37-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="69f37-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="69f37-124">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="69f37-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="69f37-125">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="69f37-125">Delegated (work or school account)</span></span> | <span data-ttu-id="69f37-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="69f37-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="69f37-127">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="69f37-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="69f37-128">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="69f37-128">Properties</span></span>

<span data-ttu-id="69f37-129">Egenskap (id)</span><span class="sxs-lookup"><span data-stu-id="69f37-129">Property (id)</span></span> | <span data-ttu-id="69f37-130">Datatyp</span><span class="sxs-lookup"><span data-stu-id="69f37-130">Data type</span></span> | <span data-ttu-id="69f37-131">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="69f37-131">Description</span></span> | <span data-ttu-id="69f37-132">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="69f37-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="69f37-133">kategori</span><span class="sxs-lookup"><span data-stu-id="69f37-133">category</span></span> | <span data-ttu-id="69f37-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-134">String</span></span> | <span data-ttu-id="69f37-135">Kategori för åtgärdsaktiviteten (konfiguration av programvara/säkerhet)</span><span class="sxs-lookup"><span data-stu-id="69f37-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="69f37-136">Programvara</span><span class="sxs-lookup"><span data-stu-id="69f37-136">Software</span></span>
<span data-ttu-id="69f37-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="69f37-137">completerEmail</span></span> | <span data-ttu-id="69f37-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-138">String</span></span> | <span data-ttu-id="69f37-139">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras e-postadress</span><span class="sxs-lookup"><span data-stu-id="69f37-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="69f37-140">null</span><span class="sxs-lookup"><span data-stu-id="69f37-140">null</span></span>
<span data-ttu-id="69f37-141">completerId</span><span class="sxs-lookup"><span data-stu-id="69f37-141">completerId</span></span> | <span data-ttu-id="69f37-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-142">String</span></span> | <span data-ttu-id="69f37-143">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras objekt-ID</span><span class="sxs-lookup"><span data-stu-id="69f37-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="69f37-144">null</span><span class="sxs-lookup"><span data-stu-id="69f37-144">null</span></span>
<span data-ttu-id="69f37-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="69f37-145">completionMethod</span></span> | <span data-ttu-id="69f37-146">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-146">String</span></span> | <span data-ttu-id="69f37-147">En åtgärdsaktivitet kan slutföras "automatiskt" (om alla enheter är korrigerade) eller "manuellt" av en person som väljer "markera som slutförd"</span><span class="sxs-lookup"><span data-stu-id="69f37-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="69f37-148">Automatisk</span><span class="sxs-lookup"><span data-stu-id="69f37-148">Automatic</span></span>
<span data-ttu-id="69f37-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="69f37-149">createdOn</span></span> | <span data-ttu-id="69f37-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="69f37-150">DateTime</span></span> | <span data-ttu-id="69f37-151">Tidpunkten då den här åtgärdsaktiviteten skapades</span><span class="sxs-lookup"><span data-stu-id="69f37-151">Time this remediation activity was created</span></span> | <span data-ttu-id="69f37-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="69f37-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="69f37-153">beskrivning</span><span class="sxs-lookup"><span data-stu-id="69f37-153">description</span></span> | <span data-ttu-id="69f37-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-154">String</span></span> | <span data-ttu-id="69f37-155">Beskrivning av den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="69f37-155">Description of this remediation activity</span></span> | <span data-ttu-id="69f37-156">Uppdatera Microsoft Silverlight till en senare version för att minimera kända säkerhetsproblem som påverkar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="69f37-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="69f37-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="69f37-157">dueOn</span></span> | <span data-ttu-id="69f37-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="69f37-158">DateTime</span></span> | <span data-ttu-id="69f37-159">Förfallodatum som skapare uppsättningen för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="69f37-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="69f37-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="69f37-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="69f37-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="69f37-161">fixedDevices</span></span> |  | <span data-ttu-id="69f37-162">Antalet enheter som har åtgärdats</span><span class="sxs-lookup"><span data-stu-id="69f37-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="69f37-163">2</span><span class="sxs-lookup"><span data-stu-id="69f37-163">2</span></span>
<span data-ttu-id="69f37-164">id</span><span class="sxs-lookup"><span data-stu-id="69f37-164">id</span></span> | <span data-ttu-id="69f37-165">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-165">String</span></span> | <span data-ttu-id="69f37-166">ID för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="69f37-166">ID of this remediation activity</span></span> | <span data-ttu-id="69f37-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="69f37-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="69f37-168">nameId</span><span class="sxs-lookup"><span data-stu-id="69f37-168">nameId</span></span> | <span data-ttu-id="69f37-169">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-169">String</span></span> | <span data-ttu-id="69f37-170">Relaterade produktnamn</span><span class="sxs-lookup"><span data-stu-id="69f37-170">Related product name</span></span> | <span data-ttu-id="69f37-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="69f37-171">Microsoft Silverlight</span></span>
<span data-ttu-id="69f37-172">prioritet</span><span class="sxs-lookup"><span data-stu-id="69f37-172">priority</span></span> | <span data-ttu-id="69f37-173">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-173">String</span></span> | <span data-ttu-id="69f37-174">Prioritet för skaparuppsättningen för den här åtgärdsaktiviteten (Hög\Medel\Låg)</span><span class="sxs-lookup"><span data-stu-id="69f37-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="69f37-175">Hög</span><span class="sxs-lookup"><span data-stu-id="69f37-175">High</span></span>
<span data-ttu-id="69f37-176">productId</span><span class="sxs-lookup"><span data-stu-id="69f37-176">productId</span></span> | <span data-ttu-id="69f37-177">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-177">String</span></span> | <span data-ttu-id="69f37-178">Relaterade produkt-ID</span><span class="sxs-lookup"><span data-stu-id="69f37-178">Related product ID</span></span> | <span data-ttu-id="69f37-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="69f37-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="69f37-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="69f37-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="69f37-181">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-181">String</span></span> | <span data-ttu-id="69f37-182">Några konfigurationsändringar kunde endast begäras för enheter utan påverkan från användare.</span><span class="sxs-lookup"><span data-stu-id="69f37-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="69f37-183">Det här värdet anger valet mellan "alla exponerade enheter" eller "endast enheter utan påverkan från användare".</span><span class="sxs-lookup"><span data-stu-id="69f37-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="69f37-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="69f37-184">AllExposedAssets</span></span>
<span data-ttu-id="69f37-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="69f37-185">rbacGroupNames</span></span> | <span data-ttu-id="69f37-186">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-186">String</span></span> | <span data-ttu-id="69f37-187">Gruppnamn för relaterade enheter</span><span class="sxs-lookup"><span data-stu-id="69f37-187">Related device group names</span></span> | <span data-ttu-id="69f37-188">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="69f37-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="69f37-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="69f37-189">recommendedProgram</span></span> | <span data-ttu-id="69f37-190">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-190">String</span></span> | <span data-ttu-id="69f37-191">Rekommenderat program att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="69f37-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="69f37-192">null</span><span class="sxs-lookup"><span data-stu-id="69f37-192">null</span></span>
<span data-ttu-id="69f37-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="69f37-193">recommendedVendor</span></span> | <span data-ttu-id="69f37-194">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-194">String</span></span> | <span data-ttu-id="69f37-195">Rekommenderad leverantör att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="69f37-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="69f37-196">null</span><span class="sxs-lookup"><span data-stu-id="69f37-196">null</span></span>
<span data-ttu-id="69f37-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="69f37-197">recommendedVersion</span></span> | <span data-ttu-id="69f37-198">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-198">String</span></span> | <span data-ttu-id="69f37-199">Rekommenderad version att uppdatera/uppgradera till</span><span class="sxs-lookup"><span data-stu-id="69f37-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="69f37-200">null</span><span class="sxs-lookup"><span data-stu-id="69f37-200">null</span></span>
<span data-ttu-id="69f37-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="69f37-201">relatedComponent</span></span> | <span data-ttu-id="69f37-202">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-202">String</span></span> | <span data-ttu-id="69f37-203">Relaterad komponent i den här åtgärdsaktiviteten (som liknar den relaterade komponenten för en säkerhetsrekommendationer)</span><span class="sxs-lookup"><span data-stu-id="69f37-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="69f37-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="69f37-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="69f37-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="69f37-205">requesterEmail</span></span> | <span data-ttu-id="69f37-206">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-206">String</span></span> | <span data-ttu-id="69f37-207">E-postadress skapad</span><span class="sxs-lookup"><span data-stu-id="69f37-207">Creator email address</span></span> | <span data-ttu-id="69f37-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="69f37-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="69f37-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="69f37-209">requesterId</span></span> | <span data-ttu-id="69f37-210">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-210">String</span></span> | <span data-ttu-id="69f37-211">Creator-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="69f37-211">Creator object id</span></span> | <span data-ttu-id="69f37-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="69f37-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="69f37-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="69f37-213">requesterNotes</span></span> | <span data-ttu-id="69f37-214">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-214">String</span></span> | <span data-ttu-id="69f37-215">Anteckningarna (fri text) som skaparen har lagt till för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="69f37-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="69f37-216">null</span><span class="sxs-lookup"><span data-stu-id="69f37-216">null</span></span>
<span data-ttu-id="69f37-217">scid</span><span class="sxs-lookup"><span data-stu-id="69f37-217">scid</span></span> | <span data-ttu-id="69f37-218">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-218">String</span></span> | <span data-ttu-id="69f37-219">SCID för relaterad säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="69f37-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="69f37-220">null</span><span class="sxs-lookup"><span data-stu-id="69f37-220">null</span></span>
<span data-ttu-id="69f37-221">status</span><span class="sxs-lookup"><span data-stu-id="69f37-221">status</span></span> | <span data-ttu-id="69f37-222">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-222">String</span></span> | <span data-ttu-id="69f37-223">Status för åtgärdsaktivitet (Aktiv/slutförd)</span><span class="sxs-lookup"><span data-stu-id="69f37-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="69f37-224">Aktiv</span><span class="sxs-lookup"><span data-stu-id="69f37-224">Active</span></span>
<span data-ttu-id="69f37-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="69f37-225">statusLastModifiedOn</span></span> | <span data-ttu-id="69f37-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="69f37-226">DateTime</span></span> | <span data-ttu-id="69f37-227">Datum när statusfältet uppdaterades</span><span class="sxs-lookup"><span data-stu-id="69f37-227">Date when the status field was updated</span></span> | <span data-ttu-id="69f37-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="69f37-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="69f37-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="69f37-229">targetDevices</span></span> | <span data-ttu-id="69f37-230">Long</span><span class="sxs-lookup"><span data-stu-id="69f37-230">Long</span></span> | <span data-ttu-id="69f37-231">Antal exponerade enheter som denna åtgärd gäller för</span><span class="sxs-lookup"><span data-stu-id="69f37-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="69f37-232">43</span><span class="sxs-lookup"><span data-stu-id="69f37-232">43</span></span>
<span data-ttu-id="69f37-233">rubrik</span><span class="sxs-lookup"><span data-stu-id="69f37-233">title</span></span> | <span data-ttu-id="69f37-234">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-234">String</span></span> | <span data-ttu-id="69f37-235">Rubrik för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="69f37-235">Title of this remediation activity</span></span> | <span data-ttu-id="69f37-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="69f37-236">Microsoft Silverlight</span></span>
<span data-ttu-id="69f37-237">skriv</span><span class="sxs-lookup"><span data-stu-id="69f37-237">type</span></span> | <span data-ttu-id="69f37-238">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-238">String</span></span> | <span data-ttu-id="69f37-239">Åtgärdstyp</span><span class="sxs-lookup"><span data-stu-id="69f37-239">Remediation type</span></span> | <span data-ttu-id="69f37-240">Uppdatera</span><span class="sxs-lookup"><span data-stu-id="69f37-240">Update</span></span>
<span data-ttu-id="69f37-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="69f37-241">vendorId</span></span> | <span data-ttu-id="69f37-242">Sträng</span><span class="sxs-lookup"><span data-stu-id="69f37-242">String</span></span> | <span data-ttu-id="69f37-243">Relaterade leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="69f37-243">Related vendor name</span></span> | <span data-ttu-id="69f37-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="69f37-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="69f37-245">Exempel</span><span class="sxs-lookup"><span data-stu-id="69f37-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="69f37-246">Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="69f37-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="69f37-247">Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="69f37-247">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="69f37-248">Se även</span><span class="sxs-lookup"><span data-stu-id="69f37-248">See also</span></span>

- [<span data-ttu-id="69f37-249">Åtgärdsmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="69f37-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="69f37-250">Lista alla åtgärdsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="69f37-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="69f37-251">Lista exponerade enheter av en åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="69f37-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="69f37-252">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="69f37-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="69f37-253">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="69f37-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
