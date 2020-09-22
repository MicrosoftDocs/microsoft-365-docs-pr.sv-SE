---
title: Visa rapporter för e-postflöden i instrument panelen rapporter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om vilka e-postflödes rapporter som är tillgängliga på instrument panelen för rapporter i säkerhets & efterlevnad.
ms.custom: ''
ms.openlocfilehash: d33bd62e9a06385bf3448b7744031ae030dbe3ca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195849"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="11462-103">Visa rapporter om e-postflöden i instrument panelen för säkerhet &</span><span class="sxs-lookup"><span data-stu-id="11462-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="11462-104">Utöver de e-postflödes rapporter som är tillgängliga i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i säkerhets & Compliance Center finns det flera olika e-postflödes rapporter som hjälper dig att övervaka din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="11462-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="11462-105">Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-these-reports)kan du visa dessa rapporter i [säkerhets & Compliance Center](https://office.protection.com) genom att gå till **Reports** \> **instrument panelen**för rapporter.</span><span class="sxs-lookup"><span data-stu-id="11462-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="11462-106">Öppna för att gå direkt till instrument panelen rapporter <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="11462-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrument panel för rapporter i centret för säkerhets &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="11462-108">Kopplings rapport</span><span class="sxs-lookup"><span data-stu-id="11462-108">Connector report</span></span>

<span data-ttu-id="11462-109">**Kopplings rapporten** visar aktivitet för e-postflöde i de [inkommande och utgående kopplingarna](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) som har kon figurer ATS för organisationen.</span><span class="sxs-lookup"><span data-stu-id="11462-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="11462-110">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **kopplings rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="11462-111">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="11462-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widgeten kopplings rapport i instrument panelen rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="11462-113">Rapportvy för kopplings rapporten</span><span class="sxs-lookup"><span data-stu-id="11462-113">Report view for the Connector report</span></span>

