---
title: Auto-vidarebefordrade meddelanden insikt
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratörer kan lära sig mer om rapporten för automatiskt vidarebefordrade meddelanden i instrument panelen för e-postflöde i säkerhets & efterlevnad.
ms.openlocfilehash: 01a094b8531672708fc024e8ed0c5833786dbb0c
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877795"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="058fd-103">Automatiskt vidarebefordrade meddelanden är inblick i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="058fd-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="058fd-104">De **automatiskt avvidarekopplade meddelandena** är inblick i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) visar information om meddelanden som automatiskt vidarebefordras från din organisation till mottagare i externa domäner.</span><span class="sxs-lookup"><span data-stu-id="058fd-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget för automatiskt vidarebefordrade meddelanden i säkerhets & efterlevnad](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="058fd-106">Information om automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="058fd-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="058fd-107">När du klickar på antalet meddelanden i widgeten visas en utfällbar ruta som visar mer information om de automatiskt vidarebefordrade meddelandena:</span><span class="sxs-lookup"><span data-stu-id="058fd-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="058fd-108">**Automatiskt vidarebefordrade meddelanden genom metoder för vidarebefordran** :</span><span class="sxs-lookup"><span data-stu-id="058fd-108">**Auto-forwarded messages by forwarding methods** :</span></span>

  - <span data-ttu-id="058fd-109">**Regler för e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="058fd-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="058fd-110">**Regler för Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="058fd-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="058fd-111">**Genom SMTP-vidarekoppling** : det här är automatisk vidarebefordran som administratörer kan konfigurera på en post låda enligt beskrivningen i [Konfigurera e-postvidarekoppling för en post låda](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="058fd-111">**By SMTP forwarding** : This is automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="058fd-112">En länk till [vidarekoppling](view-mail-flow-reports.md#forwarding-report) för mer information.</span><span class="sxs-lookup"><span data-stu-id="058fd-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="058fd-113">**Automatiskt vidarebefordrade meddelanden per domän och användare** :</span><span class="sxs-lookup"><span data-stu-id="058fd-113">**Auto-forwarded messages by domains and users** :</span></span>

  - <span data-ttu-id="058fd-114">**De fem främsta domänerna vidarekopplas till**</span><span class="sxs-lookup"><span data-stu-id="058fd-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="058fd-115">**Nya domäner (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="058fd-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="058fd-116">**De 5 vanligaste användarna**</span><span class="sxs-lookup"><span data-stu-id="058fd-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="058fd-117">**Nya användare (förra veckan)**</span><span class="sxs-lookup"><span data-stu-id="058fd-117">**New users (last week)**</span></span>
  - <span data-ttu-id="058fd-118">En länk till [rapporten för ändring av ändringar](mfi-new-users-forwarding-email.md#forwarding-modifications-report) för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="058fd-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Den utfällbara informationen för rapporten för automatiskt vidarebefordrade meddelanden i säkerhets & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="058fd-120">Insikter</span><span class="sxs-lookup"><span data-stu-id="058fd-120">Insights</span></span>

<span data-ttu-id="058fd-121">Två insikter genereras utifrån rapportens data:</span><span class="sxs-lookup"><span data-stu-id="058fd-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="058fd-122">Nya e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="058fd-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="058fd-123">Nya domäner vidarebefordras via e-post</span><span class="sxs-lookup"><span data-stu-id="058fd-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="058fd-124">Se även</span><span class="sxs-lookup"><span data-stu-id="058fd-124">See also</span></span>

<span data-ttu-id="058fd-125">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="058fd-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
