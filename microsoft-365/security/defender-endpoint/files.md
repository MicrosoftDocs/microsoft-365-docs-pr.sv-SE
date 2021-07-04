---
title: Filresurstyp
description: Hämta de senaste Microsoft Defender för slutpunktsaviseringar som är relaterade till filer.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
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
ms.openlocfilehash: 83a011e649a7289f62acd6a8d985f020b27b1e10
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290021"
---
# <a name="file-resource-type"></a>Filresurstyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Representerar en filentitet i Defender för Slutpunkt.

## <a name="methods"></a>Metoder

Metod|Returtyp |Beskrivning
:---|:---|:---
[Hämta fil](get-file-information.md) | [fil](files.md) | Hämta en enda fil 
[Listfilrelaterade aviseringar](get-file-related-alerts.md) | [aviseringssamling](alerts.md) | Få [aviseringsenheterna](alerts.md) som är associerade med filen.
[Listfilrelaterade datorer](get-file-related-machines.md) | [maskinsamling](machine.md) | Få de [datorenheter](machine.md) som är associerade med aviseringen.
[filstatistik](get-file-statistics.md) | Statistiksammanfattning | Hämtar den första filen som var den första filen.


## <a name="properties"></a>Egenskaper

|Egenskap | Typ | Beskrivning |
|:---|:---|:---|
|sha1 | Sträng | Hashtaggen Sha1 för filinnehållet |
|sha256 | Sträng | Sha256-hash för filinnehållet |
|globalprevalence | Nullbar long | Filarysen i hela organisationen |
|globalFirstObserved | DateTimeOffset | Första gången filen observerades |
|globalLastObserved | DateTimeOffset | Senaste gången filen observerades |
|storlek | Nullbar long | Storlek på filen |
|fileType | Sträng | Typ av fil |
|isPeFile | Boolesk | true om filen är bärbar körbar (t.ex. "DLL", "EXE" osv.) |
|filePublisher | Sträng | Filutgivare |
|fileProductName | Sträng | Produktnamn |
|undertecknare | Sträng | Fil signerare |
|utfärdare | Sträng | Filutfärdare |
|signerHash | Sträng | Hash-kod för signeringscertifikatet |
|isValidCertificate | Boolesk | Signeringscertifikat har verifierats av Microsoft Defender för Endpoint-agenten |
|determinationType | Sträng | Avgöra vilken typ av fil som ska avgöras |
|determinationValue | Sträng | Determination value |

## <a name="json-representation"></a>Json-representation

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
