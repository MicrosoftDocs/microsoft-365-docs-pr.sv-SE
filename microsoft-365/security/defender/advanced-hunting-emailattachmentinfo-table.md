---
title: Tabellen EmailAttachmentInfo i det avancerade sökschemat
description: Mer information om e-postbilagan i tabellen EmailAttachmentInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailAttachmentInfo, network message id, sender, recipient, attachment id, attachment name, malware
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
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 43e861d43e6e98f1e17d737f431bb72c42f3f4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073961"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Tabellen `EmailAttachmentInfo` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om bifogade filer i e-postmeddelanden som bearbetas av Microsoft Defender för Office 365. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `NetworkMessageId` | sträng | Unikt ID för e-postmeddelandet som genereras av Microsoft 365 |
| `SenderFromAddress` | sträng | Avsändarens e-postadress i sidhuvudet FRÅN, som visas för e-postmottagare i deras e-postklienter |
| `SenderDisplayName` | sträng | Namnet på avsändaren som visas i adressboken, vanligtvis en kombination av ett visst namn eller förnamn, en initial för mellannamn och efternamn eller efternamn |
| `SenderObjectId` | sträng | Unik identifierare för avsändarens konto i Azure AD |
| `RecipientEmailAddress` | sträng | Mottagarens e-postadress eller e-postadress efter att distributionslistan expanderat |
| `RecipientObjectId` | sträng | Unikt ID för e-postmottagaren i Azure AD |
| `FileName` | sträng | Namnet på filen som den inspelade åtgärden tillämpats på |
| `FileType` | sträng | Filtilläggstyp |
| `SHA256` | sträng | SHA-256 av filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `ThreatTypes` | sträng | Bedömning av e-postfiltreringsstacken utifrån om e-postmeddelandet innehåller skadlig kod, nätfiske eller andra hot |
| `ThreatNames` | sträng | Namn för identifiering av skadlig programvara eller andra hot som hittas |
| `DetectionMethods` | sträng | Metoder som används för att identifiera skadlig kod, nätfiske eller andra hot som påträffas i e-postmeddelandet |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
