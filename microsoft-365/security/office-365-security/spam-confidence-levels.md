---
title: Säkerhets nivån för skräp post
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om säkerhets nivån för skräp post (SCL) som tillämpas på meddelanden i Exchange Online Protection (EOP).
ms.openlocfilehash: 44687b8234e38e7f818aee908d1b65f382c908fe
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827403"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Säkerhets nivån för skräp post (SCL) i EOP

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor flyttas inkommande meddelanden via skräp post filtrering i EOP och har tilldelats ett skräp inlägg. Den poängen mappas till en enskild skräp konfidensnivå (SCL) som läggs till i meddelandet i ett X-sidhuvud. Ett högre SCL anger att ett meddelande är mer troligt för skräp post. EOP åtgärdar meddelande baserat på SCL.

Vad SCL betyder och vilka standard åtgärder som utförs på meddelanden beskrivs i följande tabell. Mer information om vilka åtgärder du kan vidta på meddelanden baserat på Verdict för skräp post filtrering finns i [Konfigurera principer för skräp post hantering i EOP](configure-your-spam-filter-policies.md).

****

|SCL|Definition|Standard åtgärd|
|:---:|---|---|
|-1|Meddelandet hoppade över skräp post filtrering. Meddelandet kommer till exempel från en säker avsändare, skickades till en säker mottagare eller från en e-postserver i listan över tillåtna IP-adresser. Mer information finns i [skapa säkra avsändare i EOP](create-safe-sender-lists-in-office-365.md).|Skicka meddelandet till mottagarens inkorg.|
|0, 1|Filtrering av skräp post avgjorde meddelandet skickades inte skräp post.|Skicka meddelandet till mottagarens inkorg.|
|5,0|Skräp post filtrering markerade meddelandet som **skräp post**|Skicka meddelandet till mottagarens mapp för skräp post.|
|9|Skräp post filtrering markerat meddelandet som **skräp post**|Skicka meddelandet till mottagarens mapp för skräp post.|
|

Du märker att SCL 2, 3, 4, 7 och 8 inte används för filtrering av skräp post.

Du kan använda regler för e-postflöde (kallas även transport regler) för att stämpla SCL på meddelanden. Om du använder en regel för e-post för att ange SCL utlöser värdena 5 eller 6 skräp post filtrerings åtgärden för **skräp post**och värdena 7, 8 och 9 utlöser skräp post filtrerings åtgärden för **skräp post**filter. Mer information finns i [använda regler för e-postflöde för att ange säkerhets nivån för skräp post (SCL) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

På samma sätt som i SCL (BCL) identifieras dåligt Mass utskick (kallas även _grå e-post_). Ett högre BCL tyder på att ett Mass utskick är mer sannolikt att skapa klagomål (och därför är det mer sannolikt att få skräp post). Du konfigurerar tröskelvärdet för BCL i principer för skräp post. Mer information finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md), [bulk klagomål (BCL) i EOP)](bulk-complaint-level-values.md)och [Vad är skillnaden mellan skräp post och Mass utskick?](what-s-the-difference-between-junk-email-and-bulk-email.md).

|<!-- -->|
|---|
|![Kort ikonen för LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **som är ny för Microsoft 365?** Upptäck kostnads fria video kurser för **Microsoft 365-administratörer och IT-proffs**, som du kommer åt via LinkedIn Learning.|
