---
title: Avancerad sökning med grunderna i PowerShell API
ms.reviewer: ''
description: Lär dig grunderna i fråga om Microsoft Defender för Endpoint API med hjälp av PowerShell.
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
ms.openlocfilehash: 9192662b8d4ed23a5903dddb555f07bf182ab17f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771507"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="7db05-104">Avancerad jakt med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7db05-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7db05-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7db05-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="7db05-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7db05-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7db05-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7db05-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="7db05-108">Kör avancerade frågor med hjälp av PowerShell, se [Advanced Hunting API.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="7db05-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="7db05-109">I det här avsnittet delar vi PowerShell-exempel för att hämta en token och använda den för att köra en fråga.</span><span class="sxs-lookup"><span data-stu-id="7db05-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7db05-110">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="7db05-110">Before you begin</span></span>
<span data-ttu-id="7db05-111">Först måste du [skapa en app](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="7db05-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="7db05-112">Förberedelseinstruktioner</span><span class="sxs-lookup"><span data-stu-id="7db05-112">Preparation instructions</span></span>

- <span data-ttu-id="7db05-113">Öppna ett PowerShell-fönster.</span><span class="sxs-lookup"><span data-stu-id="7db05-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="7db05-114">Om principen inte tillåter att du kör PowerShell-kommandon kan du köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="7db05-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="7db05-115">Mer information finns i [PowerShell-dokumentationen](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="7db05-115">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="7db05-116">Hämta token</span><span class="sxs-lookup"><span data-stu-id="7db05-116">Get token</span></span>

- <span data-ttu-id="7db05-117">Kör följande:</span><span class="sxs-lookup"><span data-stu-id="7db05-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="7db05-118">var</span><span class="sxs-lookup"><span data-stu-id="7db05-118">where</span></span>
- <span data-ttu-id="7db05-119">$tenantId: ID för innehavaren för vilken du vill köra frågan (frågan körs d.v.s. på data från den här klientorganisationen)</span><span class="sxs-lookup"><span data-stu-id="7db05-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="7db05-120">$appId: ID för din Azure AD-app (appen måste ha behörigheten Kör avancerade frågor till Defender för Slutpunkt)</span><span class="sxs-lookup"><span data-stu-id="7db05-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="7db05-121">$appSecret: Hemligt i Azure AD-appen</span><span class="sxs-lookup"><span data-stu-id="7db05-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="7db05-122">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="7db05-122">Run query</span></span>

<span data-ttu-id="7db05-123">Kör följande fråga:</span><span class="sxs-lookup"><span data-stu-id="7db05-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="7db05-124">$results innehåller resultatet av frågan</span><span class="sxs-lookup"><span data-stu-id="7db05-124">$results contain the results of your query</span></span>
- <span data-ttu-id="7db05-125">$schema innehåller schemat för frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="7db05-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="7db05-126">Komplexa frågor</span><span class="sxs-lookup"><span data-stu-id="7db05-126">Complex queries</span></span>

<span data-ttu-id="7db05-127">Om du vill köra komplexa frågor (eller flerradsfrågor) sparar du frågan i en fil och kör följande kommando i stället för den första raden i exemplet ovan:</span><span class="sxs-lookup"><span data-stu-id="7db05-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="7db05-128">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="7db05-128">Work with query results</span></span>

<span data-ttu-id="7db05-129">Nu kan du använda frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="7db05-129">You can now use the query results.</span></span>

<span data-ttu-id="7db05-130">Så här sparar du frågeresultatet i CSV-format file1.csv filen:</span><span class="sxs-lookup"><span data-stu-id="7db05-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="7db05-131">Om du vill spara frågeresultatet i JSON-format i file1.jspå gör du följande:</span><span class="sxs-lookup"><span data-stu-id="7db05-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="7db05-132">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="7db05-132">Related topic</span></span>
- [<span data-ttu-id="7db05-133">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="7db05-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="7db05-134">Advanced jakt-API</span><span class="sxs-lookup"><span data-stu-id="7db05-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="7db05-135">Avancerad jakt med Python</span><span class="sxs-lookup"><span data-stu-id="7db05-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
