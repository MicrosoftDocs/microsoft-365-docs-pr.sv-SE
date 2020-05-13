---
title: Förtroendenivå för skräppost
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om den nivå för att få skräppost (SCL) som tillämpas på meddelanden i Exchange Online Protection (EOP).
ms.openlocfilehash: bc3a1e7e4b3e5f737b8861c14e0fd2c3d0841940
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208018"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Spam förtroendenivå (SCL) i EOP

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor går inkommande meddelanden via skräppostfiltrering i EOP och tilldelas en spampoäng. Den poängen mappas till en enskild scl -nivå (Spam Confidence Level) som läggs till i meddelandet i ett X-header. En högre SCL anger ett meddelande är mer sannolikt att vara spam. EOP vidtar åtgärder för meddelandet baserat på SCL.

Vad SCL innebär och standardåtgärder som vidtas på meddelanden beskrivs i följande tabell. Mer information om åtgärder du kan vidta för meddelanden baserat på skräppostfiltreringsdomen finns [i Konfigurera policyer mot skräppost i EOP](configure-your-spam-filter-policies.md).

||||
|:---:|---|---|
|**SCL**|**Definition**|**Standardåtgärd**|
|-1|Meddelandet hoppade över skräppostfiltrering. Meddelandet kommer till exempel från en säker avsändare, skickades till en säker mottagare eller kommer från en e-postkällserver i listan TILLÅT IP. Mer information finns [i Skapa listor över betrodda avsändare i EOP](create-safe-sender-lists-in-office-365.md).|Leverera meddelandet till mottagarnas inkorg.|
|0, 1|Skräppostfiltrering fastställde att meddelandet inte var skräppost.|Leverera meddelandet till mottagarnas inkorg.|
|5, 6|Skräppostfiltrering markerade meddelandet som **skräppost**|Leverera meddelandet till mottagarnas skräppostmapp.|
|9|Skräppostfiltrering markerade meddelandet som **skräppost med högt förtroende**|Leverera meddelandet till mottagarnas skräppostmapp.|
|

Du kommer att märka att SCL 2, 3, 4, 7 och 8 inte används av skräppostfiltrering.

Du kan använda regler för e-postflöde (kallas även transportregler) för att stämpla SCL på meddelanden. Om du använder en regel för e-postflöde för att ställa in SCL utlöser värdena 5 eller 6 skräppostfiltreringsåtgärden för **skräppost**och värdena 7, 8 eller 9 utlöser skräppostfiltreringsåtgärden för skräppost med **högt förtroende**. Mer information finns i [Använda regler för e-postflöde för att ange scl (Spam Confidence Level) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

I likhet med SCL identifierar massklagomålsnivån (BCL) felaktig massmeddelande (kallas även _grå e-post)._ En högre BCL indikerar att ett massmeddelande är mer sannolikt att generera klagomål (och är därför mer sannolikt att vara spam). Du konfigurerar BCL-tröskelvärdet i anti-spam-principer. Mer information finns [i Konfigurera principer mot skräppost i EOP,](configure-your-spam-filter-policies.md) [Massklagomålsnivå (BCL) i EOP)](bulk-complaint-level-values.md)och [Vad är skillnaden mellan skräppost och massutskick av e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md).

||
|:-----|
|![Den korta ikonen för LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New till Microsoft 365?** Upptäck kostnadsfria videokurser för **Microsoft 365-administratörer och IT-proffs**, som du får av LinkedIn Learning.|
