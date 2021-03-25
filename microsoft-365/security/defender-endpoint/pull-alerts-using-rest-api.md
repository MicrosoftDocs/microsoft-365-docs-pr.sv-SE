---
title: Hämta Microsoft Defender för slutpunktsidentifiering med REST API
description: Lär dig hur du anropar en Microsoft Defender för Endpoint API-slutpunkt för att hämta identifieringar i JSON-format med HJÄLP av SIEM REST API.
keywords: identifieringar, dra identifieringar, rest api, begäran, svar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: a7d13da6abfb2cd6c829b6fd04fdf94de8cd20b8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186875"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>Hämta Microsoft Defender för slutpunktsidentifiering med HJÄLP av SIEM REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- [Microsoft Defender för slutpunktsavisering](alerts.md) består av en eller flera identifieringar.
>- [Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md) består av den misstänkta händelsen som inträffade på enheten och tillhörande aviseringsinformation.
>-Microsoft Defender för slutpunktsaviserings-API är det senaste API:t för aviseringsanvändning och innehåller en detaljerad lista med relaterade bevis för varje avisering. Mer information finns i [Aviseringsmetoder och egenskaper](alerts.md) och [Listaviseringar.](get-alerts.md)

Microsoft Defender för Endpoint har stöd för OAuth 2.0-protokollet för att hämta identifieringar från API:et.

OAuth 2.0-protokollet har i allmänhet stöd för fyra typer av flöden:
- Flöde för auktoriseringsauktorisering
- Implicit flöde
- Flöde för klientautentiseringsuppgifter
- Flöde för resursägare

