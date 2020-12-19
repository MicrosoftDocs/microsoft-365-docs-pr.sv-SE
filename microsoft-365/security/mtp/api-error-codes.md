---
title: Vanliga API-felkoder för Microsoft 365 Defender
description: Lär dig mer om de gemensamma API-felkoderna för Microsoft 365 Defender
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719220"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Vanliga API-felkoder för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

Felkoder kan returneras av en åtgärd med Microsoft 365 Defender API: er. Varje fel svar kommer att innehålla ett fel meddelande som kan hjälpa dig att lösa problemet. Kolumnen fel meddelande i avsnittet tabell innehåller några exempel meddelanden. Innehållet i faktiska meddelanden varierar beroende på faktorer som utlöste svaret. Variabel innehåll anges i tabellen med vinkelparenteser.

## <a name="error-codes"></a>Felkoder

Felkod | HTTP-statuskod | Meddelande
-|-|-
BadRequest | BadRequest (400) | Allmänt fel meddelande om felaktig begäran.
ODataError | BadRequest (400) | Ogiltig OData URI-fråga \<the specific error is specified\> .
InvalidInput | BadRequest (400) | Ogiltiga indata \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Ogiltigt brödtext för begäran.
InvalidHashValue | BadRequest (400) | Ogiltigt hashvärde \<the invalid hash\> .
InvalidDomainName | BadRequest (400) | Domän namnet \<the invalid domain\> är ogiltigt.
InvalidIpAddress | BadRequest (400) | IP-adressen \<the invalid IP\> är ogiltig.
InvalidUrl | BadRequest (400) | Webb adressen \<the invalid URL\> är ogiltig.
MaximumBatchSizeExceeded | BadRequest (400) | Maximal batchstorlek har överskridits. Mottaget: \<batch size received\> tillåts: {grupp storlek tillåts}.
MissingRequiredParameter | BadRequest (400) | Parameter \<the missing parameter\> saknas.
OsPlatformNotSupported | BadRequest (400) | Operativ system plattformen \<the client OS Platform\> stöder inte den här åtgärden.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> stöds på klient versionen \<supported client version\> och senare.
Saknas | Ej behörig (401) | Saknas <br /><br />*Obs! det beror vanligt vis på ett ogiltigt eller Förfallet godkännande huvud.*
Förbjudet | Förbjuden (403) | Förbjudet <br /><br />*Obs! giltig token men otillräcklig behörighet för åtgärden*.
DisabledFeature | Förbjuden (403) | Klient funktionen är inte aktive rad.
DisallowedOperation | Förbjuden (403) | \<the disallowed operation and the reason\>.
NotFound | Hittas inte (404) | Allmänt meddelande visas inte.
ResourceNotFound | Hittas inte (404) | Resursen \<the requested resource\> hittades inte.
InternalServerError | Internt Server fel (500) | *Obs! inga fel meddelanden, försök igen eller kontakta Microsoft om det inte löses*

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

## <a name="body-parameters"></a>Body-parametrar

> [!IMPORTANT]
> Text parametrar är Skift läges känsliga.

Om du upplever ett *InvalidRequestBody* -eller *MissingRequiredParameter* -fel kan det bero på ett stavfel. Granska API-dokumentationen och kontrol lera att de skickade parametrarna stämmer överens med det relevanta exemplet.

## <a name="tracking-id"></a>Spårnings-ID

Varje fel svar innehåller en parameter med unikt ID för spårning. Egenskaps namnet för den här parametern är *mål*. När vi kontaktar oss angående ett fel hjälper vi till med att hitta orsaken till problemet.

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender API](api-overview.md)
- [Microsoft 365 Defender API: er som stöds](api-supported.md)
- [Gå till API för Microsoft 365 Defender](api-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
