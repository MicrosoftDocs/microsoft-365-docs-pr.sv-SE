---
title: IdentityQueryEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om Active Directory-frågehändelser i tabellen IdentityQueryEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteter, LDAP-frågor
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204881"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Gäller:**
- Microsoft Hotskydd

`IdentityQueryEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om frågor som utförs mot Active Directory-objekt, till exempel användare, grupper, enheter och domäner. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `Application` | Sträng | Ansökan som utförde den inspelade åtgärden |
| `QueryType` | Sträng | Typ av fråga, till exempel QueryGroup, QueryUser eller UppräkningAnvändare |
| `QueryTarget` | Sträng | Namn på användare, grupp, enhet, domän eller någon annan entitetstyp som efterfrågas |
| `Query` | Sträng | Sträng som används för att köra frågan |
| `Protocol` | Sträng | Protokoll som används under kommunikationen |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountUpn` | Sträng | Användarens huvudnamn (UPN) för kontot |
| `AccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | Sträng | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | Sträng | Namn på den kontoanvändare som visas i adressboken. Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn. |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för slutpunkten |
| `IPAddress` | Sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `DestinationDeviceName` | Sträng | Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `DestinationIPAddress` | Sträng | IP-adressen för den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `TargetDeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för den enhet som den registrerade åtgärden tillämpades på |
| `TargetAccountUpn` | Sträng | Användarens huvudnamn (UPN) för det konto som den registrerade åtgärden tillämpades på |
| `TargetAccountDisplayName` | Sträng | Visa namnet på det konto som den registrerade åtgärden tillämpades på |
| `Location` | Sträng | Ort, land eller annan geografisk plats som är associerad med händelsen |
| `ReportId` | Lång | Unik identifierare för händelsen |
| `AdditionalFields` | Sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
