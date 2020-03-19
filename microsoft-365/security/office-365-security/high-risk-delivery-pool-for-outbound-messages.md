---
title: Högriskleveranspool för utgående meddelanden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: När en kunds e-postsystem har komprometterats av skadlig kod eller en skadlig skräppostattack, och den skickar utgående skräppost via den värdbaserade filtreringstjänsten, kan detta leda till att IP-adresserna till Office 365-datacenterservrarna visas på block från tredje part Listor.
ms.openlocfilehash: 19987ae74b9c78a796ddb5f13cf8291a5ed269ad
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808608"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Högriskleveranspool för utgående meddelanden

När en kunds e-postsystem har komprometterats av skadlig kod eller en skadlig skräppostattack, och den skickar utgående skräppost via den värdbaserade filtreringstjänsten, kan detta leda till att IP-adresserna till Office 365-datacenterservrarna visas på block från tredje part Listor. Målservrar som inte använder den värdbaserade filtreringstjänsten, men som använder dessa blockeringslistor, avvisar alla e-postmeddelanden som skickas från någon av de värdbaserade filtrerings-IP-adresserna som har lagts till i dessa listor. För att förhindra detta skickas alla utgående meddelanden som överskrider skräpposttröskeln via en leveranspool med hög risk. Den här sekundära utgående e-postpoolen används endast för att skicka meddelanden som kan vara av låg kvalitet. Detta hjälper till att skydda resten av nätverket från att skicka meddelanden som är mer benägna att resultera i att den sändande IP-adressen blockeras.
  
Användningen av en särskild högriskleveranspool säkerställer att den normala utgående poolen bara skickar meddelanden som är kända för att vara av hög kvalitet. Med den här sekundära IP-poolen kan du minska sannolikheten för att den normala utgående IP-poolen läggs till i en blockerad lista. Möjligheten att högriskpoolen placeras på en blockerad lista är fortfarande en risk. Detta är avsiktligt.
  
Meddelanden där den sändande domänen inte har någon adresspost (A-post), som ger dig domänens IP-adress, och ingen MX-post, som hjälper direktreklam till de servrar som ska ta emot e-post för en viss domän i DNS, dirigeras alltid genom högriskleveranspool oavsett deras spamdisposition.
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>Förstå DSN-meddelanden (Delivery Status Message)

Den utgående högriskleveranspoolen hanterar leveransen för alla "studsade" eller "misslyckade" (DSN) meddelanden.
  
Möjliga orsaker till en ökning av DSN-meddelanden är följande:
  
- En förfalskningskampanj som påverkar en av kunderna som använder tjänsten
    
- En katalog skörd attack
    
- En spamattack
    
- En oseriös SMTP-server
    
Alla dessa problem kan resultera i en plötslig ökning av antalet DSN-meddelanden som bearbetas av tjänsten. Många gånger verkar dessa DSN-meddelanden vara skräppost till andra e-postservrar och -tjänster.
  
## <a name="for-more-information"></a>Mer information

[Konfigurera principen för skräppost för utgående](configure-the-outbound-spam-policy.md)
  
[Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md)
  

