---
title: Nya domäner som vidarebefordras via e-post
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan läsa mer om hur du använder de nya domänerna som vidarebefordras via e-post i instrument panelen för e-postflöde i säkerhets & efterlevnad för att undersöka när deras användare vidarebefordrar meddelanden till externa domäner som aldrig har vidarebefordrats till.
ms.openlocfilehash: a72ffd001ea22972d9dc6c00af8a4dd7881386b7
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356961"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="38f99-103">Nya domäner vidarebefordras med e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="38f99-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="38f99-104">Det finns giltiga företags skäl till att vidarebefordra e-postmeddelanden till externa mottagare i specifika domäner.</span><span class="sxs-lookup"><span data-stu-id="38f99-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="38f99-105">Det är emellertid misstänkt när användare i organisationen plötsligt startar vidarebefordra meddelanden till en domän där det inte finns några meddelanden i organisationen som har vidarebefordrats till (en ny domän).</span><span class="sxs-lookup"><span data-stu-id="38f99-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="38f99-106">Det här problemet kan tyda på att användar kontona har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="38f99-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="38f99-107">Om du misstänker att kontona är inaktiverade kan du läsa mer i [svara på ett komprometterat e-postkonto](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="38f99-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="38f99-108">De **nya domänerna som vidarebefordras via e-post** i [säkerhets & för regelefterlevnad](https://protection.office.com) meddelar dig när användare i organisationen vidarebefordrar meddelanden till nya domäner.</span><span class="sxs-lookup"><span data-stu-id="38f99-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="38f99-109">Denna inblick visas bara när problemet identifieras och visas på sidan för [vidarebefordran av rapporter](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="38f99-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Nya domäner som vidarebefordras via e-post](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="38f99-111">När du klickar på widgeten visas en utfällbar plats där du kan hitta mer information om de vidarebefordrade meddelandena, inklusive en länk tillbaka till [vidarebefordrings rapporten](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="38f99-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Den utfällbara informationen som visas när du klickar på den nya domänen som vidarebefordrar e-postinsikt](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="38f99-113">Du kan också komma åt den här informations sidan när du väljer inblicken när du klickar på **Visa alla** i området **Top Insights & rekommendationer** på (**rapport** \> **instrument panel** eller <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="38f99-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="38f99-114">För att förhindra automatisk vidarebefordran av meddelanden till externa domäner konfigurerar du en fjärrdomän för vissa eller alla externa domäner.</span><span class="sxs-lookup"><span data-stu-id="38f99-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="38f99-115">Mer information finns i [Hantera fjärrdomäner i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="38f99-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="38f99-116">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="38f99-116">Related topics</span></span>

<span data-ttu-id="38f99-117">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="38f99-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
