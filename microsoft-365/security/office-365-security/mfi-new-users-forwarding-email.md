---
title: Nya användare vidarebefordrar insikt via e-post
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan lära sig hur de nya användarna vidarebefordrar e-postmeddelandena i säkerhets & efterlevnad för att undersöka när användare i organisationen vidarebefordrar meddelanden till nya domäner.
ms.openlocfilehash: cb2e16d321e181916219e3425c26e59ebe31b866
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826993"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="8c4e0-103">Nya användare som vidarebefordrar e-postmeddelande för säkerhets &</span><span class="sxs-lookup"><span data-stu-id="8c4e0-103">New users forwarding email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="8c4e0-104">Det är misstänkt när nya användar konton i din organisation plötsligt startar vidarebefordran av e-postmeddelanden till externa domäner.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="8c4e0-105">De **nya domänerna som vidarebefordras via e-post** meddelar dig när nyskapade användare i organisationen vidarebefordrar meddelanden till externa domäner.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-105">The **New domains being forwarded email** insight notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="8c4e0-106">Det här villkoret kan tyda på att administratören använde för att skapa nya användare.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="8c4e0-107">Om du misstänker att kontona är inaktiverade kan du läsa mer i [svara på ett komprometterat e-postkonto](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="8c4e0-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="8c4e0-108">Denna inblick visas bara när problemet identifieras och visas på sidan för [vidarebefordran av rapporter](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="8c4e0-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Nya användare vidarebefordrar insikt via e-post](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="8c4e0-110">När du klickar på widgeten visas en utfällbar plats där du kan hitta mer information om de vidarebefordrade meddelandena, inklusive en länk till [rapporten ändringar i vidarebefordring](#forwarding-modifications-report) enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![Den utfällbara informationen som visas när du klickar på den nya användaren vidarebefordrar e-postinsikt](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="8c4e0-112">Du kan också komma åt den här informations sidan när du väljer inblicken när du klickar på **Visa alla** i området **Top Insights & rekommendationer** på (**rapport** \> **instrument panel** eller <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="8c4e0-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="8c4e0-113">Du kan klicka på länken **Se rapporten som är kopplad** till en Insight-länk för att gå till **rapporten ändringar i vidarebefordring** enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="8c4e0-114">Rapport över ändringar i vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="8c4e0-114">Forwarding modifications report</span></span>

<span data-ttu-id="8c4e0-115">**Rapporten för ändringar av vidarekoppling** visar information om meddelanden som automatiskt vidarebefordras från avsändare i din organisation:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="8c4e0-116">Nyskapade konton som vidarebefordrar meddelanden till externa domäner.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="8c4e0-117">Konton som vidarebefordrar meddelanden till externa domäner som aldrig har vidarebefordrats till av andra avsändare i din organisation.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="8c4e0-118">Dessa typer av vidarebefordrade meddelanden kan utgöra en säkerhets-eller kompatibilitets risk och kan tyda på konton.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="8c4e0-119">Rapporten innehåller data för upp till 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="8c4e0-120">Som standard visar rapporten data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="8c4e0-121">Den här rapporten är inte direkt tillgänglig i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) eller rapport [instrument panelen](view-mail-flow-reports.md).</span><span class="sxs-lookup"><span data-stu-id="8c4e0-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="8c4e0-122">Förutom att klicka på länken **se en rapport som är associerad med en inblick** i den **nya användaren som vidarebefordrar e-post** , kommer du till rapporten genom att:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="8c4e0-123">Klicka på länken **vidarebefordra aviseringar** i information om de [nya domänerna som vidarebefordrar e-postinsikt](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="8c4e0-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="8c4e0-124">Öppnar <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="8c4e0-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="8c4e0-125">Rapportvy för rapporten ändringar i vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="8c4e0-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="8c4e0-126">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8c4e0-127">**Visa data för: nya vidarebefordrande användare**:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-127">**Show data for: New forwarding users**:</span></span>

  ![Ny vy för vidarebefordrade användare i rapporten ändringar av vidarebefordran](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="8c4e0-129">**Visa data för: nya vidarebefordrande domäner**:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-129">**Show data for: New forwarding domains**:</span></span>

  ![Vyn nya vidarebefordrade domäner i rapporten ändringar i vidarebefordran](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="8c4e0-131">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="8c4e0-132">Vyn detaljerad tabell för rapporten ändringar i vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="8c4e0-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="8c4e0-133">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="8c4e0-134">**Visa data för: nya vidarebefordrande användare**:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="8c4e0-135">**Namn**: avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="8c4e0-136">**Typ av vidarebefordran**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-136">**Forwarding type**</span></span>
  - <span data-ttu-id="8c4e0-137">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-137">**Recipient address**</span></span>
  - <span data-ttu-id="8c4e0-138">**Information**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-138">**Details**</span></span>
  - <span data-ttu-id="8c4e0-139">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-139">**Count**</span></span>
  - <span data-ttu-id="8c4e0-140">**Första framåtriktade datum**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-140">**First forward date**</span></span>

- <span data-ttu-id="8c4e0-141">**Visa data för: nya vidarebefordrande domäner**:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="8c4e0-142">**Namn**: avsändarens e-postdomän.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="8c4e0-143">**Typ av vidarebefordran**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-143">**Forwarding type**</span></span>
  - <span data-ttu-id="8c4e0-144">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-144">**Recipient address**</span></span>
  - <span data-ttu-id="8c4e0-145">**Information**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-145">**Details**</span></span>
  - <span data-ttu-id="8c4e0-146">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-146">**Count**</span></span>
  - <span data-ttu-id="8c4e0-147">**Första framåtriktade datum**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-147">**First forward date**</span></span>

<span data-ttu-id="8c4e0-148">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8c4e0-149">Om du väljer en rad från tabellen visas en utfällbar **lista** med följande information:</span><span class="sxs-lookup"><span data-stu-id="8c4e0-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="8c4e0-150">**Namn**: det här är antingen avsändarens e-postadress (från **Visa data för vy med nya vidarebefordrade användare** ) eller avsändarens e-postdomän (från **Visa data för ny vy med vidarebefordrings domäner** ).</span><span class="sxs-lookup"><span data-stu-id="8c4e0-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="8c4e0-151">**Typ av vidarebefordran**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-151">**Forwarding type**</span></span>
- <span data-ttu-id="8c4e0-152">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-152">**Recipient**</span></span>
- <span data-ttu-id="8c4e0-153">**Information**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-153">**Details**</span></span>
- <span data-ttu-id="8c4e0-154">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-154">**Count**</span></span>
- <span data-ttu-id="8c4e0-155">**Start datum**</span><span class="sxs-lookup"><span data-stu-id="8c4e0-155">**Start date**</span></span>
- <span data-ttu-id="8c4e0-156">**Rekommendation**: härifrån kan du klicka på länken för att hantera användaren i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Information som är utfällad från tabellen för nya användare av vidarebefordring i rapporten om ändringar för vidarebefordran](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="8c4e0-158">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c4e0-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c4e0-159">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8c4e0-159">Related topics</span></span>

<span data-ttu-id="8c4e0-160">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="8c4e0-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
