---
title: Programvarumetoder och egenskaper
description: Hämtar de senaste aviseringarna.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771423"
---
# <a name="software-resource-type"></a>Programvaruresurstyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Metoder

Metod |Returtyp |Beskrivning
:---|:---|:---
[Lista programvara](get-software.md) | Insamling av programvara | Lista organisationens programvaruinventering.
[Hämta programvara efter Id](get-software-by-id.md) | Programvara | Hämta en särskild programvara genom dess programvaru-ID.
[Lista distribution av programvaruversion](get-software-ver-distribution.md)| Distributionssamling | Lista distribution av programvaruversion efter programvaru-ID.
[Lista maskiner efter programvara](get-machines-by-software.md)| MachineRef-samling | Hämta en lista över enheter som är associerade med programvaru-ID.
[Lista sårbarhet efter programvara](get-vuln-by-software.md) | [Sårbarhetssamling](vulnerability.md) | Hämta en lista över säkerhetsproblem som är associerade med programvaru-ID.
[Hämta saknade KB:er](get-missing-kbs-software.md) | KB-samling | Visa en lista över saknade KB som är kopplade till programvaru-ID:t

## <a name="properties"></a>Egenskaper

Egenskap |   Typ   |   Beskrivning
:---|:---|:---
id | Sträng | Programvaru-ID
Namn | Sträng | Programvarunamn
Leverantör | Sträng | Namn på programvaruleverantör
Svagheter | Long | Antal identifierade säkerhetsproblem
publicExploit | Boolesk | Offentlig sårbarhet finns för en del av sårbarheterna
activeAlert | Boolesk | Aktiv avisering är kopplad till den här programvaran
exposedMachines | Long | Antal exponerade enheter
impactScore | Double | Effekterna av exponeringsresultatet för den här programvaran
