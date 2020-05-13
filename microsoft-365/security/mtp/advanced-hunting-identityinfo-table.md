---
title: IdentityInfo-tabellen i det avancerade jaktschemat
description: Läs mer om användarkontoinformation i tabellen IdentityInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AccountInfo, IdentityInfo, konto
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
ms.openlocfilehash: 12f8d0995d00daffe8a1ca1c2c8d9dfe25a11581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209781"
---
# <a name="identityinfo"></a>IdentitetInfo

**Gäller:**
- Microsoft Hotskydd

`IdentityInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om användarkonton som hämtats från olika tjänster, inklusive Azure Active Directory. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

>[!NOTE]
>Den här tabellen har bytt namn från `AccountInfo` . Under namnbyten uppdateras alla frågor som sparas i portalen automatiskt. Kontrollera frågor som du har sparat någon annanstans.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `AccountObjectId` | Sträng | Unik identifierare för kontot i Azure AD |
| `AccountUpn` | Sträng | Kontots användarnamn (UPN) |
| `OnPremSid` | Sträng | Sid-säkerhetsidentifierare (On-premises security identifier) för kontot |
| `CloudSid` | Sträng | Molnsäkerhetsidentifierare för kontot |
| `GivenName` | Sträng | Kontoanvändarens förnamn eller förnamn |
| `Surname` | Sträng | Kontoanvändarens efternamn, efternamn eller efternamn |
| `AccountDisplayName` | Sträng | Namn på den kontoanvändare som visas i adressboken. Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn. |
| `Department` | Sträng | Namn på den avdelning som kontoanvändaren tillhör |
| `JobTitle` | Sträng | Befattning för kontoanvändaren |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountDomain` | Sträng | Kontots domän |
| `EmailAddress` | Sträng | SMTP-adressen för kontot |
| `SipProxyAddress` | Sträng | Röst för kontots ip-sessionsinitieringsprotokoll (VOIP) för kontot |
| `City` | Sträng | Stad där kontoanvändaren finns |
| `Country` | Sträng | Land/region där kontoanvändaren finns |
| `IsAccountEnabled` | Boolean | Anger om kontot är aktiverat eller inte |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
