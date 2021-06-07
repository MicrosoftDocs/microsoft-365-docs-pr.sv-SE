---
title: API för listvarningar
description: Lär dig hur du använder API:t för listaviseringar för att hämta en samling aviseringar i Microsoft Defender för Slutpunkt.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4da646a52392871cde99271a17ed6eb9111f51ab
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769263"
---
# <a name="list-alerts-api"></a><span data-ttu-id="937a9-104">API för listvarningar</span><span class="sxs-lookup"><span data-stu-id="937a9-104">List alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="937a9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="937a9-105">**Applies to:**</span></span>
- [<span data-ttu-id="937a9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="937a9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="937a9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="937a9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="937a9-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="937a9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="937a9-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="937a9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="937a9-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="937a9-110">API description</span></span>
<span data-ttu-id="937a9-111">Hämtar en samling aviseringar.</span><span class="sxs-lookup"><span data-stu-id="937a9-111">Retrieves a collection of Alerts.</span></span>
<br><span data-ttu-id="937a9-112">Stöder [OData V4-frågor.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="937a9-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="937a9-113">Operatorer som stöds av OData:</span><span class="sxs-lookup"><span data-stu-id="937a9-113">OData supported operators:</span></span>
<br><span data-ttu-id="937a9-114">```$filter``` på: ```alertCreationTime``` ```lastUpdateTime``` , , , , ```incidentId``` ```InvestigationId``` och ```status``` ```severity``` ```category``` egenskaper.</span><span class="sxs-lookup"><span data-stu-id="937a9-114">```$filter``` on: ```alertCreationTime```, ```lastUpdateTime```, ```incidentId```,```InvestigationId```, ```status```, ```severity``` and ```category``` properties.</span></span>
<br><span data-ttu-id="937a9-115">```$top``` med maxvärde på 10 000</span><span class="sxs-lookup"><span data-stu-id="937a9-115">```$top``` with max value of 10,000</span></span>
<br>```$skip```
<br><span data-ttu-id="937a9-116">```$expand``` av ```evidence```</span><span class="sxs-lookup"><span data-stu-id="937a9-116">```$expand``` of ```evidence```</span></span>
<br><span data-ttu-id="937a9-117">Se exempel på [OData-frågor med Microsoft Defender för Slutpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="937a9-117">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="937a9-118">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="937a9-118">Limitations</span></span>
1. <span data-ttu-id="937a9-119">Du kan få aviseringar som senast uppdaterats enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="937a9-119">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="937a9-120">Maximal sidstorlek är 10 000.</span><span class="sxs-lookup"><span data-stu-id="937a9-120">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="937a9-121">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="937a9-121">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="937a9-122">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="937a9-122">Permissions</span></span>
<span data-ttu-id="937a9-123">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="937a9-123">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="937a9-124">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="937a9-124">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="937a9-125">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="937a9-125">Permission type</span></span> |   <span data-ttu-id="937a9-126">Behörighet</span><span class="sxs-lookup"><span data-stu-id="937a9-126">Permission</span></span>  |   <span data-ttu-id="937a9-127">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="937a9-127">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="937a9-128">Program</span><span class="sxs-lookup"><span data-stu-id="937a9-128">Application</span></span> |   <span data-ttu-id="937a9-129">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="937a9-129">Alert.Read.All</span></span> |    <span data-ttu-id="937a9-130">"Läs alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="937a9-130">'Read all alerts'</span></span>
<span data-ttu-id="937a9-131">Program</span><span class="sxs-lookup"><span data-stu-id="937a9-131">Application</span></span> |   <span data-ttu-id="937a9-132">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="937a9-132">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="937a9-133">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="937a9-133">'Read and write all alerts'</span></span>
<span data-ttu-id="937a9-134">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="937a9-134">Delegated (work or school account)</span></span> | <span data-ttu-id="937a9-135">Avisering.Läsa</span><span class="sxs-lookup"><span data-stu-id="937a9-135">Alert.Read</span></span> | <span data-ttu-id="937a9-136">Läsaviseringar</span><span class="sxs-lookup"><span data-stu-id="937a9-136">'Read alerts'</span></span>
<span data-ttu-id="937a9-137">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="937a9-137">Delegated (work or school account)</span></span> | <span data-ttu-id="937a9-138">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="937a9-138">Alert.ReadWrite</span></span> | <span data-ttu-id="937a9-139">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="937a9-139">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="937a9-140">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="937a9-140">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="937a9-141">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="937a9-141">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="937a9-142">Svaret tar bara med aviseringar som associeras med enheter som användaren kan [](machine-groups.md) komma åt, baserat på enhetsgruppsinställningar (mer information finns i Skapa och hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="937a9-142">The response will include only alerts that are associated with devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="937a9-143">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="937a9-143">HTTP request</span></span>
```
GET /api/alerts
```

## <a name="request-headers"></a><span data-ttu-id="937a9-144">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="937a9-144">Request headers</span></span>

<span data-ttu-id="937a9-145">Namn</span><span class="sxs-lookup"><span data-stu-id="937a9-145">Name</span></span> | <span data-ttu-id="937a9-146">Typ</span><span class="sxs-lookup"><span data-stu-id="937a9-146">Type</span></span> | <span data-ttu-id="937a9-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="937a9-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="937a9-148">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="937a9-148">Authorization</span></span> | <span data-ttu-id="937a9-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="937a9-149">String</span></span> | <span data-ttu-id="937a9-150">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="937a9-150">Bearer {token}.</span></span> <span data-ttu-id="937a9-151">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="937a9-151">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="937a9-152">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="937a9-152">Request body</span></span>
<span data-ttu-id="937a9-153">Tom</span><span class="sxs-lookup"><span data-stu-id="937a9-153">Empty</span></span>

## <a name="response"></a><span data-ttu-id="937a9-154">Svar</span><span class="sxs-lookup"><span data-stu-id="937a9-154">Response</span></span>
<span data-ttu-id="937a9-155">Om det lyckas returnerar den här metoden 200 OK och en lista med [aviseringsobjekt](alerts.md) i svarets brödtext.</span><span class="sxs-lookup"><span data-stu-id="937a9-155">If successful, this method returns 200 OK, and a list of [alert](alerts.md) objects in the response body.</span></span>


## <a name="example-1---default"></a><span data-ttu-id="937a9-156">Exempel 1 – Standard</span><span class="sxs-lookup"><span data-stu-id="937a9-156">Example 1 - Default</span></span>

<span data-ttu-id="937a9-157">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="937a9-157">**Request**</span></span>

<span data-ttu-id="937a9-158">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="937a9-158">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts
```

<span data-ttu-id="937a9-159">**Svar**</span><span class="sxs-lookup"><span data-stu-id="937a9-159">**Response**</span></span>

<span data-ttu-id="937a9-160">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="937a9-160">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="937a9-161">Svarslistan som visas här kan trunkeras för att vara kort.</span><span class="sxs-lookup"><span data-stu-id="937a9-161">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="937a9-162">Alla aviseringar returneras från ett faktiskt samtal.</span><span class="sxs-lookup"><span data-stu-id="937a9-162">All alerts will be returned from an actual call.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637308392288907382_-880718168",
            "incidentId": 7587,
            "investigationId": 723156,
            "assignedTo": "secop123@contoso.com",
            "severity": "Low",
            "status": "New",
            "classification": "TruePositive",
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAv",
            "category": "SuspiciousActivity",
            "threatFamilyName": "Meterpreter",
            "title": "Suspicious 'Meterpreter' behavior was detected",
            "description": "Malware and unwanted software are undesirable applications that perform annoying, disruptive, or harmful actions on affected machines. Some of these undesirable applications can replicate and spread from one machine to another. Others are able to receive commands from remote attackers and perform activities associated with cyber attacks.\n\nA malware is considered active if it is found running on the machine or it already has persistence mechanisms in place. Active malware detections are assigned higher severity ratings.\n\nBecause this malware was active, take precautionary measures and check for residual signs of infection.",
            "alertCreationTime": "2020-07-20T10:53:48.7657932Z",
            "firstEventTime": "2020-07-20T10:52:17.6654369Z",
            "lastEventTime": "2020-07-20T10:52:18.1362905Z",
            "lastUpdateTime": "2020-07-20T10:53:50.19Z",
            "resolvedTime": null,
            "machineId": "12ee6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "MiddleEast",
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
                    "createdTime": "2020-07-21T01:00:37.8404534Z"
                }
            ],
            "evidence": []
        }
        ...
    ]
}
```

## <a name="example-2---get-10-latest-alerts-with-related-evidence"></a><span data-ttu-id="937a9-163">Exempel 2 – Få 10 senaste aviseringar med relaterade bevis</span><span class="sxs-lookup"><span data-stu-id="937a9-163">Example 2 - Get 10 latest Alerts with related Evidence</span></span>

<span data-ttu-id="937a9-164">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="937a9-164">**Request**</span></span>

<span data-ttu-id="937a9-165">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="937a9-165">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```


<span data-ttu-id="937a9-166">**Svar**</span><span class="sxs-lookup"><span data-stu-id="937a9-166">**Response**</span></span>

<span data-ttu-id="937a9-167">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="937a9-167">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="937a9-168">Svarslistan som visas här kan trunkeras för att vara kort.</span><span class="sxs-lookup"><span data-stu-id="937a9-168">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="937a9-169">Alla aviseringar returneras från ett faktiskt samtal.</span><span class="sxs-lookup"><span data-stu-id="937a9-169">All alerts will be returned from an actual call.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
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
        },
        ...
    ]
}
```


## <a name="see-also"></a><span data-ttu-id="937a9-170">Se även</span><span class="sxs-lookup"><span data-stu-id="937a9-170">See also</span></span>
- [<span data-ttu-id="937a9-171">OData-frågor med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="937a9-171">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
