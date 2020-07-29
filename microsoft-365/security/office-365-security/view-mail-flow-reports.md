---
title: Visa e-postflödesrapporter i Säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Läs om hur du hittar och använder säkerhetsrapporter för e-postflödet för din organisation. E-postflödesrapporter är tillgängliga i Security & Compliance Center.
ms.custom: ''
ms.openlocfilehash: e891d9373b169dc01cfd89f114e31b23e1bd8480
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434185"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="1526e-104">Visa e-postflödesrapporter i Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="1526e-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="1526e-105">Förutom de insikter om [e-postflöde](mail-flow-insights-v2.md) som är tillgängliga i Security & Compliance Center finns det också en mängd rapporter om e-postflöde som hjälper dig att övervaka din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="1526e-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="1526e-106">Om du har [de behörigheter som krävs](#what-permissions-are-needed-to-view-these-reports)kan du visa dessa rapporter i Security & Compliance Center genom att gå till <https://office.protection.com> **Reports** \> **Instrumentpanelen**för rapporter .</span><span class="sxs-lookup"><span data-stu-id="1526e-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="1526e-107">Om du vill gå direkt till instrumentpanelen för rapporter öppnar du <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="1526e-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Rapporter instrumentpanel i Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="1526e-109">Rapport över koppling</span><span class="sxs-lookup"><span data-stu-id="1526e-109">Connector report</span></span>

<span data-ttu-id="1526e-110">**Anslutningsrapporten** visar e-postflödesaktivitet på de [inkommande och utgående anslutningsappar](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) som är konfigurerade för organisationen.</span><span class="sxs-lookup"><span data-stu-id="1526e-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="1526e-111">Om du vill visa rapporten öppnar du [Säkerhets- & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** \> **Dashboard** och väljer **Anslutningsrapport**.</span><span class="sxs-lookup"><span data-stu-id="1526e-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="1526e-112">Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="1526e-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget för anslutningsrapport på instrumentpanelen Rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="1526e-114">Rapportvy för anslutningsrapporten</span><span class="sxs-lookup"><span data-stu-id="1526e-114">Report view for the Connector report</span></span>

