---
title: Värden för massklagomålsnivå
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Lär dig mer om BCL-värden (Bulk Compliance Level) i Office 365.
ms.openlocfilehash: 82c006f05ce3d37ff23ca1e522b653bd26efeed8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035574"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Massklagomålsnivå (BCL) i Office 365

Massutskicksutskick varierar i sina sändningsmönster, skapande av innehåll och rutiner för anskaffning av mottagare. Vissa är bra massutskick som skickar önskade meddelanden med relevant innehåll till sina prenumeranter. Dessa meddelanden genererar få klagomål från mottagare. Andra massutskick skickar oönskade meddelanden som liknar skräppost och genererar många klagomål från mottagare. Meddelanden från en massutskick kallas massutskick eller grå e-post.

Om du vill skilja meddelanden från olika typer av massutskick tilldelas inkommande e-post från massutskick (Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor) en massklagomålsnivå (BCL) som läggs till i meddelandet i ett X-header. BCL liknar den nivå för [misstroendevotum (SCL)](spam-confidence-levels.md) som används för att identifiera meddelanden som skräppost. En högre BCL indikerar att ett massmeddelande är mer sannolikt att generera klagomål (och är därför mer sannolikt att vara spam). Microsoft använder både interna och tredje parts källor för att identifiera massutskick och fastställa lämplig BCL.

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
