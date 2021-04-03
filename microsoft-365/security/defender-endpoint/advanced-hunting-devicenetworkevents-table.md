---
title: DeviceNetworkEvents-tabellen i det avancerade sökschemat
description: Läs mer om nätverksanslutningshändelser som du kan fråga från tabellen DeviceNetworkEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, devicenetworkevents, nätverksanslutning, fjärr-ip, lokal ip, NetworkCommunicationEvents
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
ms.technology: mde
ms.openlocfilehash: de31cb923a0584f45cb92340cf7e1c6b5ca5e9a0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500766"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Tabellen `DeviceNetworkEvents` i det avancerade schemat för [sökning](advanced-hunting-overview.md) innehåller information om nätverksanslutningar och relaterade händelser. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen |
| `RemoteIP` | sträng | IP-adress som var ansluten till |
| `RemotePort` | int | TCP-port på den fjärrenhet som var ansluten till |
| `RemoteUrl` | sträng | URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till |
| `LocalIP` | sträng | IP-adress tilldelad till den lokala enheten som används under kommunikation |
| `LocalPort` | int | TCP-port på den lokala enheten som används under kommunikation |
| `Protocol` | sträng | IP-protokoll som används, oavsett om TCP eller UDP används |
| `LocalIPType` | sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Ochedo, FourToSixMapping och Sändning |
| `RemoteIPType` | sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Ochedo, FourToSixMapping och Sändning |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessId` | int | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessFolderPath` | sträng | Mapp som innehåller den process (bildfil) som initierade händelsen |
| `InitiatingProcessParentFileName` | sträng | Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen |
| `InitiatingProcessParentId` | int | Process-ID (PID) för den överordnade process som hanterade processen som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då föräldern till processen som ansvarar för händelsen startades |
| `InitiatingProcessAccountDomain` | sträng | Domän för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountName` | sträng | Användarnamn för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessIntegrityLevel` | sträng | Integritetsnivån för processen som initierade händelsen. I Windows tilldelar Windows integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de startades från en Internetnedladdning. De här integritetsnivåerna påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för processen som initierade händelsen |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med `DeviceName` `Timestamp` kolumnerna och |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
