---
title: EmailPostDeliveryEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om åtgärder efter leverans på Microsoft 365-e-postmeddelanden i EmailPostDeliveryEvents-tabellen i det avancerade jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, EmailPostDeliveryEvents, nätverks meddelande-ID, avsändare, mottagare, bifogade filer
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
ms.openlocfilehash: d9d3ffad156d5a27f1931c3b6ec295b022dea296
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198019"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

`EmailPostDeliveryEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om åtgärder efter leverans på de e-postmeddelanden som hanteras av Microsoft 365. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Om du vill ha mer information om enskilda e-postmeddelanden kan du även [`EmailEvents`](advanced-hunting-emailevents-table.md) använda [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tabellerna, och [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `EventId` | strängvärdet | Unik identifierare för händelsen |
| `NetworkMessageId` | strängvärdet | Unik identifierare för e-postmeddelandet, genererat av Microsoft 365 |
| `InternetMessageId` | strängvärdet | Public-Facing ID för e-postmeddelandet som anges i det sändande e-postsystemet |
| `Action` | strängvärdet | Åtgärd som utförs på enheten |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen: manuell reparation, Phish, ZAP |
| `ActionTrigger` | strängvärdet | Anger om en åtgärd som utlöstes av en administratör (manuellt eller genom godkännande av en väntande automatiserad åtgärd) eller någon särskild mekanism, till exempel en ZAP eller dynamisk leverans |
| `ActionResult` | strängvärdet | Resultat av åtgärden |
| `RecipientEmailAddress` | strängvärdet | E-postadress till mottagaren eller e-postadressen till mottagaren efter expansion av distributions lista |
| `DeliveryLocation` | strängvärdet | Plats där e-postmeddelandet levererades: Inkorgen/mapp, lokal/extern, skräp, karantän, misslyckad, avbruten, borttaget |

## <a name="supported-event-types"></a>Händelse typer som stöds
Den här tabellen registrerar händelser med följande `ActionType` värden:

- **Manuell reparation** – en administratör vidtog en åtgärd manuellt i ett e-postmeddelande efter att det har skickats till användarens post låda. Detta inkluderar åtgärder som utförs manuellt via [Threat Explorer](../office-365-security/threat-explorer.md) eller godkännanden av [automatiserade undersökningar och svar (Air)](mtp-autoir-actions.md).
- **PHISH ZAP** – [Automatisk rensning av Tom timme (Zap)](../office-365-security/zero-hour-auto-purge.md) vidtog en åtgärd på en nätfiske-e-postadress efter leverans.
- **Malware-ZAP** – automatisk rensning för en timme (Zap) vidtog en åtgärd i ett e-postmeddelande som innehöll skadlig kod efter leverans.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
