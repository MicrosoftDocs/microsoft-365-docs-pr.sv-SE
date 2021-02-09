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
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150610"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="9ffa9-103">Information om automatiskt vidarebefordrade meddelanden i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="9ffa9-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9ffa9-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-104">**Applies to**</span></span>
- [<span data-ttu-id="9ffa9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9ffa9-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="9ffa9-106">Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="9ffa9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="9ffa9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ffa9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="9ffa9-108">Insikten om vidarebefordrade meddelanden [](mail-flow-insights-v2.md) i instrumentpanelen för **e-postflöde** i Säkerhets- [&](https://protection.office.com) efterlevnadscenter visar information om meddelanden som automatiskt vidarebefordras från organisationen till mottagare i externa domäner.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget för automatiskt vidarebefordrade meddelanden i Säkerhets- & Efterlevnadscenter](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="9ffa9-110">Information om automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="9ffa9-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="9ffa9-111">När du klickar på antalet meddelanden i widgeten visas en utfällig ruta som visar mer information om automatiskt vidarebefordrade meddelanden:</span><span class="sxs-lookup"><span data-stu-id="9ffa9-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="9ffa9-112">**Automatiskt vidarebefordrade meddelanden genom vidarebefordransmetoder:**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="9ffa9-113">**Efter e-postflödesregler**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="9ffa9-114">**Efter regler för Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="9ffa9-115">**Genom SMTP-vidarebefordran:** Den här metoden anger automatisk vidarebefordran som administratörer kan konfigurera för en postlåda enligt beskrivningen i Konfigurera vidarebefordran av [e-post för en postlåda.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="9ffa9-116">En länk till [vidarebefordransrapporten för](view-mail-flow-reports.md#forwarding-report) mer information.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="9ffa9-117">**Automatiskt vidarebefordrade meddelanden efter domäner och användare:**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="9ffa9-118">**De 5 översta domänerna vidarebefordrade till**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="9ffa9-119">**Nya domäner (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="9ffa9-120">**De 5 främsta användarna för vidarebefordran**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="9ffa9-121">**Nya användare (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-121">**New users (last week)**</span></span>
  - <span data-ttu-id="9ffa9-122">En länk till rapporten [Om att vidarebefordra ändringar för](mfi-new-users-forwarding-email.md#forwarding-modifications-report) mer information.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Den utfällande informationen för rapporten om automatiskt vidarebefordrade meddelanden i & Säkerhets- och efterlevnadscenter](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="9ffa9-124">Insikter</span><span class="sxs-lookup"><span data-stu-id="9ffa9-124">Insights</span></span>

<span data-ttu-id="9ffa9-125">Två insikter skapas baserat på rapportdata:</span><span class="sxs-lookup"><span data-stu-id="9ffa9-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="9ffa9-126">Nya användare vidarebefordrar e-post</span><span class="sxs-lookup"><span data-stu-id="9ffa9-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="9ffa9-127">Nya domäner som vidarebefordras e-post</span><span class="sxs-lookup"><span data-stu-id="9ffa9-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="9ffa9-128">Se även</span><span class="sxs-lookup"><span data-stu-id="9ffa9-128">See also</span></span>

<span data-ttu-id="9ffa9-129">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
