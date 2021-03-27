---
title: Tabellen DeviceFileEvents i det avancerade sökschemat
description: Mer information om filrelaterade händelser i tabellen DeviceFileEvents i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, filecreationevents, DeviceFileEvents, files, path, hash, sha1, sha256, md5
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
ms.openlocfilehash: 62989eca2fd00757ea02d03bf24a0049135d97b0
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382871"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen `DeviceFileEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om hur du skapar filer, ändras och andra filsystemhändelser. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i portalen |
| `FileName` | sträng | Namnet på filen som den inspelade åtgärden tillämpats på |
| `FolderPath` | sträng | Mapp som innehåller den fil som den inspelade åtgärden tillämpats på |
| `SHA1` | sträng | SHA-1 för filen som den inspelade åtgärden tillämpats på |
| `SHA256` | sträng | SHA-256 av filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `MD5` | sträng | MD5-hash för filen som den inspelade åtgärden tillämpats på |
| `FileOriginUrl` | sträng | URL som filen laddades ned från |
| `FileOriginReferrerUrl` | sträng | URL-adressen till webbsidan som länkar till den hämtade filen |
| `FileOriginIP` | sträng | IP-adress där filen laddades ned från |
| `PreviousFolderPath` | sträng | Originalmapp som innehåller filen innan den inspelade åtgärden tillämpats |
| `PreviousFileName` | sträng | Det ursprungliga namnet på filen som ändrades till följd av åtgärden |
| `FileSize` | long | Storlek på filen i byte |
| `InitiatingProcessAccountDomain` | sträng | Domän för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountName` | sträng | Användarnamn för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountUpn` | sträng | Användarkontons huvudnamn (UPN) för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountObjectId` | sträng | Azure AD-objekt-ID för användarkontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | sträng | SHA-256 för processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `InitiatingProcessFolderPath` | sträng | Mapp som innehåller den process (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessFileSize` | long | Storlek på processen (bildfil) som initierade händelsen |
| `InitiatingProcessVersionInfoCompanyName` | sträng | Företagsnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoProductName` | sträng | Produktnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
|` InitiatingProcessVersionInfoProductVersion` | sträng | Produktversion från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
|` InitiatingProcessVersionInfoInternalFileName` | sträng | Internt filnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoOriginalFileName` | sträng | Det ursprungliga filnamnet från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoFileDescription` | sträng | Beskrivning av versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessId` | int | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessIntegrityLevel` | sträng | Integritetsnivån för processen som initierade händelsen. I Windows tilldelar Windows integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de startades från en Internetnedladdning. De här integritetsnivåerna påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för processen som initierade händelsen |
| `InitiatingProcessParentId` | int | Process-ID (PID) för den överordnade process som hanterade processen som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | sträng | Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då föräldern till processen som ansvarar för händelsen startades |
| `RequestProtocol` | sträng | Nätverksprotokoll, om tillämpligt, används för att starta aktiviteten: Okänd, Lokal, SMB eller NFS |
| `RequestSourceIP` | sträng | IPv4- eller IPv6-adressen för den fjärrenhet som initierade aktiviteten |
| `RequestSourcePort` | sträng | Källport på den fjärrenhet som initierade aktiviteten |
| `RequestAccountName` | sträng | Användarnamn på konto som används för att starta aktiviteten via fjärrstyrning |
| `RequestAccountDomain` | sträng | Domän för kontot som används för att starta aktiviteten via fjärrstyrning |
| `RequestAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som används för att starta aktiviteten via fjärrstyrning |
| `ShareName` | sträng | Namn på delad mapp som innehåller filen |
| `InitiatingProcessFileSize` | long | Storlek på filen som körde processen som ansvarar för händelsen |
| `SensitivityLabel` | sträng | Etikett som använts på ett e-postmeddelande, en fil eller annat innehåll för att klassificera det som informationsskydd |
| `SensitivitySubLabel` | sträng | Sublabel tillämpat på ett e-postmeddelande, en fil eller annat innehåll för att klassificera det som informationsskydd. känslighetsunderetiketter är grupperade under känslighetsetiketter, men behandlas oberoende av varandra |
| `IsAzureInfoProtectionApplied` | boolesk | Anger om filen krypteras med Azure Information Protection |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |
| `AdditionalFields` | sträng | Ytterligare information om entiteten eller händelsen |
>[!NOTE]
> Hash-information för filer visas alltid när den är tillgänglig. Det finns dock flera möjliga orsaker till varför en SHA1, SHA256 eller MD5 inte kan beräknas. Filen kan till exempel finnas i fjärrlagring, låst av en annan process, komprimerad eller markerad som virtuell. I de här scenarierna visas filhashinformationen som tom.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
