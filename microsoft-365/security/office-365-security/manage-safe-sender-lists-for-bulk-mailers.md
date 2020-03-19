---
title: Hantera säkra avsändarlistor för massutskick
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Om du vill använda listor över betrodda avsändare bör du veta att Exchange Online Protection (EOP) och Outlook hanterar bearbetningen på olika sätt. Tjänsten respekterar betrodda avsändare och domäner genom att granska RFC 5321.MailFrom-adressen och RFC 5322.From-adressen, medan Outlook lägger till RFC 5322.From-adressen till en användares säkra avsändarelista. (Obs: Tjänsten inspekterar både 5321.MailFrom-adressen och 5322.From-adressen för blockerade avsändare och domäner.)'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812604"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="fc16d-105">Hantera säkra avsändarlistor för massutskick</span><span class="sxs-lookup"><span data-stu-id="fc16d-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="fc16d-106">Om du vill använda listor över betrodda avsändare bör du veta att Exchange Online Protection (EOP) och Outlook hanterar bearbetningen på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="fc16d-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="fc16d-107">Office 365-tjänsten respekterar betrodda avsändare och `RFC 5321.MailFrom` domäner `RFC 5322.From` genom att granska `RFC 5322.From` adressen och adressen, medan Outlook lägger till adressen i en användares säkra avsändare.</span><span class="sxs-lookup"><span data-stu-id="fc16d-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="fc16d-108">(Obs: Tjänsten inspekterar `5321.MailFrom` både `5322.From` adress och adress för blockerade avsändare och domäner.)</span><span class="sxs-lookup"><span data-stu-id="fc16d-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="fc16d-109">Adressen, `SMTP MAIL FROM` även känd `RFC 5321.MailFrom address`som , är den e-postadress som används för att utföra SPF-kontroller, och om e-postmeddelandet inte kan levereras, sökvägen som det studsade meddelandet levereras till.</span><span class="sxs-lookup"><span data-stu-id="fc16d-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="fc16d-110">Det är den här e-postadressen `Return-Path` som placeras i meddelanderubrikerna som standard, men det är `Return-Path` möjligt för avsändaren att ange en annan adress.</span><span class="sxs-lookup"><span data-stu-id="fc16d-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="fc16d-111">Adressen `From:` i meddelanderubrikerna, även känd `RFC 5322.From` som adressen, är den e-postadress som visas i e-postklienten, till exempel Outlook.</span><span class="sxs-lookup"><span data-stu-id="fc16d-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="fc16d-112">Mycket av tiden, `5321.MailFrom` `5322.From` och adresser är desamma.</span><span class="sxs-lookup"><span data-stu-id="fc16d-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="fc16d-113">Detta är typiskt för person-till-person kommunikation.</span><span class="sxs-lookup"><span data-stu-id="fc16d-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="fc16d-114">Men när e-post skickas på uppdrag av någon annan, är adresserna ofta olika.</span><span class="sxs-lookup"><span data-stu-id="fc16d-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="fc16d-115">Detta händer oftast oftast för massmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fc16d-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="fc16d-116">Anta till exempel att Blue Yonder Airlines har anlitat Margie's Travel för att skicka ut sin e-postreklam.</span><span class="sxs-lookup"><span data-stu-id="fc16d-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="fc16d-117">Du får sedan ett meddelande i inkorgen från avsändare blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="fc16d-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="fc16d-118">I det här exemplet:</span><span class="sxs-lookup"><span data-stu-id="fc16d-118">In this example:</span></span>

- <span data-ttu-id="fc16d-119">Adressen `5321.MailFrom` är blueyonder.airlines@margiestravel.com.</span><span class="sxs-lookup"><span data-stu-id="fc16d-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="fc16d-120">Adressen `5322.From` är blueyonder@news.blueyonderairlines.com, vilket är vad du ser i Outlook.</span><span class="sxs-lookup"><span data-stu-id="fc16d-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="fc16d-121">Om du vill förhindra att det här meddelandet filtreras kan du:</span><span class="sxs-lookup"><span data-stu-id="fc16d-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="fc16d-122">**Som användare**: `RFC 5322.From` Lägg till adressen som en säker avsändare i Outlook.</span><span class="sxs-lookup"><span data-stu-id="fc16d-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="fc16d-123">**Som administratör**: Ställ in en [regel för e-postflöde](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (kallas även transportregel).</span><span class="sxs-lookup"><span data-stu-id="fc16d-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
