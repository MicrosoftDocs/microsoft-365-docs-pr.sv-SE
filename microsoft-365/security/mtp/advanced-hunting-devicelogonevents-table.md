---
title: DeviceLogonEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om inloggningsautentisering och inloggnings händelser i tabellen DeviceLogonEvents för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, logonevents, DeviceLogonEvents, inloggningsautentisering, inloggning, logga in
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
ms.openlocfilehash: f3c13025203a59eb192b9e0d193c429be57a83ce
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797986"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Gäller för:**
- Microsoft Hotskydd



`DeviceLogonEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om användar inloggningar och andra autentiseringsreferenser på enheter. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `ActionType` | strängvärdet |Typ av aktivitet som utlöste händelsen |
| `AccountDomain` | strängvärdet | Kontots domän |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountSid` | strängvärdet | Kontots säkerhets identifierare (SID) |
| `LogonType` | strängvärdet | Typ av inloggningssession, särskilt:<br><br> - **Interaktivt** -användaren interagerar med datorn med det lokala tangent bordet och skärmen<br><br> - **Interaktivt (RDP) inloggningar** – användaren interagerar med datorn via fjärr skrivbord, Terminal Services, Fjärrhjälp eller andra RDP-klienter<br><br> - En **nätverks** session initieras när datorn nås med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** Gruppsession initierad av schemalagda aktiviteter<br><br> - **Tjänst** -session initierad av tjänster allteftersom de startas<br> |
| `LogonId` | strängvärdet | Identifierare för en inloggningssession. Detta ID är endast unikt på samma dator mellan omstarter |
| `RemoteDeviceName` | strängvärdet | Namnet på den dator som utförde en fjärråtgärd på den påverkade datorn. Beroende på vilken händelse som rapporteras kan detta namn vara ett fullkvalificerat domän namn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domän information |
| `RemoteIP` | strängvärdet | IP-adress som var ansluten till |
| `RemoteIPType` | strängvärdet | Typ av IP-adress, till exempel offentlig, privat, reserverad, loopback, Teredo, FourToSixMapping och broadcast |
| `RemotePort` | signera | TCP-port på fjär renheten som du anslöt till |
| `AdditionalFields` | strängvärdet | Ytterligare information om händelsen i JSON-mat ris format |
| `InitiatingProcessAccountDomain` | strängvärdet | Domän för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountName` | strängvärdet | Användar namn för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountSid` | strängvärdet | Säkerhets identifierare (SID) för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessIntegrityLevel` | strängvärdet | Integritets nivå för den process som initierade händelsen. Windows tilldelar integritets nivåer för processer baserat på vissa egenskaper, till exempel om de startades från en nedladdning via Internet. Dessa integritets nivåer påverkar behörigheter för resurser |
| `InitiatingProcessTokenElevation` | strängvärdet | Tokentyp som anger närvaron av en behörighets höjning (User Access Control) som tillämpas på processen som initierade händelsen |
| `InitiatingProcessSHA1` | strängvärdet | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | strängvärdet | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt |
| `InitiatingProcessMD5` | strängvärdet | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | strängvärdet | Namn på processen som initierade händelsen |
| `InitiatingProcessId` | signera | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | strängvärdet | Kommando rad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid när processen som initierade händelsen startade |
| `InitiatingProcessFolderPath` | strängvärdet | Mapp som innehåller processen (bildfil) som initierade händelsen |
| `InitiatingProcessParentId` | signera | Process-ID (PID) för den överordnade processen som skapade processen för händelsen |
| `InitiatingProcessParentFileName` | strängvärdet | Namnet på den överordnade process som skapade processen som är ansvarig för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då den överordnade för processen som är ansvarig för händelsen startade |
| `ReportId` | tids | Händelse identifierare baserad på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel |
| `AppGuardContainerId` | strängvärdet | Identifierare för den virtualiserade behållare som används av Application Guard för att isolera webbläsaren |
| `IsLocalAdmin` | returtyp | Boolesk indikator för om användaren är lokal administratör på datorn |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
