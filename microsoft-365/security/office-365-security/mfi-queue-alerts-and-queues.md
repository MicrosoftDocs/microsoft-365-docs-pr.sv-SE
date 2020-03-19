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
description: Administratörer kan lära sig mer om köaviseringar och köer i instrumentpanelen för e-postflöde i Säkerhets- & Compliance Center.
ms.openlocfilehash: bc777e3c9764987dc72aa0407f19618bc26f7528
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812962"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="84e1e-103">Köaviseringar och köer</span><span class="sxs-lookup"><span data-stu-id="84e1e-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="84e1e-104">Köaviseringar</span><span class="sxs-lookup"><span data-stu-id="84e1e-104">Queue alerts</span></span>

<span data-ttu-id="84e1e-105">När meddelanden inte kan skickas från din Office 365-organisation till lokala e-postservrar eller partnerservrar med hjälp av kopplingar köas meddelandena i Office 365.</span><span class="sxs-lookup"><span data-stu-id="84e1e-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="84e1e-106">Vanliga exempel som orsakar detta villkor är:</span><span class="sxs-lookup"><span data-stu-id="84e1e-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="84e1e-107">Anslutningen är felaktigt konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="84e1e-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="84e1e-108">Det har skett nätverks- eller brandväggsändringar i den lokala miljön.</span><span class="sxs-lookup"><span data-stu-id="84e1e-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="84e1e-109">Office 365 fortsätter att försöka leverera igen i 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="84e1e-109">Office 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="84e1e-110">Efter 24 timmar upphör meddelandena att gälla och returneras till avsändarna i rapporter som inte levereras (kallas även en NDRs eller avvisningsmeddelanden).</span><span class="sxs-lookup"><span data-stu-id="84e1e-110">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="84e1e-111">Om den köade e-postvolymen överskrider det fördefinierade tröskelvärdet (standardvärdet är 2000-meddelanden) kommer aviseringarna att vara tillgängliga i instrumentpanelen för e-postflödet vid **senaste aviseringar**och administratörer får ett e-postmeddelande (till deras alternativa e-postadress).</span><span class="sxs-lookup"><span data-stu-id="84e1e-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="84e1e-112">Information om hur du konfigurerar tröskelvärdet för aviseringar, daglig meddelandegräns och/eller mottagare av aviseringen finns i avsnittet **Anpassa köaviseringar** nedan.</span><span class="sxs-lookup"><span data-stu-id="84e1e-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Köaviseringar i det senaste varningsområdet för instrumentpanelen för e-postflöde i Säkerhets-& Compliance Center](../../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="84e1e-114">Anpassa köaviseringar</span><span class="sxs-lookup"><span data-stu-id="84e1e-114">Customize queue alerts</span></span>

<span data-ttu-id="84e1e-115">E-postflödesinsikter skapar en varningsprincip med namnet **Meddelanden har försenats** (kryssrutan **Skicka e-postmeddelanden** i exempelskärmbilden nedan) som finns i **varningsprinciper**för **aviseringar** \> .</span><span class="sxs-lookup"><span data-stu-id="84e1e-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="84e1e-116">Du kan ändra tröskelvärdet och varningsmottagarna genom att klicka på principen.</span><span class="sxs-lookup"><span data-stu-id="84e1e-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Varningar Navigering](../../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="84e1e-118">Du ser ett nytt principinformationsblad, du kan nu klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="84e1e-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Redigera princip](../../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="84e1e-120">Informationsbladet ändras till **redigeraprincipen**.</span><span class="sxs-lookup"><span data-stu-id="84e1e-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="84e1e-121">Du kan nu ändra mottagarna för e-postmeddelandet för aviseringar, gränsen för antalet meddelanden som skickas per dag och minimitröskeln för att utlösa aviseringen (200 eller fler).</span><span class="sxs-lookup"><span data-stu-id="84e1e-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Redigera principblad](../../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="84e1e-123">Information om köavisering</span><span class="sxs-lookup"><span data-stu-id="84e1e-123">Queue alert details</span></span>

<span data-ttu-id="84e1e-124">När du klickar på aviseringen visas varningsinformationen i ett utfällbart fönster.</span><span class="sxs-lookup"><span data-stu-id="84e1e-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Välj en köavisering i området Senaste aviseringar i instrumentpanelen för e-postflöde i Säkerhets- & Compliance Center](../../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Utfällbara köaviseringsinformation i säkerhets& Compliance Center](../../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="84e1e-127">Du kan klicka på **Visa kö** i varningsinformationen om du vill visa köinformation, problem och länkar till tillgängliga korrigeringar i ett nytt utfällbart fönster.</span><span class="sxs-lookup"><span data-stu-id="84e1e-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![Utfällbara köaviseringsinformation i säkerhets& Compliance Center](../../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Visa kö i varningsinformationen](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="84e1e-130">Köer</span><span class="sxs-lookup"><span data-stu-id="84e1e-130">Queues</span></span>

<span data-ttu-id="84e1e-131">Även om den köade meddelandevolymen inte har överskridit tröskelvärdet kan du fortfarande använda området **Köer** på instrumentpanelen för e-postflöde för att se meddelanden som har köati i mer än en timme.</span><span class="sxs-lookup"><span data-stu-id="84e1e-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="84e1e-132">Du kan använda området **Köer** för att övervaka antalet köade meddelanden (värdet 0 anger att e-postflödet är OK) och vidta åtgärder innan antalet köade meddelanden blir för stort.</span><span class="sxs-lookup"><span data-stu-id="84e1e-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Köer i instrumentpanelen för e-postflöde i Säkerhets-& Compliance Center](../../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="84e1e-134">När du klickar på antalet köade meddelanden i **köer**visas köinformationen och vägledningen för hur problemet ska åtgärdas i ett utfällbart fönster (samma utfällbara fönster som visas när du har klickat på **Visa kö** i informationen om en köavisering).</span><span class="sxs-lookup"><span data-stu-id="84e1e-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Köinformation](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="84e1e-136">Se även</span><span class="sxs-lookup"><span data-stu-id="84e1e-136">See also</span></span>

<span data-ttu-id="84e1e-137">Mer information om andra insikter om e-postflöde på instrumentpanelen för e-postflöde finns [i E-postflödesinsikter i Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="84e1e-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
