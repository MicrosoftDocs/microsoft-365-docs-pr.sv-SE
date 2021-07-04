---
title: Ta bort indikator-API.
description: Lär dig hur du använder indikator-API:t för att ta bort en indikator entitet med ID i Microsoft Defender för slutpunkt.
keywords: apis, public api, apis som stöds, delete, ti indikator, entitet, id
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
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289925"
---
# <a name="delete-indicator-api"></a>Ta bort indikator-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning

Tar bort en [indikatortitet](ti-indicator.md) med hjälp av ID.

## <a name="limitations"></a>Begränsningar

Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
:---|:---|:---
Program | Ti.ReadWrite | "Läs och skriv TI-indikatorer"
Program | Ti.ReadWrite.All | Indikatorer för läsning och skrivning

## <a name="http-request"></a>HTTP-begäran

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>Frågerubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-body"></a>Frågebrödtext

Tom

## <a name="response"></a>Svar

Om indikator finns och tagits bort korrekt – 204 OK utan innehåll.

Om indikator med det angivna ID:t hittades inte – 404 Hittades inte.

## <a name="example"></a>Exempel

### <a name="request"></a>Begäran

Här är ett exempel på begäran.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
