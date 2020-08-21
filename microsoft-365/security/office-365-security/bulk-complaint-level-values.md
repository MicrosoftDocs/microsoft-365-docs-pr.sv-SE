---
title: Mass nivå värden för klagomål
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om värden för BCL (Mass Utjämnings nivå) som används i Exchange Online Protection (EOP).
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827439"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Bulk klagomål (BCL) i EOP

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor tilldelar EOP ett Mass kompatibelt (BCL) för inkommande meddelanden från andra Mass utskick. BCL läggs till i meddelandet i ett X-sidhuvud och liknar den [skräp nivå](spam-confidence-levels.md) som används för att identifiera meddelanden som skräp post. Ett högre BCL tyder på att ett Mass meddelande är mer sannolikt att skapa klagomål (och därför är det mer sannolikt att få skräp post). Microsoft använder både interna och tredje parts källor för att identifiera Mass utskick och fastställa lämpliga BCL.

Mass utskick är olika i deras skicka-och innehålls skapande och mottagnings rutiner. Goda Mass utskick skickar önskade meddelanden till sina prenumeranter med relevant innehåll. Dessa meddelanden genererar få klagomål från mottagarna. Andra Mass utskick skickar oombedda meddelanden som liknar skräp posten och ger många klagomål från mottagarna. Meddelanden från ett Mass utskick kallas Mass utskick och e-post.

 Filtrering av skräp post markerar meddelanden som **Mass utskick** baserat på tröskelvärdet för BCL (standardvärdet eller ett värde som du anger) och utför den angivna åtgärden på meddelandet (standard åtgärden skickar meddelandet till mottagarens mapp för skräp post). Mer information finns i [Konfigurera principer för skräp](configure-your-spam-filter-policies.md) post och [Vad är skillnaden mellan skräp post och Mass utskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Tröskelvärdena för BCL beskrivs i följande tabell.

****

|BCL|Beskrivning|
|:---:|---|
|siffrorna|Meddelandet är inte från en Mass avsändare.|
|1; 2; 3|Meddelandet kommer från en Mass avsändare som genererar några klagomål.|
|4, 5, 6, 7|Meddelandet kommer från en Mass avsändare som genererar ett blandat antal klagomål.|
|8, 9|Meddelandet kommer från en Mass avsändare som genererar ett stort antal klagomål.|
|
