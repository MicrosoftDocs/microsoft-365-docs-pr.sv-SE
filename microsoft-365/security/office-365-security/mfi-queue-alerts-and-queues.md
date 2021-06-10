---
title: Köinsikter på instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratörer kan lära sig att använda widgeten Köer i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka misslyckade e-postflöden till sina lokala organisationer eller partnerorganisationer via utgående anslutningar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65452b0ad7c31673c910ba48c9c6709995e563ce
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599989"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="8c131-103">Köinsikter i säkerhets- & säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="8c131-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8c131-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="8c131-104">**Applies to**</span></span>
- [<span data-ttu-id="8c131-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8c131-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8c131-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="8c131-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8c131-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c131-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8c131-108">När meddelanden inte kan skickas från organisationen till dina lokala eller partner-e-postservrar med kopplingar, är meddelandena i kö i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c131-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="8c131-109">Vanliga exempel som kan orsaka detta villkor är:</span><span class="sxs-lookup"><span data-stu-id="8c131-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="8c131-110">Kopplingen är felaktigt konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="8c131-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="8c131-111">Det har skett nätverks- eller brandväggsändringar i din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="8c131-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="8c131-112">Microsoft 365 fortsätter att försöka leverera i 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="8c131-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="8c131-113">Efter 24 timmar förfaller meddelandena och returneras till avsändarna i rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskavsändare).</span><span class="sxs-lookup"><span data-stu-id="8c131-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="8c131-114">Om den fördefinierade e-postvolymen överskrider det fördefinierade tröskelvärdet (standardvärdet är 200 meddelanden) finns informationen tillgänglig på följande platser:</span><span class="sxs-lookup"><span data-stu-id="8c131-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="8c131-115">Köinsikter i [instrumentpanelen för e-postflöde](mail-flow-insights-v2.md) [i Säkerhets- & Efterlevnadscenter.](https://protection.office.com) </span><span class="sxs-lookup"><span data-stu-id="8c131-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="8c131-116">Mer information finns i [köinsikter i instrumentpanelen för e-postflöde](#queues-insight-in-the-mail-flow-dashboard) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="8c131-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="8c131-117">En avisering visas i **Senaste aviseringar i** instrumentpanelen Aviseringar i [säkerhets- & Efterlevnadscenter](https://protection.office.com) **(Instrumentpanelen** \> **aviseringar** eller <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="8c131-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Senaste aviseringar på instrumentpanelen Aviseringar i säkerhets- & Säkerhets- och efterlevnadscenter](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="8c131-119">Administratörer får ett e-postmeddelande baserat på konfigurationen av standardaviseringsprincipen Med namnet **Meddelanden har fördröjts.**</span><span class="sxs-lookup"><span data-stu-id="8c131-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="8c131-120">Information om hur du konfigurerar meddelandeinställningarna för den här aviseringen finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="8c131-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="8c131-121">Mer information om aviseringsprinciper finns i [Aviseringsprinciper i Säkerhets- & Efterlevnadscenter.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8c131-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="8c131-122">Anpassa köaviseringar</span><span class="sxs-lookup"><span data-stu-id="8c131-122">Customize queue alerts</span></span>

1. <span data-ttu-id="8c131-123">I [säkerhets- & säkerhets- och efterlevnadscenter](https://protection.office.com)går du **till** \> **Aviseringsprinciper för aviseringar** eller öppnar <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="8c131-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="8c131-124">På sidan **Aviseringsprinciper** hittar och väljer du principen **Meddelanden har fördröjts**.</span><span class="sxs-lookup"><span data-stu-id="8c131-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="8c131-125">I meddelandet **har fördröjts** och öppnats kan du aktivera eller inaktivera aviseringen och konfigurera meddelandeinställningarna.</span><span class="sxs-lookup"><span data-stu-id="8c131-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Meddelanden har fördröjts med information om aviseringsprincipen & Säkerhets- och efterlevnadscenter](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="8c131-127">**Status:** Du kan aktivera eller inaktivera varningen.</span><span class="sxs-lookup"><span data-stu-id="8c131-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="8c131-128">**Begränsning för** **e-postmottagare och daglig** avisering: **Klicka på** Redigera för att konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="8c131-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="8c131-129">Om du vill konfigurera meddelandeinställningarna klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8c131-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="8c131-130">I den **utfällna** menyn Redigera princip som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="8c131-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8c131-131">**Skicka e-postaviseringar:** Standardvärdet är på.</span><span class="sxs-lookup"><span data-stu-id="8c131-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="8c131-132">**E-postmottagare:** Standardvärdet är **TenantAdmins.**</span><span class="sxs-lookup"><span data-stu-id="8c131-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="8c131-133">**Daglig meddelandegräns:** Standardvärdet är **Ingen begränsning.**</span><span class="sxs-lookup"><span data-stu-id="8c131-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="8c131-134">**Tröskelvärde:** Standardvärdet är 200.</span><span class="sxs-lookup"><span data-stu-id="8c131-134">**Threshold**: The default value is 200.</span></span>

   ![Meddelandeinställningar i meddelanden har fördröjts med information om aviseringspolicyn i Säkerhets- & Efterlevnadscenter](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="8c131-136">När du är klar klickar du på **Spara** och **stäng**.</span><span class="sxs-lookup"><span data-stu-id="8c131-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="8c131-137">Köinsikter på instrumentpanelen för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="8c131-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="8c131-138">Även om volymen för det köade meddelandet inte har överskridit tröskelvärdet  och genererat [](mail-flow-insights-v2.md) en avisering kan du fortfarande använda köinsikterna i instrumentpanelen för e-postflöde för att se meddelanden som har köats i mer än en timme och vidta åtgärder innan antalet i köade meddelanden blir för stort.</span><span class="sxs-lookup"><span data-stu-id="8c131-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget för köer i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-queues-widget.png)

<span data-ttu-id="8c131-140">Om du klickar på antalet meddelanden på widgeten visas en **utfällbara** meny för Meddelanden i kö med följande information:</span><span class="sxs-lookup"><span data-stu-id="8c131-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="8c131-141">**Antal meddelanden i kö**</span><span class="sxs-lookup"><span data-stu-id="8c131-141">**Number of queued messages**</span></span>
- <span data-ttu-id="8c131-142">**Kopplingsnamn**: Klicka på kopplingsnamnet för att hantera kopplingen Exchange administrationscentret (EAC).</span><span class="sxs-lookup"><span data-stu-id="8c131-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="8c131-143">**Startad kötid**</span><span class="sxs-lookup"><span data-stu-id="8c131-143">**Queue started time**</span></span>
- <span data-ttu-id="8c131-144">**Äldsta meddelandena har förfallit**</span><span class="sxs-lookup"><span data-stu-id="8c131-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="8c131-145">**Målserver**</span><span class="sxs-lookup"><span data-stu-id="8c131-145">**Destination server**</span></span>
- <span data-ttu-id="8c131-146">**Senaste IP-adress**</span><span class="sxs-lookup"><span data-stu-id="8c131-146">**Last IP address**</span></span>
- <span data-ttu-id="8c131-147">**Senaste felet**</span><span class="sxs-lookup"><span data-stu-id="8c131-147">**Last error**</span></span>
- <span data-ttu-id="8c131-148">**Så här åtgärdar** du problemet: Vanliga problem och lösningar finns tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="8c131-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="8c131-149">Om länken **Åtgärda det nu** är tillgänglig, klickar du på den för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="8c131-149">If a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="8c131-150">Annars klickar du på någon av de tillgängliga länkarna för mer information om felet och möjliga lösningar.</span><span class="sxs-lookup"><span data-stu-id="8c131-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Information när du klickar på köinsikter på instrumentpanelen för e-postflöde](../../media/mfi-queues-details.png)

<span data-ttu-id="8c131-152">Samma utfällbara objekt visas när du **klickar på Visa kö** i information om ett meddelanden har **fördröjts avisering.**</span><span class="sxs-lookup"><span data-stu-id="8c131-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Meddelanden har fördröjts med aviseringsinformation i & Säkerhets- och efterlevnadscenter](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="8c131-154">Se även</span><span class="sxs-lookup"><span data-stu-id="8c131-154">See also</span></span>

<span data-ttu-id="8c131-155">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="8c131-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
