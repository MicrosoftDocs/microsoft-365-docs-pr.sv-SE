---
title: Stöd för validering av DKIM-signerade meddelanden (Domain Keys Identified Mail)
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
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290267"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="cfff8-103">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="cfff8-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cfff8-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="cfff8-104">**Applies to**</span></span>
- [<span data-ttu-id="cfff8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cfff8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cfff8-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="cfff8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="cfff8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfff8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="cfff8-108">Både Exchange Online Protection (EOP) och Exchange Online har stöd för inkommande validering av[DKIM-meddelanden](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="cfff8-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="cfff8-109">DKIM verifierar att ett e-postmeddelande inte *kapats* av någon annan och skickades från den domän som det står *att* det kommer från.</span><span class="sxs-lookup"><span data-stu-id="cfff8-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="cfff8-110">Det binder även ett e-postmeddelande till organisationen som har skickat det.</span><span class="sxs-lookup"><span data-stu-id="cfff8-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="cfff8-111">DKIM-verifiering används automatiskt för alla meddelanden som skickas med IPv6.</span><span class="sxs-lookup"><span data-stu-id="cfff8-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="cfff8-112">Microsoft 365 har också stöd för DKIM när e-post skickas via IPv4.</span><span class="sxs-lookup"><span data-stu-id="cfff8-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="cfff8-113">(Mer information om IPv6-stöd finns i Stöd för [anonyma inkommande e-postmeddelanden via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span><span class="sxs-lookup"><span data-stu-id="cfff8-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="cfff8-114">DKIM verifierar ett digitalt signerat meddelande som visas DKIM-Signature meddelanderubriken i meddelanderubrikerna.</span><span class="sxs-lookup"><span data-stu-id="cfff8-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="cfff8-115">Resultatet av en DKIM-Signature stämplas i det Authentication-Results sidhuvudet.</span><span class="sxs-lookup"><span data-stu-id="cfff8-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="cfff8-116">Texten i meddelandehuvudet liknar följande (där contoso.com är avsändaren):</span><span class="sxs-lookup"><span data-stu-id="cfff8-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="cfff8-117">Mer information om meddelanderubriken Authentication-Results finns i RFC 7001 (fältet Meddelanderubrik för att ange[autentiseringsstatus för meddelande.](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="cfff8-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="cfff8-118">Microsofts DKIM-implementering överensstämmer med denna RFC.</span><span class="sxs-lookup"><span data-stu-id="cfff8-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="cfff8-119">Administratörer kan skapa [e-postflödesregler i](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Exchange (kallas även transportregler) på resultatet av DKIM-verifiering.</span><span class="sxs-lookup"><span data-stu-id="cfff8-119">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="cfff8-120">Med de här e-postflödesreglerna kan administratörer filtrera eller dirigera meddelanden efter behov.</span><span class="sxs-lookup"><span data-stu-id="cfff8-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
