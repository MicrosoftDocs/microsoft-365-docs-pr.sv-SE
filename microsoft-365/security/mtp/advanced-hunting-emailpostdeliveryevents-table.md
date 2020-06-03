---
title: Tabellen EmailPostDeliveryEvents i det avancerade jaktschemat
description: Lär dig mer om åtgärder efter leverans som vidtagits på Microsoft 365-e-postmeddelanden i tabellen EmailPostDeliveryEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, EPostDeliveryEvents, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, bifogad filnamn, dom för skadlig kod, phishing-dom, antal bilagor, antal länkar, url-antal
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
ms.openlocfilehash: f4b34abdbfcbd6c3a2f142001a3d486485c86fcd
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515939"
---
# <a name="emailpostdeliveryevents"></a>E-postPostDeliveryEvents

**Gäller:**
- Microsoft Hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`EmailPostDeliveryEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om åtgärder efter leverans som vidtas i e-postmeddelanden som bearbetas av Microsoft 365. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Om du vill ha mer information om enskilda e-postmeddelanden kan du också använda [`EmailEvents`](advanced-hunting-emailevents-table.md) tabellerna , [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) och [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabellerna. Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `EventId` | Sträng | Unik identifierare för händelsen |
| `NetworkMessageId` | Sträng | Unik identifierare för e-postmeddelandet, som genereras av Microsoft 365 |
| `InternetMessageId` | Sträng | Offentlig identifierare för e-postmeddelandet som anges av det sändande e-postsystemet |
| `Action` | Sträng | Åtgärder som vidtagits för enheten |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen: Manuell reparation, Phish ZAP, Malware ZAP |
| `ActionTrigger` | Sträng | Anger om en åtgärd utlöstes av en administratör (manuellt eller genom godkännande av en väntande automatiserad åtgärd) eller av någon särskild mekanism, till exempel en ZAP eller dynamisk leverans |
| `ActionResult` | Sträng | Resultatet av åtgärden |
| `RecipientEmailAddress` | Sträng | Mottagarens e-postadress eller mottagarens e-postadress efter utvidgning av distributionslistan |
| `DeliveryLocation` | Sträng | Plats där e-postmeddelandet levererades: Inkorg/mapp, lokalt/externt, Skräppost, Karantän, Misslyckades, Tappade, Borttagna objekt |

## <a name="supported-event-types"></a>Händelsetyper som stöds
Den här tabellen fångar händelser med följande `ActionType` värden:

- **Manuell reparation** – En administratör vidtog manuellt åtgärder i ett e-postmeddelande efter att det levererades till användarpostlådan. Detta inkluderar åtgärder som vidtas manuellt genom [Threat Explorer](../office-365-security/threat-explorer.md) eller godkännanden av [automatiska undersöknings- och svarsåtgärder (AIR).](mtp-autoir-actions.md)
- **Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) vidtog åtgärder på ett nätfiske e-postmeddelande efter leverans.
- **Malware ZAP** - Zero-hour auto purge (ZAP) vidtog åtgärder på ett e-postmeddelande som hittades som innehåller skadlig kod efter leverans.

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)