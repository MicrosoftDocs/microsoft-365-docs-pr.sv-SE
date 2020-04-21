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
description: Läs mer om valideringen av DKIM-signerade meddelanden i Exchange Online Protection och Exchange Online
ms.openlocfilehash: 1abe517ed7922b60abb3a78436ed61b4d0b3ed55
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631211"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="ab558-103">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="ab558-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="ab558-104">Exchange Online Protection (EOP) och Exchange Online stöder inkommande validering av[DKIM-meddelanden](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="ab558-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="ab558-105">DKIM är en metod för att validera att ett meddelande skickades från domänen det står att det kommer från och att det inte var förfalskad av någon annan.</span><span class="sxs-lookup"><span data-stu-id="ab558-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="ab558-106">Det binder ett e-postmeddelande till den organisation som ansvarar för att skicka det.</span><span class="sxs-lookup"><span data-stu-id="ab558-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="ab558-107">DKIM-verifiering används automatiskt för alla meddelanden som skickas via IPv6-kommunikation.</span><span class="sxs-lookup"><span data-stu-id="ab558-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="ab558-108">Microsoft 365 stöder nu också DKIM när e-post skickas via IPv4.</span><span class="sxs-lookup"><span data-stu-id="ab558-108">Microsoft 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="ab558-109">(Mer information om IPv6-stöd finns [i Stöd för anonyma inkommande e-postmeddelanden via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span><span class="sxs-lookup"><span data-stu-id="ab558-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="ab558-110">DKIM validerar ett digitalt signerat meddelande som visas i DKIM-signature-huvudet i meddelanderubrikerna.</span><span class="sxs-lookup"><span data-stu-id="ab558-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers.</span></span> <span data-ttu-id="ab558-111">Resultatet av en DKIM-signaturvalidering stämplas i autentiseringsresultathuvudet som överensstämmer med RFC 7001 ([Meddelandehuvudfältet för ange meddelandeautentiseringsstatus](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span><span class="sxs-lookup"><span data-stu-id="ab558-111">The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span></span> <span data-ttu-id="ab558-112">Meddelanderubriktexten liknar följande (där contoso.com är avsändare):</span><span class="sxs-lookup"><span data-stu-id="ab558-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="ab558-113">Administratörer kan skapa [Exchange-regler för e-postflöde](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) om resultatet av en DKIM-validering för att filtrera eller dirigera meddelanden efter behov.</span><span class="sxs-lookup"><span data-stu-id="ab558-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
