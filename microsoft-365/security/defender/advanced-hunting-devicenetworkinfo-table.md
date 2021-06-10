---
title: DeviceNetworkInfo-tabell i det avancerade sökschemat
description: Mer information om nätverkskonfiguration finns i tabellen DeviceNetworkInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, gateway, tunnel
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
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023199"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint



Tabellen `DeviceNetworkInfo` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om nätverkskonfiguration av maskiner, inklusive nätverkskort, IP- och MAC-adresser och anslutna nätverk eller domäner. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `NetworkAdapterName` | sträng | Namn på nätverksadaptern |
| `MacAddress` | sträng | MAC-adressen för nätverksadaptern |
| `NetworkAdapterType` | sträng | Nätverksadaptertyp. Information om möjliga värden finns i [denna uppräkning](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `NetworkAdapterStatus` | sträng | Driftstatus för nätverksadaptern. Information om möjliga värden finns i [denna uppräkning](/dotnet/api/system.net.networkinformation.operationalstatus) |
| `TunnelType` | sträng | Tunnelprotokoll, om gränssnittet används för detta ändamål, t.ex. 6to4, Det här exemplet För företag, ISATAP, PPTP, SSTP och SSH |
| `ConnectedNetworks` | sträng | Nätverk som adaptern är ansluten till. Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet |
| `DnsAddresses` | sträng | DNS-serveradresser i JSON-matrisformat |
| `IPv4Dhcp` | sträng | IPv4-adressen till PSP-servern |
| `IPv6Dhcp` | sträng | IPv6-adressen till PSP-servern |
| `DefaultGateways` | sträng | Standardgatewayadresser i JSON-matrisformat |
| `IPAddresses` | sträng | JSON-matris som innehåller alla IP-adresser som tilldelats adaptern, tillsammans med respektive undernätsprefix och IP-adressutrymme, t.ex. offentlig, privat eller länk lokalt |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)