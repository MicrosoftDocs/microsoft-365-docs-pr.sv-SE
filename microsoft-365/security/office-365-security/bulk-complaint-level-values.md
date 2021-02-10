---
title: Nivåvärden för gruppklagomål
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
description: Administratörer kan läsa mer om BCL-värden (Bulk Compliance Level) som används i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 403f79a1ce81ae13a23aa77f4cca7654939d7814
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165973"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Nivå för massklagomål (BCL) i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor tilldelar EOP en BCL (bulk-compliant level) till inkommande meddelanden från massutskick. BCL läggs till i meddelandet i en X-rubrik och liknar nivån för skräppostförtroende [(SCL)](spam-confidence-levels.md) som används för att identifiera meddelanden som skräppost. Om du får ett högre BCL-meddelande är det troligare att ett massmeddelande skapar klagomål (och därför är det troligare att det blir skräppost). Microsoft använder både interna och tredjepartskällor för att identifiera massutskick och fastställa lämplig BCL.

Massutskick varierar beroende på avsändarmönster, metoder för att skapa innehåll och mottagarköp. Bra massutskick skickar önskade meddelanden med relevant innehåll till prenumeranterna. Dessa meddelanden skapar få klagomål från mottagare. Andra massutskick skickar oönskade meddelanden som liknar skräppost och skapar många klagomål från mottagare. Meddelanden från en massutskick kallas massutskick eller grå post.

 Skräppostfiltrering  markerar meddelanden som massutskick baserat på BCL-tröskelvärdet (standardvärdet eller värdet du anger) och vidtar den angivna åtgärden för meddelandet (standardåtgärden är att leverera meddelandet till mottagarens skräppostmapp). Mer information finns i [Konfigurera principer för skräppostskydd och](configure-your-spam-filter-policies.md) Vad är skillnaden mellan skräppost och [massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)

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
