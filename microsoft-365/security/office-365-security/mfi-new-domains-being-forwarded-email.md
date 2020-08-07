---
title: Nya domäner vidarebefordrar e-postinsikt
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan läsa mer om hur du använder de nya domänerna som vidarebefordrar e-postmeddelande inblick i det moderna administrations centret för Exchange för att undersöka när användare i organisationen vidarebefordrar meddelanden till externa domäner som aldrig har vidarebefordrats till.
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578471"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="4fe70-103">Nya domäner vidarebefordras med e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="4fe70-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="4fe70-104">Även om du kan ha giltiga företags skäl att vidarebefordra e-postmeddelanden till externa mottagare i vissa domäner är det misstänkt när användare i organisationen plötsligt startar vidarebefordran av meddelanden till externa domäner och ingen i organisationen har översänt meddelanden till dessa domäner före (nya domäner).</span><span class="sxs-lookup"><span data-stu-id="4fe70-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="4fe70-105">Detta kan tyda på att användar kontona har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="4fe70-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="4fe70-106">Om du misstänker att kontona är inaktiverade kan du läsa mer i [svara på ett komprometterat e-postkonto](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="4fe70-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="4fe70-107">De **nya domänerna som vidarebefordras via e-post** meddelar dig när användare i organisationen vidarebefordrar meddelanden till nya domäner.</span><span class="sxs-lookup"><span data-stu-id="4fe70-107">The **New domains being forwarded email** insight notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="4fe70-108">Denna inblick visas bara när problemet identifieras och visas på sidan för [vidarebefordran av rapporter](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="4fe70-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Nya domäner vidarebefordrar e-postinsikt](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="4fe70-110">När du klickar på widgeten visas en utfällbar plats där du kan hitta mer information om de vidarebefordrade meddelandena, inklusive en länk tillbaka till [vidarebefordrings rapporten](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="4fe70-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Den utfällbara informationen som visas när du klickar på den nya domänen som vidarebefordrar e-postinsikt](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="4fe70-112">Du kan också komma åt den här informations sidan när du väljer inblicken när du klickar på **Visa alla** i området **Top Insights & rekommendationer** på (**rapport** \> **instrument panel** eller <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="4fe70-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="4fe70-113">För att förhindra automatisk vidarebefordran av meddelanden till externa domäner konfigurerar du en fjärrdomän för vissa eller alla externa domäner.</span><span class="sxs-lookup"><span data-stu-id="4fe70-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="4fe70-114">Mer information finns i [Hantera fjärrdomäner i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="4fe70-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4fe70-115">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4fe70-115">Related topics</span></span>

<span data-ttu-id="4fe70-116">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="4fe70-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>