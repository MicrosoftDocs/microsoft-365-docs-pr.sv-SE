---
title: Den främsta statusen för domän-e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur du använder den främsta domänens e-postflödes status inblick i instrument panelen för e-postflöde i säkerhets & efterlevnad för att felsöka e-postproblem i samband med MX-poster.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920590"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="fa0a8-103">Den främsta domänens e-postflödes status inblick i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="fa0a8-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fa0a8-104">Statusen för den **främsta domänens e-postflöde** inblickas i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) får du den aktuella e-postflödes statusen för din organisation</span><span class="sxs-lookup"><span data-stu-id="fa0a8-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="fa0a8-105">Denna inblick hjälper dig att identifiera och felsöka domäner med \* *_e-postflöde_* _ problem.</span><span class="sxs-lookup"><span data-stu-id="fa0a8-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow_* _ issues.</span></span> <span data-ttu-id="fa0a8-106">Domänen kan till exempel inte ta emot extern e-post eftersom domänen har upphört att gälla eller om domänen har en felaktig MX-post.</span><span class="sxs-lookup"><span data-stu-id="fa0a8-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Flödes schema för bästa domän status i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="fa0a8-108">När du klickar på _ *Visa information* \* i widgeten visas en utfällbar **domän status** som visar mer information om varje domän status:</span><span class="sxs-lookup"><span data-stu-id="fa0a8-108">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="fa0a8-109">**Domain**</span><span class="sxs-lookup"><span data-stu-id="fa0a8-109">**Domain**</span></span>
- <span data-ttu-id="fa0a8-110">**Föregående MX-post**</span><span class="sxs-lookup"><span data-stu-id="fa0a8-110">**Previous MX record**</span></span>
- <span data-ttu-id="fa0a8-111">**Aktuell MX-post**</span><span class="sxs-lookup"><span data-stu-id="fa0a8-111">**Current MX record**</span></span>
- <span data-ttu-id="fa0a8-112">**Status för e-postmottagning**</span><span class="sxs-lookup"><span data-stu-id="fa0a8-112">**Email receiving status**</span></span>
- <span data-ttu-id="fa0a8-113">**Domän status** : en grön bock markering anger den aktuella MX-posten (när du klickade på widgeten) matchar det värde vi har på Record och domänen har fått e-post under de senaste två timmarna.</span><span class="sxs-lookup"><span data-stu-id="fa0a8-113">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="fa0a8-114">Ett rött X anger att MX-posten har ändrats och att domänen inte har fått e-post under de senaste 6 timmarna.</span><span class="sxs-lookup"><span data-stu-id="fa0a8-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="fa0a8-115">Detta indikerar antagligen att din domän har upphört, eller att MX-posten har uppdaterats felaktigt.</span><span class="sxs-lookup"><span data-stu-id="fa0a8-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="fa0a8-116">Kontrol lera med din domän registrator eller DNS-värd om domänen har upphört att gälla, eller om domänens MX-post är felaktig.</span><span class="sxs-lookup"><span data-stu-id="fa0a8-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="fa0a8-117">Du kan klicka på **Visa mer** om du vill se samma information för fler domäner.</span><span class="sxs-lookup"><span data-stu-id="fa0a8-117">You can click **View more** to see the same information for more domains.</span></span>

![Den utfällbara informationen i den främsta domänens e-flöde-status inblick](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="fa0a8-119">Se även</span><span class="sxs-lookup"><span data-stu-id="fa0a8-119">See also</span></span>

<span data-ttu-id="fa0a8-120">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="fa0a8-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
