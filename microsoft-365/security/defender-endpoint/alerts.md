---
title: API för att hämta aviseringar
description: Läs mer om metoder och egenskaper för resurstypen Avisering i Microsoft Defender för slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4997d7118b139d993ed94ed917137ca107940e46
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199627"
---
# <a name="alert-resource-type"></a><span data-ttu-id="c0a51-104">Aviseringsresurstyp</span><span class="sxs-lookup"><span data-stu-id="c0a51-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0a51-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c0a51-105">**Applies to:**</span></span>
- [<span data-ttu-id="c0a51-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c0a51-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="c0a51-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c0a51-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c0a51-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c0a51-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="c0a51-109">Metoder</span><span class="sxs-lookup"><span data-stu-id="c0a51-109">Methods</span></span>

<span data-ttu-id="c0a51-110">Metod</span><span class="sxs-lookup"><span data-stu-id="c0a51-110">Method</span></span> |<span data-ttu-id="c0a51-111">Returtyp</span><span class="sxs-lookup"><span data-stu-id="c0a51-111">Return Type</span></span> |<span data-ttu-id="c0a51-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c0a51-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="c0a51-113">Få en avisering</span><span class="sxs-lookup"><span data-stu-id="c0a51-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="c0a51-114">Avisering</span><span class="sxs-lookup"><span data-stu-id="c0a51-114">Alert</span></span>](alerts.md) | <span data-ttu-id="c0a51-115">Få ett enda [aviseringsobjekt.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c0a51-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="c0a51-116">Listaviseringar</span><span class="sxs-lookup"><span data-stu-id="c0a51-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="c0a51-117">[Aviseringssamling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c0a51-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="c0a51-118">Samling [med listaviseringar.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c0a51-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="c0a51-119">Uppdateringsavisering</span><span class="sxs-lookup"><span data-stu-id="c0a51-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="c0a51-120">Avisering</span><span class="sxs-lookup"><span data-stu-id="c0a51-120">Alert</span></span>](alerts.md) | <span data-ttu-id="c0a51-121">Uppdatera specifik [avisering](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="c0a51-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="c0a51-122">Batchuppdateringsaviseringar</span><span class="sxs-lookup"><span data-stu-id="c0a51-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="c0a51-123">Uppdatera en uppsättning [aviseringar](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="c0a51-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="c0a51-124">Skapa avisering</span><span class="sxs-lookup"><span data-stu-id="c0a51-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="c0a51-125">Avisering</span><span class="sxs-lookup"><span data-stu-id="c0a51-125">Alert</span></span>](alerts.md)|<span data-ttu-id="c0a51-126">Skapa en avisering baserat på händelsedata från [Avancerad sökning.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="c0a51-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="c0a51-127">Visa relaterade domäner</span><span class="sxs-lookup"><span data-stu-id="c0a51-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="c0a51-128">Domänsamling</span><span class="sxs-lookup"><span data-stu-id="c0a51-128">Domain collection</span></span>| <span data-ttu-id="c0a51-129">List-URL:er som är kopplade till aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="c0a51-130">Lista relaterade filer</span><span class="sxs-lookup"><span data-stu-id="c0a51-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="c0a51-131">[Filsamling](files.md)</span><span class="sxs-lookup"><span data-stu-id="c0a51-131">[File](files.md) collection</span></span> |  <span data-ttu-id="c0a51-132">Lista de [filenheter](files.md) som är associerade med [aviseringen](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="c0a51-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="c0a51-133">Lista relaterade IP-adresser</span><span class="sxs-lookup"><span data-stu-id="c0a51-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="c0a51-134">IP-samling</span><span class="sxs-lookup"><span data-stu-id="c0a51-134">IP collection</span></span> | <span data-ttu-id="c0a51-135">List-IP:er som är associerade med aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="c0a51-136">Skaffa relaterade datorer</span><span class="sxs-lookup"><span data-stu-id="c0a51-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="c0a51-137">Dator</span><span class="sxs-lookup"><span data-stu-id="c0a51-137">Machine</span></span>](machine.md) | <span data-ttu-id="c0a51-138">Den [dator](machine.md) som är kopplad till [aviseringen](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="c0a51-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="c0a51-139">Skaffa relaterade användare</span><span class="sxs-lookup"><span data-stu-id="c0a51-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="c0a51-140">Användare</span><span class="sxs-lookup"><span data-stu-id="c0a51-140">User</span></span>](user.md) | <span data-ttu-id="c0a51-141">Användaren [som](user.md) är kopplad till [aviseringen](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="c0a51-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="c0a51-142">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="c0a51-142">Properties</span></span>

<span data-ttu-id="c0a51-143">Egenskap</span><span class="sxs-lookup"><span data-stu-id="c0a51-143">Property</span></span> |    <span data-ttu-id="c0a51-144">Skriv</span><span class="sxs-lookup"><span data-stu-id="c0a51-144">Type</span></span>    |    <span data-ttu-id="c0a51-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c0a51-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="c0a51-146">id</span><span class="sxs-lookup"><span data-stu-id="c0a51-146">id</span></span> | <span data-ttu-id="c0a51-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-147">String</span></span> | <span data-ttu-id="c0a51-148">Aviserings-ID.</span><span class="sxs-lookup"><span data-stu-id="c0a51-148">Alert ID.</span></span>
<span data-ttu-id="c0a51-149">rubrik</span><span class="sxs-lookup"><span data-stu-id="c0a51-149">title</span></span> | <span data-ttu-id="c0a51-150">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-150">String</span></span> | <span data-ttu-id="c0a51-151">Aviseringsrubrik.</span><span class="sxs-lookup"><span data-stu-id="c0a51-151">Alert title.</span></span>
<span data-ttu-id="c0a51-152">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c0a51-152">description</span></span> | <span data-ttu-id="c0a51-153">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-153">String</span></span> | <span data-ttu-id="c0a51-154">Aviseringsbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="c0a51-154">Alert description.</span></span>
<span data-ttu-id="c0a51-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="c0a51-155">alertCreationTime</span></span> | <span data-ttu-id="c0a51-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c0a51-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="c0a51-157">Datum och tid (i UTC) som aviseringen skapades.</span><span class="sxs-lookup"><span data-stu-id="c0a51-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="c0a51-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="c0a51-158">lastEventTime</span></span> | <span data-ttu-id="c0a51-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c0a51-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="c0a51-160">Den sista förekomsten av händelsen som utlöste aviseringen på samma enhet.</span><span class="sxs-lookup"><span data-stu-id="c0a51-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="c0a51-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="c0a51-161">firstEventTime</span></span> | <span data-ttu-id="c0a51-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c0a51-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="c0a51-163">Den första förekomsten av händelsen som utlöste aviseringen på enheten.</span><span class="sxs-lookup"><span data-stu-id="c0a51-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="c0a51-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="c0a51-164">lastUpdateTime</span></span> | <span data-ttu-id="c0a51-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c0a51-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="c0a51-166">Datum och tid (i UTC) som aviseringen uppdaterades senast.</span><span class="sxs-lookup"><span data-stu-id="c0a51-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="c0a51-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="c0a51-167">resolvedTime</span></span> | <span data-ttu-id="c0a51-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c0a51-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="c0a51-169">Datum och tid då statusen för aviseringen ändrades till Löst.</span><span class="sxs-lookup"><span data-stu-id="c0a51-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="c0a51-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="c0a51-170">incidentId</span></span> | <span data-ttu-id="c0a51-171">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="c0a51-171">Nullable Long</span></span> | <span data-ttu-id="c0a51-172">[Incident-ID](view-incidents-queue.md) för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="c0a51-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="c0a51-173">investigationId</span></span> | <span data-ttu-id="c0a51-174">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="c0a51-174">Nullable Long</span></span> | <span data-ttu-id="c0a51-175">[Undersöknings-ID](automated-investigations.md) relaterat till aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="c0a51-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="c0a51-176">investigationState</span></span> | <span data-ttu-id="c0a51-177">Nullbar uppräkning</span><span class="sxs-lookup"><span data-stu-id="c0a51-177">Nullable Enum</span></span> | <span data-ttu-id="c0a51-178">Aktuell status för [undersökningen](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="c0a51-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="c0a51-179">Möjliga värden är: "Okänt", "Avslutat", "SuccessfullyRemediated", 'SuppressedAlert', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="c0a51-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="c0a51-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="c0a51-180">assignedTo</span></span> | <span data-ttu-id="c0a51-181">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-181">String</span></span> | <span data-ttu-id="c0a51-182">Ägaren av aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-182">Owner of the alert.</span></span>
<span data-ttu-id="c0a51-183">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="c0a51-183">severity</span></span> | <span data-ttu-id="c0a51-184">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="c0a51-184">Enum</span></span> | <span data-ttu-id="c0a51-185">Aviseringens allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="c0a51-185">Severity of the alert.</span></span> <span data-ttu-id="c0a51-186">Möjliga värden är: "UnSpecified", 'Informational', 'Low', 'Medium' och 'High'.</span><span class="sxs-lookup"><span data-stu-id="c0a51-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="c0a51-187">status</span><span class="sxs-lookup"><span data-stu-id="c0a51-187">status</span></span> | <span data-ttu-id="c0a51-188">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="c0a51-188">Enum</span></span> | <span data-ttu-id="c0a51-189">Anger aktuell status för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="c0a51-190">Möjliga värden är: "Okänt", "Nytt", "InProgress" och "Löst".</span><span class="sxs-lookup"><span data-stu-id="c0a51-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="c0a51-191">klassificering</span><span class="sxs-lookup"><span data-stu-id="c0a51-191">classification</span></span> | <span data-ttu-id="c0a51-192">Nullbar uppräkning</span><span class="sxs-lookup"><span data-stu-id="c0a51-192">Nullable Enum</span></span> | <span data-ttu-id="c0a51-193">Specifikation för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-193">Specification of the alert.</span></span> <span data-ttu-id="c0a51-194">Möjliga värden är: "Okänt", "FalsktPositiv", "SantPositiv".</span><span class="sxs-lookup"><span data-stu-id="c0a51-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="c0a51-195">determination</span><span class="sxs-lookup"><span data-stu-id="c0a51-195">determination</span></span> | <span data-ttu-id="c0a51-196">Nullbar uppräkning</span><span class="sxs-lookup"><span data-stu-id="c0a51-196">Nullable Enum</span></span> | <span data-ttu-id="c0a51-197">Anger om aviseringen är bestämd.</span><span class="sxs-lookup"><span data-stu-id="c0a51-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="c0a51-198">Möjliga värden är: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span><span class="sxs-lookup"><span data-stu-id="c0a51-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="c0a51-199">kategori</span><span class="sxs-lookup"><span data-stu-id="c0a51-199">category</span></span>| <span data-ttu-id="c0a51-200">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-200">String</span></span> | <span data-ttu-id="c0a51-201">Kategorin för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-201">Category of the alert.</span></span>
<span data-ttu-id="c0a51-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="c0a51-202">detectionSource</span></span> | <span data-ttu-id="c0a51-203">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-203">String</span></span> | <span data-ttu-id="c0a51-204">Identifieringskälla.</span><span class="sxs-lookup"><span data-stu-id="c0a51-204">Detection source.</span></span>
<span data-ttu-id="c0a51-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="c0a51-205">threatFamilyName</span></span> | <span data-ttu-id="c0a51-206">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-206">String</span></span> | <span data-ttu-id="c0a51-207">Hotfamilj.</span><span class="sxs-lookup"><span data-stu-id="c0a51-207">Threat family.</span></span>
<span data-ttu-id="c0a51-208">threatName</span><span class="sxs-lookup"><span data-stu-id="c0a51-208">threatName</span></span> | <span data-ttu-id="c0a51-209">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-209">String</span></span> | <span data-ttu-id="c0a51-210">Hotnamn.</span><span class="sxs-lookup"><span data-stu-id="c0a51-210">Threat name.</span></span>
<span data-ttu-id="c0a51-211">machineId</span><span class="sxs-lookup"><span data-stu-id="c0a51-211">machineId</span></span> | <span data-ttu-id="c0a51-212">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-212">String</span></span> | <span data-ttu-id="c0a51-213">ID för en [maskin](machine.md) entitet som är associerad med aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="c0a51-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="c0a51-214">computerDnsName</span></span> | <span data-ttu-id="c0a51-215">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-215">String</span></span> | <span data-ttu-id="c0a51-216">[fullständigt](machine.md) kvalificerat namn.</span><span class="sxs-lookup"><span data-stu-id="c0a51-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="c0a51-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="c0a51-217">aadTenantId</span></span> | <span data-ttu-id="c0a51-218">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-218">String</span></span> | <span data-ttu-id="c0a51-219">Azure Active Directory-ID.</span><span class="sxs-lookup"><span data-stu-id="c0a51-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="c0a51-220">anslutetId</span><span class="sxs-lookup"><span data-stu-id="c0a51-220">detectorId</span></span> | <span data-ttu-id="c0a51-221">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0a51-221">String</span></span> | <span data-ttu-id="c0a51-222">ID för den som utlöste aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="c0a51-223">kommentarer</span><span class="sxs-lookup"><span data-stu-id="c0a51-223">comments</span></span> | <span data-ttu-id="c0a51-224">Lista med aviseringskommentarer</span><span class="sxs-lookup"><span data-stu-id="c0a51-224">List of Alert comments</span></span> | <span data-ttu-id="c0a51-225">Aviseringskommentarsobjekt innehåller: kommentarssträng, createdBy-sträng och createTime-datumtid.</span><span class="sxs-lookup"><span data-stu-id="c0a51-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="c0a51-226">Bevis</span><span class="sxs-lookup"><span data-stu-id="c0a51-226">Evidence</span></span> | <span data-ttu-id="c0a51-227">Lista med varningsbevis</span><span class="sxs-lookup"><span data-stu-id="c0a51-227">List of Alert evidence</span></span> | <span data-ttu-id="c0a51-228">Bevis som är relaterade till aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0a51-228">Evidence related to the alert.</span></span> <span data-ttu-id="c0a51-229">Se exemplet nedan.</span><span class="sxs-lookup"><span data-stu-id="c0a51-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="c0a51-230">Svarsexempel för att få en enda avisering:</span><span class="sxs-lookup"><span data-stu-id="c0a51-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
