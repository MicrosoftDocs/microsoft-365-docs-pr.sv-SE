---
title: DeviceNetworkInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om nätverkskonfigurationsinformation i tabellen DeviceNetworkInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, machinenetworkinfo, DeviceNetworkInfo, enhet, dator, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: ce392ee074327114b0794edfeef9eb83091447d6
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42812273"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

**Gäller:**
- Skydd av Hot mot Microsoft



Tabellen `DeviceNetworkInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om nätverkskonfiguration av datorer, inklusive nätverkskort, IP- och MAC-adresser och anslutna nätverk eller domäner. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `NetworkAdapterName` | Sträng | Nätverkskortets namn |
| `MacAddress` | Sträng | MAC-adressen för nätverkskortet |
| `NetworkAdapterType` | Sträng | Typ av nätverkskort. För möjliga värden, se [denna uppräkning](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | Sträng | Nätverkskortets driftstatus. För möjliga värden, se [denna uppräkning](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | Sträng | Tunnelprotokoll, om gränssnittet används för detta ändamål, till exempel 6to4, Teredo, ISATAP, PPTP, SSTP och SSH |
| `ConnectedNetworks` | Sträng | Nätverk som kortet är anslutet till. Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till internet |
| `DnsAddresses` | Sträng | DNS-serveradresser i JSON-matrisformat |
| `IPv4Dhcp` | Sträng | DHCP-serverns IPv4-adress |
| `IPv6Dhcp` | Sträng | DHCP-serverns IPv6-adress |
| `DefaultGateways` | Sträng | Standardgatewayadresser i JSON-matrisformat |
| `IPAddresses` | Sträng | JSON-matris som innehåller alla IP-adresser som tilldelats kortet, tillsammans med deras respektive undernätsprefix och IP-adressutrymme, till exempel offentliga, privata eller länklokala |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
