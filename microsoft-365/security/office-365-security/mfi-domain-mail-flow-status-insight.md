---
title: Statusinsikt för domän-e-postflöde på instrumentpanelen för e-postflöde
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
description: Administratörer kan lära sig att använda statusinsikten för e-postflödesstatus för toppdomänen i instrumentpanelen för e-postflöde i Säkerhets- och efterlevnadscenter för & för att felsöka problem i e-postflödet som är relaterade till MX-posterna.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207552"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="35ca5-103">Statusinsikter för e-postflöde i toppdomänen i & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="35ca5-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="35ca5-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="35ca5-104">**Applies to**</span></span>
- [<span data-ttu-id="35ca5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="35ca5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="35ca5-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="35ca5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="35ca5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35ca5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="35ca5-108">**Statusinsikten för** e-postflödet för toppdomänen i instrumentpanelen för e-postflöde i säkerhets- & [efterlevnadscenter](https://protection.office.com) ger dig den aktuella statusen för e-postflödet för din organisation. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="35ca5-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="35ca5-109">Med den här insikten kan du identifiera och felsöka domäner som har problem ***med e-postflödet.***</span><span class="sxs-lookup"><span data-stu-id="35ca5-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="35ca5-110">Domänen kan till exempel inte ta emot extern e-post eftersom domänen har upphört att gälla eller domänen har en felaktig MX-post.</span><span class="sxs-lookup"><span data-stu-id="35ca5-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widgeten för toppdomänflödesstatus på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="35ca5-112">När du klickar **på Visa** information i widgeten visas den utfällsymbolen Domänstatus med mer information om varje domäns status: </span><span class="sxs-lookup"><span data-stu-id="35ca5-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="35ca5-113">**Domän**</span><span class="sxs-lookup"><span data-stu-id="35ca5-113">**Domain**</span></span>
- <span data-ttu-id="35ca5-114">**Föregående MX-post**</span><span class="sxs-lookup"><span data-stu-id="35ca5-114">**Previous MX record**</span></span>
- <span data-ttu-id="35ca5-115">**Aktuell MX-post**</span><span class="sxs-lookup"><span data-stu-id="35ca5-115">**Current MX record**</span></span>
- <span data-ttu-id="35ca5-116">**Status för e-post som tas emot**</span><span class="sxs-lookup"><span data-stu-id="35ca5-116">**Email receiving status**</span></span>
- <span data-ttu-id="35ca5-117">**Domänstatus:** En grön bockmarkering anger den aktuella MX-posten (vid den tidpunkt då du klickade på widgeten) matchar värdet vi har på posten och domänen har fått e-post under de senaste två timmarna.</span><span class="sxs-lookup"><span data-stu-id="35ca5-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="35ca5-118">Ett rött X indikerar att MX-posten har ändrats och att domänen inte har fått något e-postmeddelande under de senaste 6 timmarna.</span><span class="sxs-lookup"><span data-stu-id="35ca5-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="35ca5-119">Det här indikerar förmodligen att din domän har upphört att gälla eller att MX-posten har uppdaterats felaktigt.</span><span class="sxs-lookup"><span data-stu-id="35ca5-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="35ca5-120">Kontrollera med din domänregistrator eller DNS-värd om domänen har upphört att gälla eller om domänens MX-post är felaktig.</span><span class="sxs-lookup"><span data-stu-id="35ca5-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="35ca5-121">Du kan klicka **på Visa fler** om du vill se samma information för fler domäner.</span><span class="sxs-lookup"><span data-stu-id="35ca5-121">You can click **View more** to see the same information for more domains.</span></span>

![Information som visas i statusinsikten för e-postflödet för toppdomänen](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="35ca5-123">Se även</span><span class="sxs-lookup"><span data-stu-id="35ca5-123">See also</span></span>

<span data-ttu-id="35ca5-124">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="35ca5-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
