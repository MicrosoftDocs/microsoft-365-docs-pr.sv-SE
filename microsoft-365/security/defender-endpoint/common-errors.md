---
title: Vanliga Microsoft Defender för slutpunkts-API-fel
description: Lista över vanliga Microsoft Defender för Endpoint API-fel med beskrivningar.
keywords: apis, mdatp api, fel, felsökning
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
ms.openlocfilehash: 4fc2aeb6ee5a95f7eb121abdcf4431dc6d34cd49
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893467"
---
# <a name="common-rest-api-error-codes"></a>Vanliga REST API-felkoder

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* Felkoderna som visas i följande tabell kan returneras av en åtgärd på någon av Microsoft Defender för slutpunkts-API:er.
* Utöver felkoden innehåller varje felsvar ett felmeddelande, som kan hjälpa dig att lösa problemet.
* Meddelandet är en kostnadsfri text som kan ändras.
* Längst ned på sidan finns svarsexempel.

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Felkod |HTTP-statuskod |Meddelande 
:---|:---|:---
BadRequest | BadRequest (400) | Felmeddelande för allmän felbegäran.
ODataError | BadRequest (400) | Ogiltig OData-URI-fråga (det specifika felet har angetts).
InvalidInput | BadRequest (400) | Ogiltiga indata {the invalid input}.
InvalidRequest Det här är ett måste | BadRequest (400) | Ogiltig begärans brödtext.
InvalidHashValue | BadRequest (400) | Hashvärdet {the invalid hash} är ogiltigt.
InvalidDomainName | BadRequest (400) | Domännamnet {the invalid domain} är ogiltigt.
InvalidIpAddress | BadRequest (400) | IP-adressen {the invalid IP} är ogiltig.
InvalidUrl | BadRequest (400) | URL {the invalid URL} är ogiltig.
MaximumBatchSizeExceededed | BadRequest (400) | Maximal överskriden batchstorlek. Mottaget: {batchstorlek mottaget}, tillåtet: {batchstorlek tillåten}.
MissingRequiredParameter | BadRequest (400) | Parametern {the missing parameter} saknas.
OsPlatformNotSupported | BadRequest (400) | OS-plattformen {the client OS Platform} stöds inte för den här åtgärden.
ClientVersionNotSupported | BadRequest (400) | {The requested action} stöds i klientversionen {supported client version} eller senare.
Obehörig | Obehörig (401) | Obehörig (ogiltig eller utgången auktoriseringsrubrik).
Förbjudet | Förbjudet (403) | Åtkomst nekas (giltig token men otillräcklig behörighet för åtgärden).
Inaktiveradfeature | Förbjudet (403) | Klientorganisationsfunktionen är inte aktiverad.
OtillåtenOperation | Förbjudet (403) | {den otillåtna åtgärden och orsaken}.
NotFound | Hittades inte (404) | Felmeddelandet Allmänt hittades inte.
ResourceNotFound | Hittades inte (404) | Resurs {den begärda resursen} hittades inte.
InternalServerError | Internt serverfel (500) | (Inget felmeddelande, försök igen)
TooManyRequests | För många begäranden (429) | Svar representerar att nå kvotgränsen antingen genom antal begäranden eller av CPU.

## <a name="body-parameters-are-case-sensitive"></a>Parametrar för brödtext är case-sensitive

Parametrarna för inskickade brödtext är för närvarande ärendekänsliga.
<br>Om du får ett **InvalidRequest Gemener-** eller **MissingRequiredParameter-fel** kan det bero på fel versaler eller gemener.
<br>Granska dokumentationen för API och kontrollera att de skickade parametrarna matchar det relevanta exemplet.

## <a name="correlation-request-id"></a>Id för korrelationsbegäran

Varje felsvar innehåller en unik ID-parameter för spårning.
<br>Egenskapsnamnet för den här parametern är "target".
<br>När du kontaktar oss om ett fel kan du bifoga det här ID:t för att hitta orsaken till problemet.

## <a name="examples"></a>Exempel

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```


```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```
