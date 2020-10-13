---
title: DeviceNetworkInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om nätverks konfigurations information i tabellen DeviceNetworkInfo för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, machinenetworkinfo, DeviceNetworkInfo, enhet, dator, Mac, IP, adapter, DNS, DHCP, Gateway, tunnel
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 36edb4c1da63949b1ec8b914f831c1c5d36b7c7c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429925"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



`DeviceNetworkInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om nätverks konfiguration för datorer, inklusive nätverkskort, IP-adresser och Mac-adress samt anslutna nätverk eller domäner. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `ReportId` | tids | Händelse identifierare baserad på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel |
| `NetworkAdapterName` | strängvärdet | Namn på nätverkskortet |
| `MacAddress` | strängvärdet | MAC-adress för nätverkskortet |
| `NetworkAdapterType` | strängvärdet | Typ av nätverkskort. För möjliga värden, se [den här uppräkningen](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | strängvärdet | Drift status för nätverkskortet. För möjliga värden, se [den här uppräkningen](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | strängvärdet | Tunnel protokoll, om gränssnittet används för detta ändamål, till exempel 6to4, Teredo, ISATAP, PPTP, SSTP och SSH |
| `ConnectedNetworks` | strängvärdet | Nätverk som adaptern är ansluten till. Varje JSON-matris innehåller nätverks namnet, kategorin (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet |
| `DnsAddresses` | strängvärdet | DNS-serveradresser i JSON-mat ris format |
| `IPv4Dhcp` | strängvärdet | IPv4-adress för DHCP-server |
| `IPv6Dhcp` | strängvärdet | IPv6-adress för DHCP-server |
| `DefaultGateways` | strängvärdet | Standardgateway-adresser i JSON-mat ris format |
| `IPAddresses` | strängvärdet | JSON-matris som innehåller alla IP-adresser som tilldelats kortet samt deras respektive prefix och IP-adressutrymmet, till exempel offentligt, privat eller länk-lokal |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
