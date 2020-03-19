---
title: Nivåer för förtroende för skräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: När ett e-postmeddelande går igenom skräppostfiltrering tilldelas det en spam-poäng. Den poängen mappas till en individuell SCL-klassificering (Spam Confidence Level) och stämplas i en X-header. Tjänsten vidtar åtgärder på meddelandena beroende på spam förtroende tolkning av SCL rating. I följande tabell visas hur de olika SCL-klassificeringarna tolkas av filtren och standardåtgärden som vidtas för inkommande meddelanden för varje klassificering.
ms.openlocfilehash: 65b6f51199e6d8f6ce17a05b28c5bad15d9d1760
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806473"
---
# <a name="spam-confidence-levels"></a>Nivåer för förtroende för skräppost

När ett e-postmeddelande går igenom skräppostfiltrering tilldelas det en spam-poäng. Den poängen mappas till en individuell SCL-klassificering (Spam Confidence Level) och stämplas i en X-header. Tjänsten vidtar åtgärder på meddelandena beroende på spam förtroende tolkning av SCL rating. I följande tabell visas hur de olika SCL-klassificeringarna tolkas av filtren och standardåtgärden som vidtas för inkommande meddelanden för varje klassificering.
  
|**SCL-klassificering**|**Tolkning av spamförtroende**|**Standardåtgärd**|
|:-----|:-----|:-----|
|-1|Icke-spam som kommer från en säker avsändare, säker mottagare eller säker IP-adress (betrodd partner).|Leverera meddelandet till mottagarnas inkorg.|
|0, 1|Icke-spam eftersom meddelandet skannades och bestämdes vara ren.|Leverera meddelandet till mottagarnas inkorg.|
|5, 6|Spam|Leverera meddelandet till mottagarnas skräppostmapp.|
|7, 8, 9|Högt förtroende spam|Leverera meddelandet till mottagarnas skräppostmapp.|
   
> [!TIP]
> SCL-klassificeringar på 2, 3, 4, 7 och 8 ställs inte in av tjänsten. En SCL rating på 5 eller 6 anses misstänkt spam, vilket är mindre säkert att vara spam än en SCL rating 9, som anses vara vissa spam. Olika åtgärder för skräppost och skräppost med hög säkerhet kan konfigureras via dina innehållsfilterprinciper i administrationscentret för Exchange. Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md). Du kan också ange SCL-klassificering för meddelanden som matchar specifika villkor med hjälp av regler för e-postflöde (kallas även transportregler), enligt beskrivningen i [Använd regler för e-postflöde för att ställa in förtroendenivån för skräppost i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Om du använder en e-postflödesregel för att ställa in SCL på 7, 8 eller 9 kommer meddelandet att behandlas som skräppost med högt förtroende. 
  
||
|:-----|
|![Den korta ikonen för](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) LinkedIn Learning **New till Office 365?**         Upptäck kostnadsfria videokurser för **Office 365-administratörer och IT-proffs**som kommer till dig genom LinkedIn Learning.|
   

