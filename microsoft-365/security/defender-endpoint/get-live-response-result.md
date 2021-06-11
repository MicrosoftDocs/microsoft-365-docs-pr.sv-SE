---
title: Få svarsresultat i livesändning
description: Lär dig hur du hämtar ett specifikt resultat av livesvarskommandot efter indexet.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879785"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="3bfcc-104">Få svarsresultat i livesändning</span><span class="sxs-lookup"><span data-stu-id="3bfcc-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3bfcc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3bfcc-105">**Applies to:**</span></span>
- [<span data-ttu-id="3bfcc-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3bfcc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="3bfcc-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3bfcc-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3bfcc-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="3bfcc-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="3bfcc-109">API description</span></span>

<span data-ttu-id="3bfcc-110">Hämtar ett specifikt resultat för livesvarskommandot efter index.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="3bfcc-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="3bfcc-111">Limitations</span></span>

1.  <span data-ttu-id="3bfcc-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="3bfcc-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="3bfcc-113">Permissions</span></span>

<span data-ttu-id="3bfcc-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3bfcc-115">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3bfcc-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="3bfcc-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="3bfcc-116">Permission type</span></span>                    | <span data-ttu-id="3bfcc-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="3bfcc-117">Permission</span></span>           | <span data-ttu-id="3bfcc-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="3bfcc-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="3bfcc-119">Program</span><span class="sxs-lookup"><span data-stu-id="3bfcc-119">Application</span></span>                        | <span data-ttu-id="3bfcc-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="3bfcc-120">Machine.LiveResponse</span></span> | <span data-ttu-id="3bfcc-121">Köra livesvar på en viss dator</span><span class="sxs-lookup"><span data-stu-id="3bfcc-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="3bfcc-122">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="3bfcc-122">Delegated (work or school account)</span></span> | <span data-ttu-id="3bfcc-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="3bfcc-123">Machine.LiveResponse</span></span> | <span data-ttu-id="3bfcc-124">Köra livesvar på en viss dator</span><span class="sxs-lookup"><span data-stu-id="3bfcc-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="3bfcc-125">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="3bfcc-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="3bfcc-126">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="3bfcc-126">Request headers</span></span>

| <span data-ttu-id="3bfcc-127">Namn</span><span class="sxs-lookup"><span data-stu-id="3bfcc-127">Name</span></span>      | <span data-ttu-id="3bfcc-128">Typ</span><span class="sxs-lookup"><span data-stu-id="3bfcc-128">Type</span></span> | <span data-ttu-id="3bfcc-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3bfcc-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="3bfcc-130">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="3bfcc-130">Authorization</span></span> | <span data-ttu-id="3bfcc-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bfcc-131">String</span></span>   | <span data-ttu-id="3bfcc-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-132">Bearer {token}.</span></span> <span data-ttu-id="3bfcc-133">Obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-133">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="3bfcc-134">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="3bfcc-134">Request body</span></span>

<span data-ttu-id="3bfcc-135">Tom</span><span class="sxs-lookup"><span data-stu-id="3bfcc-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3bfcc-136">Svar</span><span class="sxs-lookup"><span data-stu-id="3bfcc-136">Response</span></span>

<span data-ttu-id="3bfcc-137">Om det lyckas returnerar den här metoden 200, returnerar OK-svarskod med objekt som innehåller länken till kommandot resultat i *värdeegenskapen.*</span><span class="sxs-lookup"><span data-stu-id="3bfcc-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="3bfcc-138">Den här länken är giltig i 30 minuter och bör användas direkt för att ladda ned paketet till ett lokalt lagringsutrymme.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="3bfcc-139">En länk som har gått ut kan skapas på nytt av ett annat samtal och du behöver inte köra livesvar igen.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="3bfcc-140">*Egenskaper för runscript-transkription:*</span><span class="sxs-lookup"><span data-stu-id="3bfcc-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="3bfcc-141">Egenskap</span><span class="sxs-lookup"><span data-stu-id="3bfcc-141">Property</span></span>  | <span data-ttu-id="3bfcc-142">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3bfcc-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="3bfcc-143">Namn</span><span class="sxs-lookup"><span data-stu-id="3bfcc-143">name</span></span>          | <span data-ttu-id="3bfcc-144">Namn på körd skript</span><span class="sxs-lookup"><span data-stu-id="3bfcc-144">Executed script name</span></span>                  |
| <span data-ttu-id="3bfcc-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="3bfcc-145">exit_code</span></span>     | <span data-ttu-id="3bfcc-146">Körd avslutningskod för skript</span><span class="sxs-lookup"><span data-stu-id="3bfcc-146">Executed script exit code</span></span>             |
| <span data-ttu-id="3bfcc-147">script_output</span><span class="sxs-lookup"><span data-stu-id="3bfcc-147">script_output</span></span> | <span data-ttu-id="3bfcc-148">Kör skriptstandardresultat</span><span class="sxs-lookup"><span data-stu-id="3bfcc-148">Executed script standard output</span></span>       |
| <span data-ttu-id="3bfcc-149">script_error</span><span class="sxs-lookup"><span data-stu-id="3bfcc-149">script_error</span></span>  | <span data-ttu-id="3bfcc-150">Standardfelresultat för skript</span><span class="sxs-lookup"><span data-stu-id="3bfcc-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="3bfcc-151">Exempel</span><span class="sxs-lookup"><span data-stu-id="3bfcc-151">Example</span></span>

<span data-ttu-id="3bfcc-152">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="3bfcc-152">**Request**</span></span>

<span data-ttu-id="3bfcc-153">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="3bfcc-154">**Svar**</span><span class="sxs-lookup"><span data-stu-id="3bfcc-154">**Response**</span></span>

<span data-ttu-id="3bfcc-155">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="3bfcc-155">Here is an example of the response.</span></span>

<span data-ttu-id="3bfcc-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="3bfcc-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="3bfcc-157">Innehållstyp: program/json</span><span class="sxs-lookup"><span data-stu-id="3bfcc-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="3bfcc-158">*Filinnehåll:*</span><span class="sxs-lookup"><span data-stu-id="3bfcc-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="3bfcc-159">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3bfcc-159">Related topics</span></span>

- [<span data-ttu-id="3bfcc-160">Skaffa API för maskinåtgärd</span><span class="sxs-lookup"><span data-stu-id="3bfcc-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="3bfcc-161">Åtgärden Avbryt dator</span><span class="sxs-lookup"><span data-stu-id="3bfcc-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="3bfcc-162">Kör livesvar</span><span class="sxs-lookup"><span data-stu-id="3bfcc-162">Run live response</span></span>](run-live-response.md) 
