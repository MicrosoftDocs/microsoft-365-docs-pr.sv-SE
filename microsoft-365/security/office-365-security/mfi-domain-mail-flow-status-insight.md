---
title: Den främsta statusen för domän-e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur du använder den främsta domänens e-postflödes status inblick i instrument panelen för e-postflöde i säkerhets & efterlevnad för att felsöka e-postproblem i samband med MX-poster.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 457675e7f32cd513f5593ede53a64aaef9d54904
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029912"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="36b1a-103">Den främsta domänens e-postflödes status inblick i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="36b1a-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="36b1a-104">Statusen för den **främsta domänens e-postflöde** inblickas i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) får du den aktuella e-postflödes statusen för din organisation</span><span class="sxs-lookup"><span data-stu-id="36b1a-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="36b1a-105">Denna inblick hjälper dig att identifiera och felsöka domäner med \**_e-postflöde_* _ problem.</span><span class="sxs-lookup"><span data-stu-id="36b1a-105">This insight helps you identify and troubleshoot domains that are experiencing \**_mail flow_* _ issues.</span></span> <span data-ttu-id="36b1a-106">Domänen kan till exempel inte ta emot extern e-post eftersom domänen har upphört att gälla eller om domänen har en felaktig MX-post.</span><span class="sxs-lookup"><span data-stu-id="36b1a-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Flödes schema för bästa domän status i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="36b1a-108">När du klickar på _ *Visa information*\* i widgeten visas en utfällbar **domän status** som visar mer information om varje domän status:</span><span class="sxs-lookup"><span data-stu-id="36b1a-108">When you click _ *View details*\* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="36b1a-109">**Domain**</span><span class="sxs-lookup"><span data-stu-id="36b1a-109">**Domain**</span></span>
- <span data-ttu-id="36b1a-110">**Föregående MX-post**</span><span class="sxs-lookup"><span data-stu-id="36b1a-110">**Previous MX record**</span></span>
- <span data-ttu-id="36b1a-111">**Aktuell MX-post**</span><span class="sxs-lookup"><span data-stu-id="36b1a-111">**Current MX record**</span></span>
- <span data-ttu-id="36b1a-112">**Status för e-postmottagning**</span><span class="sxs-lookup"><span data-stu-id="36b1a-112">**Email receiving status**</span></span>
- <span data-ttu-id="36b1a-113">**Domän status**: en grön bock markering anger den aktuella MX-posten (när du klickade på widgeten) matchar det värde vi har på Record och domänen har fått e-post under de senaste två timmarna.</span><span class="sxs-lookup"><span data-stu-id="36b1a-113">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="36b1a-114">Ett rött X anger att MX-posten har ändrats och att domänen inte har fått e-post under de senaste 6 timmarna.</span><span class="sxs-lookup"><span data-stu-id="36b1a-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="36b1a-115">Detta indikerar antagligen att din domän har upphört, eller att MX-posten har uppdaterats felaktigt.</span><span class="sxs-lookup"><span data-stu-id="36b1a-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="36b1a-116">Kontrol lera med din domän registrator eller DNS-värd om domänen har upphört att gälla, eller om domänens MX-post är felaktig.</span><span class="sxs-lookup"><span data-stu-id="36b1a-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="36b1a-117">Du kan klicka på **Visa mer** om du vill se samma information för fler domäner.</span><span class="sxs-lookup"><span data-stu-id="36b1a-117">You can click **View more** to see the same information for more domains.</span></span>

![Den utfällbara informationen i den främsta domänens e-flöde-status inblick](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="36b1a-119">Se även</span><span class="sxs-lookup"><span data-stu-id="36b1a-119">See also</span></span>

<span data-ttu-id="36b1a-120">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="36b1a-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
