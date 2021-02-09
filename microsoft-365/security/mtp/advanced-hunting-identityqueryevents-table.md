---
title: Tabellen IdentityQueryEvents i det avancerade sökschemat
description: Läs mer om Active Directory-frågehändelser i tabellen IdentityQueryEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteter, LDAP-frågor
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 48a1520e9fc6239fd3105f01a32a03e5e58df174
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145301"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen i det avancerade utbildningsschemat innehåller information om frågor som utförs mot Active Directory-objekt, till exempel `IdentityQueryEvents` användare, grupper, enheter [](advanced-hunting-overview.md) och domäner. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` [inbyggda schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) som finns i säkerhetscentret.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i referensen till portalschemat](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | sträng | Program som utförde den inspelade åtgärden |
| `QueryType` | sträng | Typ av fråga, till exempel QueryGroup, QueryUser eller EnumerateUsers |
| `QueryTarget` | sträng | Namn på användare, grupp, enhet, domän eller någon annan entitetstyp som blir tillfrågad |
| `Query` | sträng | Sträng som används för att köra frågan |
| `Protocol` | sträng | Protokoll som används under kommunikationen |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountUpn` | sträng | Kontots huvudnamn (UPN) |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure AD |
| `AccountDisplayName` | sträng | Namnet på kontoanvändaren som visas i adressboken. Vanligtvis en kombination av ett visst namn eller förnamn, en mellaninititiering och ett efternamn eller efternamn. |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för slutpunkten |
| `IPAddress` | sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `Port` | sträng | TCP-port som används under kommunikation |
| `DestinationDeviceName` | sträng | Namn på den enhet som kör serverprogrammet som hanterade den inspelade åtgärden |
| `DestinationIPAddress` | sträng | IP-adressen för den enhet som kör serverprogrammet som hanterade den inspelade åtgärden |
| `DestinationPort` | sträng | Målport för relaterad nätverkskommunikation |
| `TargetDeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten som den inspelade åtgärden tillämpats på |
| `TargetAccountUpn` | sträng | Användarens huvudnamn (UPN) för kontot som den inspelade åtgärden tillämpats på |
| `TargetAccountDisplayName` | sträng | Visningsnamn för det konto som den inspelade åtgärden tillämpats på |
| `Location` | sträng | Stad, land eller annan geografisk plats som är kopplad till händelsen |
| `ReportId` | long | Unikt ID för händelsen |
| `AdditionalFields` | sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
