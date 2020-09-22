---
title: IdentityQueryEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om Active Directory-frågegrupper i tabellen IdentityQueryEvents för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteter, LDAP-frågor
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
ms.openlocfilehash: 3b2459d0d90f6160bcbac7efbb5c0cc0683ae8c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196815"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

`IdentityQueryEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om frågor som gjorts mot Active Directory-objekt, till exempel användare, grupper, enheter och domäner. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen. Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | strängvärdet | Program som utförde den inspelade åtgärden |
| `QueryType` | strängvärdet | Typ av fråga, till exempel QueryGroup, QueryUser eller EnumerateUsers |
| `QueryTarget` | strängvärdet | Namn på användare, grupp, enhet, domän eller annan entitetstyp som frågas |
| `Query` | strängvärdet | Sträng som används för att köra frågan |
| `Protocol` | strängvärdet | Protokoll som används under kommunikationen |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountDomain` | strängvärdet | Kontots domän |
| `AccountUpn` | strängvärdet | Kontots huvud namn (UPN) |
| `AccountSid` | strängvärdet | Kontots säkerhets identifierare (SID) |
| `AccountObjectId` | strängvärdet | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | strängvärdet | Namnet på kontot som visas i adress boken. Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång. |
| `DeviceName` | strängvärdet | Slut punktens fullständiga domän namn (FQDN) |
| `IPAddress` | strängvärdet | IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation |
| `DestinationDeviceName` | strängvärdet | Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `DestinationIPAddress` | strängvärdet | IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `TargetDeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för enheten som den inspelade åtgärden tillämpades på |
| `TargetAccountUpn` | strängvärdet | Användarens huvud namn (UPN) för det konto som den inspelade åtgärden tillämpades på |
| `TargetAccountDisplayName` | strängvärdet | Visnings namn för det konto som den inspelade åtgärden tillämpades på |
| `Location` | strängvärdet | Ort, land eller annan geografisk plats som är kopplad till evenemanget |
| `ReportId` | tids | Unik identifierare för händelsen |
| `AdditionalFields` | strängvärdet | Ytterligare information om enheten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
