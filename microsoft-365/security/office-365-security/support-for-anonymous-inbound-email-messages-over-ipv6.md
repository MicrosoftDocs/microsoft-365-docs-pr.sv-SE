---
title: Lägga till stöd för anonym inkommande e-post över IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratören kan läsa om hur du konfigurerar stöd för anonym inkommande e-post från IPv6-källor i Exchange Online och Exchange Online Protection.
ms.openlocfilehash: 7384c1044cc02ec20079dc03068c2ca99e68d2c2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826783"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="6efdb-103">Lägga till stöd för anonym inkommande e-post via IPv6 i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6efdb-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="6efdb-104">Microsoft 365-organisationer med Exchange Online-postlådor och fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor stöder anonym inkommande e-post via IPv6.</span><span class="sxs-lookup"><span data-stu-id="6efdb-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="6efdb-105">Käll-e-postservern för IPv6 måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="6efdb-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="6efdb-106">Källans IPv6-adress måste ha en giltig PTR-post (omvänd DNS lookup) som tillåter målet att hitta domän namnet från IPv6-adressen.</span><span class="sxs-lookup"><span data-stu-id="6efdb-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="6efdb-107">Avsändaren måste klara antingen SPF-verifiering (definieras i [rfc 7208](https://tools.ietf.org/html/rfc7208)) eller [DKIM-verifiering](https://dkim.org/) (definieras i [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="6efdb-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="6efdb-108">Innan din organisation kan ta emot anonym inkommande e-post via IPv6 måste en administratör kontakta Microsoft support och be om det.</span><span class="sxs-lookup"><span data-stu-id="6efdb-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="6efdb-109">Anvisningar för hur du öppnar en supportbegäran finns i [kontakta supporten för företags produkter – hjälp för administratörer](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="6efdb-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="6efdb-110">När anonymt stöd för inkommande IPv6-meddelanden är aktiverat i din organisation kommer meddelandet att gå igenom den vanliga meddelande filtreringen som tillhandahålls av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="6efdb-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6efdb-111">Felsökning</span><span class="sxs-lookup"><span data-stu-id="6efdb-111">Troubleshooting</span></span>

- <span data-ttu-id="6efdb-112">Om käll-e-postservern inte har en omvänd IPv4-uppslags post nekas meddelandena med följande fel:</span><span class="sxs-lookup"><span data-stu-id="6efdb-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="6efdb-113">450 4.7.25-tjänsten är inte tillgänglig, skickar IPv6-adress [2a01: F200:2004:: 240] måste ha omvänd DNS-post.</span><span class="sxs-lookup"><span data-stu-id="6efdb-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="6efdb-114">Om avsändaren inte skickar SPF-eller DKIM-verifiering nekas meddelandena med följande fel:</span><span class="sxs-lookup"><span data-stu-id="6efdb-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="6efdb-115">450 4.7.26-tjänsten är inte tillgänglig, meddelande skickat via IPv6 [2a01:111: F200:2004:: 240] måste klara antingen SPF-eller DKIM-verifiering.</span><span class="sxs-lookup"><span data-stu-id="6efdb-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="6efdb-116">Om du försöker ta emot anonyma IPv6-meddelanden innan du har angett avvisas meddelandet med följande fel:</span><span class="sxs-lookup"><span data-stu-id="6efdb-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="6efdb-117">550 5.2.1-tjänsten är inte tillgänglig, [contoso.com] accepterar inte e-post via IPv6.</span><span class="sxs-lookup"><span data-stu-id="6efdb-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6efdb-118">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6efdb-118">Related topics</span></span>

[<span data-ttu-id="6efdb-119">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="6efdb-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)