<span data-ttu-id="1526e-115">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="1526e-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="1526e-116">**Visa data efter: E-postflöde**: Det här diagrammet visar antalet inkommande och utgående meddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="1526e-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="1526e-117">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="1526e-117">**Total**</span></span>
  - <span data-ttu-id="1526e-118">**Från internet utan kontakt**</span><span class="sxs-lookup"><span data-stu-id="1526e-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="1526e-119">**Till internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="1526e-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="1526e-120">En specifik anslutningsapp som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="1526e-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="1526e-121">Om du vill isolera data i diagrammet använder du **visa data för** kontroll för att välja ett av dessa alternativ eller Alla **e-postflöden**.</span><span class="sxs-lookup"><span data-stu-id="1526e-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visa data per e-postflöde i anslutningsrapporten](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="1526e-123">**Visa data efter: TLS-användning**: Det här diagrammet visar procentandelen av TLS-versionsanvändning (Transport Layer Security) för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="1526e-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="1526e-124">Om du vill isolera data i diagrammet använder du **visa data för** kontroll för att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1526e-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="1526e-125">**Allt e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="1526e-125">**All mail flow**</span></span>
  - <span data-ttu-id="1526e-126">**Från internet utan kontakt**</span><span class="sxs-lookup"><span data-stu-id="1526e-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="1526e-127">**Till internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="1526e-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="1526e-128">En specifik anslutningsapp som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="1526e-128">A specific connector that you've configured.</span></span>

  ![Visa data efter TLS-användning i anslutningsrapporten](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="1526e-130">Om du klickar på **Filter** i en rapportvy kan du ange ett datumintervall med **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="1526e-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="1526e-131">Tabellvy för information för anslutningsrapporten</span><span class="sxs-lookup"><span data-stu-id="1526e-131">Details table view for the Connector report</span></span>

<span data-ttu-id="1526e-132">Om du klickar på **Visa informationstabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="1526e-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="1526e-133">**Datum**</span><span class="sxs-lookup"><span data-stu-id="1526e-133">**Date**</span></span>
- <span data-ttu-id="1526e-134">**Kopplingsriktning och namn**</span><span class="sxs-lookup"><span data-stu-id="1526e-134">**Connector direction and name**</span></span>
- <span data-ttu-id="1526e-135">**Kopplingstyp**</span><span class="sxs-lookup"><span data-stu-id="1526e-135">**Connector type**</span></span>
- <span data-ttu-id="1526e-136">**Forced TLS?**: Värdet **Sant** eller **Falskt**.</span><span class="sxs-lookup"><span data-stu-id="1526e-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="1526e-137">**Ingen TLS** (procent)</span><span class="sxs-lookup"><span data-stu-id="1526e-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="1526e-138">**TLS 1.0** (procent)</span><span class="sxs-lookup"><span data-stu-id="1526e-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="1526e-139">**TLS 1.1** (procent)</span><span class="sxs-lookup"><span data-stu-id="1526e-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="1526e-140">**TLS 1,2** (procent)</span><span class="sxs-lookup"><span data-stu-id="1526e-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="1526e-141">**Volym**: Antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="1526e-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="1526e-142">Om du klickar på **Filter** i en detaljtabellvy kan du ange ett datumintervall med **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="1526e-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1526e-143">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="1526e-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="1526e-144">Rapport över regel för utbyte av transport</span><span class="sxs-lookup"><span data-stu-id="1526e-144">Exchange transport rule report</span></span>

<span data-ttu-id="1526e-145">Rapporten **Exchange-transportregel** visar effekten av regler för e-postflöde (kallas även transportregler) på inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1526e-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="1526e-146">Om du vill visa rapporten öppnar du [säkerhets- & Compliance Center](https://protection.office.com), går till **Instrumentpanelen För rapporter** och väljer Regel för Exchange \> **Dashboard** **Transport**.</span><span class="sxs-lookup"><span data-stu-id="1526e-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="1526e-147">Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="1526e-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widgeten Exchange transportregel i instrumentpanelen Rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="1526e-149">Rapportvy för rapporten Exchange transportregel</span><span class="sxs-lookup"><span data-stu-id="1526e-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="1526e-150">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="1526e-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="1526e-151">**Visa data efter: Utbyta transportregler** \> **Bryt ned efter: Riktning**: Det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transportregler.</span><span class="sxs-lookup"><span data-stu-id="1526e-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="1526e-152">**Visa data efter: Utbyta transportregler** \> **Bryt ned efter: Allvarlighetsgrad:** Det här diagrammet visar antalet meddelanden med **hög allvarlighetsgrad** och **Medel allvarlighetsgrad**och **Låg allvarlighetsgrad.**</span><span class="sxs-lookup"><span data-stu-id="1526e-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="1526e-153">Du anger allvarlighetsgraden som en åtgärd i regeln **(Granska den här regeln med allvarlighetsgrad** eller _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="1526e-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="1526e-154">Mer information finns [i Regelåtgärder för e-postflöde i Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="1526e-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="1526e-155">**Visa data efter: Transportregler för** \> DLP Exchange **Bryt ned efter: Riktning**: Det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av DLP-transportregler (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="1526e-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="1526e-156">Du kan förfina diagrammet ytterligare genom att välja följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1526e-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="1526e-157">**Visa data för: Alla DLP-transportregler**</span><span class="sxs-lookup"><span data-stu-id="1526e-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="1526e-158">**Visa data för: Komprometterade användare**</span><span class="sxs-lookup"><span data-stu-id="1526e-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="1526e-159">**Visa data för: Låg volym av innehåll upptäckt US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="1526e-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="1526e-160">**Visa data efter: Transportregler för** \> DLP Exchange **Bryt ned efter: Riktning**: I den här vyn visas antalet **meddelanden om hög allvarlighetsgrad** och **Medel allvarlighetsgrad**och **Låg allvarlighetsgrad** som påverkades av DLP-transportregler.</span><span class="sxs-lookup"><span data-stu-id="1526e-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="1526e-161">Du kan förfina diagrammet ytterligare genom att välja följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1526e-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="1526e-162">**Visa data för: Alla DLP-transportregler**</span><span class="sxs-lookup"><span data-stu-id="1526e-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="1526e-163">**Visa data för: Komprometterade användare**</span><span class="sxs-lookup"><span data-stu-id="1526e-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="1526e-164">**Visa data för: Låg volym av innehåll upptäckt US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="1526e-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="1526e-165">Om du klickar på **Filter** i en rapportvy kan du ändra resultaten med följande filter::</span><span class="sxs-lookup"><span data-stu-id="1526e-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="1526e-166">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="1526e-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="1526e-167">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="1526e-167">Direction values</span></span>
- <span data-ttu-id="1526e-168">Allvarlighetsgradvärden</span><span class="sxs-lookup"><span data-stu-id="1526e-168">Severity values</span></span>

![Rapportvy i rapporten Exchange transportregel](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="1526e-170">Tabellvy för exchange-transportregelrapporten</span><span class="sxs-lookup"><span data-stu-id="1526e-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="1526e-171">Om du klickar på **Visa informationstabell**beror informationen som visas på vilket diagram du tittade på:</span><span class="sxs-lookup"><span data-stu-id="1526e-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1526e-172">**Visa data efter: Regler för Exchange Transport:**</span><span class="sxs-lookup"><span data-stu-id="1526e-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="1526e-173">**Datum**</span><span class="sxs-lookup"><span data-stu-id="1526e-173">**Date**</span></span>
  - <span data-ttu-id="1526e-174">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="1526e-174">**Transport rule**</span></span>
  - <span data-ttu-id="1526e-175">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="1526e-175">**Subject**</span></span>
  - <span data-ttu-id="1526e-176">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="1526e-176">**Sender address**</span></span>
  - <span data-ttu-id="1526e-177">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="1526e-177">**Recipient address**</span></span>
  - <span data-ttu-id="1526e-178">**Svårighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="1526e-178">**Severity**</span></span>
  - <span data-ttu-id="1526e-179">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="1526e-179">**Direction**</span></span>

- <span data-ttu-id="1526e-180">**Visa data efter: DLP Exchange transportregler:**</span><span class="sxs-lookup"><span data-stu-id="1526e-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="1526e-181">**Datum**</span><span class="sxs-lookup"><span data-stu-id="1526e-181">**Date**</span></span>
  - <span data-ttu-id="1526e-182">**DLP-princip**</span><span class="sxs-lookup"><span data-stu-id="1526e-182">**DLP policy**</span></span>
  - <span data-ttu-id="1526e-183">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="1526e-183">**Transport rule**</span></span>
  - <span data-ttu-id="1526e-184">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="1526e-184">**Subject**</span></span>
  - <span data-ttu-id="1526e-185">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="1526e-185">**Sender address**</span></span>
  - <span data-ttu-id="1526e-186">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="1526e-186">**Recipient address**</span></span>
  - <span data-ttu-id="1526e-187">**Svårighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="1526e-187">**Severity**</span></span>
  - <span data-ttu-id="1526e-188">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="1526e-188">**Direction**</span></span>

<span data-ttu-id="1526e-189">Om du klickar på **Filter** i en detaljtabellvy kan du ändra resultaten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="1526e-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1526e-190">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="1526e-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="1526e-191">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="1526e-191">Direction values</span></span>
- <span data-ttu-id="1526e-192">Allvarlighetsgradvärden</span><span class="sxs-lookup"><span data-stu-id="1526e-192">Severity values</span></span>

<span data-ttu-id="1526e-193">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="1526e-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="1526e-194">Vidarebefordran av rapport</span><span class="sxs-lookup"><span data-stu-id="1526e-194">Forwarding report</span></span>

<span data-ttu-id="1526e-195">I **rapporten Vidarebefordran** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="1526e-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="1526e-196">Vidarebefordrade meddelanden kan utgöra en säkerhets- eller efterlevnadsrisk och kan tyda på ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="1526e-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="1526e-197">Om du vill visa rapporten öppnar du [säkerhets- & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** \> **Dashboard** och väljer **Vidarebefordran**.</span><span class="sxs-lookup"><span data-stu-id="1526e-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="1526e-198">Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="1526e-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widgeten Vidarebefordra rapport i instrumentpanelen Rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="1526e-200">Rapportvy för rapporten Vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="1526e-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="1526e-201">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="1526e-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="1526e-202">**Visa data för: Vidarebefordran:** Följande metoder visas:</span><span class="sxs-lookup"><span data-stu-id="1526e-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="1526e-203">**Transportregel**: Kallas även [regler för e-postflöde](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="1526e-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="1526e-204">**Postlåderegel**: Kallas även [inkorgsregler](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="1526e-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vyn Vidarebefordran av vidarebefordran i rapporten Vidarebefordran](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="1526e-206">**Visa data för: Vidarebefordringsdomäner**: I den här vyn visas de mottagardomäner som är mål för vidarebefordring.</span><span class="sxs-lookup"><span data-stu-id="1526e-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vyn Vidarebefordran av domäner i rapporten Vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="1526e-208">**Visa data för: Vidarebefordrare**: Följande vidarebefordrare visas:</span><span class="sxs-lookup"><span data-stu-id="1526e-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="1526e-209">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="1526e-209">**Transport rule**</span></span>
  - <span data-ttu-id="1526e-210">Postlådan som innehåller inkorgsregeln för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="1526e-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vidarebefordrare syn i rapporten Vidarebefordran](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="1526e-212">Om du klickar på **Filter** i en rapportvy kan du ange ett datumintervall med **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="1526e-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="1526e-213">Tabellvy för information för rapporten Vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="1526e-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="1526e-214">Om du klickar på **Visa informationstabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="1526e-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="1526e-215">**Vidarebefordrare**: Värdet **Transportregel eller** postlådan som innehåller inkorgsregeln för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="1526e-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="1526e-216">**Vidarebefordringstyp**: Värdet **Postlåderegel** eller **Transportregel**.</span><span class="sxs-lookup"><span data-stu-id="1526e-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="1526e-217">**Mottagarens namn**</span><span class="sxs-lookup"><span data-stu-id="1526e-217">**Recipient name**</span></span>
- <span data-ttu-id="1526e-218">**Mottagardomän**</span><span class="sxs-lookup"><span data-stu-id="1526e-218">**Recipient domain**</span></span>
- <span data-ttu-id="1526e-219">**Information**: Det här är GUID-värdet för e-postflödesregeln eller värdet RuleIdentity för inkorgsregeln.</span><span class="sxs-lookup"><span data-stu-id="1526e-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="1526e-220">**Räkna**</span><span class="sxs-lookup"><span data-stu-id="1526e-220">**Count**</span></span>
- <span data-ttu-id="1526e-221">**Första terminsdatum**</span><span class="sxs-lookup"><span data-stu-id="1526e-221">**First forward date**</span></span>

<span data-ttu-id="1526e-222">Om du klickar på **Filter** i en detaljtabellvy kan du ange ett datumintervall med **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="1526e-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1526e-223">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="1526e-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="1526e-224">Statusrapport för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="1526e-224">Mailflow status report</span></span>

<span data-ttu-id="1526e-225">**Statusrapporten För e-postflöde** liknar [rapporten Skickat och mottaget e-post](#sent-and-received-email-report), med ytterligare information om e-post tillåten eller blockerad på kanten.</span><span class="sxs-lookup"><span data-stu-id="1526e-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="1526e-226">Detta är den enda rapporten som innehåller information om kantskydd och visar hur mycket e-post som blockeras innan den tillåts komma in i tjänsten för utvärdering av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="1526e-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="1526e-227">Om du vill visa rapporten öppnar du [säkerhets- & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen För** \> **rapporter** och väljer **statusrapport för E-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="1526e-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="1526e-228">Om du vill gå direkt till **statusrapporten För e-postflöde**öppnar du <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="1526e-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widgeten Statusrapport för e-postflöde i instrumentpanelen Rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="1526e-230">Textvy för statusrapporten för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="1526e-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="1526e-231">När du öppnar rapporten markeras fliken **Typ** som standard.</span><span class="sxs-lookup"><span data-stu-id="1526e-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="1526e-232">Som standard innehåller den här vyn ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="1526e-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="1526e-233">**Datum**: De senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="1526e-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="1526e-234">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="1526e-234">**Direction**:</span></span>

  - <span data-ttu-id="1526e-235">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="1526e-235">**Inbound**</span></span>
  - <span data-ttu-id="1526e-236">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="1526e-236">**Outbound**</span></span>
  - <span data-ttu-id="1526e-237">**Intra-org** (räknas separat från **inkommande** och **utgående)**</span><span class="sxs-lookup"><span data-stu-id="1526e-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="1526e-238">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="1526e-238">**Type**:</span></span>

  - <span data-ttu-id="1526e-239">**Bra post**</span><span class="sxs-lookup"><span data-stu-id="1526e-239">**Good mail**</span></span>
  - <span data-ttu-id="1526e-240">**Malware**</span><span class="sxs-lookup"><span data-stu-id="1526e-240">**Malware**</span></span>
  - <span data-ttu-id="1526e-241">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="1526e-241">**Spam**</span></span>
  - <span data-ttu-id="1526e-242">**Kantskydd**</span><span class="sxs-lookup"><span data-stu-id="1526e-242">**Edge protection**</span></span>
  - <span data-ttu-id="1526e-243">**Regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="1526e-243">**Rule messages**</span></span>
  - <span data-ttu-id="1526e-244">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="1526e-244">**Phishing email**</span></span>

<span data-ttu-id="1526e-245">Diagrammet ordnas efter **Type** typvärdena.</span><span class="sxs-lookup"><span data-stu-id="1526e-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="1526e-246">Du kan ändra filtren genom att klicka på **Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="1526e-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="1526e-247">Datatabellen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="1526e-247">The data table contains the following information:</span></span>

- <span data-ttu-id="1526e-248">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="1526e-248">**Direction**</span></span>
- <span data-ttu-id="1526e-249">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1526e-249">**Type**</span></span>
- <span data-ttu-id="1526e-250">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="1526e-250">**24 hours**</span></span>
- <span data-ttu-id="1526e-251">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="1526e-251">**3 days**</span></span>
- <span data-ttu-id="1526e-252">**7 dagar**</span><span class="sxs-lookup"><span data-stu-id="1526e-252">**7 days**</span></span>
- <span data-ttu-id="1526e-253">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="1526e-253">**15 days**</span></span>
- <span data-ttu-id="1526e-254">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="1526e-254">**30 days**</span></span>

<span data-ttu-id="1526e-255">Om du klickar på **Välj en kategori för mer information**kan du välja mellan följande värden:</span><span class="sxs-lookup"><span data-stu-id="1526e-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="1526e-256">**Nätfiske e-post:** Det här valet tar dig till [rapporten Hotskydd status](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="1526e-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="1526e-257">**Skadlig kod i e-post:** Det här valet tar dig till [rapporten hotskyddsstatus](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="1526e-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="1526e-258">**Spam upptäckter:** Det här valet tar dig till [rapporten Skräppostidentifieringar](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="1526e-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="1526e-259">**Edge blockerad spam:** Det här valet tar dig till [rapporten Skräppostidentifieringar.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="1526e-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="1526e-260">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="1526e-260">**Export**:</span></span>

<span data-ttu-id="1526e-261">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="1526e-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="1526e-262">Så, om du vill exportera data i 7 dagar, måste du göra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="1526e-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="1526e-263">Varje exporterad CSV-fil är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="1526e-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="1526e-264">Om data för den dagen innehåller mer än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="1526e-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="1526e-265">Textvy i statusrapporten för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="1526e-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="1526e-266">Riktningsvy för statusrapporten för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="1526e-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="1526e-267">Om du klickar på fliken **Riktning** används samma standardfilter från **vyn Typ.**</span><span class="sxs-lookup"><span data-stu-id="1526e-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="1526e-268">Diagrammet är ordnat efter **riktningsvärden.**</span><span class="sxs-lookup"><span data-stu-id="1526e-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="1526e-269">Du kan ändra filtren genom att klicka på **Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="1526e-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="1526e-270">Samma filter från **vyn Typ** används.</span><span class="sxs-lookup"><span data-stu-id="1526e-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="1526e-271">Datatabellen innehåller samma information från **vyn Typ.**</span><span class="sxs-lookup"><span data-stu-id="1526e-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="1526e-272">Välj **en kategori för mer information** tillgängliga val och beteende är desamma som **vyn Typ.**</span><span class="sxs-lookup"><span data-stu-id="1526e-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="1526e-273">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="1526e-273">**Export**:</span></span>

<span data-ttu-id="1526e-274">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="1526e-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="1526e-275">Så, om du vill exportera data i 7 dagar, måste du göra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="1526e-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="1526e-276">Varje exporterad CSV-fil är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="1526e-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="1526e-277">Om data för den dagen innehåller mer än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="1526e-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="1526e-278">Riktningsvy i statusrapporten För e-postflöde</span><span class="sxs-lookup"><span data-stu-id="1526e-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="1526e-279">Skickad och mottagen e-postrapport</span><span class="sxs-lookup"><span data-stu-id="1526e-279">Sent and received email report</span></span>

<span data-ttu-id="1526e-280">Rapporten **Skickat och mottagna e-postmeddelanden** är en smart rapport som visar information om inkommande och utgående e-post, inklusive skräppostidentifieringar, skadlig kod och e-post som identifierats som "bra".</span><span class="sxs-lookup"><span data-stu-id="1526e-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="1526e-281">Skillnaden mellan den här rapporten och [statusrapporten för Mailflow](#mailflow-status-report) är: den här rapporten innehåller inte data om meddelanden som blockerats av kantskydd.</span><span class="sxs-lookup"><span data-stu-id="1526e-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="1526e-282">Den samlade vyn och detaljvyn i rapporten tillåter 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="1526e-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="1526e-283">Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer Skickat och \> **Dashboard** **mottaget e-postmeddelande**.</span><span class="sxs-lookup"><span data-stu-id="1526e-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="1526e-284">Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="1526e-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widgeten Skickade och mottagna e-postmeddelanden i instrumentpanelen Rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="1526e-286">Rapportvy för rapporten Skickat och mottaget e-post</span><span class="sxs-lookup"><span data-stu-id="1526e-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="1526e-287">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="1526e-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="1526e-288">**Bryt ned efter: Skriv:** Diagrammet visar alla tillgängliga kategorier:</span><span class="sxs-lookup"><span data-stu-id="1526e-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="1526e-289">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="1526e-289">**Total**</span></span>
  - <span data-ttu-id="1526e-290">**Bra post**</span><span class="sxs-lookup"><span data-stu-id="1526e-290">**Good mail**</span></span>
  - <span data-ttu-id="1526e-291">**Skadlig kod (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="1526e-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="1526e-292">**Identifiering av skräppost**</span><span class="sxs-lookup"><span data-stu-id="1526e-292">**Spam detections**</span></span>
  - <span data-ttu-id="1526e-293">**Regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="1526e-293">**Rule messages**</span></span>
  - <span data-ttu-id="1526e-294">**Avancerad skadlig kod** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="1526e-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="1526e-295">När du hovrar över en dag (datapunkt) i diagrammet kan du se information för den dagen.</span><span class="sxs-lookup"><span data-stu-id="1526e-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Skriv vy i rapporten Skickat och mottaget e-post](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="1526e-297">**Bryt ned efter: Riktning:** Diagrammet visar **Summa,** **Inkommande**och **Utgående** data.</span><span class="sxs-lookup"><span data-stu-id="1526e-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="1526e-298">När du hovrar över en dag (datapunkt) i diagrammet kan du se information för den dagen.</span><span class="sxs-lookup"><span data-stu-id="1526e-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Riktningsvy i rapporten Skickat och mottaget e-post](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="1526e-300">**Öka detaljnivån efter** \> **Malware (anti-malware)**: Detta val tar dig till [Malware upptäckter i e-rapport](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="1526e-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="1526e-301">**Öka detaljnivån efter** \> **Spam upptäckter)**: Detta val tar dig till [spam Upptäckter rapporten](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="1526e-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="1526e-302">Om du klickar på **Filter** i en rapportvy kan du ändra resultaten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="1526e-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1526e-303">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="1526e-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="1526e-304">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="1526e-304">Direction values</span></span>
- <span data-ttu-id="1526e-305">Typvärden</span><span class="sxs-lookup"><span data-stu-id="1526e-305">Type values</span></span>

<span data-ttu-id="1526e-306">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="1526e-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="1526e-307">Informationstabellvy för rapporten Skickat och mottaget e-post</span><span class="sxs-lookup"><span data-stu-id="1526e-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="1526e-308">Om du klickar på **Visa informationstabell** i tabellen **Dela upp efter: Riktning** eller **Bryt ned efter: Riktningsvyn** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="1526e-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="1526e-309">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="1526e-309">**Date (UTC)**</span></span>
- <span data-ttu-id="1526e-310">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1526e-310">**Type**</span></span>
- <span data-ttu-id="1526e-311">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="1526e-311">**Direction**</span></span>
- <span data-ttu-id="1526e-312">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="1526e-312">**Message count**</span></span>

<span data-ttu-id="1526e-313">Om du klickar på **Filter** i en detaljtabellvy kan du ändra resultaten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="1526e-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1526e-314">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="1526e-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="1526e-315">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="1526e-315">Direction values</span></span>
- <span data-ttu-id="1526e-316">Typvärden</span><span class="sxs-lookup"><span data-stu-id="1526e-316">Type values</span></span>

<span data-ttu-id="1526e-317">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="1526e-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="1526e-318">Topprapport för avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="1526e-318">Top senders and recipients report</span></span>

<span data-ttu-id="1526e-319">Rapporten **Toppavsändare och mottagare** är ett cirkeldiagram som visar dina främsta e-postavsändare och -mottagare.</span><span class="sxs-lookup"><span data-stu-id="1526e-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="1526e-320">Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer \> **Dashboard** **Toppavsändare och mottagare**.</span><span class="sxs-lookup"><span data-stu-id="1526e-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="1526e-321">Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="1526e-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgeten Främsta avsändare och mottagare i instrumentpanelen Rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="1526e-323">Rapportvy för rapporten Överkant och mottagarrapport</span><span class="sxs-lookup"><span data-stu-id="1526e-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="1526e-324">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="1526e-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="1526e-325">**Visa data för avsändare av \> topputskick av e-post**</span><span class="sxs-lookup"><span data-stu-id="1526e-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="1526e-326">**Visa data för \> toppmottagare för e-post**</span><span class="sxs-lookup"><span data-stu-id="1526e-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="1526e-327">**Visa data för \> de bästa skräppostmottagarna**</span><span class="sxs-lookup"><span data-stu-id="1526e-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="1526e-328">**Visa data för \> Toppmottagare för skadlig kod** (EOP)</span><span class="sxs-lookup"><span data-stu-id="1526e-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="1526e-329">**Visa data för \> Mottagare av skadlig programvara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="1526e-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="1526e-330">Cirkeldiagrammets sammansättning ändras baserat på dessa markeringar.</span><span class="sxs-lookup"><span data-stu-id="1526e-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="1526e-331">När du hovrar över en kil i cirkeldiagrammet kan du se ett antal meddelanden som skickas eller tas emot.</span><span class="sxs-lookup"><span data-stu-id="1526e-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="1526e-332">Om du klickar på **Filter** i en rapportvy kan du ange ett datumintervall med **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="1526e-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram i rapportvyn i rapporten Överst avsändare och mottagare](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="1526e-334">Informationstabellvy för den översta avsändare och mottagarrapporten</span><span class="sxs-lookup"><span data-stu-id="1526e-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="1526e-335">Om du klickar på **Visa informationstabell**beror informationen som visas på vilket diagram du tittade på:</span><span class="sxs-lookup"><span data-stu-id="1526e-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1526e-336">**Visa data för avsändare av \> topputskick av e-post**</span><span class="sxs-lookup"><span data-stu-id="1526e-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="1526e-337">**Avsändare av bästa e-post**</span><span class="sxs-lookup"><span data-stu-id="1526e-337">**Top mail senders**</span></span>
  - <span data-ttu-id="1526e-338">**Räkna**</span><span class="sxs-lookup"><span data-stu-id="1526e-338">**Count**</span></span>

- <span data-ttu-id="1526e-339">**Visa data för \> toppmottagare för e-post**</span><span class="sxs-lookup"><span data-stu-id="1526e-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="1526e-340">**Toppmottagare för e-post**</span><span class="sxs-lookup"><span data-stu-id="1526e-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="1526e-341">**Räkna**</span><span class="sxs-lookup"><span data-stu-id="1526e-341">**Count**</span></span>

- <span data-ttu-id="1526e-342">**Visa data för \> de bästa skräppostmottagarna**</span><span class="sxs-lookup"><span data-stu-id="1526e-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="1526e-343">**De vanligaste skräppostmottagarna**</span><span class="sxs-lookup"><span data-stu-id="1526e-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="1526e-344">**Räkna**</span><span class="sxs-lookup"><span data-stu-id="1526e-344">**Count**</span></span>

- <span data-ttu-id="1526e-345">**Visa data för \> Toppmottagare för skadlig kod** (EOP)</span><span class="sxs-lookup"><span data-stu-id="1526e-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="1526e-346">**De främsta mottagarna av skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="1526e-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="1526e-347">**Räkna**</span><span class="sxs-lookup"><span data-stu-id="1526e-347">**Count**</span></span>

- <span data-ttu-id="1526e-348">**Visa data för \> Mottagare av skadlig programvara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="1526e-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="1526e-349">**Top malware mottagare (ATP)**</span><span class="sxs-lookup"><span data-stu-id="1526e-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="1526e-350">**Räkna**</span><span class="sxs-lookup"><span data-stu-id="1526e-350">**Count**</span></span>

<span data-ttu-id="1526e-351">Om du klickar på **Filter** i en detaljtabellvy kan du ange ett datumintervall med **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="1526e-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1526e-352">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="1526e-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="1526e-353">Vilka behörigheter behövs för att visa dessa rapporter?</span><span class="sxs-lookup"><span data-stu-id="1526e-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="1526e-354">Om du vill visa och använda rapporterna måste du vara medlem i den angivna rollgruppen i Security & Compliance Center **och** Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1526e-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="1526e-355">I Security & Compliance Center måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="1526e-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="1526e-356">-Organisationsledning</span><span class="sxs-lookup"><span data-stu-id="1526e-356">-Organization Management</span></span>

  <span data-ttu-id="1526e-357">-Säkerhetsadministratör (du kan också göra detta i [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span><span class="sxs-lookup"><span data-stu-id="1526e-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="1526e-358">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="1526e-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="1526e-359">I Exchange Online måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="1526e-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="1526e-360">-Organisationsledning</span><span class="sxs-lookup"><span data-stu-id="1526e-360">-Organization Management</span></span>

  <span data-ttu-id="1526e-361">-Endast visa organisationshantering</span><span class="sxs-lookup"><span data-stu-id="1526e-361">-View-only Organization Management</span></span>

  <span data-ttu-id="1526e-362">-Endast visa mottagare</span><span class="sxs-lookup"><span data-stu-id="1526e-362">-View-Only Recipients</span></span>

  <span data-ttu-id="1526e-363">-Efterlevnad Management</span><span class="sxs-lookup"><span data-stu-id="1526e-363">-Compliance Management</span></span>

<span data-ttu-id="1526e-364">Mer information finns [i Behörigheter i rollgrupper för Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) och Hantera i Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="1526e-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1526e-365">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1526e-365">Related topics</span></span>

[<span data-ttu-id="1526e-366">Smarta rapporter och insikter i Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1526e-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="1526e-367">Visa säkerhetsrapporter för e-post i Säkerhets- & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1526e-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
