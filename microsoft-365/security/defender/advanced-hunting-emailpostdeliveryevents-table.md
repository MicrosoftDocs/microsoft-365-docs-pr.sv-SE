---
title: Tabellen EmailPostDeliveryEvents i det avancerade sökschemat
description: Läs mer om åtgärder efter leverans som har Microsoft 365 i tabellen EmailPostDeliveryEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, Microsoft 365 Defender, microsoft 365, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, E-postPostDeliveryEvents, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil, bifogad fil, namn på bifogad fil, skadlig kod, nätfiske, antal bifogade filer, antal url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 444af2441eef5a3720325656f996e6bcdb42937e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935479"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen i det avancerade schemat för sökning innehåller information om åtgärder efter leverans som har vidtagits `EmailPostDeliveryEvents` för e-postmeddelanden [](advanced-hunting-overview.md) som Microsoft 365. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.

Om du vill ha mer information om enskilda e-postmeddelanden kan du också använda [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tabellerna , [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) och . Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `NetworkMessageId` | sträng | Unikt ID för e-postmeddelandet som genereras av Microsoft 365 |
| `InternetMessageId` | sträng | Offentlig identifierare för det e-postmeddelande som konfigureras av det avsändande e-postsystemet |
| `Action` | sträng | Åtgärd som vidtas på entiteten |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen: Manuell åtgärd, Phish ZAP, Malware ZAP |
| `ActionTrigger` | sträng | Anger om en åtgärd utlöstes av en administratör (manuellt eller genom godkännande av en väntande automatiserad åtgärd), eller av någon särskild mekanism, till exempel en ZAP eller dynamisk leverans |
| `ActionResult` | sträng | Åtgärdens resultat |
| `RecipientEmailAddress` | sträng | Mottagarens e-postadress eller e-postadress efter att distributionslistan expanderat |
| `DeliveryLocation` | sträng | Plats där e-postmeddelandet levererades: Inkorg/mapp, Lokal/Extern, Skräppost, Karantän, Misslyckades, Nedsl ett, Borttaget |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. |

## <a name="supported-event-types"></a>Händelsetyper som stöds
Den här tabellen fångar händelser med följande `ActionType` värden:

- **Manuell åtgärd – En** administratör har manuellt åtgärdat ett e-postmeddelande efter att det levererades till användarens postlåda. Detta omfattar åtgärder som vidtas manuellt via [Threat Explorer](../office-365-security/threat-explorer.md) eller godkännanden av [automatiserade undersöknings- och svarsåtgärder (AIR).](m365d-autoir-actions.md)
- **Zap (** [Zero-hour auto purge)](../office-365-security/zero-hour-auto-purge.md) har vidta åtgärder för nätfiske efter leverans.
- **Zap (Malware ZAP)** – ZAP (Zero-hour auto purge) har vidta åtgärder i ett e-postmeddelande som innehåller skadlig programvara efter leverans.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
