---
title: Hitta enheter med tagg-API
description: Hitta alla enheter som innehåller specifc-tagg
keywords: apis, API som stöds, skaffa, enhet, hitta, hitta enhet, efter tagg, tagg
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200155"
---
# <a name="find-devices-by-tag-api"></a>Hitta enheter med tagg-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Hitta [datorer](machine.md) efter [tagg.](machine-tags.md)
<br>```startswith``` stöds. 

## <a name="limitations"></a>Begränsningar
1. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Machine.Read.All |  "Läs alla maskinprofiler"
Program |   Machine.ReadWrite.All | "Läsa och skriva all maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.Read | "Läs maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.ReadWrite | Maskininformation för läsning och skrivning

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
> - Svar omfattar endast enheter som användaren har åtkomst till baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)
> - Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)
> - Svar omfattar endast enheter som användaren har åtkomst till baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)

## <a name="http-request"></a>HTTP-begäran
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Skriv | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-uri-parameters"></a>Begär URI-parametrar

Namn | Skriv | Beskrivning
:---|:---|:---
tagg | Sträng | Taggnamnet. **Obligatoriskt.**
useStartsWithFilter | Boolesk | När denna är autent inställd på sant hittar sökningen alla enheter med taggnamn som börjar med den givna taggen i frågan. Falskt som standard. **Valfritt.**

## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas – 200 OK med en lista över maskinerna i svarstexten.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```