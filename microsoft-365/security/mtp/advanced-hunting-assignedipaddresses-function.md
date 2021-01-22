---
title: Funktionen AssignedIPAddresses() i avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du använder funktionen AssignedIPAddresses() för att få de senaste IP-adresserna tilldelade till en enhet
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, vinst
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d16cd7efc49cc2498eff3f705bb43fa62f37d975
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933024"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Använd funktionen `AssignedIPAddresses()` i dina avancerade [sökningsfrågor](advanced-hunting-overview.md) för att snabbt hämta de senaste IP-adresserna som har tilldelats till en enhet. Om du anger ett tidsstämpelargument hämtar den här funktionen de senaste IP-adresserna vid den angivna tiden. 

Den här funktionen returnerar en tabell med följande kolumner:

| Kolumn | Datatyp | Beskrivning |
|------------|-------------|-------------|
| `Timestamp` | datetime | Senaste gången då enheten observerades med IP-adressen |
| `IPAddress` | sträng | IP-adress som används av enheten |
| `IPType` | sträng | Anger om IP-adressen är en offentlig eller privat adress |
| `NetworkAdapterType` | int | Nätverksadaptertyp som används av enheten som har tilldelats IP-adressen. Referera till den här uppräkningen [för möjliga värden](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Nätverk som adaptern med den tilldelade IP-adressen är ansluten till. Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet |

## <a name="syntax"></a>Syntax

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argument

- **x**– `DeviceId` eller värde som identifierar `DeviceName` enheten
- **y**– (datetime) som instruerar funktionen att hämta de senaste tilldelade `Timestamp` IP-adresserna från en viss tid. Om den inte anges returnerar funktionen de senaste IP-adresserna.

## <a name="examples"></a>Exempel

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Hämta listan med IP-adresser som användes av en enhet för 24 timmar sedan

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Få IP-adresser som används av en enhet och hitta enheter som kommunicerar med den
Den här frågan använder `AssignedIPAddresses()` funktionen för att få tilldelade IP-adresser för enheten `example-device-name` () på eller före ett visst datum `example-date` (). Därefter används IP-adresserna för att hitta anslutningar till enheten initierad av andra enheter. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
