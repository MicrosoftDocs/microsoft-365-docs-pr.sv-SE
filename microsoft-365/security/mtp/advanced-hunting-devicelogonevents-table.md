---
title: DeviceLogonEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om autentiserings- eller inloggningshändelser i tabellen DeviceLogonEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, logonevents, DeviceLogonEvents, autentisering, inloggning, inloggning
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
ms.openlocfilehash: 67fa551fd7c2add815d5698a22b5eb3ae607f716
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048285"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Gäller:**
- Microsoft Hotskydd



`DeviceLogonEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om användarinloggningar och andra autentiseringshändelser på enheter. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `ActionType` | Sträng |Typ av aktivitet som utlöste händelsen |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot |
| `LogonType` | Sträng | Typ av inloggningssession, särskilt:<br><br> - **Interaktiv** - Användaren interagerar fysiskt med maskinen med det lokala tangentbordet och skärmen<br><br> - **Fjärr interaktiva (RDP)-inloggningar** - Användaren interagerar med datorn på distans med fjärrskrivbord, Terminal Services, Fjärrhjälp eller andra RDP-klienter<br><br> - **Nätverk** - Session initieras när datorn används med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** - Session initierad av schemalagda aktiviteter<br><br> - **Service** - Session initierad av tjänster när de börjar<br> |
| `LogonId` | Sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `RemoteDeviceName` | Sträng | Namn på den maskin som utförde en fjärråtgärd på den berörda datorn. Beroende på vilken händelse som rapporteras kan det här namnet vara ett fullständigt kvalificerat domännamn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domäninformation |
| `RemoteIP` | Sträng | IP-adress som var ansluten till |
| `RemoteIPType` | Sträng | Typ av IP-adress, till exempel Offentlig, Privat, Reserverad, Loopback, Teredo, FourToSixMapping och Broadcast |
| `RemotePort` | Int | TCP-porten på fjärrenheten som var ansluten till |
| `AdditionalFields` | Sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `InitiatingProcessAccountDomain` | Sträng | Domän för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountName` | Sträng | Användarnamn för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessIntegrityLevel` | Sträng | Integritetsnivå för den process som initierade händelsen. Windows tilldelar integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de lanserades från en nedladdning på Internet. Dessa integritetsnivåer påverkar behörigheter för resurser |
| `InitiatingProcessTokenElevation` | Sträng | Tokentyp som anger närvaron eller frånvaron av UAC-behörighetshöjning (User Access Control) som tillämpas på den process som initierade händelsen |
| `InitiatingProcessSHA1` | Sträng | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | Sträng | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när den är tillgänglig |
| `InitiatingProcessMD5` | Sträng | MD5-hash i processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | Sträng | Namn på den process som initierade händelsen |
| `InitiatingProcessId` | Int | Process-ID (PID) för den process som initierade händelsen |
| `InitiatingProcessCommandLine` | Sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | Datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessFolderPath` | Sträng | Mapp som innehåller processen (bildfilen) som initierade händelsen |
| `InitiatingProcessParentId` | Int | Process-ID (PID) för den överordnade processen som gav upphov till den process som var ansvarig för händelsen |
| `InitiatingProcessParentFileName` | Sträng | Namn på den överordnade process som gav upphov till den process som var ansvarig för händelsen |
| `InitiatingProcessParentCreationTime` | Datetime | Datum och tid då den överordnade processen som var ansvarig för händelsen startades |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | Sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |
| `IsLocalAdmin` | Boolean | Boolesk indikator på om användaren är en lokal administratör på datorn |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
