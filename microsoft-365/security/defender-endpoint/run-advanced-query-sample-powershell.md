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
ms.technology: mde
ms.openlocfilehash: 20c63daaf61b85f35aaceccb540b6d50824c801d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198677"
---
# <a name="advanced-hunting-using-powershell"></a>Advanced Hunting med PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Kör avancerade frågor med hjälp av PowerShell, se [Advanced Hunting API.](run-advanced-query-api.md)

I det här avsnittet delar vi PowerShell-exempel för att hämta en token och använda den för att köra en fråga.

## <a name="before-you-begin"></a>Innan du börjar
Först måste du [skapa en app](apis-intro.md).

## <a name="preparation-instructions"></a>Förberedelseinstruktioner

- Öppna ett PowerShell-fönster.
- Om principen inte tillåter att du kör PowerShell-kommandon kan du köra följande kommando:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>Mer information finns i [PowerShell-dokumentationen](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Hämta token

- Kör följande:

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

var
- $tenantId: ID för innehavaren för vilken du vill köra frågan (frågan körs d.v.s. på data från den här klientorganisationen)
- $appId: ID för din Azure AD-app (appen måste ha behörigheten Kör avancerade frågor till Defender för Slutpunkt)
- $appSecret: Hemligt i Azure AD-appen

## <a name="run-query"></a>Kör fråga

Kör följande fråga:

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

- $results innehåller resultatet av frågan
- $schema innehåller schemat för frågeresultatet

### <a name="complex-queries"></a>Komplexa frågor

Om du vill köra komplexa frågor (eller flerradsfrågor) sparar du frågan i en fil och kör följande kommando i stället för den första raden i exemplet ovan:

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Arbeta med frågeresultat

Nu kan du använda frågeresultatet.

Så här sparar du frågeresultatet i CSV-format file1.csv filen:

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Om du vill spara frågeresultatet i JSON-format i file1.jspå gör du följande:

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Relaterat ämne
- [Microsoft Defender för slutpunkts-API:er](apis-intro.md)
- [Advanced jakt-API](run-advanced-query-api.md)
- [Advanced Hunting med Python](run-advanced-query-sample-python.md)