<span data-ttu-id="11462-114">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="11462-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="11462-115">**Visa data via: e-post**: det här diagrammet visar antalet inkommande och utgående meddelanden sorterade efter:</span><span class="sxs-lookup"><span data-stu-id="11462-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="11462-116">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="11462-116">**Total**</span></span>
  - <span data-ttu-id="11462-117">**Från Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="11462-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="11462-118">**Till Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="11462-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="11462-119">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="11462-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="11462-120">Om du vill isolera data i diagrammet använder du kryss rutan **Visa data för** kontroll och väljer ett av dessa alternativ eller **alla e-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="11462-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visa data efter e-postflöde i kopplings rapporten](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="11462-122">**Visa data genom: TLS-användning**: det här diagrammet visar procent av TLS-version (Transport Layer Security) för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="11462-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="11462-123">Om du vill isolera data i diagrammet använder du alternativet **Visa data för** kontroll och väljer något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="11462-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="11462-124">**Alla e-postflöden**</span><span class="sxs-lookup"><span data-stu-id="11462-124">**All mail flow**</span></span>
  - <span data-ttu-id="11462-125">**Från Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="11462-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="11462-126">**Till Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="11462-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="11462-127">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="11462-127">A specific connector that you've configured.</span></span>

  ![Visa data efter TLS-användning i kopplings rapporten](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="11462-129">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="11462-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="11462-130">Vyn detaljerad tabell för kopplings rapporten</span><span class="sxs-lookup"><span data-stu-id="11462-130">Details table view for the Connector report</span></span>

<span data-ttu-id="11462-131">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="11462-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="11462-132">**Datum**</span><span class="sxs-lookup"><span data-stu-id="11462-132">**Date**</span></span>
- <span data-ttu-id="11462-133">**Kopplingens riktning och namn**</span><span class="sxs-lookup"><span data-stu-id="11462-133">**Connector direction and name**</span></span>
- <span data-ttu-id="11462-134">**Kopplings typ**</span><span class="sxs-lookup"><span data-stu-id="11462-134">**Connector type**</span></span>
- <span data-ttu-id="11462-135">**Tvingad TLS?**: värdet **Sant** eller **falskt**.</span><span class="sxs-lookup"><span data-stu-id="11462-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="11462-136">**Inget TLS** (procent)</span><span class="sxs-lookup"><span data-stu-id="11462-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="11462-137">**TLS 1,0** (procent)</span><span class="sxs-lookup"><span data-stu-id="11462-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="11462-138">**TLS 1,1** (procent)</span><span class="sxs-lookup"><span data-stu-id="11462-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="11462-139">**TLS 1,2** (procent)</span><span class="sxs-lookup"><span data-stu-id="11462-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="11462-140">**Volym**: antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="11462-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="11462-141">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="11462-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="11462-142">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="11462-143">Rapport om Exchange-transportprovidern</span><span class="sxs-lookup"><span data-stu-id="11462-143">Exchange transport rule report</span></span>

<span data-ttu-id="11462-144">I **rapporten Exchange Transport Rule** visas resultatet av regler för e-postflöden (kallas även transport regler) i inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="11462-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="11462-145">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **Exchange Transport Rule**.</span><span class="sxs-lookup"><span data-stu-id="11462-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="11462-146">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="11462-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget för Exchange-transportläge i instrument panelen rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="11462-148">Rapportvy för rapporten om Exchange-transportprovidern</span><span class="sxs-lookup"><span data-stu-id="11462-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="11462-149">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="11462-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="11462-150">**Visa data genom att: Exchange-regler** \> **Bryt ned efter: riktning**: det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transport regler.</span><span class="sxs-lookup"><span data-stu-id="11462-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="11462-151">**Visa data genom att: Exchange-regler** \> **Bryt ned med: allvarlighets**grad: det här diagrammet visar antalet **högsta allvarlighets** **grad och mellanliggande och** **lågprioriterade** meddelanden.</span><span class="sxs-lookup"><span data-stu-id="11462-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="11462-152">Du anger allvarlighets nivån som en åtgärd i regeln (**Granska den här regeln med allvarlighets grad** eller _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="11462-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="11462-153">Mer information finns i [åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="11462-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="11462-154">**Visa data med: transport regler** \> för DLP Exchange **Bryt ned efter: riktning**: det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transport reglerna för data förlust skydd (DLP).</span><span class="sxs-lookup"><span data-stu-id="11462-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="11462-155">Du kan förfina diagrammet ytterligare genom att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="11462-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="11462-156">**Visa data för: alla DLP transport regler**</span><span class="sxs-lookup"><span data-stu-id="11462-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="11462-157">**Visa data för: äventyrade användare**</span><span class="sxs-lookup"><span data-stu-id="11462-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="11462-158">**Visa data för: den billiga Patriot Act har identifierats**</span><span class="sxs-lookup"><span data-stu-id="11462-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="11462-159">**Visa data med: transport regler** \> för DLP Exchange **Bryt ned efter: riktning**: den här vyn visar antalet **högsta allvarlighets** **grad och mellanliggande och** **låg allvarlighets grad** meddelanden som påverkades av DLP transport regler.</span><span class="sxs-lookup"><span data-stu-id="11462-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="11462-160">Du kan förfina diagrammet ytterligare genom att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="11462-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="11462-161">**Visa data för: alla DLP transport regler**</span><span class="sxs-lookup"><span data-stu-id="11462-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="11462-162">**Visa data för: äventyrade användare**</span><span class="sxs-lookup"><span data-stu-id="11462-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="11462-163">**Visa data för: den billiga Patriot Act har identifierats**</span><span class="sxs-lookup"><span data-stu-id="11462-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="11462-164">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter::</span><span class="sxs-lookup"><span data-stu-id="11462-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="11462-165">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="11462-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="11462-166">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="11462-166">Direction values</span></span>
- <span data-ttu-id="11462-167">Allvarlighets värden</span><span class="sxs-lookup"><span data-stu-id="11462-167">Severity values</span></span>

![Rapportvy i rapporten om Exchange-transportprovidern](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="11462-169">Vyn detaljerad tabell för rapporten Exchange-överföring</span><span class="sxs-lookup"><span data-stu-id="11462-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="11462-170">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="11462-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="11462-171">**Visa data genom: Exchange-transportläge**:</span><span class="sxs-lookup"><span data-stu-id="11462-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="11462-172">**Datum**</span><span class="sxs-lookup"><span data-stu-id="11462-172">**Date**</span></span>
  - <span data-ttu-id="11462-173">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="11462-173">**Transport rule**</span></span>
  - <span data-ttu-id="11462-174">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="11462-174">**Subject**</span></span>
  - <span data-ttu-id="11462-175">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="11462-175">**Sender address**</span></span>
  - <span data-ttu-id="11462-176">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="11462-176">**Recipient address**</span></span>
  - <span data-ttu-id="11462-177">**Allvarlighets grad**</span><span class="sxs-lookup"><span data-stu-id="11462-177">**Severity**</span></span>
  - <span data-ttu-id="11462-178">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="11462-178">**Direction**</span></span>

- <span data-ttu-id="11462-179">**Visa data med: transport regler för DLP Exchange**:</span><span class="sxs-lookup"><span data-stu-id="11462-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="11462-180">**Datum**</span><span class="sxs-lookup"><span data-stu-id="11462-180">**Date**</span></span>
  - <span data-ttu-id="11462-181">**DLP-princip**</span><span class="sxs-lookup"><span data-stu-id="11462-181">**DLP policy**</span></span>
  - <span data-ttu-id="11462-182">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="11462-182">**Transport rule**</span></span>
  - <span data-ttu-id="11462-183">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="11462-183">**Subject**</span></span>
  - <span data-ttu-id="11462-184">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="11462-184">**Sender address**</span></span>
  - <span data-ttu-id="11462-185">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="11462-185">**Recipient address**</span></span>
  - <span data-ttu-id="11462-186">**Allvarlighets grad**</span><span class="sxs-lookup"><span data-stu-id="11462-186">**Severity**</span></span>
  - <span data-ttu-id="11462-187">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="11462-187">**Direction**</span></span>

<span data-ttu-id="11462-188">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="11462-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="11462-189">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="11462-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="11462-190">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="11462-190">Direction values</span></span>
- <span data-ttu-id="11462-191">Allvarlighets värden</span><span class="sxs-lookup"><span data-stu-id="11462-191">Severity values</span></span>

<span data-ttu-id="11462-192">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="11462-193">Vidarebefordra rapport</span><span class="sxs-lookup"><span data-stu-id="11462-193">Forwarding report</span></span>

<span data-ttu-id="11462-194">I **vidarekoppling** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="11462-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="11462-195">Vidarebefordrade meddelanden kan utgöra en säkerhets-eller efterlevnad och kan tyda på ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="11462-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="11462-196">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **vidarebefordra rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="11462-197">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="11462-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget för vidarebefordrade rapporter i instrument panelen rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="11462-199">Rapportvy för rapport för vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="11462-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="11462-200">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="11462-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="11462-201">**Visa data för: metod för vidarekoppling**: följande metoder visas:</span><span class="sxs-lookup"><span data-stu-id="11462-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="11462-202">**Transport regel**: kallas även för [regler för e-postflöde](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="11462-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="11462-203">**Post lådans regel**: kallas även för [regler för Inkorgen](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="11462-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vyn för vidarebefordran av en rapport](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="11462-205">**Visa data för: vidarebefordrande domäner**: den här vyn visar de mottagare som är destinationer för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="11462-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vyn vidarebefordra domäner i rapport för vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="11462-207">**Visa data för: vidarebefordrare**: följande vidarebefordrare visas:</span><span class="sxs-lookup"><span data-stu-id="11462-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="11462-208">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="11462-208">**Transport rule**</span></span>
  - <span data-ttu-id="11462-209">Post lådan som innehåller inkorgen för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="11462-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vyn vidarebefordrare i rapporten vidarebefordran](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="11462-211">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="11462-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="11462-212">Vyn detaljerad tabell för vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="11462-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="11462-213">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="11462-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="11462-214">**Vidarebefordrare**: värde **transport regeln** eller post lådan som innehåller regeln för vidarebefordran av Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="11462-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="11462-215">**Typ av vidarekoppling**: regeln eller **transport regeln**för värde **post lådan** .</span><span class="sxs-lookup"><span data-stu-id="11462-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="11462-216">**Mottagarens namn**</span><span class="sxs-lookup"><span data-stu-id="11462-216">**Recipient name**</span></span>
- <span data-ttu-id="11462-217">**Mottagar domän**</span><span class="sxs-lookup"><span data-stu-id="11462-217">**Recipient domain**</span></span>
- <span data-ttu-id="11462-218">**Information**: det här är värdet på ett GUID-värde för regeln för e-postflöde, eller RuleIdentity-värdet i regeln för Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="11462-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="11462-219">**Öka**</span><span class="sxs-lookup"><span data-stu-id="11462-219">**Count**</span></span>
- <span data-ttu-id="11462-220">**Första framåtriktade datum**</span><span class="sxs-lookup"><span data-stu-id="11462-220">**First forward date**</span></span>

<span data-ttu-id="11462-221">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="11462-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="11462-222">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="11462-223">Flödes status rapport</span><span class="sxs-lookup"><span data-stu-id="11462-223">Mailflow status report</span></span>

<span data-ttu-id="11462-224">**Status rapporten** för [skicka och ta emot liknar e-](#sent-and-received-email-report)postmeddelandet, med ytterligare information om e-post som tillåts eller blockeras.</span><span class="sxs-lookup"><span data-stu-id="11462-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="11462-225">Det här är den enda rapporten som innehåller information om skydd och visar hur många e-postmeddelanden som blockeras innan de tillåts i tjänsten för utvärdering genom Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="11462-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="11462-226">Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="11462-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="11462-227">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **flödes status rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="11462-228">Om du vill gå direkt till **rapporten status för e-postflöde**öppnar du <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="11462-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget för status rapport för flödes schema i instrument panelen rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="11462-230">Skriv vy för status rapporten flödes schema</span><span class="sxs-lookup"><span data-stu-id="11462-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="11462-231">När du öppnar rapporten är fliken **typ** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="11462-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="11462-232">Den här vyn innehåller som standard ett diagram och en data tabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="11462-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="11462-233">**Datum**: de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="11462-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="11462-234">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="11462-234">**Direction**:</span></span>

  - <span data-ttu-id="11462-235">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="11462-235">**Inbound**</span></span>
  - <span data-ttu-id="11462-236">**Gående**</span><span class="sxs-lookup"><span data-stu-id="11462-236">**Outbound**</span></span>
  - <span data-ttu-id="11462-237">**Inom organisationen**: det här antalet är för meddelanden inom en klient organisation, d.v.s.</span><span class="sxs-lookup"><span data-stu-id="11462-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="11462-238">avsändarens abc@domain.com skickar till mottagaren xyz@domain.com (räknas separat från **inkommande** och **utgående**)</span><span class="sxs-lookup"><span data-stu-id="11462-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="11462-239">**Skriv**:</span><span class="sxs-lookup"><span data-stu-id="11462-239">**Type**:</span></span>

  - <span data-ttu-id="11462-240">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="11462-240">**Good mail**</span></span>
  - <span data-ttu-id="11462-241">**Program**</span><span class="sxs-lookup"><span data-stu-id="11462-241">**Malware**</span></span>
  - <span data-ttu-id="11462-242">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="11462-242">**Spam**</span></span>
  - <span data-ttu-id="11462-243">**Edge Protection**</span><span class="sxs-lookup"><span data-stu-id="11462-243">**Edge protection**</span></span>
  - <span data-ttu-id="11462-244">**Regel meddelanden**</span><span class="sxs-lookup"><span data-stu-id="11462-244">**Rule messages**</span></span>
  - <span data-ttu-id="11462-245">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="11462-245">**Phishing email**</span></span>

<span data-ttu-id="11462-246">Diagrammet är ordnat efter **textvärdena** .</span><span class="sxs-lookup"><span data-stu-id="11462-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="11462-247">Du kan ändra dessa filter genom att klicka på **filter** eller genom att klicka på ett värde i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="11462-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="11462-248">Data tabellen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="11462-248">The data table contains the following information:</span></span>

- <span data-ttu-id="11462-249">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="11462-249">**Direction**</span></span>
- <span data-ttu-id="11462-250">**Typ**</span><span class="sxs-lookup"><span data-stu-id="11462-250">**Type**</span></span>
- <span data-ttu-id="11462-251">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="11462-251">**24 hours**</span></span>
- <span data-ttu-id="11462-252">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="11462-252">**3 days**</span></span>
- <span data-ttu-id="11462-253">**sju dagar**</span><span class="sxs-lookup"><span data-stu-id="11462-253">**7 days**</span></span>
- <span data-ttu-id="11462-254">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="11462-254">**15 days**</span></span>
- <span data-ttu-id="11462-255">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="11462-255">**30 days**</span></span>

<span data-ttu-id="11462-256">Om du klickar på **Välj en kategori för mer information**kan du välja bland följande värden:</span><span class="sxs-lookup"><span data-stu-id="11462-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="11462-257">**Nät fiske meddelande**: den här markeringen tar dig till [status rapporten för hotets skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="11462-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="11462-258">**Skadlig program vara i e-post**: den här markeringen tar dig till [status rapporten för hotets skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="11462-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="11462-259">**Skräp identifiering**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="11462-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="11462-260">**Edge blockera skräp post**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="11462-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="11462-261">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="11462-261">**Export**:</span></span>

<span data-ttu-id="11462-262">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="11462-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="11462-263">Om du till exempel vill exportera data i 7 dagar måste du göra 7 olika export åtgärder.</span><span class="sxs-lookup"><span data-stu-id="11462-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="11462-264">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="11462-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="11462-265">Om data för den dagen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="11462-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="11462-266">Skriv vy i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="11462-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="11462-267">Visnings läge för vyn flödes schema</span><span class="sxs-lookup"><span data-stu-id="11462-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="11462-268">Om du klickar på fliken **riktning** används samma standard filter från **typ** vyn.</span><span class="sxs-lookup"><span data-stu-id="11462-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="11462-269">Diagrammet är ordnat efter **riktnings** värden.</span><span class="sxs-lookup"><span data-stu-id="11462-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="11462-270">Du kan ändra dessa filter genom att klicka på **filter** eller genom att klicka på ett värde i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="11462-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="11462-271">Samma filter i vyn **typ** används.</span><span class="sxs-lookup"><span data-stu-id="11462-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="11462-272">Data tabellen innehåller samma information från **typen** vy.</span><span class="sxs-lookup"><span data-stu-id="11462-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="11462-273">**Välj en kategori om** du vill se fler val och beteendet är samma som i **textfältet.**</span><span class="sxs-lookup"><span data-stu-id="11462-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="11462-274">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="11462-274">**Export**:</span></span>

<span data-ttu-id="11462-275">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="11462-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="11462-276">Om du till exempel vill exportera data i 7 dagar måste du göra 7 olika export åtgärder.</span><span class="sxs-lookup"><span data-stu-id="11462-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="11462-277">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="11462-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="11462-278">Om data för den dagen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="11462-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="11462-279">Vyn riktning i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="11462-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="11462-280">Vyn tratt för status rapporten flöde</span><span class="sxs-lookup"><span data-stu-id="11462-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="11462-281">I vyn **tratt** visas hur Microsofts funktioner för skydd mot e-posthotet filtrerar inkommande och utgående e-post i organisationen.</span><span class="sxs-lookup"><span data-stu-id="11462-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="11462-282">Den innehåller detaljerad information om det totala antalet e-postmeddelanden och hur de konfigurerade hot skydds funktionerna, inklusive Edge Protection, skadlig program vara, anti-nätfiske, anti-spam och skydd mot förfalskning påverkar det här antalet.</span><span class="sxs-lookup"><span data-stu-id="11462-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="11462-283">Om du klickar på fliken **tratt** visas den här vyn som standard ett diagram och en data tabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="11462-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="11462-284">**Datum**: de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="11462-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="11462-285">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="11462-285">**Direction**:</span></span>

  - <span data-ttu-id="11462-286">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="11462-286">**Inbound**</span></span>
  - <span data-ttu-id="11462-287">**Gående**</span><span class="sxs-lookup"><span data-stu-id="11462-287">**Outbound**</span></span>
  - <span data-ttu-id="11462-288">**Inom organisationen**: det här antalet är för meddelanden som skickas inom en klient organisation. avsändare skickar abc@domain.com till mottagaren xyz@domain.com (räknas åtskilt från inkommande och utgående).</span><span class="sxs-lookup"><span data-stu-id="11462-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="11462-289">I vyn mängd och data tabell kan du se 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="11462-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="11462-290">Om du klickar på **filter**kan du filtrera både diagrammet och data tabellen.</span><span class="sxs-lookup"><span data-stu-id="11462-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="11462-291">Det här diagrammet visar antalet e-postmeddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="11462-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="11462-292">**Totalt e-postmeddelande**</span><span class="sxs-lookup"><span data-stu-id="11462-292">**Total email**</span></span>
- <span data-ttu-id="11462-293">**E-post efter Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="11462-293">**Email after edge protection**</span></span>
- <span data-ttu-id="11462-294">**E-post efter skadlig program vara, fil rykte, fil typs block**</span><span class="sxs-lookup"><span data-stu-id="11462-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="11462-295">**E-post efter anti-Phish, URL-rykte, varumärkes-och programförfalskning**</span><span class="sxs-lookup"><span data-stu-id="11462-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="11462-296">**E-post efter anti-spam, Mass utskick**</span><span class="sxs-lookup"><span data-stu-id="11462-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="11462-297">**E-post efter användare och domän-personifiering**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="11462-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="11462-298">**E-post efter fil-och URL-sprängning**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="11462-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="11462-299">**E-post identifieras som oskadlig efter efter leverans skydd (URL-adress klicka på tids skydd)**</span><span class="sxs-lookup"><span data-stu-id="11462-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="11462-300"><sup>1</sup> Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="11462-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="11462-301">Om du vill visa e-postmeddelandet filtrerat efter EOP eller ATP klickar du på värdet i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="11462-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="11462-302">Data tabellen innehåller följande information, som visas i fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="11462-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="11462-303">**Datum**</span><span class="sxs-lookup"><span data-stu-id="11462-303">**Date**</span></span>
- <span data-ttu-id="11462-304">**Totalt e-postmeddelande**</span><span class="sxs-lookup"><span data-stu-id="11462-304">**Total email**</span></span>
- <span data-ttu-id="11462-305">**Edge Protection**</span><span class="sxs-lookup"><span data-stu-id="11462-305">**Edge protection**</span></span>
- <span data-ttu-id="11462-306">**Skadlig program vara, fil rykte, fil typs block**</span><span class="sxs-lookup"><span data-stu-id="11462-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="11462-307">**Anti-Phish, URL-rykte, varumärkes-och programförfalskning**</span><span class="sxs-lookup"><span data-stu-id="11462-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="11462-308">**Skydd mot skräp post, Mass utskick**</span><span class="sxs-lookup"><span data-stu-id="11462-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="11462-309">**Användar-och domän personifiering (ATP)**</span><span class="sxs-lookup"><span data-stu-id="11462-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="11462-310">**Fil-och URL-sprängning (ATP)**</span><span class="sxs-lookup"><span data-stu-id="11462-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="11462-311">**Efter leverans skydd och ZAP (ATP) eller ZAP (EOP)**</span><span class="sxs-lookup"><span data-stu-id="11462-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="11462-312">Om du markerar en rad i data tabellen visas en uppdelning av antalet e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="11462-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="11462-313">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="11462-313">**Export**:</span></span>

<span data-ttu-id="11462-314">När du klickar på **Exportera** under **alternativ**kan du välja ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="11462-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="11462-315">**Sammanfattning (med data för de senaste 90 dagarna)**</span><span class="sxs-lookup"><span data-stu-id="11462-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="11462-316">**Uppgifter (med data för de senaste 30 dagarna)**</span><span class="sxs-lookup"><span data-stu-id="11462-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="11462-317">Under **datum**väljer du ett område och klickar sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="11462-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="11462-318">Data för de aktuella filtren exporteras till en. csv-fil.</span><span class="sxs-lookup"><span data-stu-id="11462-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="11462-319">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="11462-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="11462-320">Om data innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="11462-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="11462-321">Vyn tratt i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="11462-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="11462-322">Teknisk vy för rapporten flödes schema</span><span class="sxs-lookup"><span data-stu-id="11462-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="11462-323">**Tech-vyn** liknar vyn **tratt** och ger mer detaljerad information om de konfigurerade hot skydds funktionerna.</span><span class="sxs-lookup"><span data-stu-id="11462-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="11462-324">Från diagrammet kan du se hur meddelanden kategoriseras i olika stadier av hotets skydd.</span><span class="sxs-lookup"><span data-stu-id="11462-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="11462-325">Om du klickar på fliken **teknisk vy** innehåller den här vyn som standard ett diagram och en data tabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="11462-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="11462-326">**Datum**: de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="11462-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="11462-327">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="11462-327">**Direction**:</span></span>

  - <span data-ttu-id="11462-328">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="11462-328">**Inbound**</span></span>
  - <span data-ttu-id="11462-329">**Gående**</span><span class="sxs-lookup"><span data-stu-id="11462-329">**Outbound**</span></span>
  - <span data-ttu-id="11462-330">**Inom organisationen**: det här antalet är för meddelanden inom en klient organisation, d.v.s.</span><span class="sxs-lookup"><span data-stu-id="11462-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="11462-331">avsändarens abc@domain.com skickar till mottagaren xyz@domain.com (räknas separat från inkommande och utgående)</span><span class="sxs-lookup"><span data-stu-id="11462-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="11462-332">I vyn mängd och data tabell kan du se 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="11462-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="11462-333">Om du klickar på **filter**kan du filtrera både diagrammet och data tabellen.</span><span class="sxs-lookup"><span data-stu-id="11462-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="11462-334">I det här diagrammet visas meddelanden ordnade i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="11462-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="11462-335">**Totalt e-postmeddelande**</span><span class="sxs-lookup"><span data-stu-id="11462-335">**Total email**</span></span>
- <span data-ttu-id="11462-336">**Edge Allow, Edge filtrerat**</span><span class="sxs-lookup"><span data-stu-id="11462-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="11462-337">**Ej skadlig kod, identifiering av säkra bifogade filer (ATP), identifiering av skadlig program vara, regel block**</span><span class="sxs-lookup"><span data-stu-id="11462-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="11462-338">**Inte Phish, DMARC-fel, identifiering av obehörig person, förfalsknings avkänning, Phish-identifiering**</span><span class="sxs-lookup"><span data-stu-id="11462-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="11462-339">**Ingen identifiering med URL-sprängning, identifiering av URL-sprängor (ATP)**</span><span class="sxs-lookup"><span data-stu-id="11462-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="11462-340">**Inte skräp post, spam**</span><span class="sxs-lookup"><span data-stu-id="11462-340">**Not spam, spam**</span></span>
- <span data-ttu-id="11462-341">**Icke-skadlig e-post, identifiering av säkra länkar (ATP), ZAP**</span><span class="sxs-lookup"><span data-stu-id="11462-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="11462-342">När du hovrar över en kategori i diagrammet kan du se antalet meddelanden i den kategorin.</span><span class="sxs-lookup"><span data-stu-id="11462-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="11462-343">Data tabellen innehåller följande information, som visas i fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="11462-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="11462-344">**Datum**</span><span class="sxs-lookup"><span data-stu-id="11462-344">**Date**</span></span>
- <span data-ttu-id="11462-345">**Totalt e-postmeddelande**</span><span class="sxs-lookup"><span data-stu-id="11462-345">**Total email**</span></span>
- <span data-ttu-id="11462-346">**Filtrerad**</span><span class="sxs-lookup"><span data-stu-id="11462-346">**Edge filtered**</span></span>
- <span data-ttu-id="11462-347">**Skydd mot skadlig program vara, säkra bilagor, regel filtrerat**</span><span class="sxs-lookup"><span data-stu-id="11462-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="11462-348">**DMARC, Phish, filtrerat**</span><span class="sxs-lookup"><span data-stu-id="11462-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="11462-349">**Identifiering av URL-sprängning**</span><span class="sxs-lookup"><span data-stu-id="11462-349">**URL detonation detection**</span></span>
- <span data-ttu-id="11462-350">**Skräp post filter**</span><span class="sxs-lookup"><span data-stu-id="11462-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="11462-351">**ZAP borttagen**</span><span class="sxs-lookup"><span data-stu-id="11462-351">**ZAP removed**</span></span>
- <span data-ttu-id="11462-352">**Identifiering via säkra länkar**</span><span class="sxs-lookup"><span data-stu-id="11462-352">**Detection by safe links**</span></span>

<span data-ttu-id="11462-353">Om du markerar en rad i data tabellen visas en uppdelning av antalet e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="11462-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="11462-354">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="11462-354">**Export**:</span></span>

<span data-ttu-id="11462-355">Om du klickar på **Exportera**kan du välja ett av följande värden under **alternativ** :</span><span class="sxs-lookup"><span data-stu-id="11462-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="11462-356">**Sammanfattning (med data för de senaste 90 dagarna)**</span><span class="sxs-lookup"><span data-stu-id="11462-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="11462-357">**Uppgifter (med data för de senaste 30 dagarna)**</span><span class="sxs-lookup"><span data-stu-id="11462-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="11462-358">Under **datum**väljer du ett område och klickar sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="11462-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="11462-359">Data för de aktuella filtren exporteras till en. csv-fil.</span><span class="sxs-lookup"><span data-stu-id="11462-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="11462-360">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="11462-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="11462-361">Om data innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="11462-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="11462-362">Teknisk vy i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="11462-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="11462-363">Skicka och ta emot e-postrapport</span><span class="sxs-lookup"><span data-stu-id="11462-363">Sent and received email report</span></span>

<span data-ttu-id="11462-364">Rapporten **skickat och mottaget e-postmeddelande** är en Smart rapport som visar information om inkommande och utgående e-post, inklusive skräp identifiering, skadlig program vara och e-postmeddelanden som identifieras som "bra".</span><span class="sxs-lookup"><span data-stu-id="11462-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="11462-365">Skillnaden mellan den här rapporten och [flödet flödes status](#mailflow-status-report) är: den här rapporten innehåller inte data om meddelanden som blockeras av Edge Protection. Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="11462-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="11462-366">I den aggregerade vyn och detaljvyn för rapporten får du 90 dagar på filtreringen.</span><span class="sxs-lookup"><span data-stu-id="11462-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="11462-367">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **skickade och mottagna e-postmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="11462-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="11462-368">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="11462-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget för skicka och ta emot e-post i instrument panelen rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="11462-370">Rapportvy för rapporten för skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="11462-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="11462-371">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="11462-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="11462-372">**Bryt ned per: typ**: diagrammet visar alla tillgängliga kategorier:</span><span class="sxs-lookup"><span data-stu-id="11462-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="11462-373">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="11462-373">**Total**</span></span>
  - <span data-ttu-id="11462-374">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="11462-374">**Good mail**</span></span>
  - <span data-ttu-id="11462-375">**Skadlig program vara (antivirus program)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="11462-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="11462-376">**Skräp identifiering**</span><span class="sxs-lookup"><span data-stu-id="11462-376">**Spam detections**</span></span>
  - <span data-ttu-id="11462-377">**Regel meddelanden**</span><span class="sxs-lookup"><span data-stu-id="11462-377">**Rule messages**</span></span>
  - <span data-ttu-id="11462-378">**Avancerad skadlig program vara** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="11462-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="11462-379">När du hovrar över en dag (data punkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="11462-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Skriv vy i rapporten för skickad och mottagen e-post](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="11462-381">**Bryt ned efter: riktning**: diagrammet visar **totalt**, **inkommande**och **utgående** data.</span><span class="sxs-lookup"><span data-stu-id="11462-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="11462-382">När du hovrar över en dag (data punkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="11462-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vyn riktning i e-postrapporten för skicka och ta emot](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="11462-384">**Öka detalj nivån med** \> **Skadlig program vara (skadlig program vara)**: den här markeringen tar dig till [identifieringar av skadlig program vara i e-postrapporten](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="11462-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="11462-385">**Öka detalj nivån med** \> **Skräp identifiering)**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="11462-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="11462-386">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="11462-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="11462-387">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="11462-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="11462-388">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="11462-388">Direction values</span></span>
- <span data-ttu-id="11462-389">Ange värden</span><span class="sxs-lookup"><span data-stu-id="11462-389">Type values</span></span>

<span data-ttu-id="11462-390">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="11462-391">Vyn detaljerad tabell för den skickade och mottagna e-postrapporten</span><span class="sxs-lookup"><span data-stu-id="11462-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="11462-392">Om du klickar på **Visa informations tabell** i **Bryt ned efter: riktning** eller **Bryt ned efter: vyn riktning** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="11462-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="11462-393">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="11462-393">**Date (UTC)**</span></span>
- <span data-ttu-id="11462-394">**Typ**</span><span class="sxs-lookup"><span data-stu-id="11462-394">**Type**</span></span>
- <span data-ttu-id="11462-395">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="11462-395">**Direction**</span></span>
- <span data-ttu-id="11462-396">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="11462-396">**Message count**</span></span>

<span data-ttu-id="11462-397">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="11462-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="11462-398">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="11462-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="11462-399">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="11462-399">Direction values</span></span>
- <span data-ttu-id="11462-400">Ange värden</span><span class="sxs-lookup"><span data-stu-id="11462-400">Type values</span></span>

<span data-ttu-id="11462-401">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="11462-402">Rapporter för högsta avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="11462-402">Top senders and recipients report</span></span>

<span data-ttu-id="11462-403">Den **översta rapporten avsändare och mottagare** är ett cirkel diagram som visar dina e-postmeddelanden och mottagare.</span><span class="sxs-lookup"><span data-stu-id="11462-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="11462-404">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **de översta avsändaren och mottagarna**.</span><span class="sxs-lookup"><span data-stu-id="11462-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="11462-405">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="11462-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgeten vanliga avsändare och mottagare i instrument panelen rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="11462-407">Rapportvy för rapporten högsta avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="11462-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="11462-408">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="11462-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="11462-409">**Visa data för \> de flesta e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="11462-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="11462-410">**Visa data för \> högsta antal e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="11462-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="11462-411">**Visa data för \> mottagare av reklam**</span><span class="sxs-lookup"><span data-stu-id="11462-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="11462-412">**Visa data för \> Högsta antal mottagare av skadlig program vara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="11462-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="11462-413">**Visa data för \> Högsta antal mottagare av skadlig program vara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="11462-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="11462-414">Sammansättningen för cirkel diagrammet ändras utifrån de här valen.</span><span class="sxs-lookup"><span data-stu-id="11462-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="11462-415">När du hovrar över en sektor i cirkel diagrammet kan du se antalet meddelanden som skickats eller tagits emot.</span><span class="sxs-lookup"><span data-stu-id="11462-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="11462-416">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="11462-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkel diagram i rapportvyn i rapporten överst avsändare och mottagare](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="11462-418">Vyn detaljerad lista för rapporten överst avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="11462-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="11462-419">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="11462-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="11462-420">**Visa data för \> de flesta e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="11462-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="11462-421">**Vanligaste e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="11462-421">**Top mail senders**</span></span>
  - <span data-ttu-id="11462-422">**Öka**</span><span class="sxs-lookup"><span data-stu-id="11462-422">**Count**</span></span>

- <span data-ttu-id="11462-423">**Visa data för \> högsta antal e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="11462-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="11462-424">**Vanligaste e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="11462-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="11462-425">**Öka**</span><span class="sxs-lookup"><span data-stu-id="11462-425">**Count**</span></span>

- <span data-ttu-id="11462-426">**Visa data för \> mottagare av reklam**</span><span class="sxs-lookup"><span data-stu-id="11462-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="11462-427">**Populära skräp mottagare**</span><span class="sxs-lookup"><span data-stu-id="11462-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="11462-428">**Öka**</span><span class="sxs-lookup"><span data-stu-id="11462-428">**Count**</span></span>

- <span data-ttu-id="11462-429">**Visa data för \> Högsta antal mottagare av skadlig program vara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="11462-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="11462-430">**Högsta antal mottagare av skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="11462-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="11462-431">**Öka**</span><span class="sxs-lookup"><span data-stu-id="11462-431">**Count**</span></span>

- <span data-ttu-id="11462-432">**Visa data för \> Högsta antal mottagare av skadlig program vara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="11462-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="11462-433">**Högsta antal mottagare av skadlig program vara (ATP)**</span><span class="sxs-lookup"><span data-stu-id="11462-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="11462-434">**Öka**</span><span class="sxs-lookup"><span data-stu-id="11462-434">**Count**</span></span>

<span data-ttu-id="11462-435">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="11462-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="11462-436">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="11462-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="11462-437">Vilka behörigheter behövs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="11462-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="11462-438">Om du vill visa och använda rapporterna måste du vara medlem i den angivna roll gruppen i säkerhets & efterföljandekrav **och** i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11462-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="11462-439">I säkerhets & Compliance Center måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="11462-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="11462-440">-Organisations hantering-säkerhets administratör (du kan också göra det i [Azure Active Directory Admin Center](https://aad.portal.azure.com) -säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="11462-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="11462-441">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="11462-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="11462-442">I Exchange Online måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="11462-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="11462-443">-Organisations hantering-Visa endast organisations hantering-endast Visa-mottagare-kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="11462-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="11462-444">Mer information finns i [behörigheter i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) och [Hantera roll grupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="11462-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="11462-445">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="11462-445">Related topics</span></span>

[<span data-ttu-id="11462-446">Smarta rapporter och insikter i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="11462-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="11462-447">Insikter om e-postflöde i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="11462-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="11462-448">Visa säkerhets rapporter för e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="11462-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="11462-449">Visa rapporter för Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="11462-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
