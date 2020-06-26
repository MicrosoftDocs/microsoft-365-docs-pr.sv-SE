---
title: AppFileEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om filrelaterade händelser som är associerade med molnappar och molntjänster i tabellen AppFileEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899345"
---
# <a name="appfileevents"></a>AppFileEvents

**Gäller:**
- Microsoft Hotskydd

`AppFileEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om filrelaterade aktiviteter i molnappar och tjänster som övervakas av Microsoft Cloud App Security. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `Application` | Sträng | Ansökan som utförde den inspelade åtgärden |
| `FileName` | Sträng | Namnet på den fil som den registrerade åtgärden tillämpades på |
| `FolderPath` | Sträng | Mapp som innehåller filen som den inspelade åtgärden tillämpades på |
| `PreviousFileName` | Sträng | Det ursprungliga namnet på filen som har bytt namn till följd av åtgärden |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountUpn` | Sträng | Användarens huvudnamn (UPN) för kontot |
| `AccountObjectId` | Sträng | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | Sträng | Namn på den kontoanvändare som visas i adressboken. Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn. |
| `IPAddress` | Sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `Location` | Sträng | Ort, land eller annan geografisk plats som är associerad med händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
