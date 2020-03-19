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
description: Läs mer om valideringav DKIM-signerade meddelanden i Exchange Online Protection and Exchange Online
ms.openlocfilehash: 1dc160a4aa01a1a1e46a9b31bb09206d4b385d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812608"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="6cb5e-103">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="6cb5e-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="6cb5e-104">EOP-meddelanden (Exchange Online Protection) och Exchange Online-stöd för inkommande validering av Meddelanden om identifierade e-postmeddelanden[(Domain](https://www.rfc-editor.org/rfc/rfc6376.txt)Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="6cb5e-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="6cb5e-105">DKIM är en metod för att validera att ett meddelande skickades från domänen den säger att det härstammar från och att det inte var förfalskad av någon annan.</span><span class="sxs-lookup"><span data-stu-id="6cb5e-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="6cb5e-106">Det binder ett e-postmeddelande till den organisation som ansvarar för att skicka det.</span><span class="sxs-lookup"><span data-stu-id="6cb5e-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="6cb5e-107">DKIM-verifiering används automatiskt för alla meddelanden som skickas via IPv6-kommunikation.</span><span class="sxs-lookup"><span data-stu-id="6cb5e-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="6cb5e-108">Office 365 stöder nu även DKIM när e-post skickas över IPv4.</span><span class="sxs-lookup"><span data-stu-id="6cb5e-108">Office 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="6cb5e-109">(Mer information om IPv6-support finns i [Support för anonyma inkommande e-postmeddelanden via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span><span class="sxs-lookup"><span data-stu-id="6cb5e-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="6cb5e-110">DKIM validerar ett digitalt signerat meddelande som visas i DKIM-signaturhuvudet i meddelanderubrikerna.</span><span class="sxs-lookup"><span data-stu-id="6cb5e-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers.</span></span> <span data-ttu-id="6cb5e-111">Resultaten av en DKIM-signaturvalidering stämplas i rubriken Autentiseringsresultat som överensstämmer med RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span><span class="sxs-lookup"><span data-stu-id="6cb5e-111">The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span></span> <span data-ttu-id="6cb5e-112">Texten i meddelandehuvudet visas ungefär så här (där contoso.com är avsändaren):</span><span class="sxs-lookup"><span data-stu-id="6cb5e-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="6cb5e-113">Administratörer kan skapa [Exchange-regler för e-postflöde](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) för resultaten av en DKIM-validering för att filtrera eller dirigera meddelanden efter behov.</span><span class="sxs-lookup"><span data-stu-id="6cb5e-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
