---
title: Nya domäner som vidarebefordras via e-post
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan lära sig hur de använder de nya domänerna som vidarebefordras e-postinsikter i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att undersöka när användarna vidarebefordrar meddelanden till externa domäner som aldrig har vidarebefordrats till.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1310350bd4ff6b43d321f5888c9436ac71debb82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929354"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="22c47-103">Nya domäner som vidarebefordras e-postinsikter i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="22c47-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="22c47-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="22c47-104">**Applies to**</span></span>
- [<span data-ttu-id="22c47-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="22c47-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="22c47-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="22c47-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="22c47-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22c47-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="22c47-108">Det finns giltiga affärsorsaker till att vidarebefordra e-postmeddelanden till externa mottagare i specifika domäner.</span><span class="sxs-lookup"><span data-stu-id="22c47-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="22c47-109">Det börjar dock bli misstänkt när användare i organisationen plötsligt börjar vidarebefordra meddelanden till en domän där ingen i organisationen någonsin har vidarebefordrat meddelanden till (en ny domän).</span><span class="sxs-lookup"><span data-stu-id="22c47-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="22c47-110">Det här villkoret kan ange att användarkontona har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="22c47-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="22c47-111">Om du misstänker att kontona har komprometterats kan du [gå till Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="22c47-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="22c47-112">De **nya domäner som vidarebefordras e-postinsikter** i & [säkerhets-](https://protection.office.com) och efterlevnadscentret meddelar dig när användare i organisationen vidarebefordrar meddelanden till nya domäner.</span><span class="sxs-lookup"><span data-stu-id="22c47-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="22c47-113">Den här insikten visas bara när problemet identifieras och visas på [sidan Vidarebefordransrapport.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="22c47-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Nya domäner som vidarebefordras via e-post](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="22c47-115">När du klickar på widgeten visas en utfällningsruta där du kan hitta mer information om vidarebefordrade meddelanden, inklusive en länk tillbaka till [vidarebefordransrapporten.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="22c47-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Information som visas när du klickar på e-postinsikterna Nya domäner som vidarebefordras](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="22c47-117">Du kan också gå till den här informationssidan  när du väljer insikten när du har klickat på Visa alla i området **& rekommendationer** på (**Instrumentpanelen** \> **Rapporter** eller <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="22c47-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="22c47-118">Om du vill förhindra automatisk vidarebefordran av meddelanden till externa domäner konfigurerar du en fjärrdomän för vissa eller alla externa domäner.</span><span class="sxs-lookup"><span data-stu-id="22c47-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="22c47-119">Mer information finns i [Hantera fjärrdomäner i Exchange Online.](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="22c47-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="22c47-120">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="22c47-120">Related topics</span></span>

<span data-ttu-id="22c47-121">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="22c47-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>