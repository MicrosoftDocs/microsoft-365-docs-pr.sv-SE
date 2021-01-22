---
title: Tabellen EmailAttachmentInfo i det avancerade sökschemat
description: Läs mer om information om bifogade filer i e-post i tabellen EmailAttachmentInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, E-postbilagaInfo, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, namn på bifogad fil, skadlig programvara
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c6cab4d813eba79e298d0082072888e3ef1ad1cd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927008"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Tabellen `EmailAttachmentInfo` i det avancerade [utbildningsschemat](advanced-hunting-overview.md) innehåller information om bifogade filer i e-postmeddelanden som bearbetas av Microsoft Defender för Office 365. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `AttachmentId` | sträng | Unik identifierare för e-postbilaga |
| `NetworkMessageId` | sträng | Unikt ID för e-postmeddelandet som genereras av Microsoft 365 |
| `SenderFromAddress` | sträng | Avsändarens e-postadress i sidhuvudet FRÅN, som visas för e-postmottagare i deras e-postklienter |
| `RecipientEmailAddress` | sträng | Mottagarens e-postadress eller e-postadress för mottagaren efter distributionslistans expansion |
| `FileName` | sträng | Namnet på filen där den inspelade åtgärden tillämpats på |
| `FileType` | sträng | Filtilläggstyp |
| `SHA256` | sträng | SHA-256 för filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `MalwareFilterVerdict` | sträng | Information om e-postfiltreringsstacken på om e-postmeddelandet innehåller skadlig programvara: skadlig programvara, inte skadlig programvara |
| `MalwareDetectionMethod` | sträng | Metod som används för att identifiera skadlig kod i e-postmeddelandet: Motor mot skadlig kod, ryktet Arkiv, Säkra bifogade filer |
| `SenderDisplayName` | sträng | Namnet på avsändaren som visas i adressboken, vanligtvis en kombination av ett visst namn eller förnamn, en initial för mellannamn och efternamn eller efternamn |
| `SenderObjectId` | sträng | Unikt ID för avsändarens konto i Azure AD |
| `ThreatTypes` | sträng | Bedömning av e-postfiltreringsstacken på om e-postmeddelandet innehåller skadlig kod, nätfiske eller andra hot |
| `ThreatNames` | sträng | Identifieringsnamn för skadlig programvara eller andra hot hittades |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
