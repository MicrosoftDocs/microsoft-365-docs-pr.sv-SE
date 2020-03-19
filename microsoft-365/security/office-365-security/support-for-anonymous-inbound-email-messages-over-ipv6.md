---
title: Stöd för anonyma inkommande e-postmeddelanden via IPv6
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Läs om hur du konfigurerar stöd för anonyma meddelanden från IPv6-källor för Exchange Online Protection och Exchange Online.
ms.openlocfilehash: 1cd38798aa644b79c8f1d6362edd17a515b5c98d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807955"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Stöd för anonyma inkommande e-postmeddelanden via IPv6

Exchange Online Protection (EOP) och Exchange Online-support som tar emot anonyma inkommande e-postmeddelanden via IPv6-kommunikation från avsändare som inte skickar meddelanden via Transport Layer Security (TLS). Du kan välja att ta emot meddelanden via IPv6 genom att begära den här funktionen från [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)Microsoft Support genom att öppna microsoft 365-administrationscentret på , klicka på **Support**och sedan klicka på **Ny tjänstbegäran**). Om du inte anmäler dig till IPv6 fortsätter du att ta emot meddelanden via IPv4.
  
Avsändare som överför meddelanden till tjänsten via IPv6 måste uppfylla följande två krav:
  
1. Den sändande IPv6-adressen måste ha en giltig[PTR-post (omvänd DNS-post](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) för den sändande IPv6-adressen). 
    
2. Avsändaren måste godkänna antingen SPF-verifiering (definierad i [RFC 7208)](https://tools.ietf.org/html/rfc7208)eller [DKIM-verifiering](https://dkim.org/) (definierad i [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)
    
Det är obligatoriskt att uppfylla dessa krav oavsett din konfiguration innan du väljer i IPv6. Om båda kraven är uppfyllda går meddelandet igenom normal e-postfiltrering som tillhandahålls av tjänsten. Om det ena eller det andra inte uppfylls avvisas meddelandet med något av följande 450 svar:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Om du inte har valt att ta emot meddelanden via IPv6 och avsändaren försöker tvinga fram ett meddelande via IPv6 genom att manuellt ansluta till e-postservern, avvisas meddelandet med ett 550-svar som liknar följande:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Mer information

[Stöd för validering av DKIM-signerade meddelanden](support-for-validation-of-dkim-signed-messages.md)
  

