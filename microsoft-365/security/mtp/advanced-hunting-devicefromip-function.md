---
title: DeviceFromIP ()-funktion i avancerad jakt för Microsoft 365 Defender
description: Lär dig hur du använder funktionen DeviceFromIP () för att hämta enheter som har tilldelats en viss IP-adress
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, enhet, devicefromIP, funktion och berikning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741118"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Använd `DeviceFromIP()` funktionen i de [avancerade jakt](advanced-hunting-overview.md) frågorna för att snabbt få reda på listan med enheter som har tilldelats en viss IP-adress vid en viss tidpunkt. 

Den här funktionen returnerar en tabell med följande kolumner:

| Kolumn | Datatyp | Beskrivning |
|------------|-------------|-------------|
| `IP` | strängvärdet | IP-adress  |
| `DeviceId` | strängvärdet | Unik identifierare för enheten i tjänsten |


## <a name="syntax"></a>Frågesyntaxen

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argument

Den här funktionen anropas som en del av en fråga.

- **x**– den första parametern är oftast redan en kolumn i frågan. I det här fallet är det kolumnen som heter `IP` , den IP-adress som du vill visa en lista över enheter som har tilldelats till den. Det ska vara en lokal IP-adress. Externa IP-adresser stöds inte.
- **y**– en andra valfri parameter är den `Timestamp` som används för att hämta de senaste tilldelade enheterna från en viss tid. Om det inte anges returnerar funktionen de senaste tillgängliga posterna.

## <a name="example"></a>Exempel


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Skaffa de senaste enheterna som har tilldelats särskilda IP-adresser

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
