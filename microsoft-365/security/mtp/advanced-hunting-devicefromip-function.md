---
title: Funktionen DeviceFromIP() i avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du använder funktionen DeviceFromIP() för att få enheter som har tilldelats en specifik IP-adress
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, enhet, devicefromIP, funktion, vinst
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931308"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Använd funktionen i dina avancerade sökningsfrågor för att snabbt hämta listan över enheter som har tilldelats till en viss `DeviceFromIP()` IP-adress vid en [](advanced-hunting-overview.md) viss tidpunkt. 

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

- **x**– Den första parametern är vanligtvis redan en kolumn i frågan. I det här fallet är det kolumnen med namnet , IP-adressen som du vill se en lista med `IP` enheter som har tilldelats till den. Det ska vara en lokal IP-adress. Externa IP-adresser stöds inte.
- **y**– En andra valfri parameter är den som instruerar funktionen att hämta de senaste tilldelade enheterna `Timestamp` från en viss tid. Om den inte anges returnerar funktionen de senaste tillgängliga posterna.

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
