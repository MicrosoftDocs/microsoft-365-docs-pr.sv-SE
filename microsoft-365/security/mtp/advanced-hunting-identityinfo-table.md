---
title: IdentityInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om användar konto information i tabellen IdentityInfo för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AccountInfo, IdentityInfo, konto
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
ms.openlocfilehash: 3d59f987ae4d670e3d7c6f1638f8090ffc3ba7fe
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649313"
---
# <a name="identityinfo"></a>IdentityInfo

**Gäller för:**
- Microsoft Hotskydd

`IdentityInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om användar konton som hämtas från olika tjänster, inklusive Azure Active Directory. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!NOTE]
>Tabellen har bytt namn från `AccountInfo` . När du byter namn uppdateras alla frågor som sparats i portalen automatiskt. Kolla frågor som du har sparat någon annan stans.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `AccountObjectId` | strängvärdet | Unik identifierare för kontot i Azure AD |
| `AccountUpn` | strängvärdet | Kontots huvud namn (UPN) |
| `OnPremSid` | strängvärdet | Lokal säkerhets identifierare (SID) för kontot |
| `CloudSid` | strängvärdet | Moln säkerhets identifierare för kontot |
| `GivenName` | strängvärdet | Tilldelat namn eller förnamn för konto användaren |
| `Surname` | strängvärdet | Efter namn, familje namn eller efter namnet på konto användaren |
| `AccountDisplayName` | strängvärdet | Namnet på kontot som visas i adress boken. Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång. |
| `Department` | strängvärdet | Namn på avdelningen som konto användaren tillhör |
| `JobTitle` | strängvärdet | Befattning för konto användaren |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountDomain` | strängvärdet | Kontots domän |
| `EmailAddress` | strängvärdet | SMTP-adressen för kontot |
| `SipProxyAddress` | strängvärdet | Kontots SIP-adress (Voice over IP) |
| `City` | strängvärdet | Ort där konto användaren finns |
| `Country` | strängvärdet | Land/region där konto användaren finns |
| `IsAccountEnabled` | returtyp | Anger om kontot är aktiverat eller inte |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
