---
title: Skapa avisering från händelse-API
description: Lär dig hur du använder API:t för att skapa en ny avisering ovanpå händelsen i Microsoft Defender för slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, avisering, information, id
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289469"
---
# <a name="create-alert-api"></a><span data-ttu-id="73805-104">Skapa aviserings-API</span><span class="sxs-lookup"><span data-stu-id="73805-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73805-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="73805-105">**Applies to:**</span></span>
- [<span data-ttu-id="73805-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="73805-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="73805-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73805-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="73805-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="73805-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="73805-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="73805-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="73805-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="73805-110">API description</span></span>

<span data-ttu-id="73805-111">Skapar ny [avisering](alerts.md) ovanpå **händelse**.</span><span class="sxs-lookup"><span data-stu-id="73805-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>

- <span data-ttu-id="73805-112">**Microsoft Defender för Endpoint-händelse** krävs för att aviseringen ska kunna skapas.</span><span class="sxs-lookup"><span data-stu-id="73805-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
- <span data-ttu-id="73805-113">Du måste ange 3 parametrar från händelsen i begäran: Händelsetid, **Maskin-ID** och  **Rapport-ID.**</span><span class="sxs-lookup"><span data-stu-id="73805-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="73805-114">Se exemplet nedan.</span><span class="sxs-lookup"><span data-stu-id="73805-114">See example below.</span></span>
- <span data-ttu-id="73805-115">Du kan använda en händelse i Advanced Hunting API eller Portal.</span><span class="sxs-lookup"><span data-stu-id="73805-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
- <span data-ttu-id="73805-116">Om det finns en öppen avisering på samma enhet med samma rubrik, slås den nya skapade aviseringen ihop med den.</span><span class="sxs-lookup"><span data-stu-id="73805-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
- <span data-ttu-id="73805-117">En automatisk undersökning startar automatiskt för aviseringar som skapas via API:t.</span><span class="sxs-lookup"><span data-stu-id="73805-117">An automatic investigation starts automatically on alerts created via the API.</span></span>

## <a name="limitations"></a><span data-ttu-id="73805-118">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="73805-118">Limitations</span></span>

1. <span data-ttu-id="73805-119">Prisbegränsningar för detta API är 15 samtal per minut.</span><span class="sxs-lookup"><span data-stu-id="73805-119">Rate limitations for this API are 15 calls per minute.</span></span>

## <a name="permissions"></a><span data-ttu-id="73805-120">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="73805-120">Permissions</span></span>

<span data-ttu-id="73805-121">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="73805-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="73805-122">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="73805-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="73805-123">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="73805-123">Permission type</span></span> | <span data-ttu-id="73805-124">Behörighet</span><span class="sxs-lookup"><span data-stu-id="73805-124">Permission</span></span> | <span data-ttu-id="73805-125">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="73805-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="73805-126">Program</span><span class="sxs-lookup"><span data-stu-id="73805-126">Application</span></span> | <span data-ttu-id="73805-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="73805-127">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="73805-128">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="73805-128">'Read and write all alerts'</span></span>
<span data-ttu-id="73805-129">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="73805-129">Delegated (work or school account)</span></span> | <span data-ttu-id="73805-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="73805-130">Alert.ReadWrite</span></span> | <span data-ttu-id="73805-131">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="73805-131">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="73805-132">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="73805-132">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="73805-133">Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="73805-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="73805-134">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="73805-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="73805-135">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="73805-135">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="73805-136">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="73805-136">Request headers</span></span>

<span data-ttu-id="73805-137">Namn</span><span class="sxs-lookup"><span data-stu-id="73805-137">Name</span></span> | <span data-ttu-id="73805-138">Typ</span><span class="sxs-lookup"><span data-stu-id="73805-138">Type</span></span> | <span data-ttu-id="73805-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="73805-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="73805-140">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="73805-140">Authorization</span></span> | <span data-ttu-id="73805-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-141">String</span></span> | <span data-ttu-id="73805-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="73805-142">Bearer {token}.</span></span> <span data-ttu-id="73805-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="73805-143">**Required**.</span></span>
<span data-ttu-id="73805-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="73805-144">Content-Type</span></span> | <span data-ttu-id="73805-145">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-145">String</span></span> | <span data-ttu-id="73805-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="73805-146">application/json.</span></span> <span data-ttu-id="73805-147">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="73805-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="73805-148">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="73805-148">Request body</span></span>

<span data-ttu-id="73805-149">Ange följande värden i brödtexten för begäran (alla är obligatoriska):</span><span class="sxs-lookup"><span data-stu-id="73805-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="73805-150">Egenskap</span><span class="sxs-lookup"><span data-stu-id="73805-150">Property</span></span> | <span data-ttu-id="73805-151">Typ</span><span class="sxs-lookup"><span data-stu-id="73805-151">Type</span></span> | <span data-ttu-id="73805-152">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="73805-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="73805-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="73805-153">eventTime</span></span> | <span data-ttu-id="73805-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="73805-154">DateTime(UTC)</span></span> | <span data-ttu-id="73805-155">Den exakta tiden för händelsen som sträng, från avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="73805-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="73805-156">t.ex. ```2018-08-03T16:45:21.7115183Z``` **Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="73805-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="73805-157">reportId</span><span class="sxs-lookup"><span data-stu-id="73805-157">reportId</span></span> | <span data-ttu-id="73805-158">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-158">String</span></span> | <span data-ttu-id="73805-159">ReportId för händelsen, från avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="73805-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="73805-160">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="73805-160">**Required**.</span></span>
<span data-ttu-id="73805-161">machineId</span><span class="sxs-lookup"><span data-stu-id="73805-161">machineId</span></span> | <span data-ttu-id="73805-162">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-162">String</span></span> | <span data-ttu-id="73805-163">ID för enheten där händelsen identifierades.</span><span class="sxs-lookup"><span data-stu-id="73805-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="73805-164">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="73805-164">**Required**.</span></span>
<span data-ttu-id="73805-165">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="73805-165">severity</span></span> | <span data-ttu-id="73805-166">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-166">String</span></span> | <span data-ttu-id="73805-167">Aviseringens allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="73805-167">Severity of the alert.</span></span> <span data-ttu-id="73805-168">Egenskapsvärdena är: "Låg", "Medel" och "Hög".</span><span class="sxs-lookup"><span data-stu-id="73805-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="73805-169">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="73805-169">**Required**.</span></span>
<span data-ttu-id="73805-170">rubrik</span><span class="sxs-lookup"><span data-stu-id="73805-170">title</span></span> | <span data-ttu-id="73805-171">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-171">String</span></span> | <span data-ttu-id="73805-172">Rubrik för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="73805-172">Title for the alert.</span></span> <span data-ttu-id="73805-173">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="73805-173">**Required**.</span></span>
<span data-ttu-id="73805-174">description</span><span class="sxs-lookup"><span data-stu-id="73805-174">description</span></span> | <span data-ttu-id="73805-175">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-175">String</span></span> | <span data-ttu-id="73805-176">Beskrivning av aviseringen.</span><span class="sxs-lookup"><span data-stu-id="73805-176">Description of the alert.</span></span> <span data-ttu-id="73805-177">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="73805-177">**Required**.</span></span>
<span data-ttu-id="73805-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="73805-178">recommendedAction</span></span>| <span data-ttu-id="73805-179">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-179">String</span></span> | <span data-ttu-id="73805-180">En åtgärd som rekommenderas att vidtas av säkerhetsofficer när du analyserar aviseringen.</span><span class="sxs-lookup"><span data-stu-id="73805-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="73805-181">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="73805-181">**Required**.</span></span>
<span data-ttu-id="73805-182">kategori</span><span class="sxs-lookup"><span data-stu-id="73805-182">category</span></span>| <span data-ttu-id="73805-183">Sträng</span><span class="sxs-lookup"><span data-stu-id="73805-183">String</span></span> | <span data-ttu-id="73805-184">Kategorin för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="73805-184">Category of the alert.</span></span> <span data-ttu-id="73805-185">Egenskapsvärdena är: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "Malware", "Malware", "Per persist", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span><span class="sxs-lookup"><span data-stu-id="73805-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="73805-186">Svar</span><span class="sxs-lookup"><span data-stu-id="73805-186">Response</span></span>

<span data-ttu-id="73805-187">Om det lyckas returnerar den här metoden 200 OK och ett [nytt aviseringsobjekt](alerts.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="73805-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="73805-188">Om en händelse med de angivna egenskaperna _(reportId,_ _eventTime_ och _machineId)_ inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="73805-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="73805-189">Exempel</span><span class="sxs-lookup"><span data-stu-id="73805-189">Example</span></span>

### <a name="request"></a><span data-ttu-id="73805-190">Begäran</span><span class="sxs-lookup"><span data-stu-id="73805-190">Request</span></span>

<span data-ttu-id="73805-191">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="73805-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
