---
title: MailAttachmentInfo tabellen i det avancerade jaktschemat
description: Läs mer om information om bifogade filer i tabellen EmailAttachmentInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, EmailAttachmentInfo, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, bifogad filnamn, malware dom
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
ms.openlocfilehash: c396689942a72a03120f0acd41d0d76abb720702
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899405"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**Gäller:**
- Microsoft Hotskydd



`EmailAttachmentInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om bilagor i e-postmeddelanden som bearbetas av Office 365 ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `AttachmentId` | Sträng | Unik identifierare för bifogade filer för e-post |
| `NetworkMessageId` | Sträng | Unik identifierare för e-postmeddelandet som genereras av Microsoft 365 |
| `SenderFromAddress` | Sträng | Avsändare e-postadress i FRÅN-huvudet, som är synlig för e-postmottagare på deras e-postklienter |
| `RecipientEmailAddress` | Sträng | Mottagarens e-postadress eller mottagarens e-postadress efter utvidgning av distributionslistan |
| `FileName` | Sträng | Namnet på den fil som den registrerade åtgärden tillämpades på |
| `FileType` | Sträng | Typ av filnamnstillägg |
| `SHA256` | Sträng | SHA-256 i filen som den inspelade åtgärden tillämpades på. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt. |
| `MalwareFilterVerdict` | Sträng | Dom av e-filtrering stacken om huruvida e-post innehåller skadlig kod: Malware, Inte skadlig kod |
| `MalwareDetectionMethod` | Sträng | Metod som används för att upptäcka skadlig kod i e-post: Antimalware motor, File rykte, ATP säkra bilagor |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
