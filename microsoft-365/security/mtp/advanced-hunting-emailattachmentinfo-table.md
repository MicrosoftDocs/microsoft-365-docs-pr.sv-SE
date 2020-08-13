---
title: EmailAttachmentInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om information om e-postbilagor i EmailAttachmentInfo-tabellen för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, EmailAttachmentInfo, nätverks meddelande-ID, avsändare, mottagare, bifogade filer, namn och skadlig program vara Verdict
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
ms.openlocfilehash: 2f050885d731563c27100b2d14a3c32cd1a84df1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648915"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**Gäller för:**
- Microsoft Hotskydd



`EmailAttachmentInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om bifogade filer i e-postmeddelanden som bearbetas av Office 365 ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `AttachmentId` | strängvärdet | Unikt ID för bifogad fil |
| `NetworkMessageId` | strängvärdet | Unik identifierare för e-postmeddelandet, genererat av Microsoft 365 |
| `SenderFromAddress` | strängvärdet | Avsändarens e-postadress i formuläret från som visas för e-postmottagare på sina e-postklienter |
| `RecipientEmailAddress` | strängvärdet | E-postadress till mottagaren eller e-postadressen till mottagaren efter expansion av distributions lista |
| `FileName` | strängvärdet | Namnet på filen som den inspelade åtgärden tillämpades för |
| `FileType` | strängvärdet | Fil namns tillägg |
| `SHA256` | strängvärdet | SHA-256 av filen som den registrerade åtgärden tillämpades på. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `MalwareFilterVerdict` | strängvärdet | Verdict av e-postfiltrerings stack på om e-postmeddelandet innehåller skadlig kod: skadlig kod, inte skadlig kod |
| `MalwareDetectionMethod` | strängvärdet | Metod som används för att upptäcka skadlig program vara i e-postmeddelandet: Antiskadlig kod, fil rykte, säkra filer för ATP |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
