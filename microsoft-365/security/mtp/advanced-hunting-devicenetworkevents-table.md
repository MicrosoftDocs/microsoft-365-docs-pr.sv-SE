---
title: DeviceNetworkEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om nätverks anslutnings händelser du kan söka i DeviceNetworkEvents-tabellen för det avancerade jakt schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, devicenetworkevents, NetworkCommunicationEvents, nätverks anslutning, fjärr-IP, lokal IP
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 8a385989bc7fd21a136124fdd4658ef64538c82a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414100"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



`DeviceNetworkEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om nätverks anslutningar och relaterade händelser. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen. Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `RemoteIP` | strängvärdet | IP-adress som var ansluten till |
| `RemotePort` | signera | TCP-port på fjär renheten som du anslöt till |
| `RemoteUrl` | strängvärdet | URL-adressen eller det fullständigt kvalificerade domän namnet (FQDN) som anslöts till |
| `LocalIP` | strängvärdet | IP-adress som tilldelats till den lokala datorn under kommunikationen |
| `LocalPort` | signera | TCP-port på den lokala datorn som används vid kommunikation |
| `Protocol` | strängvärdet | Protokoll som används under kommunikationen |
| `LocalIPType` | strängvärdet | Typ av IP-adress, till exempel offentlig, privat, reserverad, loopback, Teredo, FourToSixMapping och broadcast |
| `RemoteIPType` | strängvärdet | Typ av IP-adress, till exempel offentlig, privat, reserverad, loopback, Teredo, FourToSixMapping och broadcast |
| `InitiatingProcessSHA1` | strängvärdet | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | strängvärdet | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `InitiatingProcessMD5` | strängvärdet | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | strängvärdet | Namn på processen som initierade händelsen |
| `InitiatingProcessId` | signera | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | strängvärdet | Kommando rad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid när processen som initierade händelsen startade |
| `InitiatingProcessFolderPath` | strängvärdet | Mapp som innehåller processen (bildfil) som initierade händelsen |
| `InitiatingProcessParentFileName` | strängvärdet | Namnet på den överordnade process som skapade processen som är ansvarig för händelsen |
| `InitiatingProcessParentId` | signera | Process-ID (PID) för den överordnade processen som skapade processen för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då den överordnade för processen som är ansvarig för händelsen startade |
| `InitiatingProcessAccountDomain` | strängvärdet | Domän för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountName` | strängvärdet | Användar namn för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountSid` | strängvärdet | Säkerhets identifierare (SID) för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessIntegrityLevel` | strängvärdet | Integritets nivå för den process som initierade händelsen. Windows tilldelar integritets nivåer för processer baserat på vissa egenskaper, till exempel om de startades från en nedladdning via Internet. Dessa integritets nivåer påverkar behörigheter för resurser |
| `InitiatingProcessTokenElevation` | strängvärdet | Tokentyp som anger närvaron av en behörighets höjning (User Access Control) som tillämpas på processen som initierade händelsen |
| `ReportId` | tids | Händelse identifierare baserad på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel |
| `AppGuardContainerId` | strängvärdet | Identifierare för den virtualiserade behållare som används av Application Guard för att isolera webbläsaren |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
