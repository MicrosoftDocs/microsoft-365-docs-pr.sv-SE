---
title: Tabellen DeviceLogonEvents i det avancerade sökschemat
description: Läs mer om autentiserings- eller inloggningshändelser i tabellen DeviceLogonEvents i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicelogonevents, authentication, logon, sign in, LogonEvents
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
ms.openlocfilehash: c270f54c856c1ed504533c826ca884786c784549
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499153"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Tabellen `DeviceLogonEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om användarinloggningar och andra autentiseringshändelser. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

> [!NOTE]
> Samling av DeviceLogonEvents stöds inte i Windows 7 eller Windows Server 2008 R2.
> Vi rekommenderar att du uppgraderar till Windows 10 eller Windows Server 2019 för optimal insyn i användarnas inloggningsaktivitet.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `ActionType` | sträng |Typ av aktivitet som utlöste händelsen |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `LogonType` | sträng | Typ av inloggningssession, särskilt:<br><br> - **Interaktivt** – Användaren interagerar fysiskt med enheten med det lokala tangentbordet och den lokala skärmen<br><br> - **Fjärr interaktiva inloggningar (RDP)** – Användaren interagerar med enheten via fjärrstyrning med Fjärrskrivbord, Terminal Services, Fjärrhjälp eller andra RDP-klienter<br><br> - **Nätverk** – session initierad när enheten nås med PsExec eller när delade resurser på enheten, till exempel skrivare och delade mappar, används<br><br> - **Batch** – session initierad av schemalagda aktiviteter<br><br> - **Tjänst** – session initierad av tjänster när de startar<br> |
| `LogonId` | sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma enhet bara mellan omstarter |
| `RemoteDeviceName` | sträng | Namnet på enheten som utförde en fjärråtgärd på den aktuella enheten. Beroende på vilken händelse som rapporteras kan det här namnet vara ett fullständigt kvalificerat domännamn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domäninformation |
| `RemoteIP` | sträng | IP-adress som var ansluten till |
| `RemoteIPType` | sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Ochedo, FourToSixMapping och Sändning |
| `RemotePort` | int | TCP-port på den fjärrenhet som var ansluten till |
| `AdditionalFields` | sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `InitiatingProcessAccountDomain` | sträng | Domän för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountName` | sträng | Användarnamn för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessIntegrityLevel` | sträng | Integritetsnivån för processen som initierade händelsen. I Windows tilldelar Windows integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de startades från en Internetnedladdning. De här integritetsnivåerna påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för processen som initierade händelsen |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | sträng | SHA-256 för processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessId` | int | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessFolderPath` | sträng | Mapp som innehåller den process (bildfil) som initierade händelsen |
| `InitiatingProcessParentId` | int | Process-ID (PID) för den överordnade process som hanterade processen som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | sträng | Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då föräldern till processen som ansvarar för händelsen startades |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med `DeviceName` `Timestamp` kolumnerna och |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |
| `IsLocalAdmin` | boolesk | Boolesk indikator om användaren är lokal administratör på enheten |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
