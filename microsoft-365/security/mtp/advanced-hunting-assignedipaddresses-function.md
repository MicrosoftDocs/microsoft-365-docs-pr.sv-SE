---
title: AssignedIPAddresses ()-funktion i avancerad jakt för skydd mot Microsoft Threat
description: Lär dig hur du använder funktionen AssignedIPAddresses () för att få de senaste IP-adresserna tilldelade till en enhet
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, FileProfile, fil profil, funktion och berikning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ea6b65e5e6d676c5efb2622193197bae5b9ba1b2
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338551"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

Använd `AssignedIPAddresses()` funktionen i de [avancerade jakt](advanced-hunting-overview.md) frågorna för att snabbt få de senaste IP-adresserna som har tilldelats till en enhet. Om du anger ett timestamp-argument får den här funktionen de senaste IP-adresserna vid den angivna tiden. 

Den här funktionen returnerar en tabell med följande kolumner:

| Kolumn | Datatyp | Beskrivning |
|------------|-------------|-------------|
| `Timestamp` | datetime | Senaste gången när enheten observerats med hjälp av IP-adressen |
| `IPAddress` | strängvärdet | IP-adress som används av enheten |
| `IPType` | strängvärdet | Anger om IP-adressen är en offentlig eller privat adress |
| `NetworkAdapterType` | signera | Nätverkskort typ som används av enheten som tilldelats IP-adressen. För möjliga värden, se [den här uppräkningen](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | signera | Nätverk som adaptern med den tilldelade IP-adressen är ansluten till. Varje JSON-matris innehåller nätverks namnet, kategorin (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet |

## <a name="syntax"></a>Frågesyntaxen

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argument

- **x**– `DeviceId` eller `DeviceName` värde som identifierar enheten
- **y**– `Timestamp` (datetime)-värde som anger funktionen för att hämta de senaste tilldelade IP-adresserna från en viss tidpunkt. Om inget anges returnerar funktionen de senaste IP-adresserna.

## <a name="examples"></a>Exempel

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Hämta listan med IP-adresser som används av en enhet för mer än 24 timmar sedan

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Hämta IP-adresser som används av en enhet och hitta enheter som kommunicerar med den
Den här frågan använder `AssignedIPAddresses()` funktionen för att få tilldelade IP-adresser för enheten ( `example-device-name` ) på eller före ett visst datum ( `example-date` ). Därefter används IP-adresserna för att hitta anslutningar till enheten som initieras av andra enheter. 

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
