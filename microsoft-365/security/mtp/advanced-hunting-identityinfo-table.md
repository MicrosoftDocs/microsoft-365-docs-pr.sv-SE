---
title: IdentityInfo-tabell i det avancerade sökschemat
description: Mer information om användarkonton i tabellen IdentityInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AccountInfo, IdentityInfo, konto
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929916"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen `IdentityInfo` i det avancerade [utbildningsschemat](advanced-hunting-overview.md) innehåller information om användarkonton som hämtas från olika tjänster, bland annat Azure Active Directory. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!NOTE]
>Den här tabellen har bytt namn `AccountInfo` från. Vid namnbyte uppdateras automatiskt alla frågor som sparas i portalen. Kontrollera frågor som du har sparat någon annanstans.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure AD |
| `AccountUpn` | sträng | Kontots huvudnamn (UPN) |
| `OnPremSid` | sträng | Lokal säkerhetsidentifierare (SID) för kontot |
| `CloudSid` | sträng | Kontots molnsäkerhetsidentifierare |
| `GivenName` | sträng | Kontoanvändareens förnamn eller förnamn |
| `Surname` | sträng | Efternamn, kontoanvändares efternamn eller efternamn |
| `AccountDisplayName` | sträng | Namnet på kontoanvändaren som visas i adressboken. Vanligtvis en kombination av ett visst namn eller förnamn, en mellaninititiering och ett efternamn eller efternamn. |
| `Department` | sträng | Namnet på avdelningen som kontoanvändaren tillhör |
| `JobTitle` | sträng | Befattning för kontoanvändaren |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountDomain` | sträng | Domänen för kontot |
| `EmailAddress` | sträng | SMTP-adressen för kontot |
| `SipProxyAddress` | sträng | Kontots initieringsprotokoll (Voice over IP) (VOIP) session initiation protocol (SIP) |
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
