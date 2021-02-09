---
title: Tabellen EmailAttachmentInfo i det avancerade sökschemat
description: Läs mer om information om e-postbilaga i tabellen EmailAttachmentInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, E-postBilagaInfo, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, namn på bifogad fil, skadlig kod
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
ms.openlocfilehash: b810d7b15ef47a33a0675086219d2193cea00f2e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145025"
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
| `NetworkMessageId` | sträng | Unikt ID för e-postmeddelandet som genereras av Microsoft 365 |
| `SenderFromAddress` | sträng | Avsändarens e-postadress i sidhuvudet FRÅN, som visas för e-postmottagare i deras e-postklienter |
| `SenderDisplayName` | sträng | Namnet på avsändaren som visas i adressboken, vanligtvis en kombination av ett visst namn eller förnamn, en initial för mellannamn och efternamn eller efternamn |
| `SenderObjectId` | sträng | Unikt ID för avsändarens konto i Azure AD |
| `RecipientEmailAddress` | sträng | Mottagarens e-postadress eller e-postadress för mottagaren efter distributionslistans expansion |
| `RecipientObjectId` | sträng | Unikt ID för e-postmottagaren i Azure AD |
| `FileName` | sträng | Namnet på filen där den inspelade åtgärden tillämpats på |
| `FileType` | sträng | Filtilläggstyp |
| `SHA256` | sträng | SHA-256 för filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `MalwareFilterVerdict` | sträng | Information om e-postfiltreringsstacken på om e-postmeddelandet innehåller skadlig programvara: skadlig programvara, inte skadlig programvara |
| `MalwareDetectionMethod` | sträng | Metod som används för att identifiera skadlig kod i e-postmeddelandet: Motor mot skadlig kod, ryktet Arkiv, Säkra bifogade filer |
| `ThreatTypes` | sträng | Bedömning av e-postfiltreringsstacken på om e-postmeddelandet innehåller skadlig kod, nätfiske eller andra hot |
| `ThreatNames` | sträng | Identifieringsnamn för skadlig programvara eller andra hot hittades |
| `DetectionMethods` | sträng | Metoder som används för att identifiera skadlig kod, nätfiske eller andra hot som påträffas i e-postmeddelandet |
| `ReportId` | long | Händelseidentifierare baserade på en återkommande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
