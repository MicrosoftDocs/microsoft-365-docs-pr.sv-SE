---
title: IdentityInfo-tabell i det avancerade sökschemat
description: Mer information om användarkonton finns i tabellen IdentityInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935827"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen `IdentityInfo` i det avancerade schemat för [sökning](advanced-hunting-overview.md) innehåller information om användarkonton från olika tjänster, bland annat Azure Active Directory. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!NOTE]
>Den här tabellen har bytt namn från `AccountInfo` . Vid namnbyte uppdateras automatiskt alla frågor som sparas i portalen. Kontrollera frågor som du har sparat någon annanstans.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure AD |
| `AccountUpn` | sträng | Användarkontons huvudnamn (UPN) |
| `OnPremSid` | sträng | Sid för kontots lokala säkerhetsidentifierare |
| `CloudSid` | sträng | Molnsäkerhetsidentifierare för kontot |
| `GivenName` | sträng | Användarens förnamn eller förnamn |
| `Surname` | sträng | Efternamn, kontoanvändares efternamn eller efternamn |
| `AccountDisplayName` | sträng | Namnet på kontoanvändaren som visas i adressboken. Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn. |
| `Department` | sträng | Namn på avdelningen som kontoanvändaren tillhör |
| `JobTitle` | sträng | Befattning för kontoanvändaren |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountDomain` | sträng | Domän för kontot |
| `EmailAddress` | sträng | SMTP-adressen för kontot |
| `SipProxyAddress` | sträng | Kontots startprotokoll för Voice over IP (VOIP) session initiation protocol (SIP) |
| `City` | sträng | Ort där kontoanvändaren finns |
| `Country` | sträng | Land/region där kontoanvändaren finns |
| `IsAccountEnabled` | boolesk | Anger om kontot är aktiverat eller inte |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
