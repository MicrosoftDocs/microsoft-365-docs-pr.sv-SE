---
title: Lägga till stöd för anonym inkommande e-post över IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Administratör kan lära sig hur du konfigurerar stöd för anonym inkommande e-post från IPv6-källor i Exchange Online och Exchange Online Protection.
ms.openlocfilehash: 86de431f8f46af1c5ddae8ecc91f326c6e3280e6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631223"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="1f5d4-103">Lägga till stöd för anonym inkommande e-post via IPv6 i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f5d4-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="1f5d4-104">Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor stöder anonym inkommande e-post via IPv6.</span><span class="sxs-lookup"><span data-stu-id="1f5d4-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="1f5d4-105">Käll-IPv6-e-postservern måste uppfylla båda följande krav:</span><span class="sxs-lookup"><span data-stu-id="1f5d4-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="1f5d4-106">Käll-IPv6-adressen måste ha en giltig PTR-post (Reverse DNS lookup) som gör att målet kan hitta domännamnet från IPv6-adressen.</span><span class="sxs-lookup"><span data-stu-id="1f5d4-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="1f5d4-107">Avsändaren måste godkänna antingen SPF-verifiering (definierad i [RFC 7208)](https://tools.ietf.org/html/rfc7208)eller [DKIM-verifiering](https://dkim.org/) (definierad i [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="1f5d4-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="1f5d4-108">Innan din organisation kan ta emot anonymt inkommande e-postmeddelande via IPv6 måste en administratör kontakta Microsoft-supporten och be om den.</span><span class="sxs-lookup"><span data-stu-id="1f5d4-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="1f5d4-109">Instruktioner om hur du öppnar en supportbegäran finns i [Kontakta support för företagsprodukter - Hjälp om administratörer](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="1f5d4-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="1f5d4-110">När anonymt inkommande IPv6-meddelandestöd har aktiverats i din organisation går meddelandet igenom den normala meddelandefiltrering som tillhandahålls av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1f5d4-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1f5d4-111">Felsökning</span><span class="sxs-lookup"><span data-stu-id="1f5d4-111">Troubleshooting</span></span>

- <span data-ttu-id="1f5d4-112">Om källmeddelandeservern inte har en omvänd DNS-sökningspost för IPv6 avvisas meddelandena med följande fel:</span><span class="sxs-lookup"><span data-stu-id="1f5d4-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="1f5d4-113">450 4.7.25 Tjänsten är inte tillgänglig, vilket skickar IPv6-adress [2a01:111:f200:2004::240] måste ha omvänd DNS-post.</span><span class="sxs-lookup"><span data-stu-id="1f5d4-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="1f5d4-114">Om avsändaren inte skickar SPF- eller DKIM-validering avvisas meddelandena med följande fel:</span><span class="sxs-lookup"><span data-stu-id="1f5d4-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="1f5d4-115">450 4.7.26 Tjänsten är inte tillgänglig, meddelande som skickas via IPv6 [2a01:111:f200:2004::240] måste passera antingen SPF- eller DKIM-validering.</span><span class="sxs-lookup"><span data-stu-id="1f5d4-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="1f5d4-116">Om du försöker ta emot anonyma IPv6-meddelanden innan du har anmält dig kommer meddelandet att avvisas med följande fel:</span><span class="sxs-lookup"><span data-stu-id="1f5d4-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="1f5d4-117">550 5.2.1 Tjänsten är inte tillgänglig, [contoso.com] accepterar inte e-post via IPv6.</span><span class="sxs-lookup"><span data-stu-id="1f5d4-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1f5d4-118">Mer information</span><span class="sxs-lookup"><span data-stu-id="1f5d4-118">For more information</span></span>

[<span data-ttu-id="1f5d4-119">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="1f5d4-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)