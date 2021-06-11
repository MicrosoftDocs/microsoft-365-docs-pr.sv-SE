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
description: Administratörer kan läsa mer om rapporten Om vidarebefordrade meddelanden automatiskt i instrumentpanelen för e-postflöde i Säkerhets- & efterlevnadscenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207325"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="df8fe-103">Information om automatiskt vidarebefordrade meddelanden i Säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="df8fe-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="df8fe-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="df8fe-104">**Applies to**</span></span>
- [<span data-ttu-id="df8fe-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="df8fe-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="df8fe-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="df8fe-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="df8fe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df8fe-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="df8fe-108">Insikten om vidarebefordrade meddelanden [](mail-flow-insights-v2.md) i instrumentpanelen för **e-postflöde** i Säkerhets- och & [efterlevnadscenter](https://protection.office.com) visar information om meddelanden som automatiskt vidarebefordras från organisationen till mottagare i externa domäner.</span><span class="sxs-lookup"><span data-stu-id="df8fe-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget för automatiskt vidarebefordrade meddelanden i Säkerhets- & Säkerhets- och efterlevnadscenter](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="df8fe-110">Information om automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="df8fe-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="df8fe-111">När du klickar på antalet meddelanden i widgeten visas en utfällig ruta med mer information om automatiskt vidarebefordrade meddelanden:</span><span class="sxs-lookup"><span data-stu-id="df8fe-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="df8fe-112">**Meddelanden som vidarebefordras automatiskt med vidarebefordransmetoder:**</span><span class="sxs-lookup"><span data-stu-id="df8fe-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="df8fe-113">**Efter e-postflödesregler**</span><span class="sxs-lookup"><span data-stu-id="df8fe-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="df8fe-114">**Efter inkorgsregler**</span><span class="sxs-lookup"><span data-stu-id="df8fe-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="df8fe-115">**Genom SMTP-vidarebefordran:** Den här metoden anger automatisk vidarebefordran som administratörer kan konfigurera för en postlåda enligt beskrivningen i Konfigurera vidarebefordran av [e-post för en postlåda.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="df8fe-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="df8fe-116">En länk till [vidarebefordransrapporten för](view-mail-flow-reports.md#forwarding-report) mer information.</span><span class="sxs-lookup"><span data-stu-id="df8fe-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="df8fe-117">**Meddelanden vidarebefordras automatiskt av domäner och användare:**</span><span class="sxs-lookup"><span data-stu-id="df8fe-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="df8fe-118">**De 5 översta domänerna vidarebefordras till**</span><span class="sxs-lookup"><span data-stu-id="df8fe-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="df8fe-119">**Nya domäner (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="df8fe-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="df8fe-120">**De 5 främsta användarna av vidarebefordran**</span><span class="sxs-lookup"><span data-stu-id="df8fe-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="df8fe-121">**Nya användare (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="df8fe-121">**New users (last week)**</span></span>
  - <span data-ttu-id="df8fe-122">En länk till rapporten [Ändringar av vidarebefordran om](mfi-new-users-forwarding-email.md#forwarding-modifications-report) du vill ha mer information.</span><span class="sxs-lookup"><span data-stu-id="df8fe-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Den utfällande informationen för rapporten Automatiskt vidarebefordrade meddelanden i säkerhets- & Säkerhets- och efterlevnadscenter](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="df8fe-124">Insikter</span><span class="sxs-lookup"><span data-stu-id="df8fe-124">Insights</span></span>

<span data-ttu-id="df8fe-125">Två insikter skapas baserat på rapportdata:</span><span class="sxs-lookup"><span data-stu-id="df8fe-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="df8fe-126">Nya användare vidarebefordrar e-post</span><span class="sxs-lookup"><span data-stu-id="df8fe-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="df8fe-127">Nya domäner som vidarebefordras e-post</span><span class="sxs-lookup"><span data-stu-id="df8fe-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="df8fe-128">Se även</span><span class="sxs-lookup"><span data-stu-id="df8fe-128">See also</span></span>

<span data-ttu-id="df8fe-129">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="df8fe-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>