---
title: Pooler för utgående leverans
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Lär dig hur leverans mediepooler används för att skydda e-postservrarnas rykte i Microsoft 365-datacenter.
ms.openlocfilehash: b3016be7c1887536fe3e742b5ab4ec598b6a5f89
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201495"
---
# <a name="outbound-delivery-pools"></a>Pooler för utgående leverans

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


E-postservrar i Microsoft 365-datacentrerna kanske inte är överbelastade att skicka skräp post. Till exempel en skadlig program vara eller skadlig skräp post i en lokal e-postorganisation som skickar utgående e-post via Microsoft 365 eller Microsoft 365-konton. Attackerare försöker också undvika identifiering genom att vidarebefordra meddelanden via Microsoft 365-vidarekoppling.

De här scenarierna kan leda till att IP-adresserna för de Microsoft 365 datacenter-servrar som visas på program från tredje part. Mål-e-postorganisationer som använder dessa block listor kommer att neka e-post från källorna till dessa meddelanden.

## <a name="high-risk-delivery-pool"></a>Pool med högrisk leverans
För att förhindra detta kan alla utgående meddelanden från Microsoft 365 Data Center-servrar som identifieras som skräp post eller som överskrider [tjänstens](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) avsändare eller [utgående skräp post](configure-the-outbound-spam-policy.md) , skickas via _poolen med högrisk mottagare_.

Poolen med hög risk är en separat IP-adresspool för utgående e-post som bara används för att skicka "lågupplösta" meddelanden (till exempel skräp post och [bakpunkt](backscatter-messages-and-eop.md)). Genom att använda den högrisk leveransen kan du förhindra att den vanliga IP-adresspoolen för utgående e-post skickar skräp post. Den vanliga IP-adresspoolen för utgående e-post ger upphov till det rykte som skickar "högkvalitativa" meddelanden, vilket minskar sannolikheten för att dessa IP-adresser visas i listor över IP-block.

Den yttersta möjligheten att IP-adresser i poolen med högrisk leveranser läggs till i listor med IP-block kvarstår, men det är avsiktligt. Leverans till avsedda mottagare är inte säkert, eftersom många e-postorganisationer inte accepterar meddelanden från poolen med högrisk leveranser.

Mer information finns i [styra utgående skräp post](outbound-spam-controls.md).

> [!NOTE]
> Meddelanden där käll-e-postdomänen inte har någon post, och ingen MX-post har definierats i offentliga DNS, dirigeras alltid genom den pool som används för att avsända och begränsa den.

### <a name="bounce-messages"></a>Studsande meddelanden

Den utgående poolen med hög risk hanterar leveransen för alla icke-leverans rapporter (kallas även NDR, studs meddelanden, leverans status meddelanden eller DSN).

Möjliga orsaker till att en spänning i NDR är:

- En förfalsknings kampanj som påverkar en av de kunder som använder tjänsten.
- En katalog skörde attack.
- En skräp attack.
- En falsk e-postserver.

Alla dessa problem kan leda till plötslig ökning av antalet NDR som bearbetas av tjänsten. Många gånger verkar dessa NDR vara skräp post till andra e-postservrar och tjänster (kallas även för bakgrunds _[punkt](backscatter-messages-and-eop.md)_).

## <a name="relay-pool"></a>Relayrouter

Meddelanden som vidarebefordras eller hanteras av Microsoft 365 skickas med en särskild relayrouter, eftersom den slutgiltiga destinationen inte bör tänka på Microsoft 365 som den faktiska avsändaren. Det är också viktigt för oss att hitta den här trafiken eftersom det finns legitima och ogiltiga scenarier för att vidarebefordra eller vidarebefordra e-post från Microsoft 365. På samma sätt som poolen med hög risk används en separat IP-adresspool för vidarebefordran av e-post. Den här adresspoolen är inte publicerad eftersom den kan ändras ofta.

Microsoft 365 måste kontrol lera att den ursprungliga avsändaren är legitim så att vi säkert kan tillhandahålla det vidarebefordrade meddelandet. För att göra detta måste e-postinloggningsautentisering (SPF, DKIM och DMARC) passera när meddelandet kommer till oss. Om vi kan autentisera avsändaren använder vi avsändare för att hjälpa mottagaren att veta att det vidarebefordrade meddelandet kommer från en betrodd källa. Du kan läsa mer om hur det fungerar och vad du kan göra för att se till att den sändande domänen skickar en [inskrivnings plan för avsändare (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).
