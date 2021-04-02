---
title: Funktionen AssignedIPAddresses() i avancerad sökning för Microsoft Defender för slutpunkt
description: Lär dig hur du använder funktionen AssignedIPAddresses() för att få de senaste IP-adresserna tilldelade till en enhet
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, mdatp, Microsoft Defender ATP, Microsoft Defender för slutpunkt, Windows Defender, Windows Defender ATP, Windows Defender Avancerat skydd, sökning, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, vinst
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 5dcc41302d797b4084c36d020908ba59131c90d4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499278"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Använd funktionen `AssignedIPAddresses()` för avancerade sökfrågor för att snabbt hämta de senaste IP-adresserna som har tilldelats till en enhet. Om du anger ett tidsstämpelargument hämtar den här funktionen de senaste IP-adresserna vid den angivna tiden.

Den här funktionen returnerar en tabell med följande kolumner:

Kolumn | Datatyp | Beskrivning
-|-|-
`Timestamp` | datetime | Senaste gången då enheten observerades med HJÄLP av IP-adressen
`IPAddress` | sträng | IP-adress som används av enheten
`IPType` | sträng | Anger om IP-adressen är en offentlig eller privat adress
`NetworkAdapterType` | int | Nätverksadaptertyp som används av enheten som har tilldelats IP-adressen. Information om möjliga värden finns i [denna uppräkning](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)
`ConnectedNetworks` | int | Nätverk som adaptern med den tilldelade IP-adressen är ansluten till. Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet

## <a name="syntax"></a>Syntax

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argument

- **x**– `DeviceId` eller värde som identifierar `DeviceName` enheten
- **y**– (datetime)-värde som instruerar funktionen för att hämta de senast tilldelade `Timestamp` IP-adresserna från en viss tid. Om detta inte anges returnerar funktionen de senaste IP-adresserna.

## <a name="examples"></a>Exempel

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Hämta listan med IP-adresser som användes av en enhet för 24 timmar sedan

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Få IP-adresser använda av en enhet och hitta enheter som kommunicerar med den

Den här frågan använder `AssignedIPAddresses()` funktionen för att hämta tilldelade IP-adresser för enheten `example-device-name` () på eller före ett visst datum ( `example-date` ). Därefter används IP-adresserna för att hitta anslutningar till enheten initierad av andra enheter. 

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
- [Förstå schemat](advanced-hunting-schema-reference.md)
