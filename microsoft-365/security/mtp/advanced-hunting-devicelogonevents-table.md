---
title: Tabellen DeviceLogonEvents i det avancerade jaktschemat
description: Läs mer om autentiserings- eller inloggningshändelser i tabellen DeviceLogonEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, inloggningshändelser, DeviceLogonEvents, autentisering, inloggning, logga in
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
ms.openlocfilehash: 7c7f1bba23379b25ccecc427b2aa866a1105396d
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807663"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Gäller:**
- Skydd av Hot mot Microsoft



Tabellen `DeviceLogonEvents` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om användarinloggningar och andra autentiseringshändelser. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `ActionType` | Sträng |Typ av aktivitet som utlöste händelsen |
| `AccountDomain` | Sträng | Kontodomänen |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountSid` | Sträng | SID(SECURITY Identifier) för kontot |
| `LogonType` | Sträng | Typ av inloggningssession, särskilt:<br><br> - **Interaktiv** - Användaren interagerar fysiskt med maskinen med det lokala tangentbordet och skärmen<br><br> - **Fjärrstyrda inloggningar (RDP)** – Användaren interagerar med datorn på distans med fjärrskrivbord, terminaltjänster, fjärrhjälp eller andra RDP-klienter<br><br> - **Nätverk** - Session initieras när datorn nås med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** - Session initierad av schemalagda aktiviteter<br><br> - **Service** - Session initierad av tjänster när de startar<br> |
| `LogonId` | Sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `RemoteDeviceName` | Sträng | Namnet på maskinen som utförde en fjärråtgärd på den berörda datorn. Beroende på vilken händelse som rapporteras kan det här namnet vara ett fullständigt kvalificerat domännamn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domäninformation |
| `RemoteIP` | Sträng | IP-adress som var ansluten till |
| `RemoteIPType` | Sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Teredo, FourToSixMapping och Broadcast |
| `RemotePort` | Int | TCP-port på fjärrenheten som var ansluten till |
| `AdditionalFields` | Sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `InitiatingProcessAccountDomain` | Sträng | Domän för kontot som körde den process som ansvarar för händelsen |
| `InitiatingProcessAccountName` | Sträng | Användarnamn för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessIntegrityLevel` | Sträng | Integritetsnivån för den process som initierade händelsen. Windows tilldelar integritetsnivåer till processer som baseras på vissa egenskaper, till exempel om de lanserades från en internetnedladdning. Dessa integritetsnivåer påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | Sträng | Tokentyp som anger förekomsten eller frånvaron av UAC-behörighetshöjning (User Access Control) som tillämpats på den process som initierade händelsen |
| `InitiatingProcessSHA1` | Sträng | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | Sträng | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt |
| `InitiatingProcessMD5` | Sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | Sträng | Namnet på den process som initierade händelsen |
| `InitiatingProcessId` | Int | Process-ID (PID) för den process som initierade händelsen |
| `InitiatingProcessCommandLine` | Sträng | Kommandorad som används för att köra den process som initierade händelsen |
| `InitiatingProcessCreationTime` | Datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessFolderPath` | Sträng | Mapp som innehåller processen (bildfilen) som initierade händelsen |
| `InitiatingProcessParentId` | Int | Process-ID (PID) för den överordnade processen som gav upphov till den process som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | Sträng | Namnet på den överordnade process som gav upphov till den process som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | Datetime | Datum och tid då den överordnade processen som ansvarar för händelsen startades |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | Sträng | Identifierare för den virtualiserade behållare som används av Application Guard för att isolera webbläsaraktiviteten |
| `IsLocalAdmin` | Boolean | Boolesk indikator på om användaren är en lokal administratör på datorn |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
