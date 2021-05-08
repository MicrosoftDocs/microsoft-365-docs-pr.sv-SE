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
ms.technology: mde
ms.openlocfilehash: cf7c79cb6cc76af88ce0293a013ba6edbf435d8c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245498"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="a3f8d-104">Lista alla åtgärdsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="a3f8d-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a3f8d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a3f8d-105">**Applies to:**</span></span>

- [<span data-ttu-id="a3f8d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3f8d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a3f8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3f8d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a3f8d-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a3f8d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a3f8d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a3f8d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="a3f8d-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="a3f8d-110">API description</span></span>

<span data-ttu-id="a3f8d-111">Returnerar information om alla åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a3f8d-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="a3f8d-112">[Läs mer om åtgärder](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="a3f8d-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="a3f8d-113">**URL:** HÄMTA: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="a3f8d-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="a3f8d-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="a3f8d-114">Permissions</span></span>

<span data-ttu-id="a3f8d-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="a3f8d-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a3f8d-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a3f8d-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="a3f8d-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="a3f8d-117">Permission type</span></span> | <span data-ttu-id="a3f8d-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="a3f8d-118">Permission</span></span> | <span data-ttu-id="a3f8d-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="a3f8d-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a3f8d-120">Program</span><span class="sxs-lookup"><span data-stu-id="a3f8d-120">Application</span></span> | <span data-ttu-id="a3f8d-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="a3f8d-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="a3f8d-122">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="a3f8d-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="a3f8d-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="a3f8d-123">Delegated (work or school account)</span></span> | <span data-ttu-id="a3f8d-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="a3f8d-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="a3f8d-125">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="a3f8d-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="a3f8d-126">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="a3f8d-126">Properties</span></span>

<span data-ttu-id="a3f8d-127">Egenskap (id)</span><span class="sxs-lookup"><span data-stu-id="a3f8d-127">Property (id)</span></span> | <span data-ttu-id="a3f8d-128">Datatyp</span><span class="sxs-lookup"><span data-stu-id="a3f8d-128">Data type</span></span> | <span data-ttu-id="a3f8d-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a3f8d-129">Description</span></span> | <span data-ttu-id="a3f8d-130">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="a3f8d-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="a3f8d-131">kategori</span><span class="sxs-lookup"><span data-stu-id="a3f8d-131">category</span></span> | <span data-ttu-id="a3f8d-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-132">String</span></span> | <span data-ttu-id="a3f8d-133">Kategori för åtgärdsaktiviteten (konfiguration av programvara/säkerhet)</span><span class="sxs-lookup"><span data-stu-id="a3f8d-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="a3f8d-134">Programvara</span><span class="sxs-lookup"><span data-stu-id="a3f8d-134">Software</span></span>
<span data-ttu-id="a3f8d-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="a3f8d-135">completerEmail</span></span> | <span data-ttu-id="a3f8d-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-136">String</span></span> | <span data-ttu-id="a3f8d-137">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras e-postadress</span><span class="sxs-lookup"><span data-stu-id="a3f8d-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="a3f8d-138">null</span><span class="sxs-lookup"><span data-stu-id="a3f8d-138">null</span></span>
<span data-ttu-id="a3f8d-139">completerId</span><span class="sxs-lookup"><span data-stu-id="a3f8d-139">completerId</span></span> | <span data-ttu-id="a3f8d-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-140">String</span></span> | <span data-ttu-id="a3f8d-141">Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras objekt-ID</span><span class="sxs-lookup"><span data-stu-id="a3f8d-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="a3f8d-142">null</span><span class="sxs-lookup"><span data-stu-id="a3f8d-142">null</span></span>
<span data-ttu-id="a3f8d-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="a3f8d-143">completionMethod</span></span> | <span data-ttu-id="a3f8d-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-144">String</span></span> | <span data-ttu-id="a3f8d-145">En åtgärdsaktivitet kan slutföras "automatiskt" (om alla enheter är korrigerade) eller "manuellt" av en person som väljer "markera som slutförd"</span><span class="sxs-lookup"><span data-stu-id="a3f8d-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="a3f8d-146">Automatisk</span><span class="sxs-lookup"><span data-stu-id="a3f8d-146">Automatic</span></span>
<span data-ttu-id="a3f8d-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="a3f8d-147">createdOn</span></span> | <span data-ttu-id="a3f8d-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="a3f8d-148">DateTime</span></span> | <span data-ttu-id="a3f8d-149">Tidpunkten då den här åtgärdsaktiviteten skapades</span><span class="sxs-lookup"><span data-stu-id="a3f8d-149">Time this remediation activity was created</span></span> | <span data-ttu-id="a3f8d-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="a3f8d-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="a3f8d-151">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a3f8d-151">description</span></span> | <span data-ttu-id="a3f8d-152">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-152">String</span></span> | <span data-ttu-id="a3f8d-153">Beskrivning av den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="a3f8d-153">Description of this remediation activity</span></span> | <span data-ttu-id="a3f8d-154">Uppdatera Microsoft Silverlight till en senare version för att minimera kända säkerhetsproblem som påverkar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="a3f8d-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="a3f8d-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="a3f8d-155">dueOn</span></span> | <span data-ttu-id="a3f8d-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="a3f8d-156">DateTime</span></span> | <span data-ttu-id="a3f8d-157">Förfallodatum som skapare uppsättningen för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="a3f8d-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="a3f8d-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="a3f8d-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="a3f8d-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="a3f8d-159">fixedDevices</span></span> | <span data-ttu-id="a3f8d-160">.</span><span class="sxs-lookup"><span data-stu-id="a3f8d-160">.</span></span> | <span data-ttu-id="a3f8d-161">Antalet enheter som har åtgärdats</span><span class="sxs-lookup"><span data-stu-id="a3f8d-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="a3f8d-162">2</span><span class="sxs-lookup"><span data-stu-id="a3f8d-162">2</span></span>
<span data-ttu-id="a3f8d-163">id</span><span class="sxs-lookup"><span data-stu-id="a3f8d-163">id</span></span> | <span data-ttu-id="a3f8d-164">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-164">String</span></span> | <span data-ttu-id="a3f8d-165">ID för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="a3f8d-165">ID of this remediation activity</span></span> | <span data-ttu-id="a3f8d-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="a3f8d-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="a3f8d-167">nameId</span><span class="sxs-lookup"><span data-stu-id="a3f8d-167">nameId</span></span> | <span data-ttu-id="a3f8d-168">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-168">String</span></span> | <span data-ttu-id="a3f8d-169">Relaterade produktnamn</span><span class="sxs-lookup"><span data-stu-id="a3f8d-169">Related product name</span></span> | <span data-ttu-id="a3f8d-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="a3f8d-170">Microsoft Silverlight</span></span>
<span data-ttu-id="a3f8d-171">prioritet</span><span class="sxs-lookup"><span data-stu-id="a3f8d-171">priority</span></span> | <span data-ttu-id="a3f8d-172">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-172">String</span></span> | <span data-ttu-id="a3f8d-173">Prioritet för skaparuppsättningen för den här åtgärdsaktiviteten (Hög\Medel\Låg)</span><span class="sxs-lookup"><span data-stu-id="a3f8d-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="a3f8d-174">Hög</span><span class="sxs-lookup"><span data-stu-id="a3f8d-174">High</span></span>
<span data-ttu-id="a3f8d-175">productId</span><span class="sxs-lookup"><span data-stu-id="a3f8d-175">productId</span></span> | <span data-ttu-id="a3f8d-176">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-176">String</span></span> | <span data-ttu-id="a3f8d-177">Relaterade produkt-ID</span><span class="sxs-lookup"><span data-stu-id="a3f8d-177">Related product ID</span></span> | <span data-ttu-id="a3f8d-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="a3f8d-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="a3f8d-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="a3f8d-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="a3f8d-180">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-180">String</span></span> | <span data-ttu-id="a3f8d-181">Några konfigurationsändringar kunde endast begäras för enheter utan påverkan från användare.</span><span class="sxs-lookup"><span data-stu-id="a3f8d-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="a3f8d-182">Det här värdet anger valet mellan "alla exponerade enheter" eller "endast enheter utan påverkan från användare".</span><span class="sxs-lookup"><span data-stu-id="a3f8d-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="a3f8d-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="a3f8d-183">AllExposedAssets</span></span>
<span data-ttu-id="a3f8d-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="a3f8d-184">rbacGroupNames</span></span> | <span data-ttu-id="a3f8d-185">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-185">String</span></span> | <span data-ttu-id="a3f8d-186">Gruppnamn för relaterade enheter</span><span class="sxs-lookup"><span data-stu-id="a3f8d-186">Related device group names</span></span> | <span data-ttu-id="a3f8d-187">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="a3f8d-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="a3f8d-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="a3f8d-188">recommendedProgram</span></span> | <span data-ttu-id="a3f8d-189">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-189">String</span></span> | <span data-ttu-id="a3f8d-190">Rekommenderat program att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="a3f8d-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="a3f8d-191">null</span><span class="sxs-lookup"><span data-stu-id="a3f8d-191">null</span></span>
<span data-ttu-id="a3f8d-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="a3f8d-192">recommendedVendor</span></span> | <span data-ttu-id="a3f8d-193">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-193">String</span></span> | <span data-ttu-id="a3f8d-194">Rekommenderad leverantör att uppgradera till</span><span class="sxs-lookup"><span data-stu-id="a3f8d-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="a3f8d-195">null</span><span class="sxs-lookup"><span data-stu-id="a3f8d-195">null</span></span>
<span data-ttu-id="a3f8d-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="a3f8d-196">recommendedVersion</span></span> | <span data-ttu-id="a3f8d-197">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-197">String</span></span> | <span data-ttu-id="a3f8d-198">Rekommenderad version att uppdatera/uppgradera till</span><span class="sxs-lookup"><span data-stu-id="a3f8d-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="a3f8d-199">null</span><span class="sxs-lookup"><span data-stu-id="a3f8d-199">null</span></span>
<span data-ttu-id="a3f8d-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="a3f8d-200">relatedComponent</span></span> | <span data-ttu-id="a3f8d-201">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-201">String</span></span> | <span data-ttu-id="a3f8d-202">Relaterad komponent i den här åtgärdsaktiviteten (som liknar den relaterade komponenten för en säkerhetsrekommendationer)</span><span class="sxs-lookup"><span data-stu-id="a3f8d-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="a3f8d-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="a3f8d-203">Microsoft Silverlight</span></span>
<span data-ttu-id="a3f8d-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="a3f8d-204">requesterEmail</span></span> | <span data-ttu-id="a3f8d-205">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-205">String</span></span> | <span data-ttu-id="a3f8d-206">E-postadress skapad</span><span class="sxs-lookup"><span data-stu-id="a3f8d-206">Creator email address</span></span> | <span data-ttu-id="a3f8d-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3f8d-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="a3f8d-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="a3f8d-208">requesterId</span></span> | <span data-ttu-id="a3f8d-209">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-209">String</span></span> | <span data-ttu-id="a3f8d-210">Creator-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="a3f8d-210">Creator object id</span></span> | <span data-ttu-id="a3f8d-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="a3f8d-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="a3f8d-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="a3f8d-212">requesterNotes</span></span> | <span data-ttu-id="a3f8d-213">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-213">String</span></span> | <span data-ttu-id="a3f8d-214">Anteckningarna (fri text) som skaparen har lagt till för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="a3f8d-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="a3f8d-215">null</span><span class="sxs-lookup"><span data-stu-id="a3f8d-215">null</span></span>
<span data-ttu-id="a3f8d-216">scid</span><span class="sxs-lookup"><span data-stu-id="a3f8d-216">scid</span></span> | <span data-ttu-id="a3f8d-217">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-217">String</span></span> | <span data-ttu-id="a3f8d-218">SCID för relaterad säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="a3f8d-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="a3f8d-219">null</span><span class="sxs-lookup"><span data-stu-id="a3f8d-219">null</span></span>
<span data-ttu-id="a3f8d-220">status</span><span class="sxs-lookup"><span data-stu-id="a3f8d-220">status</span></span> | <span data-ttu-id="a3f8d-221">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-221">String</span></span> | <span data-ttu-id="a3f8d-222">Status för åtgärdsaktivitet (Aktiv/slutförd)</span><span class="sxs-lookup"><span data-stu-id="a3f8d-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="a3f8d-223">Aktiv</span><span class="sxs-lookup"><span data-stu-id="a3f8d-223">Active</span></span>
<span data-ttu-id="a3f8d-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="a3f8d-224">statusLastModifiedOn</span></span> | <span data-ttu-id="a3f8d-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="a3f8d-225">DateTime</span></span> | <span data-ttu-id="a3f8d-226">Datum när statusfältet uppdaterades</span><span class="sxs-lookup"><span data-stu-id="a3f8d-226">Date when the status field was updated</span></span> | <span data-ttu-id="a3f8d-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="a3f8d-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="a3f8d-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="a3f8d-228">targetDevices</span></span> | <span data-ttu-id="a3f8d-229">Long</span><span class="sxs-lookup"><span data-stu-id="a3f8d-229">Long</span></span> | <span data-ttu-id="a3f8d-230">Antal exponerade enheter som denna åtgärd gäller för</span><span class="sxs-lookup"><span data-stu-id="a3f8d-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="a3f8d-231">43</span><span class="sxs-lookup"><span data-stu-id="a3f8d-231">43</span></span>
<span data-ttu-id="a3f8d-232">rubrik</span><span class="sxs-lookup"><span data-stu-id="a3f8d-232">title</span></span> | <span data-ttu-id="a3f8d-233">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-233">String</span></span> | <span data-ttu-id="a3f8d-234">Rubrik för den här åtgärdsaktiviteten</span><span class="sxs-lookup"><span data-stu-id="a3f8d-234">Title of this remediation activity</span></span> | <span data-ttu-id="a3f8d-235">Uppdatera Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="a3f8d-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="a3f8d-236">skriv</span><span class="sxs-lookup"><span data-stu-id="a3f8d-236">type</span></span> | <span data-ttu-id="a3f8d-237">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-237">String</span></span> | <span data-ttu-id="a3f8d-238">Åtgärdstyp</span><span class="sxs-lookup"><span data-stu-id="a3f8d-238">Remediation type</span></span> | <span data-ttu-id="a3f8d-239">Uppdatera</span><span class="sxs-lookup"><span data-stu-id="a3f8d-239">Update</span></span>
<span data-ttu-id="a3f8d-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="a3f8d-240">vendorId</span></span> | <span data-ttu-id="a3f8d-241">Sträng</span><span class="sxs-lookup"><span data-stu-id="a3f8d-241">String</span></span> | <span data-ttu-id="a3f8d-242">Relaterade leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="a3f8d-242">Related vendor name</span></span> | <span data-ttu-id="a3f8d-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="a3f8d-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="a3f8d-244">Exempel</span><span class="sxs-lookup"><span data-stu-id="a3f8d-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="a3f8d-245">Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="a3f8d-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="a3f8d-246">Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="a3f8d-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a3f8d-247">Se även</span><span class="sxs-lookup"><span data-stu-id="a3f8d-247">See also</span></span>

- [<span data-ttu-id="a3f8d-248">Åtgärdsmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="a3f8d-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="a3f8d-249">Få en åtgärdsaktivitet efter ID</span><span class="sxs-lookup"><span data-stu-id="a3f8d-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="a3f8d-250">Lista exponerade enheter av en åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="a3f8d-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="a3f8d-251">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="a3f8d-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="a3f8d-252">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="a3f8d-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
