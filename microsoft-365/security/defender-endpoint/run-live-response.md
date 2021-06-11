---
title: Köra svarskommandon i livesändning på en enhet
description: Lär dig hur du kör en sekvens av kommandon för livesvar på en enhet.
keywords: apis, graph api, API som stöds, ladda upp till bibliotek
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879766"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="eecfc-104">Köra svarskommandon i livesändning på en enhet</span><span class="sxs-lookup"><span data-stu-id="eecfc-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eecfc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="eecfc-105">**Applies to:**</span></span>
- [<span data-ttu-id="eecfc-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="eecfc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="eecfc-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="eecfc-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eecfc-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="eecfc-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="eecfc-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="eecfc-109">API description</span></span>

<span data-ttu-id="eecfc-110">Kör en sekvens av kommandon för livesvar på en enhet</span><span class="sxs-lookup"><span data-stu-id="eecfc-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="eecfc-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="eecfc-111">Limitations</span></span>

1.  <span data-ttu-id="eecfc-112">Prisbegränsningar för detta API är 10 samtal per minut (ytterligare förfrågningar besvaras med HTTP 429).</span><span class="sxs-lookup"><span data-stu-id="eecfc-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="eecfc-113">25 samtidiga sessioner (förfrågningar som överskrider begränsningsgränsen får svaret "429 – För många begäranden").</span><span class="sxs-lookup"><span data-stu-id="eecfc-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="eecfc-114">Om datorn inte är tillgänglig köas sessionen i upp till 3 dagar.</span><span class="sxs-lookup"><span data-stu-id="eecfc-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="eecfc-115">Tidsgränser för RunScript-kommandon efter 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="eecfc-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="eecfc-116">När ett live-svarskommando inte utför alla följda åtgärder.</span><span class="sxs-lookup"><span data-stu-id="eecfc-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="eecfc-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="eecfc-117">Permissions</span></span>

<span data-ttu-id="eecfc-118">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="eecfc-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eecfc-119">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="eecfc-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="eecfc-120">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="eecfc-120">Permission type</span></span>                    | <span data-ttu-id="eecfc-121">Behörighet</span><span class="sxs-lookup"><span data-stu-id="eecfc-121">Permission</span></span>           | <span data-ttu-id="eecfc-122">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="eecfc-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="eecfc-123">Program</span><span class="sxs-lookup"><span data-stu-id="eecfc-123">Application</span></span>                        | <span data-ttu-id="eecfc-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="eecfc-124">Machine.LiveResponse</span></span> | <span data-ttu-id="eecfc-125">Köra livesvar på en viss dator</span><span class="sxs-lookup"><span data-stu-id="eecfc-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="eecfc-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="eecfc-126">Delegated (work or school account)</span></span> | <span data-ttu-id="eecfc-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="eecfc-127">Machine.LiveResponse</span></span> | <span data-ttu-id="eecfc-128">Köra livesvar på en viss dator</span><span class="sxs-lookup"><span data-stu-id="eecfc-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="eecfc-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="eecfc-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="eecfc-130">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="eecfc-130">Request headers</span></span>

| <span data-ttu-id="eecfc-131">Namn</span><span class="sxs-lookup"><span data-stu-id="eecfc-131">Name</span></span>      | <span data-ttu-id="eecfc-132">Typ</span><span class="sxs-lookup"><span data-stu-id="eecfc-132">Type</span></span> | <span data-ttu-id="eecfc-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="eecfc-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="eecfc-134">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="eecfc-134">Authorization</span></span> | <span data-ttu-id="eecfc-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="eecfc-135">String</span></span>   | <span data-ttu-id="eecfc-136">Bearer\<token>\.</span><span class="sxs-lookup"><span data-stu-id="eecfc-136">Bearer\<token>\.</span></span> <span data-ttu-id="eecfc-137">Obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="eecfc-137">Required.</span></span>   |
| <span data-ttu-id="eecfc-138">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="eecfc-138">Content-Type</span></span>  | <span data-ttu-id="eecfc-139">sträng</span><span class="sxs-lookup"><span data-stu-id="eecfc-139">string</span></span>   | <span data-ttu-id="eecfc-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="eecfc-140">application/json.</span></span> <span data-ttu-id="eecfc-141">Obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="eecfc-141">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="eecfc-142">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="eecfc-142">Request body</span></span>

| <span data-ttu-id="eecfc-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="eecfc-143">Parameter</span></span> | <span data-ttu-id="eecfc-144">Typ</span><span class="sxs-lookup"><span data-stu-id="eecfc-144">Type</span></span> | <span data-ttu-id="eecfc-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="eecfc-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="eecfc-146">Kommentar</span><span class="sxs-lookup"><span data-stu-id="eecfc-146">Comment</span></span>       | <span data-ttu-id="eecfc-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="eecfc-147">String</span></span>   | <span data-ttu-id="eecfc-148">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="eecfc-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="eecfc-149">Kommandon</span><span class="sxs-lookup"><span data-stu-id="eecfc-149">Commands</span></span>      | <span data-ttu-id="eecfc-150">Matris</span><span class="sxs-lookup"><span data-stu-id="eecfc-150">Array</span></span>    | <span data-ttu-id="eecfc-151">Kommandon som ska köras.</span><span class="sxs-lookup"><span data-stu-id="eecfc-151">Commands to run.</span></span> <span data-ttu-id="eecfc-152">Tillåtna värden är PutFile, RunScript och GetFile.</span><span class="sxs-lookup"><span data-stu-id="eecfc-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="eecfc-153">Kommandon:</span><span class="sxs-lookup"><span data-stu-id="eecfc-153">Commands:</span></span>

| <span data-ttu-id="eecfc-154">Kommandotyp</span><span class="sxs-lookup"><span data-stu-id="eecfc-154">Command Type</span></span> | <span data-ttu-id="eecfc-155">Parametrar</span><span class="sxs-lookup"><span data-stu-id="eecfc-155">Parameters</span></span>                                                                          | <span data-ttu-id="eecfc-156">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="eecfc-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="eecfc-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="eecfc-157">PutFile</span></span>      | <span data-ttu-id="eecfc-158">Nyckel: Filnamn</span><span class="sxs-lookup"><span data-stu-id="eecfc-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="eecfc-159">Värde: \<file name\></span><span class="sxs-lookup"><span data-stu-id="eecfc-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="eecfc-160">Lägger till en fil från biblioteket till enheten.</span><span class="sxs-lookup"><span data-stu-id="eecfc-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="eecfc-161">Filer sparas i en arbetsmapp och tas bort när enheten startas om som standard.</span><span class="sxs-lookup"><span data-stu-id="eecfc-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="eecfc-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="eecfc-162">RunScript</span></span>    | <span data-ttu-id="eecfc-163">Nyckel: ScriptName</span><span class="sxs-lookup"><span data-stu-id="eecfc-163">Key: ScriptName</span></span><br><span data-ttu-id="eecfc-164">Värde: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="eecfc-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="eecfc-165">Tangent: Args</span><span class="sxs-lookup"><span data-stu-id="eecfc-165">Key: Args</span></span>  <br> <span data-ttu-id="eecfc-166">Värde: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="eecfc-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="eecfc-167">Kör ett skript från biblioteket på en enhet.</span><span class="sxs-lookup"><span data-stu-id="eecfc-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="eecfc-168">Parametern Args skickas till skriptet.</span><span class="sxs-lookup"><span data-stu-id="eecfc-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="eecfc-169">Tidsgränser efter 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="eecfc-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="eecfc-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="eecfc-170">GetFile</span></span>      | <span data-ttu-id="eecfc-171">Nyckel: Sökväg</span><span class="sxs-lookup"><span data-stu-id="eecfc-171">Key: Path</span></span> <br> <span data-ttu-id="eecfc-172">Värde: \<File path\></span><span class="sxs-lookup"><span data-stu-id="eecfc-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="eecfc-173">Samla in en fil från en enhet.</span><span class="sxs-lookup"><span data-stu-id="eecfc-173">Collect file from a device.</span></span> <span data-ttu-id="eecfc-174">Obs! Omslag i sökväg måste komma i väg.</span><span class="sxs-lookup"><span data-stu-id="eecfc-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="eecfc-175">Svar</span><span class="sxs-lookup"><span data-stu-id="eecfc-175">Response</span></span>

-   <span data-ttu-id="eecfc-176">Om det lyckas returnerar den här metoden 200, OK.</span><span class="sxs-lookup"><span data-stu-id="eecfc-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="eecfc-177">Åtgärd entitet.</span><span class="sxs-lookup"><span data-stu-id="eecfc-177">Action entity.</span></span> <span data-ttu-id="eecfc-178">Om ingen dator med det angivna ID:t hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="eecfc-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="eecfc-179">Exempel</span><span class="sxs-lookup"><span data-stu-id="eecfc-179">Example</span></span>

<span data-ttu-id="eecfc-180">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="eecfc-180">**Request**</span></span>

<span data-ttu-id="eecfc-181">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="eecfc-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="eecfc-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="eecfc-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="eecfc-183">**Svar**</span><span class="sxs-lookup"><span data-stu-id="eecfc-183">**Response**</span></span>

<span data-ttu-id="eecfc-184">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="eecfc-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="eecfc-185">Innehållstyp: program/json</span><span class="sxs-lookup"><span data-stu-id="eecfc-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="eecfc-186">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="eecfc-186">Related topics</span></span>
- [<span data-ttu-id="eecfc-187">Skaffa API för maskinåtgärd</span><span class="sxs-lookup"><span data-stu-id="eecfc-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="eecfc-188">Få livesvarsresultat</span><span class="sxs-lookup"><span data-stu-id="eecfc-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="eecfc-189">Åtgärden Avbryt dator</span><span class="sxs-lookup"><span data-stu-id="eecfc-189">Cancel machine action</span></span>](cancel-machine-action.md)
