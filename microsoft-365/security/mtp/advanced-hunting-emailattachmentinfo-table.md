---
title: E-postBilagaInfo-tabellen i det avancerade jaktschemat
description: Läs mer om information om e-postbilaga info i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, EmailAttachmentInfo, nätverksmeddelande-ID, avsändare, mottagare, bilaga id, bilaga namn, malware dom
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
ms.openlocfilehash: d35313cf481ecd6892725ae385e7db1032565611
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807661"
---
# <a name="emailattachmentinfo"></a>E-postAttachmentInfo

**Gäller:**
- Skydd av Hot mot Microsoft



Tabellen `EmailAttachmentInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om bilagor på e-postmeddelanden som bearbetas av Office 365 ATP. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `AttachmentId` | Sträng | Unik identifierare för e-postbilaga |
| `NetworkMessageId` | Sträng | Unik identifierare för e-postmeddelandet, genererad av Office 365 |
| `SenderFromAddress` | Sträng | Avsändarens e-postadress i FRÅN-huvudet, som är synlig för e-postmottagare på sina e-postklienter |
| `RecipientEmailAddress` | Sträng | Mottagarens e-postadress eller mottagarens e-postadress efter distributionen sã¤r utvidgning av distributionslistan |
| `FileName` | Sträng | Namnet på filen som den inspelade åtgärden tillämpades på |
| `FileType` | Sträng | Typ av filtillägg |
| `SHA256` | Sträng | SHA-256 i filen som den inspelade åtgärden tillämpades på. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt. |
| `MalwareFilterVerdict` | Sträng | Dom av e-filtrering stack på om e-postmeddelandet innehåller skadlig kod: Malware, Inte malware |
| `MalwareDetectionMethod` | Sträng | Metod som används för att upptäcka skadlig kod i e-post: Antimalware motor, Fil rykte, ATP Säkra bilagor |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
