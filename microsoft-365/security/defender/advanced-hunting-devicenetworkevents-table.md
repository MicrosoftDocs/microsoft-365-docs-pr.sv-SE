---
title: DeviceNetworkEvents-tabellen i det avancerade sökschemat
description: Läs mer om nätverksanslutningshändelser som du kan fråga från tabellen DeviceNetworkEvents i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, devicenetworkevents, NetworkCommunicationEvents, network connection, remote ip, local ip
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ffa79ea7e3c75887531020e83d081ee3206d1a11
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382859"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Tabellen `DeviceNetworkEvents` i det avancerade schemat för [sökning](advanced-hunting-overview.md) innehåller information om nätverksanslutningar och relaterade händelser. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i portalen |
| `RemoteIP` | sträng | IP-adress som var ansluten till |
| `RemotePort` | int | TCP-port på den fjärrenhet som var ansluten till |
| `RemoteUrl` | sträng | URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till |
| `LocalIP` | sträng | IP-adress tilldelad till den lokala datorn som används under kommunikation |
| `LocalPort` | int | TCP-port på den lokala datorn som används under kommunikation |
| `Protocol` | sträng | Protokoll som används under kommunikationen |
| `LocalIPType` | sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Ochedo, FourToSixMapping och Sändning |
| `RemoteIPType` | sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Ochedo, FourToSixMapping och Sändning |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | sträng | SHA-256 för processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessFileSize` | long | Storlek på filen som körde processen som ansvarar för händelsen |
| `InitiatingProcessVersionInfoCompanyName` | sträng | Företagsnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoProductName` | sträng | Produktnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoProductVersion` | sträng | Produktversion från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoInternalFileName` | sträng | Internt filnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoOriginalFileName` | sträng | Det ursprungliga filnamnet från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoFileDescription` | sträng | Beskrivning av versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
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
| `InitiatingProcessAccountUpn` | sträng | Användarkontons huvudnamn (UPN) för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountObjectId` | sträng | Azure AD-objekt-ID för användarkontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessIntegrityLevel` | sträng | Integritetsnivån för processen som initierade händelsen. I Windows tilldelar Windows integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de startades från en Internetnedladdning. De här integritetsnivåerna påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för processen som initierade händelsen |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |
| `AdditionalFields` | sträng | Ytterligare information om händelsen i JSON-matrisformat |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
