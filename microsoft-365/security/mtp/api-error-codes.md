---
title: Vanliga fel koder för Microsoft Threat Protection REST API
description: Läs mer om de vanliga fel koderna för Microsoft Threat Protection REST API
keywords: API, fel, koder, vanliga fel, MTP, API-felkoder
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 36a1cedacc5f16c422e2b0d458b0d1767cf08b64
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650587"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a>Vanliga fel koder för Microsoft Threat Protection REST API

**Gäller för:**
- Microsoft Hotskydd

>[!IMPORTANT] 
>Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

Felkoderna som visas i följande tabell kan returneras av en åtgärd på något av Microsofts skydds-API: er.

Alla fel meddelanden innehåller ett fel meddelande som kan hjälpa dig att lösa problemet.

Meddelandet är en fri text som du kan ändra.

Längst ned på sidan hittar du svars exempel.

Felkod |HTTP-statuskod |Meddelande 
:---|:---|:---
BadRequest | BadRequest (400) | Allmänt fel meddelande om felaktig begäran.
ODataError | BadRequest (400) | Ogiltig OData URI-fråga (det specifika felet har angetts).
InvalidInput | BadRequest (400) | Ogiltig inmatning {ogiltigt värde}.
InvalidRequestBody | BadRequest (400) | Ogiltigt brödtext för begäran.
InvalidHashValue | BadRequest (400) | Hash-värde {ogiltigt hash} är ogiltigt.
InvalidDomainName | BadRequest (400) | Domän namn {den ogiltiga domänen} är ogiltig.
InvalidIpAddress | BadRequest (400) | IP-adress {ogiltigt IP} är ogiltigt.
InvalidUrl | BadRequest (400) | URL {ogiltig URL} är ogiltig.
MaximumBatchSizeExceeded | BadRequest (400) | Maximal batchstorlek har överskridits. Mottaget: {batch-storlek mottaget}, tillåts: {batchstorlek tillåts}.
MissingRequiredParameter | BadRequest (400) | Parameter {den saknade parametern} saknas.
OsPlatformNotSupported | BadRequest (400) | OS-plattform {OS-plattformen} stöds inte för den här åtgärden.
ClientVersionNotSupported | BadRequest (400) | {Den begärda åtgärden} stöds för klient version {-kompatibel klient version} och senare.
Saknas | Ej behörig (401) | Ej behörig (vanligt vis ogiltigt eller Förfallet godkännande rubrik).
Förbjudet | Förbjuden (403) | Förbjuden (giltig token men otillräcklig behörighet för åtgärden).
DisabledFeature | Förbjuden (403) | Klient funktionen är inte aktive rad.
DisallowedOperation | Förbjuden (403) | {åtgärden är inte tillåten och anledningen}.
NotFound | Hittas inte (404) | Allmänt meddelande visas inte.
ResourceNotFound | Hittas inte (404) | Resurs {den begärda resursen} hittades inte.
InternalServerError | Internt Server fel (500) | (Inget fel meddelande, försök igen eller kontakta oss om det inte löses)

## <a name="body-parameters-are-case-sensitive"></a>Text parametrar är Skift läges känsliga

De skickade huvud parametrarna är för närvarande Skift läges känsliga.
<br>Om du stöter på ett **InvalidRequestBody** -eller **MissingRequiredParameter** -fel kan det bero på felaktig tecken parameter eller gemen.
<br>Vi rekommenderar att du granskar sidan API-dokumentation och kontrollerar att de skickade parametrarna stämmer överens med det relevanta exemplet.

## <a name="correlation-request-id"></a>Korrelations-ID

Varje fel svar innehåller en parameter med unikt ID för spårning.
<br>Egenskaps namnet för den här parametern är "mål".
<br>När vi kontaktar oss om ett fel kan du hitta orsaken till problemet genom att bifoga detta ID.

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

