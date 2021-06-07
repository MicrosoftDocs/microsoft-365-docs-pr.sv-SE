---
title: Microsoft Defender för Endpoint API:er som stöds
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 61c7c8022ed89a4d10e5737e2dcdf92a4375bedd
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770415"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender för Endpoint API:er som stöds

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>Slutpunkts-URI och versionshantering

### <a name="endpoint-uri"></a>Slutpunkts-URI

> Tjänstens bas-URI är: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> De frågor som baseras på OData har prefixet "/api". Om du till exempel vill få aviseringar kan du skicka [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Versionshantering

> API:t har stöd för versionshantering.
>
> Den aktuella versionen är **V1.0.**
>
> Om du vill använda en särskild version använder du följande format: `https://api.securitycenter.microsoft.com/api/{Version}` . Till exempel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Om du inte anger någon version (t.ex. `https://api.securitycenter.microsoft.com/api/alerts` ) kommer du till den senaste versionen.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Läs mer om de enskilda enheter som stöds, där du kan köra API-anrop till, och information som HTTP-begärans värden, begärans rubriker och förväntade svar.

## <a name="in-this-section"></a>I det här avsnittet

Ämne | Beskrivning
:---|:---
[Avancerad jakt](run-advanced-query-api.md) | Köra frågor från API.
[Metod och egenskaper för varningar](alerts.md) | Kör API-anrop \- som få aviseringar, skapa en avisering, uppdatera avisering och mycket mer.
[Exportera utvärderingsmetoder och egenskaper per enhet](get-assessmnt-1methods-properties.md) | Kör API-anrop som \- export secure configuration assessment, export software inventory assessment och export software vulnerabilities assessment.
[Metoder och egenskaper för automatisk undersökning](investigation.md) | Kör API-anrop, \- till exempel hämta undersökningssamling.
[Hämta domänrelaterade varningar](get-domain-related-alerts.md) | Kör API-anrop \- som att hämta domänrelaterade enheter, domänstatistik och mycket mer.
[Filmetoder och -egenskaper](files.md) | Kör API-anrop \- som att få filinformation, filrelaterade aviseringar, filrelaterade enheter och filstatistik.
[Indikatormetoder och -egenskaper](ti-indicator.md) | Kör API-anrop, \- t.ex. hämta indikatorer, skapa indikator och ta bort indikatorer.
[Hämta IP-relaterade varningar](get-ip-related-alerts.md) | Kör API-anrop som \- få IP-relaterade aviseringar och få IP-statistik.
[Maskinmetoder och egenskaper](machine.md) | Kör API-anrop \- som att hämta enheter, hämta enheter efter ID, information om inloggade användare, redigera taggar med mera.
[Metoder och egenskaper för maskinåtgärd](machineaction.md) | Kör API-anrop som \- isolation, kör antivirussökning och mycket mer.
[Metoder och egenskaper för rekommendation](recommendation.md) | Kör API-anrop som \- få rekommendation från ID.
[Metoder och egenskaper för åtgärdsaktivitet](get-remediation-methods-properties.md) | Kör API-anrop som få alla åtgärder, få åtgärder på exponerade enheter och \- få en åtgärdsaktivitet per id.
[Poängmetoder och egenskaper](score.md) | Kör API-anrop, \- till exempel för att få exponeringsresultat eller för att få ett säkert enhetsresultat.
[Programvarumetoder och egenskaper](software.md) | Kör API-anrop, \- till exempel säkerhetsproblem efter programvara.
[Användarmetoder](user.md) | Kör \- API-anrop, till exempel få användarrelaterade aviseringar och användarrelaterade enheter.
[Metoder och egenskaper för sårbarhet](vulnerability.md) | Kör API-anrop som \- listenheter efter säkerhetsproblem.

## <a name="see-also"></a>Se även

- [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

- [Information om Microsoft Defender för Endpoint API](api-release-notes.md)
