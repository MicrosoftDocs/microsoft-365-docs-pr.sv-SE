---
title: Stöd för validering av DKIM-signerade e-postmeddelanden (Domain Keys Identified Mail)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Läs mer om validering av DKIM-signerade meddelanden i Exchange Online Protection och Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207348"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="92775-103">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="92775-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="92775-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="92775-104">**Applies to**</span></span>
- [<span data-ttu-id="92775-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="92775-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="92775-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="92775-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="92775-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92775-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="92775-108">Exchange Online Protection (EOP) Exchange Online båda har stöd för inkommande validering av[DKIM-meddelanden](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="92775-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="92775-109">DKIM verifierar att ett e-postmeddelande inte *kapats* av någon annan och skickades från den domän som det står *att* det kommer från.</span><span class="sxs-lookup"><span data-stu-id="92775-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="92775-110">Det binder ett e-postmeddelande till organisationen som har skickat det.</span><span class="sxs-lookup"><span data-stu-id="92775-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="92775-111">DKIM-verifiering används automatiskt för alla meddelanden som skickas med IPv6.</span><span class="sxs-lookup"><span data-stu-id="92775-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="92775-112">Microsoft 365 stöd för DKIM när e-post skickas över IPv4.</span><span class="sxs-lookup"><span data-stu-id="92775-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="92775-113">(Mer information om stöd för IPv6 finns i [Stöd för anonyma inkommande e-postmeddelanden över IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span><span class="sxs-lookup"><span data-stu-id="92775-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="92775-114">DKIM verifierar ett digitalt signerat meddelande som visas DKIM-Signature i meddelanderubriken.</span><span class="sxs-lookup"><span data-stu-id="92775-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="92775-115">Resultatet av en DKIM-Signature stämplas i Authentication-Results rubrik.</span><span class="sxs-lookup"><span data-stu-id="92775-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="92775-116">Texten i meddelanderubriken liknar följande (contoso.com är avsändaren):</span><span class="sxs-lookup"><span data-stu-id="92775-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="92775-117">Mer information om rubriken Authentication-Results i RFC 7001 (fältet Meddelanderubrik för[att visa autentiseringsstatus för meddelande.](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="92775-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="92775-118">Microsofts DKIM-implementering överensstämmer med denna RFC.</span><span class="sxs-lookup"><span data-stu-id="92775-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="92775-119">Administratörer kan skapa Exchange [e-postflödesregler](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) på resultatet av DKIM-validering.</span><span class="sxs-lookup"><span data-stu-id="92775-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="92775-120">Med de här e-postflödesreglerna kan administratörer filtrera eller dirigera meddelanden efter behov.</span><span class="sxs-lookup"><span data-stu-id="92775-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>