---
title: Stöd för validering av domän nycklar identifieras e-postmeddelanden (DKIM) signerade meddelanden
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
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845065"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="74f21-103">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="74f21-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="74f21-104">Exchange Online Protection (EOP) och Exchange Online båda stöder inkommande verifiering av domän nycklar identifieras e-postmeddelanden ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="74f21-104">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="74f21-105">DKIM verifierar att ett e-postmeddelande inte är *falsk* för någon annan och att det har skickats från den domän det *står* från.</span><span class="sxs-lookup"><span data-stu-id="74f21-105">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="74f21-106">Den bevarar ett e-postmeddelande till organisationen som skickade det.</span><span class="sxs-lookup"><span data-stu-id="74f21-106">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="74f21-107">DKIM-verifiering används automatiskt för alla meddelanden som skickas med IPv6.</span><span class="sxs-lookup"><span data-stu-id="74f21-107">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="74f21-108">Microsoft 365 har också stöd för DKIM när e-post skickas via IPv4.</span><span class="sxs-lookup"><span data-stu-id="74f21-108">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="74f21-109">(Mer information om IPv6-support finns i [stöd för anonyma inkommande e-postmeddelanden över IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span><span class="sxs-lookup"><span data-stu-id="74f21-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="74f21-110">DKIM verifierar ett digitalt signerat meddelande som visas i meddelande rubrikernas DKIM-Signature rubrik.</span><span class="sxs-lookup"><span data-stu-id="74f21-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="74f21-111">Resultatet av en DKIM-Signature validering är stämplat i Authentication-Results huvudet.</span><span class="sxs-lookup"><span data-stu-id="74f21-111">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="74f21-112">Meddelandets rubrik text ser ut ungefär så här (där contoso.com är avsändaren):</span><span class="sxs-lookup"><span data-stu-id="74f21-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="74f21-113">Mer information om Authentication-Results rubrik finns i RFC 7001 ([meddelande fältet för att ange meddelandets status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span><span class="sxs-lookup"><span data-stu-id="74f21-113">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="74f21-114">Microsofts DKIM-implementering följer med RFC.</span><span class="sxs-lookup"><span data-stu-id="74f21-114">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="74f21-115">Administratörer kan skapa regler för Exchange [-flöden](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transport regler) på resultaten av DKIM-verifiering.</span><span class="sxs-lookup"><span data-stu-id="74f21-115">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="74f21-116">Dessa regler för e-postflöden gör att administratörer kan filtrera eller dirigera meddelanden efter behov.</span><span class="sxs-lookup"><span data-stu-id="74f21-116">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
