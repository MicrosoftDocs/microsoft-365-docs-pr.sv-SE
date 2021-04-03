---
title: Tabellen IdentityDirectoryEvents i det avancerade sökschemat
description: Läs mer om domänkontrollanter och Active Directory-händelser i tabellen IdentityDirectoryEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityDirectoryEvents, domänkontrollant, Active Directory, Azure ATP, identiteter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 73018bb65c011d10234ec9c02fc61bfb93fa125a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501133"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen `IdentityDirectoryEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD). I den här tabellen visas olika identitetsrelaterade händelser, som lösenordsändringar, giltighetstid för lösenord och ändringar av huvudnamn (UPN). Den fångar även systemhändelser på domänkontrollanten, som schemaläggning av uppgifter och PowerShell-aktivitet. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i portalen |
| `Application` | sträng | Program som utförde den inspelade åtgärden |
| `TargetAccountUpn` | sträng | Användarens huvudnamn (UPN) för det konto som den inspelade åtgärden tillämpats på |
| `TargetAccountDisplayName` | sträng | Visningsnamn för det konto som den inspelade åtgärden tillämpats på |
| `TargetDeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten som den inspelade åtgärden tillämpats på |
| `DestinationDeviceName` | sträng | Namn på den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden |
| `DestinationIPAddress` | sträng | IP-adress för den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden |
| `DestinationPort` | sträng | Målport för aktiviteten |
| `Protocol` | sträng | Protokoll som används under kommunikationen |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountUpn` | sträng | Användarkontons huvudnamn (UPN) |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure Active Directory |
| `AccountDisplayName` | sträng | Namnet på kontoanvändaren som visas i adressboken. Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn. |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `IPAddress` | sträng | IP-adress tilldelad till enheten under kommunikation |
| `Port` | sträng | TCP-port som används under kommunikation |
| `Location` | sträng | Stad, land eller annan geografisk plats som är kopplad till händelsen |
| `ISP` | sträng | Internetleverantör som är kopplad till IP-adressen |
| `ReportId` | long | Unikt ID för händelsen |
| `AdditionalFields` | sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
