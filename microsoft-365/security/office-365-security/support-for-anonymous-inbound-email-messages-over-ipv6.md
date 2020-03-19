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
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="9c8ca-103">Stöd för anonyma inkommande e-postmeddelanden via IPv6</span><span class="sxs-lookup"><span data-stu-id="9c8ca-103">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="9c8ca-104">Exchange Online Protection (EOP) och Exchange Online-support som tar emot anonyma inkommande e-postmeddelanden via IPv6-kommunikation från avsändare som inte skickar meddelanden via Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="9c8ca-104">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS).</span></span> <span data-ttu-id="9c8ca-105">Du kan välja att ta emot meddelanden via IPv6 genom att begära den här funktionen från [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)Microsoft Support genom att öppna microsoft 365-administrationscentret på , klicka på **Support**och sedan klicka på **Ny tjänstbegäran**).</span><span class="sxs-lookup"><span data-stu-id="9c8ca-105">You can opt-in to receive messages over IPv6 by requesting this functionality from Microsoft Support by opening the Microsoft 365 admin center at [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), clicking **Support**, and then clicking **New service request**).</span></span> <span data-ttu-id="9c8ca-106">Om du inte anmäler dig till IPv6 fortsätter du att ta emot meddelanden via IPv4.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-106">If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="9c8ca-107">Avsändare som överför meddelanden till tjänsten via IPv6 måste uppfylla följande två krav:</span><span class="sxs-lookup"><span data-stu-id="9c8ca-107">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="9c8ca-108">Den sändande IPv6-adressen måste ha en giltig[PTR-post (omvänd DNS-post](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) för den sändande IPv6-adressen).</span><span class="sxs-lookup"><span data-stu-id="9c8ca-108">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="9c8ca-109">Avsändaren måste godkänna antingen SPF-verifiering (definierad i [RFC 7208)](https://tools.ietf.org/html/rfc7208)eller [DKIM-verifiering](https://dkim.org/) (definierad i [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="9c8ca-109">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="9c8ca-110">Det är obligatoriskt att uppfylla dessa krav oavsett din konfiguration innan du väljer i IPv6.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-110">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6.</span></span> <span data-ttu-id="9c8ca-111">Om båda kraven är uppfyllda går meddelandet igenom normal e-postfiltrering som tillhandahålls av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-111">If both requirements are met, the message will go through normal email message filtering provided by the service.</span></span> <span data-ttu-id="9c8ca-112">Om det ena eller det andra inte uppfylls avvisas meddelandet med något av följande 450 svar:</span><span class="sxs-lookup"><span data-stu-id="9c8ca-112">If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="9c8ca-113">Om du inte har valt att ta emot meddelanden via IPv6 och avsändaren försöker tvinga fram ett meddelande via IPv6 genom att manuellt ansluta till e-postservern, avvisas meddelandet med ett 550-svar som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="9c8ca-113">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="9c8ca-114">Mer information</span><span class="sxs-lookup"><span data-stu-id="9c8ca-114">For more information</span></span>

[<span data-ttu-id="9c8ca-115">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="9c8ca-115">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

