---
title: Köaviseringar och köer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratörer kan lära sig mer om köaviseringar och köer i instrumentpanelen för e-postflödet i Security & Compliance Center.
ms.openlocfilehash: 7bb103bad89ee39991a5c16d7101ab4658842479
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635190"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="d69ce-103">Köaviseringar och köer</span><span class="sxs-lookup"><span data-stu-id="d69ce-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="d69ce-104">Köaviseringar</span><span class="sxs-lookup"><span data-stu-id="d69ce-104">Queue alerts</span></span>

<span data-ttu-id="d69ce-105">När meddelanden inte kan skickas från din organisation till dina lokala eller partner-e-postservrar med hjälp av anslutningsappar, står meddelandena i kö i Office 365.</span><span class="sxs-lookup"><span data-stu-id="d69ce-105">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="d69ce-106">Vanliga exempel som orsakar detta tillstånd är:</span><span class="sxs-lookup"><span data-stu-id="d69ce-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="d69ce-107">Anslutningen är felaktigt konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="d69ce-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="d69ce-108">Det har skett nätverks- eller brandväggsändringar i din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="d69ce-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="d69ce-109">Microsoft 365 fortsätter att försöka levereras igen i 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="d69ce-109">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="d69ce-110">Efter 24 timmar upphör meddelandena att gälla och returneras till avsändarna i rapporter som inte levereras (kallas även ndr-meddelanden eller avstudsar).</span><span class="sxs-lookup"><span data-stu-id="d69ce-110">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="d69ce-111">Om den köade e-postvolymen överskrider det fördefinierade tröskelvärdet (standardvärdet är 2000-meddelanden) är aviseringarna tillgängliga i instrumentpanelen för e-postflödet vid **de senaste aviseringarna**och administratörer får ett e-postmeddelande (till deras alternativa e-postadress).</span><span class="sxs-lookup"><span data-stu-id="d69ce-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="d69ce-112">Information om hur du konfigurerar varningströskeln, den dagliga meddelandegränsen och/eller mottagarna av aviseringen finns i avsnittet **Anpassa köaviseringar** nedan.</span><span class="sxs-lookup"><span data-stu-id="d69ce-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Kövarningar i området Senaste aviseringar i instrumentpanelen för e-postflödet i Säkerhets- & Compliance Center](../../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="d69ce-114">Anpassa köaviseringar</span><span class="sxs-lookup"><span data-stu-id="d69ce-114">Customize queue alerts</span></span>

<span data-ttu-id="d69ce-115">Statistik för e-postflöde skapar en aviseringsprincip med namnet **Meddelanden har försenats** (kryssrutan **Skicka e-postmeddelanden** i exempelskärmen nedan) som finns i **varningsprinciper** \> **Alert Policies**för aviseringar .</span><span class="sxs-lookup"><span data-stu-id="d69ce-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="d69ce-116">Du kan ändra tröskelvärdet och varna mottagarna genom att klicka på principen.</span><span class="sxs-lookup"><span data-stu-id="d69ce-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Navigering i varningar](../../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="d69ce-118">Du ser ett nytt policyinformationsblad, du kan nu klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="d69ce-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Redigera princip](../../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="d69ce-120">Informationsbladet ändras till **redigeringsprincipen**.</span><span class="sxs-lookup"><span data-stu-id="d69ce-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="d69ce-121">Du kan nu ändra mottagarna för aviseringsmeddelandet, gränsen för antalet meddelanden som skickas per dag och minimitröskeln för att utlösa aviseringen (200 eller fler).</span><span class="sxs-lookup"><span data-stu-id="d69ce-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Redigera principblad](../../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="d69ce-123">Information om köavisering</span><span class="sxs-lookup"><span data-stu-id="d69ce-123">Queue alert details</span></span>

<span data-ttu-id="d69ce-124">När du klickar på aviseringen visas varningsinformationen i ett utfällbart fönster.</span><span class="sxs-lookup"><span data-stu-id="d69ce-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Välj en köavisering i området Senaste aviseringar på instrumentpanelen för e-postflödet i Säkerhets- & Compliance Center](../../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Köaviseringsinformationen Utfällbara information i Security & Compliance Center](../../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="d69ce-127">Du kan klicka på **Visa kö** i aviseringsinformationen om du vill se köinformation, problem och länkar till tillgängliga korrigeringar i ett nytt utfällbart fönster.</span><span class="sxs-lookup"><span data-stu-id="d69ce-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![Köaviseringsinformationen Utfällbara information i Security & Compliance Center](../../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Visa kö i varningsinformationen](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="d69ce-130">Köer</span><span class="sxs-lookup"><span data-stu-id="d69ce-130">Queues</span></span>

<span data-ttu-id="d69ce-131">Även om den köade meddelandevolymen inte har överskridit tröskelvärdet kan du fortfarande använda området **Köer** på instrumentpanelen för e-postflödet för att se meddelanden som har köats i mer än en timme.</span><span class="sxs-lookup"><span data-stu-id="d69ce-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="d69ce-132">Du kan använda **området Köer** för att övervaka antalet meddelanden i kö (värdet 0 anger att e-postflödet är OK) och vidta åtgärder innan antalet köade meddelanden blir för stort.</span><span class="sxs-lookup"><span data-stu-id="d69ce-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Köer i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="d69ce-134">När du klickar på antalet meddelanden i kö **i Köer**visas köinformation och vägledning för hur du åtgärdar problemet i ett utfällbart fönster (samma utfällbara objekt som visas när du klickar på **Visa kö** i information om en köavisering).</span><span class="sxs-lookup"><span data-stu-id="d69ce-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Köinformation](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="d69ce-136">Snabbreferens</span><span class="sxs-lookup"><span data-stu-id="d69ce-136">See also</span></span>

<span data-ttu-id="d69ce-137">Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d69ce-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
