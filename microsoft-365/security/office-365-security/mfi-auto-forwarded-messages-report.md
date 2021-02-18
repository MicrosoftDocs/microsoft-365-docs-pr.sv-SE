---
title: Auto-vidarebefordrade meddelanden insikt
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratörer kan läsa mer om rapporten om automatiskt vidarebefordrade meddelanden i instrumentpanelen för e-postflöde i Säkerhets- & Efterlevnadscenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290639"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="ce69d-103">Information om automatiskt vidarebefordrade meddelanden i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="ce69d-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ce69d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="ce69d-104">**Applies to**</span></span>
- [<span data-ttu-id="ce69d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ce69d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ce69d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="ce69d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ce69d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce69d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ce69d-108">Insikten om vidarebefordrade meddelanden [](mail-flow-insights-v2.md) i instrumentpanelen för **e-postflöde** i Säkerhets- [&](https://protection.office.com) efterlevnadscenter visar information om meddelanden som automatiskt vidarebefordras från organisationen till mottagare i externa domäner.</span><span class="sxs-lookup"><span data-stu-id="ce69d-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget för automatiskt vidarebefordrade meddelanden i Säkerhets- & Efterlevnadscenter](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="ce69d-110">Information om automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="ce69d-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="ce69d-111">När du klickar på antalet meddelanden i widgeten visas en utfällig ruta med mer information om automatiskt vidarebefordrade meddelanden:</span><span class="sxs-lookup"><span data-stu-id="ce69d-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="ce69d-112">**Automatiskt vidarebefordrade meddelanden genom vidarebefordransmetoder:**</span><span class="sxs-lookup"><span data-stu-id="ce69d-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="ce69d-113">**Efter e-postflödesregler**</span><span class="sxs-lookup"><span data-stu-id="ce69d-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="ce69d-114">**Efter regler för Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="ce69d-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="ce69d-115">**Genom SMTP-vidarebefordran:** Den här metoden anger automatisk vidarebefordran som administratörer kan konfigurera för en postlåda enligt beskrivningen i Konfigurera vidarebefordran av [e-post för en postlåda.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="ce69d-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="ce69d-116">En länk till [vidarebefordransrapporten](view-mail-flow-reports.md#forwarding-report) för mer information.</span><span class="sxs-lookup"><span data-stu-id="ce69d-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="ce69d-117">**Automatiskt vidarebefordrade meddelanden efter domäner och användare:**</span><span class="sxs-lookup"><span data-stu-id="ce69d-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="ce69d-118">**De 5 översta domänerna vidarebefordrade till**</span><span class="sxs-lookup"><span data-stu-id="ce69d-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="ce69d-119">**Nya domäner (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="ce69d-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="ce69d-120">**De 5 främsta användarna för vidarebefordran**</span><span class="sxs-lookup"><span data-stu-id="ce69d-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="ce69d-121">**Nya användare (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="ce69d-121">**New users (last week)**</span></span>
  - <span data-ttu-id="ce69d-122">En länk till rapporten [Om att vidarebefordra ändringar för](mfi-new-users-forwarding-email.md#forwarding-modifications-report) mer information.</span><span class="sxs-lookup"><span data-stu-id="ce69d-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Den utfällande informationen för rapporten om automatiskt vidarebefordrade meddelanden i & Säkerhets- och efterlevnadscenter](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="ce69d-124">Insikter</span><span class="sxs-lookup"><span data-stu-id="ce69d-124">Insights</span></span>

<span data-ttu-id="ce69d-125">Två insikter skapas baserat på rapportdata:</span><span class="sxs-lookup"><span data-stu-id="ce69d-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="ce69d-126">Nya användare vidarebefordrar e-post</span><span class="sxs-lookup"><span data-stu-id="ce69d-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="ce69d-127">Nya domäner som vidarebefordras e-post</span><span class="sxs-lookup"><span data-stu-id="ce69d-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="ce69d-128">Se även</span><span class="sxs-lookup"><span data-stu-id="ce69d-128">See also</span></span>

<span data-ttu-id="ce69d-129">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ce69d-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
