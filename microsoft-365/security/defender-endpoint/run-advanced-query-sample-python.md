---
title: Avancerad sökning med Python API-guide
ms.reviewer: ''
description: Lär dig hur du frågar med Hjälp av Microsoft Defender för Endpoint API, genom att använda Python, med exempel.
keywords: apis, apis som stöds, avancerad sökning, fråga
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
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771459"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="f6d33-104">Avancerad jakt med Python</span><span class="sxs-lookup"><span data-stu-id="f6d33-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6d33-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f6d33-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f6d33-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f6d33-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6d33-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f6d33-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f6d33-108">Köra avancerade frågor med Python, se [Advanced Hunting API](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="f6d33-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="f6d33-109">I det här avsnittet delar vi Python-exempel för att hämta en token och använda den för att köra en fråga.</span><span class="sxs-lookup"><span data-stu-id="f6d33-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="f6d33-110">**Nödvändiga:** Först måste du [skapa en app](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="f6d33-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="f6d33-111">Hämta token</span><span class="sxs-lookup"><span data-stu-id="f6d33-111">Get token</span></span>

- <span data-ttu-id="f6d33-112">Kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="f6d33-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="f6d33-113">var</span><span class="sxs-lookup"><span data-stu-id="f6d33-113">where</span></span>
- <span data-ttu-id="f6d33-114">tenantId: ID för den klientorganisation för vilken du vill köra frågan (d.v.s. att frågan körs på data för den här klientorganisationen)</span><span class="sxs-lookup"><span data-stu-id="f6d33-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="f6d33-115">appId: ID för din Azure AD-app (appen måste ha behörigheten Kör avancerade frågor till Microsoft Defender för Slutpunkt)</span><span class="sxs-lookup"><span data-stu-id="f6d33-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="f6d33-116">appSekret: Hemligt för din Azure AD-app</span><span class="sxs-lookup"><span data-stu-id="f6d33-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="f6d33-117">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="f6d33-117">Run query</span></span>

 <span data-ttu-id="f6d33-118">Kör följande fråga:</span><span class="sxs-lookup"><span data-stu-id="f6d33-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="f6d33-119">schemat innehåller schemat för resultaten av frågan</span><span class="sxs-lookup"><span data-stu-id="f6d33-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="f6d33-120">resultat innehåller resultatet av frågan</span><span class="sxs-lookup"><span data-stu-id="f6d33-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="f6d33-121">Komplexa frågor</span><span class="sxs-lookup"><span data-stu-id="f6d33-121">Complex queries</span></span>

<span data-ttu-id="f6d33-122">Om du vill köra komplexa frågor (eller flerradsfrågor) sparar du frågan i en fil och kör följande kommando i stället för den första raden i exemplet ovan:</span><span class="sxs-lookup"><span data-stu-id="f6d33-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="f6d33-123">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="f6d33-123">Work with query results</span></span>

<span data-ttu-id="f6d33-124">Nu kan du använda frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="f6d33-124">You can now use the query results.</span></span>

<span data-ttu-id="f6d33-125">För att iterera över resultaten gör du följande:</span><span class="sxs-lookup"><span data-stu-id="f6d33-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="f6d33-126">Så här sparar du frågeresultatet i CSV-format file1.csv filen:</span><span class="sxs-lookup"><span data-stu-id="f6d33-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="f6d33-127">Om du vill spara frågeresultatet i JSON-format i file1.jspå gör du följande:</span><span class="sxs-lookup"><span data-stu-id="f6d33-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="f6d33-128">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="f6d33-128">Related topic</span></span>
- [<span data-ttu-id="f6d33-129">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="f6d33-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="f6d33-130">Advanced jakt-API</span><span class="sxs-lookup"><span data-stu-id="f6d33-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="f6d33-131">Avancerad jakt med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6d33-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
