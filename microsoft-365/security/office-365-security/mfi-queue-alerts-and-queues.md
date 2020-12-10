---
title: Köers inblick i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratörer kan lära dig hur du använder widgeten köer i instrument panelen för e-postflöde i säkerhets & Compliance Center för att övervaka misslyckade e-postflöden till deras lokala eller partner organisationer via utgående anslutningar.
ms.openlocfilehash: c582a7f459d89fa1515713c4f55dea14b619a6ec
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616398"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="aa029-103">Köer inblickar i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="aa029-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="aa029-104">När meddelanden inte kan skickas från din organisation till lokala eller partnersbaserade e-postservrar med kopplingar köas de i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aa029-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="aa029-105">Vanliga exempel som orsakar det här problemet:</span><span class="sxs-lookup"><span data-stu-id="aa029-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="aa029-106">Kopplingen är felaktigt konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="aa029-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="aa029-107">Nätverks-eller vägg ändringar har gjorts i din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="aa029-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="aa029-108">Microsoft 365 fortsätter att försöka leverera i 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="aa029-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="aa029-109">Efter 24 timmar upphör meddelanden att gälla och kommer att återföras till avsändare i rapporter som inte kunde levereras (kallas även för NDR eller studs meddelanden).</span><span class="sxs-lookup"><span data-stu-id="aa029-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="aa029-110">Om den köade e-postvolymen överskrider det fördefinierade tröskelvärdet (Standardvärdet är 200 meddelanden) finns informationen på följande platser:</span><span class="sxs-lookup"><span data-stu-id="aa029-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="aa029-111">**Köerna** inblickar i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="aa029-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="aa029-112">Mer information finns i [köerna under rubriken e-postflöde](#queues-insight-in-the-mail-flow-dashboard) i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="aa029-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>

- <span data-ttu-id="aa029-113">En avisering visas i de **senaste varningarna** instrument panelen för aviseringar i [säkerhets & Compliance Center](https://protection.office.com) (instrument panelen för **aviseringar** \>  eller <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="aa029-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Senaste meddelanden i instrument panelen för aviseringar i säkerhets & efterlevnad](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="aa029-115">Administratörer får ett e-postmeddelande baserat på konfigurationen av den standard aviserings princip som heter **meddelanden har försen ATS**.</span><span class="sxs-lookup"><span data-stu-id="aa029-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="aa029-116">Se nästa avsnitt om du vill konfigurera aviserings inställningarna för den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="aa029-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="aa029-117">Mer information om aviserings principer finns i [aviserings principer i säkerhets & efterlevnad](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aa029-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="aa029-118">Anpassa aviseringar i kö</span><span class="sxs-lookup"><span data-stu-id="aa029-118">Customize queue alerts</span></span>

1. <span data-ttu-id="aa029-119">Gå till **aviserings** principer för varningar eller öppna i fönstret [säkerhets & efterlevnad](https://protection.office.com) \>  <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="aa029-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="aa029-120">Leta reda på och välj policyn som heter **meddelanden** på sidan **aviserings principer** .</span><span class="sxs-lookup"><span data-stu-id="aa029-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="aa029-121">I **meddelandet har fördröjd** utfällning som öppnas kan du aktivera eller inaktivera aviseringen och konfigurera aviserings inställningarna.</span><span class="sxs-lookup"><span data-stu-id="aa029-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Meddelanden har fördröjts med aviserings princip uppgifter säkerhets & efterlevnad](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="aa029-123">**Status**: du kan aktivera eller inaktivera aviseringen.</span><span class="sxs-lookup"><span data-stu-id="aa029-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="aa029-124">**E-postmottagare** och **daglig meddelande gräns**: Klicka på **Redigera** för att konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="aa029-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="aa029-125">Konfigurera aviserings inställningarna genom att klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="aa029-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="aa029-126">I redigera utfällbar **princip** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="aa029-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="aa029-127">**Skicka e-postmeddelanden**: standardvärdet är på.</span><span class="sxs-lookup"><span data-stu-id="aa029-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="aa029-128">**E-postmottagare**: standardvärdet är **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="aa029-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="aa029-129">**Daglig meddelande gräns**: standardvärdet är **ingen gräns**.</span><span class="sxs-lookup"><span data-stu-id="aa029-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="aa029-130">**Tröskelvärde**: standardvärdet är 200.</span><span class="sxs-lookup"><span data-stu-id="aa029-130">**Threshold**: The default value is 200.</span></span>

   ![Aviserings inställningar i meddelanden har fördröjts med aviserings princip uppgifter säkerhets & efterlevnad](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="aa029-132">När du är klar klickar du på **Spara** och **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="aa029-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="aa029-133">Köers inblick i instrument panelen för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="aa029-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="aa029-134">Även om den köade meddelande volymen inte har överskridit tröskelvärdet och genererat en avisering kan du ändå använda **köer** i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) för att visa meddelanden som har placerats i kö i mer än en timme och vidta åtgärder innan antalet köade meddelanden blir för stora.</span><span class="sxs-lookup"><span data-stu-id="aa029-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widgeten för köer i instrument panelen för säkerhets &](../../media/mfi-queues-widget.png)

<span data-ttu-id="aa029-136">Om du klickar på antalet meddelanden i widgeten visas en utfällbar **meddelande** med följande information:</span><span class="sxs-lookup"><span data-stu-id="aa029-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="aa029-137">**Antal köade meddelanden**</span><span class="sxs-lookup"><span data-stu-id="aa029-137">**Number of queued messages**</span></span>
- <span data-ttu-id="aa029-138">**Anslutnings namn**: Klicka på kopplingens namn för att hantera kopplingen i administrations centret för Exchange (UK).</span><span class="sxs-lookup"><span data-stu-id="aa029-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="aa029-139">**Start tid för kö**</span><span class="sxs-lookup"><span data-stu-id="aa029-139">**Queue started time**</span></span>
- <span data-ttu-id="aa029-140">**Äldsta meddelanden har upphört**</span><span class="sxs-lookup"><span data-stu-id="aa029-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="aa029-141">**Mål Server**</span><span class="sxs-lookup"><span data-stu-id="aa029-141">**Destination server**</span></span>
- <span data-ttu-id="aa029-142">**Sista IP-adress**</span><span class="sxs-lookup"><span data-stu-id="aa029-142">**Last IP address**</span></span>
- <span data-ttu-id="aa029-143">**Senaste fel**</span><span class="sxs-lookup"><span data-stu-id="aa029-143">**Last error**</span></span>
- <span data-ttu-id="aa029-144">**Så här löser du problemet**: vanliga problem och lösningar finns tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="aa029-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="aa029-145">Om du har en lösning på att länken **nu** är tillgänglig klickar du på den för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="aa029-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="aa029-146">Annars kan du klicka på eventuella tillgängliga länkar för mer information om felet och möjliga lösningar.</span><span class="sxs-lookup"><span data-stu-id="aa029-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Information efter att du klickat på ärende köerna i instrument panelen för e-postflöde](../../media/mfi-queues-details.png)

<span data-ttu-id="aa029-148">Samma utfällda meddelande visas när du klickar på **Visa kö** i **meddelandet har fördröjts** .</span><span class="sxs-lookup"><span data-stu-id="aa029-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Meddelanden har fördröjts med aviserings informationen i centret för säkerhets &](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="aa029-150">Se även</span><span class="sxs-lookup"><span data-stu-id="aa029-150">See also</span></span>

<span data-ttu-id="aa029-151">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="aa029-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
