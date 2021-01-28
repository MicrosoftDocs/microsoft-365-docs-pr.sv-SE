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
description: Administratörer kan lära sig mer om rapporten för automatiskt vidarebefordrade meddelanden i instrument panelen för e-postflöde i säkerhets & efterlevnad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029948"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="db9af-103">Automatiskt vidarebefordrade meddelanden är inblick i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="db9af-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="db9af-104">De **automatiskt avvidarekopplade meddelandena** är inblick i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) visar information om meddelanden som automatiskt vidarebefordras från din organisation till mottagare i externa domäner.</span><span class="sxs-lookup"><span data-stu-id="db9af-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget för automatiskt vidarebefordrade meddelanden i säkerhets & efterlevnad](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="db9af-106">Information om automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="db9af-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="db9af-107">När du klickar på antalet meddelanden i widgeten visas en utfällbar ruta som visar mer information om de automatiskt vidarebefordrade meddelandena:</span><span class="sxs-lookup"><span data-stu-id="db9af-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="db9af-108">**Automatiskt vidarebefordrade meddelanden genom metoder för vidarebefordran**:</span><span class="sxs-lookup"><span data-stu-id="db9af-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="db9af-109">**Regler för e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="db9af-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="db9af-110">**Regler för Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="db9af-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="db9af-111">**Genom SMTP-vidarebefordran**: den här metoden indikerar automatisk vidarebefordran som administratörer kan konfigurera på en post låda enligt beskrivningen i [Konfigurera e-postvidarekoppling för en post låda](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="db9af-111">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="db9af-112">En länk till [vidarekoppling](view-mail-flow-reports.md#forwarding-report) för mer information.</span><span class="sxs-lookup"><span data-stu-id="db9af-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="db9af-113">**Automatiskt vidarebefordrade meddelanden per domän och användare**:</span><span class="sxs-lookup"><span data-stu-id="db9af-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="db9af-114">**De fem främsta domänerna vidarekopplas till**</span><span class="sxs-lookup"><span data-stu-id="db9af-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="db9af-115">**Nya domäner (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="db9af-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="db9af-116">**De 5 vanligaste användarna**</span><span class="sxs-lookup"><span data-stu-id="db9af-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="db9af-117">**Nya användare (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="db9af-117">**New users (last week)**</span></span>
  - <span data-ttu-id="db9af-118">En länk till [rapporten för ändring av ändringar](mfi-new-users-forwarding-email.md#forwarding-modifications-report) för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="db9af-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Den utfällbara informationen för rapporten för automatiskt vidarebefordrade meddelanden i säkerhets & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="db9af-120">Insikter</span><span class="sxs-lookup"><span data-stu-id="db9af-120">Insights</span></span>

<span data-ttu-id="db9af-121">Två insikter genereras utifrån rapportens data:</span><span class="sxs-lookup"><span data-stu-id="db9af-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="db9af-122">Nya e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="db9af-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="db9af-123">Nya domäner vidarebefordras via e-post</span><span class="sxs-lookup"><span data-stu-id="db9af-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="db9af-124">Se även</span><span class="sxs-lookup"><span data-stu-id="db9af-124">See also</span></span>

<span data-ttu-id="db9af-125">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="db9af-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
