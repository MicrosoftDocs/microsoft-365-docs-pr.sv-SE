---
title: Värden på nivå med massklagomål
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om BCL-värden (mass klagomålsnivå) som används i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537949"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Nivå för mass klagomål (BCL) i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, tilldelar EOP en BCL (Bulk Complaint Level) till inkommande meddelanden från massutskick. BCL läggs till i meddelandet i ett X-sidhuvud och liknar konfidensnivån för skräppost [(SCL)](spam-confidence-levels.md) som används för att identifiera meddelanden som skräppost. Om ett större BCL-tecken anges är det mer sannolikt att ett massmeddelande skapar klagomål (och därför är det troligare att det är skräppost). Microsoft använder både interna och tredjepartskällor för att identifiera massutskick och fastställa lämplig BCL.

Massutskick varierar vad gäller deras metoder för att skicka, skapa innehåll och mottagarköp. Bra massutskick skickar önskade meddelanden med relevant innehåll till prenumeranterna. Dessa meddelanden genererar få klagomål från mottagare. Andra massutskick skickar oönskade meddelanden som liknar skräppost och skapar många klagomål från mottagare. Meddelanden från en massutskick kallas massutskick eller grå e-post.

 Skräppostfiltrering  markerar meddelanden som Massutskick baserat på BCL-tröskelvärdet (standardvärdet eller ett värde som du anger) och vidtar den angivna åtgärden för meddelandet (standardåtgärden är att leverera meddelandet till mottagarens skräppostmapp). Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md) [och Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Du kan använda listan över tillåtna/blockerade klientorganisationen för att konfigurera undantag för massfiltrering. Meddelanden från avsändare i de angivna domänerna får  inte åtgärden för skräppostfiltrering av massutskick i skräppostprinciper. Mer information finns i [Hantera listan över tillåtna/blockerade klientorganisationen.](tenant-allow-block-list.md)

BCL-tröskelvärdena beskrivs i följande tabell.

****

|BCL|Beskrivning|
|:---:|---|
|0|Meddelandet kommer inte från en massavsändare.|
|1, 2, 3|Meddelandet kommer från en massavsändare som genererar få klagomål.|
|4, 5, 6, 7<sup>\*</sup>|Meddelandet kommer från en massavsändare som genererar ett blandat antal klagomål.|
|8, 9|Meddelandet kommer från en massavsändare som genererar ett stort antal klagomål.|
|

<sup>\*</sup> Det här är det standardtröskelvärde som används i principer mot skräppost.
