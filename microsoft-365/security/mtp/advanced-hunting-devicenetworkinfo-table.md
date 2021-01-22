---
title: DeviceNetworkInfo-tabell i det avancerade sökschemat
description: Läs mer om information om nätverkskonfiguration i tabellen DeviceNetworkInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, machinenetworkinfo, DeviceNetworkInfo, enhet, dator, mac, ip, adapter, dns, gateway, tunnel
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931212"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Tabellen `DeviceNetworkInfo` i det avancerade [utbildningsschemat](advanced-hunting-overview.md) innehåller information om nätverkskonfiguration av maskiner, inklusive nätverkskort, IP- och MAC-adresser och anslutna nätverk eller domäner. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `ReportId` | long | Händelseidentifierare baserade på en återkommande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `NetworkAdapterName` | sträng | Namn på nätverksadaptern |
| `MacAddress` | sträng | MAC-adressen för nätverksadaptern |
| `NetworkAdapterType` | sträng | Nätverksadaptertyp. Referera till den här uppräkningen [för möjliga värden](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | sträng | Driftstatus för nätverksadaptern. Referera till den här uppräkningen [för möjliga värden](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | sträng | Tunnelprotokoll, om gränssnittet används för detta ändamål, till exempel 6to4,Certifikatedo, ISATAP, PPTP, SSTP och SSH |
| `ConnectedNetworks` | sträng | Nätverk som adaptern är ansluten till. Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet |
| `DnsAddresses` | sträng | DNS-serveradresser i JSON-matrisformat |
| `IPv4Dhcp` | sträng | IPv4-adressen till DEN HÄR SERVERN |
| `IPv6Dhcp` | sträng | IPv6-adressen till DEN HÄR SERVERN |
| `DefaultGateways` | sträng | Standardgatewayadresser i JSON-matrisformat |
| `IPAddresses` | sträng | JSON-matris som innehåller alla IP-adresser som tilldelats adaptern, tillsammans med respektive undernätsprefix och IP-adressutrymme, till exempel offentliga, privata eller länk-lokala |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
