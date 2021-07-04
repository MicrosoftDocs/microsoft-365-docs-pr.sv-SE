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
ms.openlocfilehash: 7ee431c88430916fcba60266a3a3a5180d830c0d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289265"
---
# <a name="advanced-hunting-using-python"></a>Avancerad jakt med Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Köra avancerade frågor med Python, se [Advanced Hunting API](run-advanced-query-api.md).

I det här avsnittet delar vi Python-exempel för att hämta en token och använda den för att köra en fråga.

> **Nödvändiga:** Först måste du [skapa en app](apis-intro.md).

## <a name="get-token"></a>Hämta token

- Kör följande kommandon:

```python
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

var

- tenantId: ID för den klientorganisation för vilken du vill köra frågan (d.v.s. att frågan körs på data för den här klientorganisationen)
- appId: ID för din Azure AD-app (appen måste ha behörigheten Kör avancerade frågor till Microsoft Defender för Slutpunkt)
- appSekret: Hemligt för din Azure AD-app

## <a name="run-query"></a>Kör fråga

 Kör följande fråga:

```python
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

- schemat innehåller schemat för resultaten av frågan
- resultat innehåller resultatet av frågan

### <a name="complex-queries"></a>Komplexa frågor

Om du vill köra komplexa frågor (eller flerradsfrågor) sparar du frågan i en fil och kör följande kommando i stället för den första raden i exemplet ovan:

```python
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Arbeta med frågeresultat

Nu kan du använda frågeresultatet.

För att iterera över resultaten gör du följande:

```python
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result
```

Så här sparar du frågeresultatet i CSV-format file1.csv filen:

```python
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Om du vill spara frågeresultatet i JSON-format i file1.jspå gör du följande:

```python
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```

## <a name="related-topic"></a>Relaterat ämne

- [Microsoft Defender för slutpunkts-API:er](apis-intro.md)
- [Avancerad jakt-API](run-advanced-query-api.md)
- [Avancerad jakt med PowerShell](run-advanced-query-sample-powershell.md)
