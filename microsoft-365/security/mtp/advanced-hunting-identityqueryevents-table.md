---
title: Registret IdentityQueryEvents i det avancerade jaktschemat
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929314"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Gäller:**
- Microsofts hotskydd

Tabellen `IdentityQueryEvents` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om frågor som utförs mot Active Directory-objekt, till exempel användare, grupper, enheter och domäner. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `Application` | Sträng | Ansökan som utförde den registrerade åtgärden |
| `Query` | Sträng | Typ av fråga: QueryGroup, QueryUser eller UppräkningAnvändare |
| `QueryObject` | Sträng | Namn på den användare, grupp, enhet, domän eller någon annan entitetstyp som efterfrågas |
| `Protocol` | Sträng | Protokoll som används under kommunikationen |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountUpn` | Sträng | Kontots användarnamn (UPN) |
| `AccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | Sträng | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | Sträng | Namn på den kontoanvändare som visas i adressboken. Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn. |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för slutpunkten |
| `IPAddress` | Sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `Location` | Sträng | Ort, land eller annan geografisk plats som är associerad med händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Tillämpa metodtips för frågor](advanced-hunting-best-practices.md)
