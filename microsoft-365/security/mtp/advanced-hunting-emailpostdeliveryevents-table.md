---
title: Tabellen EmailPostDeliveryEvents i det avancerade sökschemat
description: Läs mer om åtgärder efter leverans som har vidtagits i e-postmeddelanden från Microsoft 365 i tabellen EmailPostDeliveryEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, E-postPostDeliveryEvents, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, namn på bifogad fil, skadlig kod
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 774676e15e9018b13674149b6a2e147a91000814
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145505"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen i det avancerade utbildningsschemat innehåller information om åtgärder efter leverans av `EmailPostDeliveryEvents` e-postmeddelanden [](advanced-hunting-overview.md) som bearbetats av Microsoft 365. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` [inbyggda schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) som finns i säkerhetscentret.

Du kan också använda tabellerna och tabellerna om du vill ha mer information [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) om enskilda [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) e-postmeddelanden. Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `NetworkMessageId` | sträng | Unikt ID för e-postmeddelandet som genereras av Microsoft 365 |
| `InternetMessageId` | sträng | Offentlig identifierare för e-postmeddelandet som anges av det avsändande e-postsystemet |
| `Action` | sträng | Åtgärd som vidtas på entiteten |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen: Manuell åtgärd, Phish ZAP, Malware ZAP |
| `ActionTrigger` | sträng | Anger om en åtgärd utlöstes av en administratör (manuellt eller genom godkännande av en väntande automatiserad åtgärd) eller av någon särskild mekanism, till exempel en ZAP eller dynamisk leverans |
| `ActionResult` | sträng | Åtgärdens resultat |
| `RecipientEmailAddress` | sträng | Mottagarens e-postadress eller e-postadress för mottagaren efter distributionslistans expansion |
| `DeliveryLocation` | sträng | Plats där e-postmeddelandet levererades: Inkorg/Mapp, Lokal/Extern, Skräppost, Karantän, Misslyckades, Nedsänt, Borttaget |
| `ReportId` | long | Händelseidentifierare baserade på en återkommande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. |

## <a name="supported-event-types"></a>Händelsetyper som stöds
I den här tabellen visas händelser med följande `ActionType` värden:

- **Manuell åtgärd – en** administratör har manuellt åtgärdat ett e-postmeddelande efter att det levererades till användarens postlåda. Detta omfattar åtgärder som vidtas manuellt via [Threat Explorer](../office-365-security/threat-explorer.md) eller godkännanden av automatisk undersökning [och svarsåtgärder (AIR).](mtp-autoir-actions.md)
- **Zap i phish** – [zap (Zero-hour auto purge)](../office-365-security/zero-hour-auto-purge.md) har vidta åtgärder för nätfiske efter leverans.
- **Malware ZAP** – ZAP (Zero-hour auto purge) vidtog åtgärder på ett e-postmeddelande som innehöll skadlig kod efter leverans.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
