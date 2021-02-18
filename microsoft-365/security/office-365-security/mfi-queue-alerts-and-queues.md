---
title: Köinsikter i instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratörer kan lära sig att använda widgeten Köer i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka ett misslyckat e-postflöde till sina lokala organisationer eller partnerorganisationer via utgående anslutningar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8ee5ea37fa5a63b8035572059e419c400d66f3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289443"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="30dd9-103">Köinsikter i säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="30dd9-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="30dd9-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="30dd9-104">**Applies to**</span></span>
- [<span data-ttu-id="30dd9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="30dd9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="30dd9-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="30dd9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="30dd9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30dd9-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="30dd9-108">När meddelanden inte kan skickas från din organisation till dina lokala e-postservrar eller partner-e-postservrar med hjälp av kopplingar, är meddelandena i kö i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="30dd9-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="30dd9-109">Vanliga exempel som kan orsaka detta villkor är:</span><span class="sxs-lookup"><span data-stu-id="30dd9-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="30dd9-110">Kopplingen är felaktigt konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="30dd9-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="30dd9-111">Det har skett nätverks- eller brandväggsändringar i din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="30dd9-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="30dd9-112">Microsoft 365 fortsätter att försöka leverera igen i 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="30dd9-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="30dd9-113">Efter 24 timmar förfaller meddelandena och returneras till avsändarna i rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskavsändarmeddelanden).</span><span class="sxs-lookup"><span data-stu-id="30dd9-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="30dd9-114">Om den fördefinierade e-postvolymen överskrider det fördefinierade tröskelvärdet (standardvärdet är 200 meddelanden) är informationen tillgänglig på följande platser:</span><span class="sxs-lookup"><span data-stu-id="30dd9-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="30dd9-115">**Köinsikter** i [instrumentpanelen för e-postflöde](mail-flow-insights-v2.md) i [& Säkerhets- och efterlevnadscenter.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="30dd9-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="30dd9-116">Mer information finns i [köinsikter i instrumentpanelen för e-postflöde](#queues-insight-in-the-mail-flow-dashboard) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="30dd9-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="30dd9-117">En avisering visas i **instrumentpanelen för senaste** aviseringar i [säkerhets- & (instrumentpanelen](https://protection.office.com) för aviseringar \>  <https://protection.office.com/alertsdashboard> eller).</span><span class="sxs-lookup"><span data-stu-id="30dd9-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Senaste aviseringar i instrumentpanelen för aviseringar i Säkerhets- & Efterlevnadscenter](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="30dd9-119">Administratörer får ett e-postmeddelande baserat på konfigurationen av standardaviseringsprincipen **med namnet Meddelanden har fördröjts.**</span><span class="sxs-lookup"><span data-stu-id="30dd9-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="30dd9-120">Information om hur du konfigurerar aviseringsinställningarna för den här aviseringen finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="30dd9-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="30dd9-121">Mer information om aviseringsprinciper finns i [Aviseringsprinciper i Säkerhets- & Efterlevnadscenter.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="30dd9-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="30dd9-122">Anpassa köaviseringar</span><span class="sxs-lookup"><span data-stu-id="30dd9-122">Customize queue alerts</span></span>

1. <span data-ttu-id="30dd9-123">Gå till [aviseringsprinciperna eller öppna i säkerhets-](https://protection.office.com)och **&** säkerhets- \>  och efterlevnadscentret. <https://protection.office.com/alertpolicies></span><span class="sxs-lookup"><span data-stu-id="30dd9-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="30dd9-124">Sök efter **och välj** principen Meddelanden har fördröjts på sidan **Aviseringsprinciper.**</span><span class="sxs-lookup"><span data-stu-id="30dd9-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="30dd9-125">I meddelandet **har fördröjts** och öppnats kan du aktivera eller inaktivera aviseringen och konfigurera aviseringsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="30dd9-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Meddelanden har fördröjts med information om avisering & Säkerhets- och efterlevnadscenter](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="30dd9-127">**Status:** Du kan aktivera eller inaktivera aviseringen.</span><span class="sxs-lookup"><span data-stu-id="30dd9-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="30dd9-128">**Gräns för** **e-postmottagare och daglig** avisering: **Klicka på** Redigera för att konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="30dd9-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="30dd9-129">Om du vill konfigurera meddelandeinställningarna klickar du på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="30dd9-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="30dd9-130">Konfigurera följande **inställningar i** den utfällna menyn Redigera princip som visas:</span><span class="sxs-lookup"><span data-stu-id="30dd9-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="30dd9-131">**Skicka e-postaviseringar:** Standardvärdet är på.</span><span class="sxs-lookup"><span data-stu-id="30dd9-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="30dd9-132">**E-postmottagare:** Standardvärdet är **TenantAdmins.**</span><span class="sxs-lookup"><span data-stu-id="30dd9-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="30dd9-133">**Daglig meddelandegräns:** Standardvärdet är **Ingen gräns.**</span><span class="sxs-lookup"><span data-stu-id="30dd9-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="30dd9-134">**Tröskelvärde:** Standardvärdet är 200.</span><span class="sxs-lookup"><span data-stu-id="30dd9-134">**Threshold**: The default value is 200.</span></span>

   ![Meddelandeinställningar i meddelanden har fördröjts med information om säkerhets- & Efterlevnadscenter](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="30dd9-136">Klicka på Spara och Stäng **när** du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30dd9-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="30dd9-137">Köinsikter i instrumentpanelen för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="30dd9-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="30dd9-138">Även om volymen för det köade meddelandet inte har överskridit tröskelvärdet  och genererat [](mail-flow-insights-v2.md) en avisering kan du fortfarande använda köinsikterna i instrumentpanelen för e-postflöde för att se meddelanden som har köats i mer än en timme och vidta åtgärder innan antalet köade meddelanden blir för stora.</span><span class="sxs-lookup"><span data-stu-id="30dd9-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget för köer i instrumentpanelen för e-postflöde i Säkerhets- & Efterlevnadscenter](../../media/mfi-queues-widget.png)

<span data-ttu-id="30dd9-140">Om du klickar på antalet meddelanden  på widgeten visas en utfällbara meddelandekö med följande information:</span><span class="sxs-lookup"><span data-stu-id="30dd9-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="30dd9-141">**Antal meddelanden i kö**</span><span class="sxs-lookup"><span data-stu-id="30dd9-141">**Number of queued messages**</span></span>
- <span data-ttu-id="30dd9-142">**Kopplingsnamn:** Klicka på kopplingsnamnet för att hantera kopplingen i administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="30dd9-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="30dd9-143">**Starttid för kö**</span><span class="sxs-lookup"><span data-stu-id="30dd9-143">**Queue started time**</span></span>
- <span data-ttu-id="30dd9-144">**Äldsta meddelanden har förfallit**</span><span class="sxs-lookup"><span data-stu-id="30dd9-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="30dd9-145">**Målserver**</span><span class="sxs-lookup"><span data-stu-id="30dd9-145">**Destination server**</span></span>
- <span data-ttu-id="30dd9-146">**Senaste IP-adress**</span><span class="sxs-lookup"><span data-stu-id="30dd9-146">**Last IP address**</span></span>
- <span data-ttu-id="30dd9-147">**Senaste felet**</span><span class="sxs-lookup"><span data-stu-id="30dd9-147">**Last error**</span></span>
- <span data-ttu-id="30dd9-148">**Så här åtgärdar** du problemet: Vanliga problem och lösningar finns tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="30dd9-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="30dd9-149">Om länken Åtgärda **det nu** är tillgänglig kan du klicka på den för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="30dd9-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="30dd9-150">Annars klickar du på de tillgängliga länkarna för att få mer information om felet och möjliga lösningar.</span><span class="sxs-lookup"><span data-stu-id="30dd9-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Information när du klickar på köinsikter på instrumentpanelen för e-postflöde](../../media/mfi-queues-details.png)

<span data-ttu-id="30dd9-152">Samma utfällbara bild visas när du **klickar på Visa kö** i information om ett meddelande har **fördröjts.**</span><span class="sxs-lookup"><span data-stu-id="30dd9-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Meddelanden har fördröjts i säkerhets- & Efterlevnadscenter](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="30dd9-154">Se även</span><span class="sxs-lookup"><span data-stu-id="30dd9-154">See also</span></span>

<span data-ttu-id="30dd9-155">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="30dd9-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
