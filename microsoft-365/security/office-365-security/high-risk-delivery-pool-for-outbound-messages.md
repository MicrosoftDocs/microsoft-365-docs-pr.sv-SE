---
title: Pool med hög riskleverans för utgående meddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Lär dig hur högriskleveranspoolen används för att skydda ryktet för e-postservrar i Office 365-datacenter.
ms.openlocfilehash: 5d1bd2b14eb17ed74ee1cf1e44967f660f4595b8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895365"
---
# <a name="high-risk-delivery-pool-for-outbound-messages-in-office-365"></a>Högriskleveranspool för utgående meddelanden i Office 365

E-postservrar i Office 365-datacenter kan vara tillfälligt skyldiga till att skicka skräppost. Till exempel en skadlig kod eller skadlig skräppostattack i en lokal e-postorganisation som skickar utgående e-post via Office 365 eller komprometterade Office 365-konton. Dessa scenarier kan resultera i IP-adressen för de berörda Office 365-datacenterservrarna som visas i blocklistor från tredje part. Mål e-postorganisationer som använder dessa blocklistor kommer att avvisa e-post från dessa meddelanden källor.

För att förhindra detta skickas alla utgående meddelanden från Office 365-datacenterservrar som är fast beslutna att vara skräppost eller som överskrider sändningsgränserna för [tjänsten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller [utgående skräppostprinciper](configure-the-outbound-spam-policy.md) via _högriskleveranspoolen_.

Högriskleveranspoolen är en sekundär IP-adresspool för utgående e-post som endast används för att skicka meddelanden av "låg kvalitet" (till exempel skräppost och [backscatter).](backscatter-messages-and-eop.md) Med hjälp av hög risk leveranspoolen hjälper till att förhindra den normala IP-adresspoolen för utgående e-post från att skicka skräppost. Den normala IP-adresspoolen för utgående e-post upprätthåller ryktet att skicka "högkvalitativa" meddelanden, vilket minskar sannolikheten för att dessa IP-adresser visas på IP-blockeringslistor.

Den mycket verkliga möjligheten att IP-adresser i högriskleveranspoolen kommer att placeras på IP-blocklistor kvarstår, men detta är avsiktligt. Leverans till de avsedda mottagarna är inte garanterad, eftersom många e-postorganisationer inte accepterar meddelanden från högriskleveranspoolen.

Mer information finns [i Kontrollera utgående skräppost i Office 365](outbound-spam-controls.md).

> [!NOTE]
> Meddelanden där källe-domänen inte har någon A-post och ingen MX-post som definieras i offentlig DNS dirigeras alltid genom högriskleveranspoolen, oavsett deras spam eller skicka gränsdisposition.

## <a name="bounce-messages"></a>Studsa meddelanden

Den utgående högriskleveranspoolen hanterar leveransen för alla rapporter som inte levereras (kallas även NDRs, avstudsmeddelanden, leveransstatusmeddelanden eller DSN-nätverk).

Möjliga orsaker till en ökning av NDR inkluderar:

- En förfalskningskampanj som påverkar en av kunderna som använder tjänsten.

- En katalog skörd attack.

- En spamattack.

- En oseriös e-postserver.

Alla dessa problem kan resultera i en plötslig ökning av antalet NDR som behandlas av tjänsten. Många gånger, dessa NDRs verkar vara spam till andra e-postservrar och tjänster (även känd som _[backscatter).](backscatter-messages-and-eop.md)_
