---
title: Funktionen DeviceFromIP() i avancerad sökning efter Microsoft 365 Defender
description: Lär dig hur du använder funktionen DeviceFromIP() för att få de enheter som har tilldelats en specifik IP-adress
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d2996021a84186adc6656927dbdc910db4d037de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071570"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Använd funktionen i dina avancerade sökfrågor för att snabbt hämta listan över enheter som har tilldelats en `DeviceFromIP()` viss IP-adress vid en viss tidpunkt. [](advanced-hunting-overview.md) 

Den här funktionen returnerar en tabell med följande kolumner:

| Kolumn | Datatyp | Beskrivning |
|------------|-------------|-------------|
| `IP` | sträng | IP-adress  |
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |


## <a name="syntax"></a>Syntax

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argument

Den här funktionen anropas som en del av en fråga.

- **x**– Den första parametern är vanligtvis redan en kolumn i frågan. I det här fallet är det kolumnen med namnet , IP-adressen som du vill se en lista med enheter `IP` som har tilldelats till den. Det ska vara en lokal IP-adress. Externa IP-adresser stöds inte.
- **y**– En andra valfri parameter är , som instruerar funktionen för att hämta de senast tilldelade enheterna `Timestamp` från en viss tid. Om den inte anges returnerar funktionen de senaste tillgängliga posterna.

## <a name="example"></a>Exempel


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Hämta de senaste enheterna som har tilldelats specifika IP-adresser

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
