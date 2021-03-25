---
title: Vanliga Microsoft 365 Defender REST API-felkoder
description: Läs mer om de vanliga Microsoft 365 Defender REST API-felkoderna
keywords: api, fel, koder, vanliga fel, mtp, api-felkoder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ab564ddb0263b501b6aca979f2148dfb5cf92758
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076697"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Vanliga Microsoft 365 Defender REST API-felkoder

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft Threat Protection

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Felkoder kan returneras av en åtgärd på någon av Microsoft 365 Defender-API:erna. Alla felsvar kommer att innehålla ett felmeddelande, som kan hjälpa dig att lösa problemet. Kolumnen med felmeddelanden i tabellavsnittet innehåller några exempelmeddelanden. Innehållet i faktiska meddelanden varierar beroende på de faktorer som utlöste svaret. Variabelt innehåll anges i tabellen med vinkelparenteser.

## <a name="error-codes"></a>Felkoder

Felkod | HTTP-statuskod | Meddelande
-|-|-
BadRequest | BadRequest (400) | Felmeddelande för allmän felbegäran.
ODataError | BadRequest (400) | Ogiltig OData-URI-fråga. \<the specific error is specified\>
InvalidInput | BadRequest (400) | Ogiltiga indata \<the invalid input\> .
InvalidRequest Det här är ett måste | BadRequest (400) | Ogiltig begärans brödtext.
InvalidHashValue | BadRequest (400) | Hashvärdet \<the invalid hash\> är ogiltigt.
InvalidDomainName | BadRequest (400) | Domännamnet \<the invalid domain\> är ogiltigt.
InvalidIpAddress | BadRequest (400) | IP-adressen \<the invalid IP\> är ogiltig.
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> är ogiltig.
MaximumBatchSizeExceededed | BadRequest (400) | Maximal överskriden batchstorlek. Mottaget: \<batch size received\> , tillåtet: {batchstorlek tillåten}.
MissingRequiredParameter | BadRequest (400) | Parametern \<the missing parameter\> saknas.
OsPlatformNotSupported | BadRequest (400) | \<the client OS Platform\>OS-plattformen stöds inte för den här åtgärden.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> stöds i både \<supported client version\> klientversionen och senare.
Obehörig | Obehörig (401) | Obehörig <br /><br />*Obs! Detta orsakas vanligtvis av ett ogiltigt eller utgånget auktoriseringshuvud.*
Förbjudet | Förbjudet (403) | Förbjudet <br /><br />*Obs! Giltig token men otillräcklig behörighet för åtgärden*.
Inaktiveradfeature | Förbjudet (403) | Klientorganisationsfunktionen är inte aktiverad.
OtillåtenOperation | Förbjudet (403) | \<the disallowed operation and the reason\>.
NotFound | Hittades inte (404) | Felmeddelandet Allmänt hittades inte.
ResourceNotFound | Hittades inte (404) | Resursen \<the requested resource\> hittades inte.
InternalServerError | Internt serverfel (500) | *Obs! Inget felmeddelande, försök igen eller kontakta Microsoft om problemet inte åtgärdas*

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

## <a name="body-parameters"></a>Parametrar för brödtext

> [!IMPORTANT]
> Parametrar för brödtext är case-sensitive.

Om du får ett *fel av typ InvalidRequest Det* här felet eller felet *MissingRequiredParameter* kan det bero på ett stavfel. Granska API-dokumentationen och kontrollera att de skickade parametrarna matchar det relevanta exemplet.

## <a name="tracking-id"></a>Spårnings-ID

Varje felsvar innehåller en unik ID-parameter för spårning. Egenskapsnamnet för den här parametern är *mål*. När du kontaktar oss om ett fel kan du bifoga det här ID:t för att hitta orsaken till problemet.

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender-API:er](api-overview.md)
- [Microsoft 365 Defender API: er som stöds](api-supported.md)
- [Åtkomst till Microsoft 365 Defender-API:er](api-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
