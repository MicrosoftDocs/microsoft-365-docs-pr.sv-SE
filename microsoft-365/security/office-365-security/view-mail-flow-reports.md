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
ms.openlocfilehash: 3db9130083565d77bb84b4b31ec63eee5cc7a7c9
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171404"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="8c0b2-103">Visa rapporter om e-postflöden i instrument panelen för säkerhet &</span><span class="sxs-lookup"><span data-stu-id="8c0b2-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="8c0b2-104">Utöver de e-postflödes rapporter som är tillgängliga i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i säkerhets & Compliance Center finns det flera olika e-postflödes rapporter som hjälper dig att övervaka din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="8c0b2-105">Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-these-reports)kan du visa dessa rapporter i [säkerhets & Compliance Center](https://office.protection.com) genom att gå till **Reports** \> **instrument panelen**för rapporter.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="8c0b2-106">Öppna för att gå direkt till instrument panelen rapporter <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrument panel för rapporter i centret för säkerhets &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="8c0b2-108">Kopplings rapport</span><span class="sxs-lookup"><span data-stu-id="8c0b2-108">Connector report</span></span>

<span data-ttu-id="8c0b2-109">**Kopplings rapporten** visar aktivitet för e-postflöde i de [inkommande och utgående kopplingarna](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) som har kon figurer ATS för organisationen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="8c0b2-110">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **kopplings rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="8c0b2-111">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widgeten kopplings rapport i instrument panelen rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="8c0b2-113">Rapportvy för kopplings rapporten</span><span class="sxs-lookup"><span data-stu-id="8c0b2-113">Report view for the Connector report</span></span>

<span data-ttu-id="8c0b2-114">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="8c0b2-115">**Visa data via: e-post**: det här diagrammet visar antalet inkommande och utgående meddelanden sorterade efter:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="8c0b2-116">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-116">**Total**</span></span>
  - <span data-ttu-id="8c0b2-117">**Från Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="8c0b2-118">**Till Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="8c0b2-119">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="8c0b2-120">Om du vill isolera data i diagrammet använder du kryss rutan **Visa data för** kontroll och väljer ett av dessa alternativ eller **alla e-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visa data efter e-postflöde i kopplings rapporten](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="8c0b2-122">**Visa data genom: TLS-användning**: det här diagrammet visar procent av TLS-version (Transport Layer Security) för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="8c0b2-123">Om du vill isolera data i diagrammet använder du alternativet **Visa data för** kontroll och väljer något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="8c0b2-124">**Alla e-postflöden**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-124">**All mail flow**</span></span>
  - <span data-ttu-id="8c0b2-125">**Från Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="8c0b2-126">**Till Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="8c0b2-127">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-127">A specific connector that you've configured.</span></span>

  ![Visa data efter TLS-användning i kopplings rapporten](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="8c0b2-129">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="8c0b2-130">Vyn detaljerad tabell för kopplings rapporten</span><span class="sxs-lookup"><span data-stu-id="8c0b2-130">Details table view for the Connector report</span></span>

<span data-ttu-id="8c0b2-131">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="8c0b2-132">**Datum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-132">**Date**</span></span>
- <span data-ttu-id="8c0b2-133">**Kopplingens riktning och namn**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-133">**Connector direction and name**</span></span>
- <span data-ttu-id="8c0b2-134">**Kopplings typ**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-134">**Connector type**</span></span>
- <span data-ttu-id="8c0b2-135">**Tvingad TLS?**: värdet **Sant** eller **falskt**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="8c0b2-136">**Inget TLS** (procent)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="8c0b2-137">**TLS 1,0** (procent)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="8c0b2-138">**TLS 1,1** (procent)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="8c0b2-139">**TLS 1,2** (procent)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="8c0b2-140">**Volym**: antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="8c0b2-141">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8c0b2-142">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="8c0b2-143">Rapport om Exchange-transportprovidern</span><span class="sxs-lookup"><span data-stu-id="8c0b2-143">Exchange transport rule report</span></span>

<span data-ttu-id="8c0b2-144">I **rapporten Exchange Transport Rule** visas resultatet av regler för e-postflöden (kallas även transport regler) i inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="8c0b2-145">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **Exchange Transport Rule**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="8c0b2-146">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget för Exchange-transportläge i instrument panelen rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="8c0b2-148">Rapportvy för rapporten om Exchange-transportprovidern</span><span class="sxs-lookup"><span data-stu-id="8c0b2-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="8c0b2-149">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="8c0b2-150">**Visa data genom att: Exchange-regler** \> **Bryt ned efter: riktning**: det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transport regler.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="8c0b2-151">**Visa data genom att: Exchange-regler** \> **Bryt ned med: allvarlighets**grad: det här diagrammet visar antalet **högsta allvarlighets** **grad och mellanliggande och** **lågprioriterade** meddelanden.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="8c0b2-152">Du anger allvarlighets nivån som en åtgärd i regeln (**Granska den här regeln med allvarlighets grad** eller _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="8c0b2-153">Mer information finns i [åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="8c0b2-154">**Visa data med: transport regler** \> för DLP Exchange **Bryt ned efter: riktning**: det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transport reglerna för data förlust skydd (DLP).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="8c0b2-155">Du kan förfina diagrammet ytterligare genom att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="8c0b2-156">**Visa data för: alla DLP transport regler**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="8c0b2-157">**Visa data för: äventyrade användare**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="8c0b2-158">**Visa data för: den billiga Patriot Act har identifierats**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="8c0b2-159">**Visa data med: transport regler** \> för DLP Exchange **Bryt ned efter: riktning**: den här vyn visar antalet **högsta allvarlighets** **grad och mellanliggande och** **låg allvarlighets grad** meddelanden som påverkades av DLP transport regler.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="8c0b2-160">Du kan förfina diagrammet ytterligare genom att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="8c0b2-161">**Visa data för: alla DLP transport regler**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="8c0b2-162">**Visa data för: äventyrade användare**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="8c0b2-163">**Visa data för: den billiga Patriot Act har identifierats**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="8c0b2-164">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter::</span><span class="sxs-lookup"><span data-stu-id="8c0b2-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="8c0b2-165">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="8c0b2-166">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="8c0b2-166">Direction values</span></span>
- <span data-ttu-id="8c0b2-167">Allvarlighets värden</span><span class="sxs-lookup"><span data-stu-id="8c0b2-167">Severity values</span></span>

![Rapportvy i rapporten om Exchange-transportprovidern](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="8c0b2-169">Vyn detaljerad tabell för rapporten Exchange-överföring</span><span class="sxs-lookup"><span data-stu-id="8c0b2-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="8c0b2-170">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="8c0b2-171">**Visa data genom: Exchange-transportläge**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="8c0b2-172">**Datum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-172">**Date**</span></span>
  - <span data-ttu-id="8c0b2-173">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-173">**Transport rule**</span></span>
  - <span data-ttu-id="8c0b2-174">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-174">**Subject**</span></span>
  - <span data-ttu-id="8c0b2-175">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-175">**Sender address**</span></span>
  - <span data-ttu-id="8c0b2-176">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-176">**Recipient address**</span></span>
  - <span data-ttu-id="8c0b2-177">**Allvarlighets grad**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-177">**Severity**</span></span>
  - <span data-ttu-id="8c0b2-178">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-178">**Direction**</span></span>

- <span data-ttu-id="8c0b2-179">**Visa data med: transport regler för DLP Exchange**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="8c0b2-180">**Datum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-180">**Date**</span></span>
  - <span data-ttu-id="8c0b2-181">**DLP-princip**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-181">**DLP policy**</span></span>
  - <span data-ttu-id="8c0b2-182">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-182">**Transport rule**</span></span>
  - <span data-ttu-id="8c0b2-183">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-183">**Subject**</span></span>
  - <span data-ttu-id="8c0b2-184">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-184">**Sender address**</span></span>
  - <span data-ttu-id="8c0b2-185">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-185">**Recipient address**</span></span>
  - <span data-ttu-id="8c0b2-186">**Allvarlighets grad**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-186">**Severity**</span></span>
  - <span data-ttu-id="8c0b2-187">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-187">**Direction**</span></span>

<span data-ttu-id="8c0b2-188">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="8c0b2-189">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="8c0b2-190">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="8c0b2-190">Direction values</span></span>
- <span data-ttu-id="8c0b2-191">Allvarlighets värden</span><span class="sxs-lookup"><span data-stu-id="8c0b2-191">Severity values</span></span>

<span data-ttu-id="8c0b2-192">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="8c0b2-193">Vidarebefordra rapport</span><span class="sxs-lookup"><span data-stu-id="8c0b2-193">Forwarding report</span></span>

<span data-ttu-id="8c0b2-194">I **vidarekoppling** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="8c0b2-195">Vidarebefordrade meddelanden kan utgöra en säkerhets-eller efterlevnad och kan tyda på ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="8c0b2-196">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **vidarebefordra rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="8c0b2-197">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget för vidarebefordrade rapporter i instrument panelen rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="8c0b2-199">Rapportvy för rapport för vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="8c0b2-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="8c0b2-200">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8c0b2-201">**Visa data för: metod för vidarekoppling**: följande metoder visas:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="8c0b2-202">**Transport regel**: kallas även för [regler för e-postflöde](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="8c0b2-203">**Post lådans regel**: kallas även för [regler för Inkorgen](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vyn för vidarebefordran av en rapport](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="8c0b2-205">**Visa data för: vidarebefordrande domäner**: den här vyn visar de mottagare som är destinationer för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vyn vidarebefordra domäner i rapport för vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="8c0b2-207">**Visa data för: vidarebefordrare**: följande vidarebefordrare visas:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="8c0b2-208">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-208">**Transport rule**</span></span>
  - <span data-ttu-id="8c0b2-209">Post lådan som innehåller inkorgen för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vyn vidarebefordrare i rapporten vidarebefordran](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="8c0b2-211">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="8c0b2-212">Vyn detaljerad tabell för vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="8c0b2-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="8c0b2-213">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="8c0b2-214">**Vidarebefordrare**: värde **transport regeln** eller post lådan som innehåller regeln för vidarebefordran av Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="8c0b2-215">**Typ av vidarekoppling**: regeln eller **transport regeln**för värde **post lådan** .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="8c0b2-216">**Mottagarens namn**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-216">**Recipient name**</span></span>
- <span data-ttu-id="8c0b2-217">**Mottagar domän**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-217">**Recipient domain**</span></span>
- <span data-ttu-id="8c0b2-218">**Information**: det här är värdet på ett GUID-värde för regeln för e-postflöde, eller RuleIdentity-värdet i regeln för Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="8c0b2-219">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-219">**Count**</span></span>
- <span data-ttu-id="8c0b2-220">**Första framåtriktade datum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-220">**First forward date**</span></span>

<span data-ttu-id="8c0b2-221">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8c0b2-222">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="8c0b2-223">Flödes status rapport</span><span class="sxs-lookup"><span data-stu-id="8c0b2-223">Mailflow status report</span></span>

<span data-ttu-id="8c0b2-224">**Status rapporten** för [skicka och ta emot liknar e-](#sent-and-received-email-report)postmeddelandet, med ytterligare information om e-post som tillåts eller blockeras.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="8c0b2-225">Det här är den enda rapporten som innehåller information om skydd och visar hur många e-postmeddelanden som blockeras innan de tillåts i tjänsten för utvärdering genom Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="8c0b2-226">Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="8c0b2-227">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **flödes status rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="8c0b2-228">Om du vill gå direkt till **rapporten status för e-postflöde**öppnar du <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget för status rapport för flödes schema i instrument panelen rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="8c0b2-230">Skriv vy för status rapporten flödes schema</span><span class="sxs-lookup"><span data-stu-id="8c0b2-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="8c0b2-231">När du öppnar rapporten är fliken **typ** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="8c0b2-232">Den här vyn innehåller som standard ett diagram och en data tabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="8c0b2-233">**Datum**: de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="8c0b2-234">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-234">**Direction**:</span></span>

  - <span data-ttu-id="8c0b2-235">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-235">**Inbound**</span></span>
  - <span data-ttu-id="8c0b2-236">**Gående**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-236">**Outbound**</span></span>
  - <span data-ttu-id="8c0b2-237">**Inom organisationen**: det här antalet är för meddelanden inom en klient organisation, d.v.s.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="8c0b2-238">avsändarens abc@domain.com skickar till mottagaren xyz@domain.com (räknas separat från **inkommande** och **utgående**)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="8c0b2-239">**Skriv**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-239">**Type**:</span></span>

  - <span data-ttu-id="8c0b2-240">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-240">**Good mail**</span></span>
  - <span data-ttu-id="8c0b2-241">**Program**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-241">**Malware**</span></span>
  - <span data-ttu-id="8c0b2-242">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-242">**Spam**</span></span>
  - <span data-ttu-id="8c0b2-243">**Edge Protection**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-243">**Edge protection**</span></span>
  - <span data-ttu-id="8c0b2-244">**Regel meddelanden**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-244">**Rule messages**</span></span>
  - <span data-ttu-id="8c0b2-245">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-245">**Phishing email**</span></span>

<span data-ttu-id="8c0b2-246">Diagrammet är ordnat efter **textvärdena** .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="8c0b2-247">Du kan ändra dessa filter genom att klicka på **filter** eller genom att klicka på ett värde i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="8c0b2-248">Data tabellen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-248">The data table contains the following information:</span></span>

- <span data-ttu-id="8c0b2-249">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-249">**Direction**</span></span>
- <span data-ttu-id="8c0b2-250">**Typ**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-250">**Type**</span></span>
- <span data-ttu-id="8c0b2-251">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-251">**24 hours**</span></span>
- <span data-ttu-id="8c0b2-252">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-252">**3 days**</span></span>
- <span data-ttu-id="8c0b2-253">**sju dagar**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-253">**7 days**</span></span>
- <span data-ttu-id="8c0b2-254">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-254">**15 days**</span></span>
- <span data-ttu-id="8c0b2-255">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-255">**30 days**</span></span>

<span data-ttu-id="8c0b2-256">Om du klickar på **Välj en kategori för mer information**kan du välja bland följande värden:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="8c0b2-257">**Nät fiske meddelande**: den här markeringen tar dig till [status rapporten för hotets skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="8c0b2-258">**Skadlig program vara i e-post**: den här markeringen tar dig till [status rapporten för hotets skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="8c0b2-259">**Skräp identifiering**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="8c0b2-260">**Edge blockera skräp post**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="8c0b2-261">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-261">**Export**:</span></span>

<span data-ttu-id="8c0b2-262">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="8c0b2-263">Om du till exempel vill exportera data i 7 dagar måste du göra 7 olika export åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="8c0b2-264">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="8c0b2-265">Om data för den dagen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="8c0b2-266">Skriv vy i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="8c0b2-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="8c0b2-267">Visnings läge för vyn flödes schema</span><span class="sxs-lookup"><span data-stu-id="8c0b2-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="8c0b2-268">Om du klickar på fliken **riktning** används samma standard filter från **typ** vyn.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="8c0b2-269">Diagrammet är ordnat efter **riktnings** värden.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="8c0b2-270">Du kan ändra dessa filter genom att klicka på **filter** eller genom att klicka på ett värde i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="8c0b2-271">Samma filter i vyn **typ** används.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="8c0b2-272">Data tabellen innehåller samma information från **typen** vy.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="8c0b2-273">**Välj en kategori om** du vill se fler val och beteendet är samma som i **textfältet.**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="8c0b2-274">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-274">**Export**:</span></span>

<span data-ttu-id="8c0b2-275">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="8c0b2-276">Om du till exempel vill exportera data i 7 dagar måste du göra 7 olika export åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="8c0b2-277">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="8c0b2-278">Om data för den dagen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="8c0b2-279">Vyn riktning i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="8c0b2-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="8c0b2-280">Vyn tratt för status rapporten flöde</span><span class="sxs-lookup"><span data-stu-id="8c0b2-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="8c0b2-281">I vyn **tratt** visas hur Microsofts funktioner för skydd mot e-posthotet filtrerar inkommande och utgående e-post i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="8c0b2-282">Den innehåller detaljerad information om det totala antalet e-postmeddelanden och hur de konfigurerade hot skydds funktionerna, inklusive Edge Protection, skadlig program vara, anti-nätfiske, anti-spam och skydd mot förfalskning påverkar det här antalet.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="8c0b2-283">Om du klickar på fliken **tratt** visas den här vyn som standard ett diagram och en data tabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="8c0b2-284">**Datum**: de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="8c0b2-285">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-285">**Direction**:</span></span>

  - <span data-ttu-id="8c0b2-286">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-286">**Inbound**</span></span>
  - <span data-ttu-id="8c0b2-287">**Gående**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-287">**Outbound**</span></span>
  - <span data-ttu-id="8c0b2-288">**Inom organisationen**: det här antalet är för meddelanden som skickas inom en klient organisation. avsändare skickar abc@domain.com till mottagaren xyz@domain.com (räknas åtskilt från inkommande och utgående).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="8c0b2-289">I vyn mängd och data tabell kan du se 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="8c0b2-290">Om du klickar på **filter**kan du filtrera både diagrammet och data tabellen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="8c0b2-291">Det här diagrammet visar antalet e-postmeddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="8c0b2-292">**Totalt e-postmeddelande**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-292">**Total email**</span></span>
- <span data-ttu-id="8c0b2-293">**E-post efter Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-293">**Email after edge protection**</span></span>
- <span data-ttu-id="8c0b2-294">**E-post efter skadlig program vara, fil rykte, fil typs block**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="8c0b2-295">**E-post efter anti-Phish, URL-rykte, varumärkes-och programförfalskning**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="8c0b2-296">**E-post efter anti-spam, Mass utskick**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="8c0b2-297">**E-post efter användare och domän-personifiering**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8c0b2-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="8c0b2-298">**E-post efter fil-och URL-sprängning**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8c0b2-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="8c0b2-299">**E-post identifieras som oskadlig efter efter leverans skydd (URL-adress klicka på tids skydd)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="8c0b2-300"><sup>1</sup> Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8c0b2-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="8c0b2-301">Om du vill visa e-postmeddelandet filtrerat efter EOP eller ATP klickar du på värdet i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="8c0b2-302">Data tabellen innehåller följande information, som visas i fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="8c0b2-303">**Datum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-303">**Date**</span></span>
- <span data-ttu-id="8c0b2-304">**Totalt e-postmeddelande**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-304">**Total email**</span></span>
- <span data-ttu-id="8c0b2-305">**Edge Protection**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-305">**Edge protection**</span></span>
- <span data-ttu-id="8c0b2-306">**Skadlig program vara, fil rykte, fil typs block**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="8c0b2-307">**Anti-Phish, URL-rykte, varumärkes-och programförfalskning**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="8c0b2-308">**Skydd mot skräp post, Mass utskick**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="8c0b2-309">**Användar-och domän personifiering (ATP)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="8c0b2-310">**Fil-och URL-sprängning (ATP)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="8c0b2-311">**Efter leverans skydd och ZAP (ATP) eller ZAP (EOP)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="8c0b2-312">Om du markerar en rad i data tabellen visas en uppdelning av antalet e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="8c0b2-313">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-313">**Export**:</span></span>

<span data-ttu-id="8c0b2-314">När du klickar på **Exportera** under **alternativ**kan du välja ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="8c0b2-315">**Sammanfattning (med data för de senaste 90 dagarna)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="8c0b2-316">**Uppgifter (med data för de senaste 30 dagarna)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="8c0b2-317">Under **datum**väljer du ett område och klickar sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="8c0b2-318">Data för de aktuella filtren exporteras till en. csv-fil.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="8c0b2-319">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="8c0b2-320">Om data innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="8c0b2-321">Vyn tratt i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="8c0b2-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="8c0b2-322">Teknisk vy för rapporten flödes schema</span><span class="sxs-lookup"><span data-stu-id="8c0b2-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="8c0b2-323">**Tech-vyn** liknar vyn **tratt** och ger mer detaljerad information om de konfigurerade hot skydds funktionerna.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="8c0b2-324">Från diagrammet kan du se hur meddelanden kategoriseras i olika stadier av hotets skydd.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="8c0b2-325">Om du klickar på fliken **teknisk vy** innehåller den här vyn som standard ett diagram och en data tabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="8c0b2-326">**Datum**: de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="8c0b2-327">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-327">**Direction**:</span></span>

  - <span data-ttu-id="8c0b2-328">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-328">**Inbound**</span></span>
  - <span data-ttu-id="8c0b2-329">**Gående**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-329">**Outbound**</span></span>
  - <span data-ttu-id="8c0b2-330">**Inom organisationen**: det här antalet är för meddelanden inom en klient organisation, d.v.s.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="8c0b2-331">avsändarens abc@domain.com skickar till mottagaren xyz@domain.com (räknas separat från inkommande och utgående)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="8c0b2-332">I vyn mängd och data tabell kan du se 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="8c0b2-333">Om du klickar på **filter**kan du filtrera både diagrammet och data tabellen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="8c0b2-334">I det här diagrammet visas meddelanden ordnade i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="8c0b2-335">**Totalt e-postmeddelande**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-335">**Total email**</span></span>
- <span data-ttu-id="8c0b2-336">**Edge Allow, Edge filtrerat**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="8c0b2-337">**Ej skadlig kod, identifiering av säkra bifogade filer (ATP), identifiering av skadlig program vara, regel block**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="8c0b2-338">**Inte Phish, DMARC-fel, identifiering av obehörig person, förfalsknings avkänning, Phish-identifiering**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="8c0b2-339">**Ingen identifiering med URL-sprängning, identifiering av URL-sprängor (ATP)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="8c0b2-340">**Inte skräp post, spam**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-340">**Not spam, spam**</span></span>
- <span data-ttu-id="8c0b2-341">**Icke-skadlig e-post, identifiering av säkra länkar (ATP), ZAP**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="8c0b2-342">När du hovrar över en kategori i diagrammet kan du se antalet meddelanden i den kategorin.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="8c0b2-343">Data tabellen innehåller följande information, som visas i fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="8c0b2-344">**Datum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-344">**Date**</span></span>
- <span data-ttu-id="8c0b2-345">**Totalt e-postmeddelande**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-345">**Total email**</span></span>
- <span data-ttu-id="8c0b2-346">**Filtrerad**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-346">**Edge filtered**</span></span>
- <span data-ttu-id="8c0b2-347">**Skydd mot skadlig program vara, säkra bilagor, regel filtrerat**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="8c0b2-348">**DMARC, Phish, filtrerat**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="8c0b2-349">**Identifiering av URL-sprängning**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-349">**URL detonation detection**</span></span>
- <span data-ttu-id="8c0b2-350">**Skräp post filter**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="8c0b2-351">**ZAP borttagen**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-351">**ZAP removed**</span></span>
- <span data-ttu-id="8c0b2-352">**Identifiering via säkra länkar**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-352">**Detection by safe links**</span></span>

<span data-ttu-id="8c0b2-353">Om du markerar en rad i data tabellen visas en uppdelning av antalet e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="8c0b2-354">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-354">**Export**:</span></span>

<span data-ttu-id="8c0b2-355">Om du klickar på **Exportera**kan du välja ett av följande värden under **alternativ** :</span><span class="sxs-lookup"><span data-stu-id="8c0b2-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="8c0b2-356">**Sammanfattning (med data för de senaste 90 dagarna)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="8c0b2-357">**Uppgifter (med data för de senaste 30 dagarna)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="8c0b2-358">Under **datum**väljer du ett område och klickar sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="8c0b2-359">Data för de aktuella filtren exporteras till en. csv-fil.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="8c0b2-360">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="8c0b2-361">Om data innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="8c0b2-362">Teknisk vy i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="8c0b2-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="8c0b2-363">Skicka och ta emot e-postrapport</span><span class="sxs-lookup"><span data-stu-id="8c0b2-363">Sent and received email report</span></span>

<span data-ttu-id="8c0b2-364">Rapporten **skickat och mottaget e-postmeddelande** är en Smart rapport som visar information om inkommande och utgående e-post, inklusive skräp identifiering, skadlig program vara och e-postmeddelanden som identifieras som "bra".</span><span class="sxs-lookup"><span data-stu-id="8c0b2-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="8c0b2-365">Skillnaden mellan den här rapporten och [flödet flödes status](#mailflow-status-report) är: den här rapporten innehåller inte data om meddelanden som blockeras av Edge Protection. Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="8c0b2-366">I den aggregerade vyn och detaljvyn för rapporten får du 90 dagar på filtreringen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="8c0b2-367">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **skickade och mottagna e-postmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="8c0b2-368">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget för skicka och ta emot e-post i instrument panelen rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="8c0b2-370">Rapportvy för rapporten för skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="8c0b2-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="8c0b2-371">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8c0b2-372">**Bryt ned per: typ**: diagrammet visar alla tillgängliga kategorier:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="8c0b2-373">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-373">**Total**</span></span>
  - <span data-ttu-id="8c0b2-374">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-374">**Good mail**</span></span>
  - <span data-ttu-id="8c0b2-375">**Skadlig program vara (antivirus program)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="8c0b2-376">**Skräp identifiering**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-376">**Spam detections**</span></span>
  - <span data-ttu-id="8c0b2-377">**Regel meddelanden**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-377">**Rule messages**</span></span>
  - <span data-ttu-id="8c0b2-378">**Avancerad skadlig program vara** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="8c0b2-379">När du hovrar över en dag (data punkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Skriv vy i rapporten för skickad och mottagen e-post](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="8c0b2-381">**Bryt ned efter: riktning**: diagrammet visar **totalt**, **inkommande**och **utgående** data.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="8c0b2-382">När du hovrar över en dag (data punkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vyn riktning i e-postrapporten för skicka och ta emot](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="8c0b2-384">**Öka detalj nivån med** \> **Skadlig program vara (skadlig program vara)**: den här markeringen tar dig till [identifieringar av skadlig program vara i e-postrapporten](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="8c0b2-385">**Öka detalj nivån med** \> **Skräp identifiering)**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="8c0b2-386">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="8c0b2-387">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="8c0b2-388">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="8c0b2-388">Direction values</span></span>
- <span data-ttu-id="8c0b2-389">Ange värden</span><span class="sxs-lookup"><span data-stu-id="8c0b2-389">Type values</span></span>

<span data-ttu-id="8c0b2-390">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="8c0b2-391">Vyn detaljerad tabell för den skickade och mottagna e-postrapporten</span><span class="sxs-lookup"><span data-stu-id="8c0b2-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="8c0b2-392">Om du klickar på **Visa informations tabell** i **Bryt ned efter: riktning** eller **Bryt ned efter: vyn riktning** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="8c0b2-393">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-393">**Date (UTC)**</span></span>
- <span data-ttu-id="8c0b2-394">**Typ**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-394">**Type**</span></span>
- <span data-ttu-id="8c0b2-395">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-395">**Direction**</span></span>
- <span data-ttu-id="8c0b2-396">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-396">**Message count**</span></span>

<span data-ttu-id="8c0b2-397">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="8c0b2-398">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="8c0b2-399">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="8c0b2-399">Direction values</span></span>
- <span data-ttu-id="8c0b2-400">Ange värden</span><span class="sxs-lookup"><span data-stu-id="8c0b2-400">Type values</span></span>

<span data-ttu-id="8c0b2-401">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="8c0b2-402">Rapporter för högsta avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="8c0b2-402">Top senders and recipients report</span></span>

<span data-ttu-id="8c0b2-403">Den **översta rapporten avsändare och mottagare** är ett cirkel diagram som visar dina e-postmeddelanden och mottagare.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="8c0b2-404">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **de översta avsändaren och mottagarna**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="8c0b2-405">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="8c0b2-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgeten vanliga avsändare och mottagare i instrument panelen rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="8c0b2-407">Rapportvy för rapporten högsta avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="8c0b2-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="8c0b2-408">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8c0b2-409">**Visa data för \> de flesta e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="8c0b2-410">**Visa data för \> högsta antal e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="8c0b2-411">**Visa data för \> mottagare av reklam**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="8c0b2-412">**Visa data för \> Högsta antal mottagare av skadlig program vara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="8c0b2-413">**Visa data för \> Högsta antal mottagare av skadlig program vara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="8c0b2-414">Sammansättningen för cirkel diagrammet ändras utifrån de här valen.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="8c0b2-415">När du hovrar över en sektor i cirkel diagrammet kan du se antalet meddelanden som skickats eller tagits emot.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="8c0b2-416">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkel diagram i rapportvyn i rapporten överst avsändare och mottagare](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="8c0b2-418">Vyn detaljerad lista för rapporten överst avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="8c0b2-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="8c0b2-419">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="8c0b2-420">**Visa data för \> de flesta e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="8c0b2-421">**Vanligaste e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-421">**Top mail senders**</span></span>
  - <span data-ttu-id="8c0b2-422">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-422">**Count**</span></span>

- <span data-ttu-id="8c0b2-423">**Visa data för \> högsta antal e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="8c0b2-424">**Vanligaste e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="8c0b2-425">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-425">**Count**</span></span>

- <span data-ttu-id="8c0b2-426">**Visa data för \> mottagare av reklam**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="8c0b2-427">**Populära skräp mottagare**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="8c0b2-428">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-428">**Count**</span></span>

- <span data-ttu-id="8c0b2-429">**Visa data för \> Högsta antal mottagare av skadlig program vara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="8c0b2-430">**Högsta antal mottagare av skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="8c0b2-431">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-431">**Count**</span></span>

- <span data-ttu-id="8c0b2-432">**Visa data för \> Högsta antal mottagare av skadlig program vara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="8c0b2-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="8c0b2-433">**Högsta antal mottagare av skadlig program vara (ATP)**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="8c0b2-434">**Öka**</span><span class="sxs-lookup"><span data-stu-id="8c0b2-434">**Count**</span></span>

<span data-ttu-id="8c0b2-435">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8c0b2-436">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="8c0b2-437">Vilka behörigheter behövs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="8c0b2-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="8c0b2-438">Om du vill visa och använda rapporterna måste du vara medlem i den angivna roll gruppen i säkerhets & efterföljandekrav **och** i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="8c0b2-439">I säkerhets & Compliance Center måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="8c0b2-440">-Organisations hantering-säkerhets administratör (du kan också göra det i [Azure Active Directory Admin Center](https://aad.portal.azure.com) -säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="8c0b2-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="8c0b2-441">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="8c0b2-442">I Exchange Online måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="8c0b2-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="8c0b2-443">-Organisations hantering-Visa endast organisations hantering-endast Visa-mottagare-kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="8c0b2-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="8c0b2-444">Mer information finns i [behörigheter i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) och [Hantera roll grupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="8c0b2-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c0b2-445">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8c0b2-445">Related topics</span></span>

[<span data-ttu-id="8c0b2-446">Smarta rapporter och insikter i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="8c0b2-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="8c0b2-447">Insikter om e-postflöde i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="8c0b2-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="8c0b2-448">Visa säkerhets rapporter för e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="8c0b2-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="8c0b2-449">Visa rapporter för Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="8c0b2-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
