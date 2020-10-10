---
title: DeviceFileEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om filrelaterade händelser i tabellen DeviceFileEvents i det avancerade Antivirus schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, filecreationevents, DeviceFileEvents, filer, sökväg, hash, SHA1, SHA256, MD5
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
ms.openlocfilehash: 2d1b8e871a4139a4e025313fe1bda724e87c9b6d
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412220"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

`DeviceFileEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om hur du skapar, ändrar och andra fil system händelser. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen. Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | strängvärdet | Namnet på filen som den inspelade åtgärden tillämpades för |
| `FolderPath` | strängvärdet | Mapp som innehåller filen som den inspelade åtgärden tillämpades för |
| `SHA1` | strängvärdet | SHA-1 av filen som den inspelade åtgärden tillämpades på |
| `SHA256` | strängvärdet | SHA-256 av filen som den registrerade åtgärden tillämpades på. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `MD5` | strängvärdet | MD5-hash för filen som den inspelade åtgärden tillämpades för |
| `FileOriginUrl` | strängvärdet | URL dit filen laddades ned från |
| `FileOriginReferrerUrl` | strängvärdet | URL för webb sidan som länkar till den hämtade filen |
| `FileOriginIP` | strängvärdet | IP-adress dit filen laddades ned från |
| `InitiatingProcessAccountDomain` | strängvärdet | Domän för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountName` | strängvärdet | Användar namn för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountSid` | strängvärdet | Säkerhets identifierare (SID) för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessMD5` | strängvärdet | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA1` | strängvärdet | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | strängvärdet | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `InitiatingProcessFolderPath` | strängvärdet | Mapp som innehåller processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | strängvärdet | Namn på processen som initierade händelsen |
| `InitiatingProcessId` | signera | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | strängvärdet | Kommando rad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid när processen som initierade händelsen startade |
| `InitiatingProcessIntegrityLevel` | strängvärdet | Integritets nivå för den process som initierade händelsen. Windows tilldelar integritets nivåer för processer baserat på vissa egenskaper, till exempel om de startades från en nedladdning via Internet. Dessa integritets nivåer påverkar behörigheter för resurser |
| `InitiatingProcessTokenElevation` | strängvärdet | Tokentyp som anger närvaron av en behörighets höjning (User Access Control) som tillämpas på processen som initierade händelsen |
| `InitiatingProcessParentId` | signera | Process-ID (PID) för den överordnade processen som skapade processen för händelsen |
| `InitiatingProcessParentFileName` | strängvärdet | Namnet på den överordnade process som skapade processen som är ansvarig för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då den överordnade för processen som är ansvarig för händelsen startade |
| `RequestProtocol` | strängvärdet | Nätverks protokoll, om tillämpligt, används för att initiera aktiviteten: okänd, lokal, SMB eller NFS |
| `ShareName` | strängvärdet | Namn på den delade mappen som innehåller filen |
| `RequestSourceIP` | strängvärdet | IPv4-eller IPv6-adress för den fjär renhet som initierade aktiviteten |
| `RequestSourcePort` | strängvärdet | Käll port på fjär renheten som initierade aktiviteten |
| `RequestAccountName` | strängvärdet | Användar namnet på kontot som används för att fjärrstarta aktiviteten |
| `RequestAccountDomain` | strängvärdet | Domän för det konto som används för att fjärrstarta aktiviteten |
| `RequestAccountSid` | strängvärdet | Säkerhets identifierare (SID) för det konto som används för att fjärrstarta aktiviteten |
| `ReportId` | tids | Händelse identifierare baserad på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel |
| `AppGuardContainerId` | strängvärdet | Identifierare för den virtualiserade behållare som används av Application Guard för att isolera webbläsaren |
| `SensitivityLabel` | strängvärdet | Etikett som används för ett e-postmeddelande, en fil eller annat innehåll för att klassificera den för informations skydd |
| `SensitivitySubLabel` | strängvärdet | Under etikett används för ett e-postmeddelande, en fil eller annat innehåll för att klassificera den för informations skydd; under etiketter för känslighet är grupperade under känslighets etiketter men behandlas oberoende av varandra |
| `IsAzureInfoProtectionApplied` | returtyp | Anger om filen har krypterats med Azure information Protection |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
