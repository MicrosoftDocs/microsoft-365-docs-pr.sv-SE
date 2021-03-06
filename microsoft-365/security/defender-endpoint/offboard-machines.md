---
title: Offboard-enheter från Microsoft Defender för Slutpunkt-tjänsten
description: Få Windows 10 enheter, servrar, icke-Windows enheter från Microsoft Defender för slutpunktstjänsten
keywords: offboarding, Microsoft Defender för offboarding för slutpunkt, offboarding
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934159"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Offboard-enheter från Microsoft Defender för Slutpunkt-tjänsten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattformar**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Följ motsvarande instruktioner beroende på vilken distributionsmetod du föredrar.

>[!NOTE]
> Status för en enhet växlas till [Inaktiv](fix-unhealthy-sensors.md#inactive-devices) 7 dagar efter offboarding. <br> Data för offboarded-enheter (till exempel tidslinje, varningar, säkerhetsproblem och så vidare) kommer att finnas kvar i portalen tills den konfigurerade [lagringstiden](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) löper ut. <br>
> Enhetens profil (utan data) finns kvar i [enhetslistan](machines-view-overview.md) i högst 180 dagar.
> Dessutom räknas inte enheter som inte är aktiva de senaste 30 dagarna i på de [](tvm-exposure-score.md) data som återspeglar organisationens Hantering av hot och säkerhetsrisker exponeringsresultat och Microsoft Secure Score för enheter. <br>
> Om du bara vill visa aktiva enheter kan du filtrera [efter status,](machines-view-overview.md#health-state) [enhetstaggar](machine-tags.md) eller [datorgrupper.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Offboard Windows 10 enheter
- [Offboard-enheter med ett lokalt skript](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Offboard-enheter med grupprincip](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Offboard-enheter med mobila enhetshanteringsverktyg](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Offboard-servrar
- [Offboard-servrar](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Offboard-enheter som Windows enheter
- [Offboard-enheter som Windows enheter](configure-endpoints-non-windows.md#offboard-non-windows-devices)

