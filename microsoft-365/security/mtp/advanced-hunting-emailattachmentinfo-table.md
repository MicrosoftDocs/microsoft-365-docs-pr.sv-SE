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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6d88303b34f78abc857e9aec749bf2f58090f43a
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667655"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



`EmailAttachmentInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om bifogade filer i e-postmeddelanden som hanteras av Microsoft Defender för Office 365. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

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
| `MalwareDetectionMethod` | strängvärdet | Metod som används för att upptäcka skadlig program vara i e-postmeddelandet: skadlig program vara, fil rykte, säkra bilagor |
| `SenderDisplayName` | strängvärdet | Namnet på den avsändare som visas i adress boken, vanligt vis en kombination av ett visst eller förnamn, en mellan initial och ett efter-eller efter namn |
| `SenderObjectId` | strängvärdet | Unik identifierare för avsändarens konto i Azure AD |
| `ThreatTypes` | strängvärdet | Verdict från e-postfiltrerings gruppen om e-postmeddelandet innehåller skadlig kod, nätfiske eller andra hot |
| `ThreatNames` | strängvärdet | Identifierings namn för skadlig program vara eller andra hot Funna |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