Mer information om OAuth-specifikationer finns på [OAuth-webbplatsen.](http://www.oauth.net)

Microsoft Defender för  Endpoint har  stöd för flöde för auktoriseringsauktorisering och autentiseringsuppgifter för klient för att få åtkomst till identifieringar med Azure Active Directory (AAD) som auktoriseringsserver.

Flödet för auktoriseringsauktoriseringsautentisering använder användarautentiseringsuppgifter för att få en auktoriseringskod som sedan används för att hämta en åtkomsttoken. 

Flödet _för autentiseringsuppgifter för klient använder_ klientautentiseringsuppgifter för att autentisera mot Microsoft Defender för slutpunktsslutpunkts-URL. Det här flödet passar för scenarier när en OAuth-klient skapar begäranden till ett API som inte kräver användarautentiseringsuppgifter.

Använd följande metod i Microsoft Defender för Endpoint API för att hämta identifieringar i JSON-format.

>[!NOTE]
>I Microsoft Defender Säkerhetscenter slås liknande aviseringsidentifiering ihop till en enda avisering. Detta API hämtar aviseringsidentifiering i sin rådata utifrån de frågeparametrar du anger, så att du kan använda din egen gruppering och filtrering. 

## <a name="before-you-begin"></a>Innan du börjar
- Innan du anropar Microsoft Defender för slutpunktsslutpunkten för att hämta identifieringar måste du aktivera SIEM-integrationsprogrammet i Azure Active Directory (AAD). Mer information finns i Aktivera [SIEM-integrering i Microsoft Defender för slutpunkt.](enable-siem-integration.md)

- Notera följande värden i din Azure-programregistrering. Du behöver dessa värden för att konfigurera OAuth-flödet i tjänsten eller daemon-appen:
  - Program-ID (unikt för ditt program)
  - Appnyckel eller hemlig (unik för ditt program)
  - OAuth 2.0-tokenslutpunkt för appen
    - Hitta det här värdet genom **att klicka på** Visa slutpunkter längst ned på Azure Management Portal på appsidan. Slutpunkten ser ut så `https://login.microsoftonline.com/{tenantId}/oauth2/token` här.

## <a name="get-an-access-token"></a>Hämta en åtkomsttoken
Innan du skapar samtal till slutpunkten måste du få en åtkomsttoken.

Du använder åtkomsttoken för att komma åt den skyddade resursen, vilket identifieringar visas i Microsoft Defender för slutpunkt.

För att få en åtkomsttoken måste du göra en POST-begäran till den token som utfärdar slutpunkten. Här är ett exempel på en förfrågan:

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
Svaret innehåller information om åtkomsttoken och utgångsbehörighet.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
Nu kan du använda värdet i fältet *access_token* i en begäran till Defender för slutpunkts-API.

## <a name="request"></a>Begäran
Med en åtkomsttoken kan appen göra autentiserade begäranden till Microsoft Defender för Endpoint API. Appen måste lägga till åtkomsttoken i rubriken Auktorisering för varje begäran.

### <a name="request-syntax"></a>Syntax för begäran
Metod | Begär URI
:---|:---|
SKAFFA| Använd URI:en som gäller för din region. <br><br> **För EU:**`https://wdatp-alertexporter-eu.windows.com/api/alerts` </br> **För USA:**`https://wdatp-alertexporter-us.windows.com/api/alerts` <br> **För Storbritannien:**`https://wdatp-alertexporter-uk.windows.com/api/alerts` 

### <a name="request-header"></a>Sidhuvud för begäran
Sidhuvud | Skriv | Beskrivning|
:--|:--|:--
Auktorisering | sträng | Obligatoriskt. Azure AD-åtkomsttoken i formuläret **Bearer-token.** &lt;  &gt; |

### <a name="request-parameters"></a>Begär parametrar

Använd valfria frågeparametrar för att ange och styra mängden data som returneras i ett svar. Om du anropar den här metoden utan parametrar innehåller svaret alla aviseringar i organisationen under de senaste 2 timmarna.

Namn | Värde| Beskrivning
:---|:---|:---
sinceTimeUtc | DateTime | Definierar att aviseringar med lägre tidsbunden tid hämtas från, baserat på fält: <br> `LastProcessedTimeUtc` <br> Tidsperioden blir: fråntimeUtc-tid till aktuell tid. <br><br> **Obs!** När det inte har angetts hämtas alla aviseringar som genererats de senaste två timmarna.
untilTimeUtc | DateTime | Definierar den övre tidsbundna aviseringarna hämtas. <br> Tidsperioden blir då och `sinceTimeUtc` `untilTimeUtc` då. <br><br> **Obs!** När det inte anges används den aktuella tiden som standardvärde.
sedan | sträng | Hämtar aviseringar i följande tidsperiod: från `(current_time - ago)` tid till `current_time` tid. <br><br> Värdet ska anges i enlighet med **iso 8601-varaktighetsformatet** <br> Exempel: `ago=PT10M` hämtar aviseringar som tagits emot de senaste 10 minuterna.
gräns | int | Definierar antalet aviseringar som ska hämtas. De senaste aviseringarna hämtas baserat på det definierade antalet.<br><br> **Obs!** När det inte anges hämtas alla aviseringar som finns tillgängliga inom tidsperioden.
maskingrupper | sträng | Anger vilka enhetsgrupper som aviseringar ska hämta aviseringar från. <br><br> **Obs!** När det inte anges hämtas aviseringar från alla enhetsgrupper. <br><br> Exempel: <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
DeviceCreatedMachineTags | sträng | En enstaka enhetstagg från registret.
CloudCreatedMachineTags | sträng | Enhetstaggar som har skapats i Microsoft Defender Säkerhetscenter.

### <a name="request-example"></a>Exempel på förfrågan
I följande exempel visas hur du hämtar alla identifieringar i organisationen.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

I följande exempel visas en begäran om att få de senaste 20 identifieringarna sedan 2016-09-12 00:00:00.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>Svar
Returvärdet är en matris med aviseringsobjekt i JSON-format.

Här är ett exempel på ett returvärde:

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>Kodexempel
### <a name="get-access-token"></a>Hämta åtkomsttoken
Följande kodexempel visar hur du hämtar en åtkomsttoken för att anropa Microsoft Defender för Endpoint SIEM API.

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>Använd token för att ansluta till identifieringsslutpunkten
Följande kodexempel visar hur du använder en åtkomsttoken för att anropa Defender för slutpunkt SIEM API för att få aviseringar.

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>Felkoder
Microsoft Defender för slutpunkt REST API returnerar följande felkoder som orsakas av en ogiltig begäran.

HTTP-felkod | Beskrivning
:---|:---
401 | Felaktig begäran eller ogiltig token.
403 | Obehörigt undantag – någon av domänerna hanteras inte av innehavaradministratören eller innehavartillståndet tas bort.
500 | Fel i tjänsten.

## <a name="related-topics"></a>Relaterade ämnen
- [Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt](enable-siem-integration.md)
- [Konfigurera ArcSight för att hämta Microsoft Defender för identifiering av slutpunkter](configure-arcsight.md)
- [Dra identifieringar till dina SIEM-verktyg](configure-siem.md)
- [Fälten Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md)
- [Felsöka problem med SIEM-verktygsintegrering](troubleshoot-siem.md)
