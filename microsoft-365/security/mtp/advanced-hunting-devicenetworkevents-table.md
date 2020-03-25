---
title: DeviceNetworkEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om nätverksanslutningshändelser som du kan fråga från tabellen DeviceNetworkEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, devicenetworkevents, NetworkCommunicationEvents, nätverk anslutning, fjärr-ip, lokal ip
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
ms.openlocfilehash: d5e3327f4b4e066b3e4c14f646ad8db78ff3804a
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929046"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

**Gäller:**
- Microsofts hotskydd



Tabellen `DeviceNetworkEvents` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om nätverksanslutningar och relaterade händelser. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `RemoteIP` | Sträng | IP-adress som var ansluten till |
| `RemotePort` | Int | TCP-porten på fjärrenheten som var ansluten till |
| `RemoteUrl` | Sträng | URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till |
| `LocalIP` | Sträng | IP-adress som tilldelats den lokala dator som används under kommunikation |
| `LocalPort` | Int | TCP-port på den lokala maskinen som används under kommunikation |
| `Protocol` | Sträng | Protokoll som används under kommunikationen |
| `LocalIPType` | Sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Teredo, FourToSixMapping och Broadcast |
| `RemoteIPType` | Sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Teredo, FourToSixMapping och Broadcast |
| `InitiatingProcessSHA1` | Sträng | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessMD5` | Sträng | MD5-hash i processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | Sträng | Namnet på den process som initierade händelsen |
| `InitiatingProcessId` | Int | Process-ID (PID) för den process som initierade händelsen |
| `InitiatingProcessCommandLine` | Sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | Datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessFolderPath` | Sträng | Mapp som innehåller processen (bildfilen) som initierade händelsen |
| `InitiatingProcessParentFileName` | Sträng | Namn på den överordnade process som gav upphov till den process som ansvarar för händelsen |
| `InitiatingProcessParentId` | Int | Process-ID (PID) för den överordnade processen som gav upphov till den process som var ansvarig för händelsen |
| `InitiatingProcessParentCreationTime` | Datetime | Datum och tid då den överordnade processen som ansvarar för händelsen startades |
| `InitiatingProcessAccountDomain` | Sträng | Domän för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountName` | Sträng | Användarnamn för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessIntegrityLevel` | Sträng | Integritetsnivå för den process som initierade händelsen. Windows tilldelar integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de lanserades från en nedladdning på Internet. Dessa integritetsnivåer påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | Sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighetshöjning (User Access Control) som tillämpas på den process som initierade händelsen |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | Sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Tillämpa metodtips för frågor](advanced-hunting-best-practices.md)
