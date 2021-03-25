---
title: Tabellen DeviceFileEvents i det avancerade sökschemat
description: Mer information om filrelaterade händelser i tabellen DeviceFileEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, enhetsfiler, filer, sökväg, hash, sha1, sha256, md5, FileCreationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21a1bb17771314bc64f92009df4138e9550a7389
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075113"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Tabellen `DeviceFileEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om hur du skapar filer, ändras och andra filsystemhändelser. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen |
| `FileName` | sträng | Namnet på filen som den inspelade åtgärden tillämpats på |
| `FolderPath` | sträng | Mapp som innehåller den fil som den inspelade åtgärden tillämpats på |
| `SHA1` | sträng | SHA-1 för filen som den inspelade åtgärden tillämpats på |
| `SHA256` | sträng | SHA-256 av filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig |
| `MD5` | sträng | MD5-hash för filen som den inspelade åtgärden tillämpats på |
| `FileOriginUrl` | sträng | URL som filen laddades ned från |
| `FileOriginReferrerUrl` | sträng | URL-adressen till webbsidan som länkar till den hämtade filen |
| `FileOriginIP` | sträng | IP-adress där filen laddades ned från |
| `InitiatingProcessAccountDomain` | sträng | Domän för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountName` | sträng | Användarnamn för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFolderPath` | sträng | Mapp som innehåller den process (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessId` | int | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessIntegrityLevel` | sträng | integritetsnivån för den process som initierade händelsen. I Windows tilldelar Windows integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de startades från en Internetnedladdning. De här integritetsnivåerna påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för processen som initierade händelsen |
| `InitiatingProcessParentId` | int | Process-ID (PID) för den överordnade process som hanterade processen som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | sträng | Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då föräldern till processen som ansvarar för händelsen startades |
| `RequestProtocol` | sträng | Nätverksprotokoll, om tillämpligt, används för att starta aktiviteten: Okänd, Lokal, SMB eller NFS |
| `ShareName` | sträng | Namn på delad mapp som innehåller filen |
| `RequestSourceIP` | sträng | IPv4- eller IPv6-adressen för den fjärrenhet som initierade aktiviteten |
| `RequestSourcePort` | sträng | Källport på den fjärrenhet som initierade aktiviteten |
| `RequestAccountName` | sträng | Användarnamn på konto som används för att starta aktiviteten via fjärrstyrning |
| `RequestAccountDomain` | sträng | Domän för kontot som används för att starta aktiviteten via fjärrstyrning |
| `RequestAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot för att fjärr initiera aktiviteten |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |
| `SensitivityLabel` | sträng | Etikett som använts på ett e-postmeddelande, en fil eller annat innehåll för att klassificera det som informationsskydd |
| `SensitivitySubLabel` | sträng | Sublabel tillämpat på ett e-postmeddelande, en fil eller annat innehåll för att klassificera det som informationsskydd. känslighetsunderetiketter är grupperade under känslighetsetiketter, men behandlas oberoende av varandra |
| `IsAzureInfoProtectionApplied` | boolesk | Anger om filen krypteras med Azure Information Protection |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
