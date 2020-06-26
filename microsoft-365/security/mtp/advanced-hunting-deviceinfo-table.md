---
title: DeviceInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om operativsystem, datornamn och annan maskininformation i tabellen DeviceInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, maskininfo, DeviceInfo, enhet, maskin, OS, plattform, användare
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
ms.openlocfilehash: 526e210a472862593f2652e9b2b21957702c48f0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899285"
---
# <a name="deviceinfo"></a>DeviceInfo

**Gäller:**
- Microsoft Hotskydd



`DeviceInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om datorer i organisationen, inklusive OS-version, aktiva användare och datornamn. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `ClientVersion` | Sträng | Version av slutpunktsagenten eller sensorn som körs på maskinen |
| `PublicIP` | Sträng | Offentlig IP-adress som används av den inbyggda datorn för att ansluta till Microsoft Defender ATP-tjänsten. Detta kan vara IP-adressen för själva maskinen, en NAT-enhet eller en proxy |
| `OSArchitecture` | Sträng | Arkitektur för operativsystemet som körs på datorn |
| `OSPlatform` | Sträng | Plattform för operativsystemet som körs på maskinen. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7 |
| `OSBuild` | Sträng | Skapa version av operativsystemet som körs på datorn |
| `IsAzureADJoined` | Boolean | Boolesk indikator på om datorn är ansluten till Azure Active Directory |
| `LoggedOnUsers` | Sträng | Lista över alla användare som är inloggade på datorn vid tidpunkten för händelsen i JSON-matrisformat |
| `RegistryDeviceTag` | Sträng | Maskintagg som lagts till i registret |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `OSVersion` | Sträng | Version av operativsystemet som körs på datorn |
| `MachineGroup` | Sträng | Maskinens maskingrupp. Den här gruppen används av rollbaserad åtkomstkontroll för att fastställa åtkomst till datorn |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
