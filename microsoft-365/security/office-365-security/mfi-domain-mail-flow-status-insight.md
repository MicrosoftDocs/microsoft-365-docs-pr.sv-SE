---
title: Statusinsikter för e-postflöde för toppdomän på instrumentpanelen för e-postflöde
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
description: Administratörer kan lära sig att använda statusinsikten för e-postflödesstatus för toppdomänen i instrumentpanelen för e-postflöde i Säkerhets- & efterlevnadscenter för att felsöka e-postflödesproblem som rör deras MX-poster.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ecda78047384a581a1043d0049b8dd25fadbe27
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290627"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="ab15a-103">Statusinsikter för e-postflöde i toppdomänen & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="ab15a-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ab15a-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="ab15a-104">**Applies to**</span></span>
- [<span data-ttu-id="ab15a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ab15a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ab15a-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="ab15a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ab15a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab15a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ab15a-108">**Statusinsikten för det** [](mail-flow-insights-v2.md) översta domänflödet i instrumentpanelen för e-postflöde i Säkerhets- & [efterlevnadscenter](https://protection.office.com) ger dig den aktuella e-postflödesstatusen för din organisation.</span><span class="sxs-lookup"><span data-stu-id="ab15a-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="ab15a-109">Den här insikten hjälper dig att identifiera och felsöka domäner som har problem ***med e-postflödet.***</span><span class="sxs-lookup"><span data-stu-id="ab15a-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="ab15a-110">Domänen kan till exempel inte ta emot extern e-post eftersom domänen har upphört att gälla eller domänen har en felaktig MX-post.</span><span class="sxs-lookup"><span data-stu-id="ab15a-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget för toppdomänflödesstatus i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="ab15a-112">När du klickar **på Visa** information i widgeten visas en **utfällsymbol** för Domänstatus som visar mer information om status för varje domän:</span><span class="sxs-lookup"><span data-stu-id="ab15a-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="ab15a-113">**Domain**</span><span class="sxs-lookup"><span data-stu-id="ab15a-113">**Domain**</span></span>
- <span data-ttu-id="ab15a-114">**Föregående MX-post**</span><span class="sxs-lookup"><span data-stu-id="ab15a-114">**Previous MX record**</span></span>
- <span data-ttu-id="ab15a-115">**Aktuell MX-post**</span><span class="sxs-lookup"><span data-stu-id="ab15a-115">**Current MX record**</span></span>
- <span data-ttu-id="ab15a-116">**Status för e-postmottagning**</span><span class="sxs-lookup"><span data-stu-id="ab15a-116">**Email receiving status**</span></span>
- <span data-ttu-id="ab15a-117">**Domänstatus:** En grön bockmarkering anger den aktuella MX-posten (vid den tidpunkt då du klickade på widgeten) matchar värdet vi har i posten och domänen har fått e-post under de senaste två timmarna.</span><span class="sxs-lookup"><span data-stu-id="ab15a-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="ab15a-118">Ett rött X indikerar att MX-posten har ändrats och att domänen inte har fått någon e-post under de senaste 6 timmarna.</span><span class="sxs-lookup"><span data-stu-id="ab15a-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="ab15a-119">Det här indikerar sannolikt att domänen har upphört att gälla eller att MX-posten har uppdaterats felaktigt.</span><span class="sxs-lookup"><span data-stu-id="ab15a-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="ab15a-120">Kontrollera med din domänregistrator eller DNS-värd om domänen har upphört att gälla eller om domänens MX-post är felaktig.</span><span class="sxs-lookup"><span data-stu-id="ab15a-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="ab15a-121">Du kan klicka **på Visa fler** om du vill se samma information för fler domäner.</span><span class="sxs-lookup"><span data-stu-id="ab15a-121">You can click **View more** to see the same information for more domains.</span></span>

![Den utfällna informationen i statusinformation för e-postflödet för toppdomänen](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="ab15a-123">Se även</span><span class="sxs-lookup"><span data-stu-id="ab15a-123">See also</span></span>

<span data-ttu-id="ab15a-124">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ab15a-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
