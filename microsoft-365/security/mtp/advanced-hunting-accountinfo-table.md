---
title: AccountInfo-tabellen i det avancerade jaktschemat
description: Läs mer om användarkontoinformation i tabellen AccountInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, alert, enheter, bevis, fil, IP-adress, enhet, maskin, användare, konto
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929534"
---
# <a name="accountinfo"></a>KontoInfo

**Gäller:**
- Microsofts hotskydd

Tabellen `AccountInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om användarkonton som hämtats från olika tjänster, inklusive Azure Active Directory. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

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
- [Tillämpa metodtips för frågor](advanced-hunting-best-practices.md)
