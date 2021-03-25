---
title: Microsoft Defender-API:er som stöds för slutpunkts-API:er
ms.reviewer: ''
description: Läs mer om specifika Microsoft Defender för slutpunktsenheter där du kan skapa API-anrop till.
keywords: apis, apis som stöds, aktör, aviseringar, enhet, användare, domän, ip, fil, avancerade frågor, avancerad sökning
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198334"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender-API:er som stöds för slutpunkts-API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>Slutpunkts-URI och versionshantering

### <a name="endpoint-uri"></a>Slutpunkt-URI:

> Tjänstens bas-URI är: https://api.securitycenter.microsoft.com
> 
> De frågor som baseras på OData har prefixet "/api". Om du till exempel vill få aviseringar kan du skicka https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>Versionshantering:

> API:t har stöd för versionshantering.
> 
> Den aktuella versionen är **V1.0.**
> 
> Om du vill använda en särskild version använder du följande format: `https://api.securitycenter.microsoft.com/api/{Version}` . Till exempel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> Om du inte anger någon version (t.ex. https://api.securitycenter.microsoft.com/api/alerts ) kommer du till den senaste versionen.


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Läs mer om de enskilda enheter som stöds, där du kan köra API-anrop till, och information som HTTP-begärans värden, begärans rubriker och förväntade svar.

## <a name="in-this-section"></a>I det här avsnittet

Ämne | Beskrivning
:---|:---
Advanced Hunting | Köra frågor från API.
Varningar | Kör API-anrop som få aviseringar, skapa en avisering, uppdatera avisering och mycket mer.
Domäner | Kör API-anrop som att hämta domänrelaterade enheter, domänstatistik och mycket mer.
Filer | Kör API-anrop som att få filinformation, filrelaterade aviseringar, filrelaterade enheter och filstatistik.
IP-adresser | Kör API-anrop som få IP-relaterade aviseringar och få IP-statistik.
Datorer | Kör API-anrop som att hämta enheter, hämta enheter efter ID, information om inloggade användare, redigera taggar med mera.
Datoråtgärder | Kör API-anrop som isolation, kör antivirussökning och mycket mer.
Indikatorer | Kör API-anrop som att skapa indikator, hämta indikatorer och ta bort indikatorer.
Användare | Kör API-anrop, till exempel få användarrelaterade aviseringar och användarrelaterade enheter.
Poäng | Kör API-anrop, till exempel för att få exponeringsresultat eller för att få ett säkert enhetsresultat.
Programvara | Kör API-anrop, till exempel säkerhetsproblem efter programvara.
Sårbarhet | Kör API-anrop som listenheter efter säkerhetsproblem.
Rekommendation | Kör API-anrop som Få rekommendation via ID.

## <a name="see-also"></a>Se även
- [Microsoft Defender för slutpunkts-API:er](apis-intro.md)
