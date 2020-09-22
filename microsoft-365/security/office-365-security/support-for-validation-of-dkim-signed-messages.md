---
title: Stöd för validering av DKIM-signerade meddelanden
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
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Lär dig mer om validering av DKIM-signerade meddelanden i Exchange Online Protection och Exchange Online
ms.openlocfilehash: e2e91fe426348487fa4dfa8ef929d2d8129ffddc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202143"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="e4ba7-103">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="e4ba7-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e4ba7-104">Exchange Online Protection (EOP) och Exchange Online-Support för inkommande verifiering av domän nycklar identifieras e-postmeddelanden ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="e4ba7-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="e4ba7-105">DKIM är en metod för att verifiera att ett meddelande har skickats från den domän som det står från och att det inte har manipulerats av någon annan.</span><span class="sxs-lookup"><span data-stu-id="e4ba7-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="e4ba7-106">Det besvarar ett e-postmeddelande till den organisation som är ansvarig för att skicka det.</span><span class="sxs-lookup"><span data-stu-id="e4ba7-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="e4ba7-107">DKIM-verifiering används automatiskt för alla meddelanden som skickas via IPv6-kommunikation.</span><span class="sxs-lookup"><span data-stu-id="e4ba7-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="e4ba7-108">Microsoft 365 stöder nu DKIM när e-post skickas via IPv4.</span><span class="sxs-lookup"><span data-stu-id="e4ba7-108">Microsoft 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="e4ba7-109">(Mer information om IPv6-support finns i [stöd för anonyma inkommande e-postmeddelanden över IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span><span class="sxs-lookup"><span data-stu-id="e4ba7-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="e4ba7-110">DKIM verifierar ett digitalt signerat meddelande som visas i DKIM rubrik i meddelande huvudet.</span><span class="sxs-lookup"><span data-stu-id="e4ba7-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers.</span></span> <span data-ttu-id="e4ba7-111">Resultatet av en verifiering med DKIM är stämplat i det verifierings resultat huvud som följer med RFC 7001 ([meddelande huvudet för att ange meddelande verifierings status](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span><span class="sxs-lookup"><span data-stu-id="e4ba7-111">The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span></span> <span data-ttu-id="e4ba7-112">Meddelandets rubrik text ser ut ungefär så här (där contoso.com är avsändaren):</span><span class="sxs-lookup"><span data-stu-id="e4ba7-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="e4ba7-113">Administratörer kan skapa regler för Exchange [-flöden](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transport regler) för resultaten av en DKIM-verifiering för att filtrera eller dirigera meddelanden efter behov.</span><span class="sxs-lookup"><span data-stu-id="e4ba7-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
