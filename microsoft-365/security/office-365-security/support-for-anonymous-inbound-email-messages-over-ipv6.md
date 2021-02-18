---
title: Lägga till stöd för anonym inkommande e-post över IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratören kan läsa mer om hur du konfigurerar stöd för anonym inkommande e-post från IPv6-källor i Exchange Online och Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290279"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="c22e6-103">Lägga till stöd för anonym inkommande e-post via IPv6 i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c22e6-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c22e6-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="c22e6-104">**Applies to**</span></span>
- [<span data-ttu-id="c22e6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c22e6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c22e6-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="c22e6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c22e6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c22e6-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c22e6-108">Microsoft 365-organisationer med Exchange Online-postlådor och fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor har stöd för anonym inkommande e-post via IPv6.</span><span class="sxs-lookup"><span data-stu-id="c22e6-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="c22e6-109">Käll-IPv6-e-postservern måste uppfylla båda följande krav:</span><span class="sxs-lookup"><span data-stu-id="c22e6-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="c22e6-110">Käll-IPv6-adressen måste ha en giltig omvänd DNS-uppslagspost (PTR) som gör att destinationen kan hitta domännamnet från IPv6-adressen.</span><span class="sxs-lookup"><span data-stu-id="c22e6-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="c22e6-111">Avsändaren måste överföra antingen SPF-verifiering (definierad i [RFC 7208)](https://tools.ietf.org/html/rfc7208)eller [DKIM-verifiering](http://dkim.org/) (definierad i [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="c22e6-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="c22e6-112">Innan din organisation kan ta emot anonym inkommande e-post via IPv6 måste en administratör kontakta Microsofts support och be om det.</span><span class="sxs-lookup"><span data-stu-id="c22e6-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="c22e6-113">Anvisningar om hur du öppnar en supportbegäran finns i [Kontakta supporten för företagsprodukter – hjälp för administratörer.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="c22e6-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="c22e6-114">När stödet för anonyma inkommande IPv6-meddelanden har aktiverats i organisationen går meddelandet igenom den vanliga meddelandefiltrering som tillhandahålls av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="c22e6-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c22e6-115">Felsökning</span><span class="sxs-lookup"><span data-stu-id="c22e6-115">Troubleshooting</span></span>

- <span data-ttu-id="c22e6-116">Om käll-e-postservern inte har en IPv6 omvänd DNS-uppslagspost, avvisas meddelandena med följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="c22e6-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="c22e6-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span><span class="sxs-lookup"><span data-stu-id="c22e6-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="c22e6-118">Om avsändaren inte klarar SPF- eller DKIM-valideringen avvisas meddelandena med följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="c22e6-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="c22e6-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span><span class="sxs-lookup"><span data-stu-id="c22e6-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="c22e6-120">Om du försöker ta emot anonyma IPv6-meddelanden innan du har valt att delta, avvisas meddelandet med följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="c22e6-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="c22e6-121">550 5.2.1 Tjänsten är inte tillgänglig, [contoso.com] accepterar inte e-post via IPv6.</span><span class="sxs-lookup"><span data-stu-id="c22e6-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c22e6-122">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c22e6-122">Related topics</span></span>

[<span data-ttu-id="c22e6-123">Stöd för validering av DKIM-signerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="c22e6-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
