---
title: Nya användare vidarebefordrar insikt via e-post
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan ta & reda på hur de kan använda information om vidarebefordran av e-post i Säkerhets- och efterlevnadscenter för att undersöka när användare i organisationen vidarebefordrar meddelanden till nya domäner.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b86d726979991a55e7d4e43bf3581a4a664ee4f
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150261"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="31d44-103">Nya användare som vidarebefordrar e-postmeddelanden i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="31d44-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="31d44-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="31d44-104">**Applies to**</span></span>
- [<span data-ttu-id="31d44-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="31d44-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="31d44-106">Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="31d44-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="31d44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31d44-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="31d44-108">Det är misstänkt när nya användarkonton i organisationen plötsligt börjar vidarebefordra e-postmeddelanden till externa domäner.</span><span class="sxs-lookup"><span data-stu-id="31d44-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="31d44-109">De **nya domäner som** vidarebefordras i Säkerhets- & [och](https://protection.office.com) efterlevnadscenter meddelar dig när nyligen skapade användare i organisationen vidarebefordrar meddelanden till externa domäner.</span><span class="sxs-lookup"><span data-stu-id="31d44-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="31d44-110">Det här villkoret kan ange att komprometterade administratörskonton användes för att skapa nya användare.</span><span class="sxs-lookup"><span data-stu-id="31d44-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="31d44-111">Om du misstänker att kontona har komprometterats kan du gå [till Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="31d44-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="31d44-112">Den här insikten visas bara när problemet identifieras och visas på [sidan Med vidarebefordransrapport.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="31d44-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Nya användare vidarebefordrar insikt via e-post](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="31d44-114">När du klickar på widgeten visas en utfällig meny där du kan [](#forwarding-modifications-report) hitta mer information om vidarebefordrade meddelanden, inklusive en länk till rapporten om ändringar av vidarebefordran, som beskrivs senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="31d44-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Information som visas när du klickar på e-postinsikten Nya användare som vidarebefordrar e-postmeddelanden](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="31d44-116">Du kan också gå till den här informationssidan  när du väljer insikten när du har klickat på Visa allt i området **& rekommendationer** **på** (Instrumentpanelen Rapporter \>  <https://protection.office.com/insightdashboard> eller).</span><span class="sxs-lookup"><span data-stu-id="31d44-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="31d44-117">Du kan klicka på **länken Visa rapport som är** kopplad till insikter om du vill gå till rapporten om ändringar i **vidarebefordran** enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="31d44-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="31d44-118">Rapporten Om att vidarebefordra ändringar</span><span class="sxs-lookup"><span data-stu-id="31d44-118">Forwarding modifications report</span></span>

<span data-ttu-id="31d44-119">Rapporten **Om ändringar av vidarebefordran** visas information om meddelanden som vidarebefordras automatiskt från avsändare i organisationen:</span><span class="sxs-lookup"><span data-stu-id="31d44-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="31d44-120">Nyligen skapade konton som vidarebefordrar meddelanden till externa domäner.</span><span class="sxs-lookup"><span data-stu-id="31d44-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="31d44-121">Konton som vidarebefordrar meddelanden till externa domäner som inte har vidarebefordrats till av andra avsändare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="31d44-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="31d44-122">Den här typen av vidarebefordrade meddelanden kan utgöra en säkerhets- eller efterlevnadsrisk och kan indikera komprometterade konton.</span><span class="sxs-lookup"><span data-stu-id="31d44-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="31d44-123">Rapporten innehåller data för upp till 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="31d44-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="31d44-124">Som standard visar rapporten data för de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="31d44-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="31d44-125">Den här rapporten är inte direkt tillgänglig på instrumentpanelen för [e-postflöde](mail-flow-insights-v2.md) eller i [instrumentpanelen Rapporter.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="31d44-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="31d44-126">Förutom att klicka på länken Visa rapport  som är **kopplad** till insikter i den nya användare som vidarebefordrar e-postinsikter, kommer du till rapporten genom att:</span><span class="sxs-lookup"><span data-stu-id="31d44-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="31d44-127">Klicka på **länken till rapporten om vidarebefordran av** meddelanden i informationen om de nya domäner som [vidarebefordras.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="31d44-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="31d44-128">Öppna <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="31d44-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="31d44-129">Rapportvy för rapporten Om att vidarebefordra ändringar</span><span class="sxs-lookup"><span data-stu-id="31d44-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="31d44-130">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="31d44-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="31d44-131">**Visa data för: Nya vidarebefordran av användare:**</span><span class="sxs-lookup"><span data-stu-id="31d44-131">**Show data for: New forwarding users**:</span></span>

  ![Ny vy för vidarebefordran av användare i rapporten Om vidarebefordran](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="31d44-133">**Visa data för: Nya domäner för vidarebefordran:**</span><span class="sxs-lookup"><span data-stu-id="31d44-133">**Show data for: New forwarding domains**:</span></span>

  ![Ny vy för vidarebefordrade domäner i rapporten Om vidarebefordran](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="31d44-135">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="31d44-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="31d44-136">Detaljtabellvy för rapporten Om att vidarebefordra ändringar</span><span class="sxs-lookup"><span data-stu-id="31d44-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="31d44-137">Om du **klickar på Tabellen** Visa information beror den information som visas på det diagram som du visade:</span><span class="sxs-lookup"><span data-stu-id="31d44-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="31d44-138">**Visa data för: Nya vidarebefordran av användare:**</span><span class="sxs-lookup"><span data-stu-id="31d44-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="31d44-139">**Namn:** Avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="31d44-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="31d44-140">**Vidarebefordranstyp**</span><span class="sxs-lookup"><span data-stu-id="31d44-140">**Forwarding type**</span></span>
  - <span data-ttu-id="31d44-141">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="31d44-141">**Recipient address**</span></span>
  - <span data-ttu-id="31d44-142">**Information**</span><span class="sxs-lookup"><span data-stu-id="31d44-142">**Details**</span></span>
  - <span data-ttu-id="31d44-143">**Antal**</span><span class="sxs-lookup"><span data-stu-id="31d44-143">**Count**</span></span>
  - <span data-ttu-id="31d44-144">**Första vidarebefordransdatum**</span><span class="sxs-lookup"><span data-stu-id="31d44-144">**First forward date**</span></span>

- <span data-ttu-id="31d44-145">**Visa data för: Nya domäner för vidarebefordran:**</span><span class="sxs-lookup"><span data-stu-id="31d44-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="31d44-146">**Namn:** Avsändarens e-postdomän.</span><span class="sxs-lookup"><span data-stu-id="31d44-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="31d44-147">**Vidarebefordranstyp**</span><span class="sxs-lookup"><span data-stu-id="31d44-147">**Forwarding type**</span></span>
  - <span data-ttu-id="31d44-148">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="31d44-148">**Recipient address**</span></span>
  - <span data-ttu-id="31d44-149">**Information**</span><span class="sxs-lookup"><span data-stu-id="31d44-149">**Details**</span></span>
  - <span data-ttu-id="31d44-150">**Antal**</span><span class="sxs-lookup"><span data-stu-id="31d44-150">**Count**</span></span>
  - <span data-ttu-id="31d44-151">**Första vidarebefordransdatum**</span><span class="sxs-lookup"><span data-stu-id="31d44-151">**First forward date**</span></span>

<span data-ttu-id="31d44-152">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="31d44-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="31d44-153">Om du väljer en rad i tabellen visas **en** utfälltabell med följande information:</span><span class="sxs-lookup"><span data-stu-id="31d44-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="31d44-154">**Namn:** Det här är antingen avsändarens e-postadress (från Visa **data för:** vyn Nya vidarebefordran av användare) eller avsändarens e-postdomän (från Visa **data för:** vyn Nya domäner för vidarebefordran).</span><span class="sxs-lookup"><span data-stu-id="31d44-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="31d44-155">**Vidarebefordranstyp**</span><span class="sxs-lookup"><span data-stu-id="31d44-155">**Forwarding type**</span></span>
- <span data-ttu-id="31d44-156">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="31d44-156">**Recipient**</span></span>
- <span data-ttu-id="31d44-157">**Information**</span><span class="sxs-lookup"><span data-stu-id="31d44-157">**Details**</span></span>
- <span data-ttu-id="31d44-158">**Antal**</span><span class="sxs-lookup"><span data-stu-id="31d44-158">**Count**</span></span>
- <span data-ttu-id="31d44-159">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="31d44-159">**Start date**</span></span>
- <span data-ttu-id="31d44-160">**Rekommendation:** Härifrån kan du klicka på länken för att hantera användaren i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31d44-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Den utfällna informationen från detaljtabellen i vyn Nya användare för vidarebefordran i rapporten Om vidarebefordran](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="31d44-162">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="31d44-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="31d44-163">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="31d44-163">Related topics</span></span>

<span data-ttu-id="31d44-164">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="31d44-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
