---
title: Värden för massnivå för klagomål
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om BCL-värden (Bulk Compliance Level) som används i Exchange Online Protection (EOP).
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209613"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Massklagomålsnivå (BCL) i EOP

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor tilldelar EOP en masskompatibel nivå (BCL) till inkommande meddelanden från massutskick. BCL läggs till i meddelandet i en X-header och liknar [den spam-konfidensnivå (SCL)](spam-confidence-levels.md) som används för att identifiera meddelanden som skräppost. En högre BCL indikerar att ett massmeddelande är mer sannolikt att generera klagomål (och är därför mer sannolikt att vara spam). Microsoft använder både interna och tredje parts källor för att identifiera massutskick och fastställa lämplig BCL.

Massutskicksutskick varierar i sina sändningsmönster, skapande av innehåll och rutiner för anskaffning av mottagare. Bra massutskick skickar önskade meddelanden med relevant innehåll till sina prenumeranter. Dessa meddelanden genererar få klagomål från mottagare. Andra massutskick skickar oönskade meddelanden som liknar skräppost och genererar många klagomål från mottagare. Meddelanden från en massutskick kallas massutskick eller grå e-post.

 Skräppostfiltrering markerar meddelanden som **massmeddelande** baserat på BCL-tröskelvärdet (standardvärdet eller ett värde som du anger) och vidtar den angivna åtgärden i meddelandet (standardåtgärden levereras till mottagarens skräppostmapp). Mer information finns i [Konfigurera policyer mot skräppost](configure-your-spam-filter-policies.md) och Vad är skillnaden mellan skräppost och [massutskick av e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md)

BCL-tröskelvärdena beskrivs i följande tabell.

|||
|:---:|---|
|**BCL**|**Beskrivning**|
|0|Meddelandet kommer inte från en massavsändare.|
|1, 2, 3|Meddelandet kommer från en massavsändare som genererar få klagomål.|
|4, 5, 6, 7|Meddelandet kommer från en massavsändare som genererar ett blandat antal klagomål.|
|8, 9|Meddelandet kommer från en massavsändare som genererar ett stort antal klagomål.|
|
