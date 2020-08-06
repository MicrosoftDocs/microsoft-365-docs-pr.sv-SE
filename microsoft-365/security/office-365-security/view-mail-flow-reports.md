---
title: Visa rapporter för e-postflöden i instrument panelen rapporter
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
description: Administratörer kan läsa om vilka e-postflödes rapporter som är tillgängliga på instrument panelen för rapporter i säkerhets & efterlevnad.
ms.custom: ''
ms.openlocfilehash: 69b2c3383862860b4616d95c2a6a1bb3a525d842
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578024"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="4c51c-103">Visa rapporter om e-postflöden i instrument panelen för säkerhet &</span><span class="sxs-lookup"><span data-stu-id="4c51c-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="4c51c-104">Utöver de e-postflödes rapporter som är tillgängliga i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i säkerhets & Compliance Center finns det flera olika e-postflödes rapporter som hjälper dig att övervaka din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="4c51c-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="4c51c-105">Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-these-reports)kan du visa dessa rapporter i [säkerhets & Compliance Center](https://office.protection.com) genom att gå till **Reports** \> **instrument panelen**för rapporter.</span><span class="sxs-lookup"><span data-stu-id="4c51c-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="4c51c-106">Öppna för att gå direkt till instrument panelen rapporter <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="4c51c-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Instrument panel för rapporter i centret för säkerhets &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="4c51c-108">Kopplings rapport</span><span class="sxs-lookup"><span data-stu-id="4c51c-108">Connector report</span></span>

<span data-ttu-id="4c51c-109">**Kopplings rapporten** visar aktivitet för e-postflöde i de [inkommande och utgående kopplingarna](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) som har kon figurer ATS för organisationen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="4c51c-110">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **kopplings rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="4c51c-111">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="4c51c-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widgeten kopplings rapport i instrument panelen rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="4c51c-113">Rapportvy för kopplings rapporten</span><span class="sxs-lookup"><span data-stu-id="4c51c-113">Report view for the Connector report</span></span>

<span data-ttu-id="4c51c-114">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="4c51c-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="4c51c-115">**Visa data via: e-post**: det här diagrammet visar antalet inkommande och utgående meddelanden sorterade efter:</span><span class="sxs-lookup"><span data-stu-id="4c51c-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="4c51c-116">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="4c51c-116">**Total**</span></span>
  - <span data-ttu-id="4c51c-117">**Från Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="4c51c-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="4c51c-118">**Till Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="4c51c-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="4c51c-119">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="4c51c-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="4c51c-120">Om du vill isolera data i diagrammet använder du kryss rutan **Visa data för** kontroll och väljer ett av dessa alternativ eller **alla e-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visa data efter e-postflöde i kopplings rapporten](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="4c51c-122">**Visa data genom: TLS-användning**: det här diagrammet visar procent av TLS-version (Transport Layer Security) för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="4c51c-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="4c51c-123">Om du vill isolera data i diagrammet använder du alternativet **Visa data för** kontroll och väljer något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="4c51c-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="4c51c-124">**Alla e-postflöden**</span><span class="sxs-lookup"><span data-stu-id="4c51c-124">**All mail flow**</span></span>
  - <span data-ttu-id="4c51c-125">**Från Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="4c51c-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="4c51c-126">**Till Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="4c51c-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="4c51c-127">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="4c51c-127">A specific connector that you've configured.</span></span>

  ![Visa data efter TLS-användning i kopplings rapporten](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="4c51c-129">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="4c51c-130">Vyn detaljerad tabell för kopplings rapporten</span><span class="sxs-lookup"><span data-stu-id="4c51c-130">Details table view for the Connector report</span></span>

<span data-ttu-id="4c51c-131">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="4c51c-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="4c51c-132">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4c51c-132">**Date**</span></span>
- <span data-ttu-id="4c51c-133">**Kopplingens riktning och namn**</span><span class="sxs-lookup"><span data-stu-id="4c51c-133">**Connector direction and name**</span></span>
- <span data-ttu-id="4c51c-134">**Kopplings typ**</span><span class="sxs-lookup"><span data-stu-id="4c51c-134">**Connector type**</span></span>
- <span data-ttu-id="4c51c-135">**Tvingad TLS?**: värdet **Sant** eller **falskt**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="4c51c-136">**Inget TLS** (procent)</span><span class="sxs-lookup"><span data-stu-id="4c51c-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="4c51c-137">**TLS 1,0** (procent)</span><span class="sxs-lookup"><span data-stu-id="4c51c-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="4c51c-138">**TLS 1,1** (procent)</span><span class="sxs-lookup"><span data-stu-id="4c51c-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="4c51c-139">**TLS 1,2** (procent)</span><span class="sxs-lookup"><span data-stu-id="4c51c-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="4c51c-140">**Volym**: antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4c51c-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="4c51c-141">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4c51c-142">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="4c51c-143">Rapport om Exchange-transportprovidern</span><span class="sxs-lookup"><span data-stu-id="4c51c-143">Exchange transport rule report</span></span>

<span data-ttu-id="4c51c-144">I **rapporten Exchange Transport Rule** visas resultatet av regler för e-postflöden (kallas även transport regler) i inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="4c51c-145">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **Exchange Transport Rule**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="4c51c-146">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="4c51c-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget för Exchange-transportläge i instrument panelen rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="4c51c-148">Rapportvy för rapporten om Exchange-transportprovidern</span><span class="sxs-lookup"><span data-stu-id="4c51c-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="4c51c-149">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="4c51c-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="4c51c-150">**Visa data genom att: Exchange-regler** \> **Bryt ned efter: riktning**: det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transport regler.</span><span class="sxs-lookup"><span data-stu-id="4c51c-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="4c51c-151">**Visa data genom att: Exchange-regler** \> **Bryt ned med: allvarlighets**grad: det här diagrammet visar antalet **högsta allvarlighets** **grad och mellanliggande och** **lågprioriterade** meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4c51c-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="4c51c-152">Du anger allvarlighets nivån som en åtgärd i regeln (**Granska den här regeln med allvarlighets grad** eller _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="4c51c-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="4c51c-153">Mer information finns i [åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="4c51c-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="4c51c-154">**Visa data med: transport regler** \> för DLP Exchange **Bryt ned efter: riktning**: det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transport reglerna för data förlust skydd (DLP).</span><span class="sxs-lookup"><span data-stu-id="4c51c-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="4c51c-155">Du kan förfina diagrammet ytterligare genom att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="4c51c-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="4c51c-156">**Visa data för: alla DLP transport regler**</span><span class="sxs-lookup"><span data-stu-id="4c51c-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="4c51c-157">**Visa data för: äventyrade användare**</span><span class="sxs-lookup"><span data-stu-id="4c51c-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="4c51c-158">**Visa data för: den billiga Patriot Act har identifierats**</span><span class="sxs-lookup"><span data-stu-id="4c51c-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="4c51c-159">**Visa data med: transport regler** \> för DLP Exchange **Bryt ned efter: riktning**: den här vyn visar antalet **högsta allvarlighets** **grad och mellanliggande och** **låg allvarlighets grad** meddelanden som påverkades av DLP transport regler.</span><span class="sxs-lookup"><span data-stu-id="4c51c-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="4c51c-160">Du kan förfina diagrammet ytterligare genom att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="4c51c-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="4c51c-161">**Visa data för: alla DLP transport regler**</span><span class="sxs-lookup"><span data-stu-id="4c51c-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="4c51c-162">**Visa data för: äventyrade användare**</span><span class="sxs-lookup"><span data-stu-id="4c51c-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="4c51c-163">**Visa data för: den billiga Patriot Act har identifierats**</span><span class="sxs-lookup"><span data-stu-id="4c51c-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="4c51c-164">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter::</span><span class="sxs-lookup"><span data-stu-id="4c51c-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="4c51c-165">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4c51c-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="4c51c-166">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="4c51c-166">Direction values</span></span>
- <span data-ttu-id="4c51c-167">Allvarlighets värden</span><span class="sxs-lookup"><span data-stu-id="4c51c-167">Severity values</span></span>

![Rapportvy i rapporten om Exchange-transportprovidern](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="4c51c-169">Vyn detaljerad tabell för rapporten Exchange-överföring</span><span class="sxs-lookup"><span data-stu-id="4c51c-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="4c51c-170">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="4c51c-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="4c51c-171">**Visa data genom: Exchange-transportläge**:</span><span class="sxs-lookup"><span data-stu-id="4c51c-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="4c51c-172">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4c51c-172">**Date**</span></span>
  - <span data-ttu-id="4c51c-173">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="4c51c-173">**Transport rule**</span></span>
  - <span data-ttu-id="4c51c-174">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="4c51c-174">**Subject**</span></span>
  - <span data-ttu-id="4c51c-175">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="4c51c-175">**Sender address**</span></span>
  - <span data-ttu-id="4c51c-176">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="4c51c-176">**Recipient address**</span></span>
  - <span data-ttu-id="4c51c-177">**Allvarlighets grad**</span><span class="sxs-lookup"><span data-stu-id="4c51c-177">**Severity**</span></span>
  - <span data-ttu-id="4c51c-178">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="4c51c-178">**Direction**</span></span>

- <span data-ttu-id="4c51c-179">**Visa data med: transport regler för DLP Exchange**:</span><span class="sxs-lookup"><span data-stu-id="4c51c-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="4c51c-180">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4c51c-180">**Date**</span></span>
  - <span data-ttu-id="4c51c-181">**DLP-princip**</span><span class="sxs-lookup"><span data-stu-id="4c51c-181">**DLP policy**</span></span>
  - <span data-ttu-id="4c51c-182">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="4c51c-182">**Transport rule**</span></span>
  - <span data-ttu-id="4c51c-183">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="4c51c-183">**Subject**</span></span>
  - <span data-ttu-id="4c51c-184">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="4c51c-184">**Sender address**</span></span>
  - <span data-ttu-id="4c51c-185">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="4c51c-185">**Recipient address**</span></span>
  - <span data-ttu-id="4c51c-186">**Allvarlighets grad**</span><span class="sxs-lookup"><span data-stu-id="4c51c-186">**Severity**</span></span>
  - <span data-ttu-id="4c51c-187">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="4c51c-187">**Direction**</span></span>

<span data-ttu-id="4c51c-188">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4c51c-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4c51c-189">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4c51c-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="4c51c-190">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="4c51c-190">Direction values</span></span>
- <span data-ttu-id="4c51c-191">Allvarlighets värden</span><span class="sxs-lookup"><span data-stu-id="4c51c-191">Severity values</span></span>

<span data-ttu-id="4c51c-192">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="4c51c-193">Vidarebefordra rapport</span><span class="sxs-lookup"><span data-stu-id="4c51c-193">Forwarding report</span></span>

<span data-ttu-id="4c51c-194">I **vidarekoppling** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="4c51c-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="4c51c-195">Vidarebefordrade meddelanden kan utgöra en säkerhets-eller efterlevnad och kan tyda på ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="4c51c-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="4c51c-196">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **vidarebefordra rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="4c51c-197">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="4c51c-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget för vidarebefordrade rapporter i instrument panelen rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="4c51c-199">Rapportvy för rapport för vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="4c51c-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="4c51c-200">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="4c51c-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4c51c-201">**Visa data för: metod för vidarekoppling**: följande metoder visas:</span><span class="sxs-lookup"><span data-stu-id="4c51c-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="4c51c-202">**Transport regel**: kallas även för [regler för e-postflöde](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="4c51c-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="4c51c-203">**Post lådans regel**: kallas även för [regler för Inkorgen](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="4c51c-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vyn för vidarebefordran av en rapport](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="4c51c-205">**Visa data för: vidarebefordrande domäner**: den här vyn visar de mottagare som är destinationer för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="4c51c-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vyn vidarebefordra domäner i rapport för vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="4c51c-207">**Visa data för: vidarebefordrare**: följande vidarebefordrare visas:</span><span class="sxs-lookup"><span data-stu-id="4c51c-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="4c51c-208">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="4c51c-208">**Transport rule**</span></span>
  - <span data-ttu-id="4c51c-209">Post lådan som innehåller inkorgen för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="4c51c-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vyn vidarebefordrare i rapporten vidarebefordran](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="4c51c-211">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="4c51c-212">Vyn detaljerad tabell för vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="4c51c-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="4c51c-213">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="4c51c-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="4c51c-214">**Vidarebefordrare**: värde **transport regeln** eller post lådan som innehåller regeln för vidarebefordran av Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="4c51c-215">**Typ av vidarekoppling**: regeln eller **transport regeln**för värde **post lådan** .</span><span class="sxs-lookup"><span data-stu-id="4c51c-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="4c51c-216">**Mottagarens namn**</span><span class="sxs-lookup"><span data-stu-id="4c51c-216">**Recipient name**</span></span>
- <span data-ttu-id="4c51c-217">**Mottagar domän**</span><span class="sxs-lookup"><span data-stu-id="4c51c-217">**Recipient domain**</span></span>
- <span data-ttu-id="4c51c-218">**Information**: det här är värdet på ett GUID-värde för regeln för e-postflöde, eller RuleIdentity-värdet i regeln för Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="4c51c-219">**Öka**</span><span class="sxs-lookup"><span data-stu-id="4c51c-219">**Count**</span></span>
- <span data-ttu-id="4c51c-220">**Första framåtriktade datum**</span><span class="sxs-lookup"><span data-stu-id="4c51c-220">**First forward date**</span></span>

<span data-ttu-id="4c51c-221">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4c51c-222">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="4c51c-223">Flödes status rapport</span><span class="sxs-lookup"><span data-stu-id="4c51c-223">Mailflow status report</span></span>

<span data-ttu-id="4c51c-224">**Status rapporten** för [skicka och ta emot liknar e-](#sent-and-received-email-report)postmeddelandet, med ytterligare information om e-post som tillåts eller blockeras.</span><span class="sxs-lookup"><span data-stu-id="4c51c-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="4c51c-225">Det här är den enda rapporten som innehåller information om skydd och visar hur många e-postmeddelanden som blockeras innan de tillåts i tjänsten för utvärdering genom Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="4c51c-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="4c51c-226">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **flödes status rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-226">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="4c51c-227">Om du vill gå direkt till **rapporten status för e-postflöde**öppnar du <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="4c51c-227">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget för status rapport för flödes schema i instrument panelen rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="4c51c-229">Skriv vy för status rapporten flödes schema</span><span class="sxs-lookup"><span data-stu-id="4c51c-229">Type view for the Mailflow status report</span></span>

<span data-ttu-id="4c51c-230">När du öppnar rapporten är fliken **typ** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="4c51c-230">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="4c51c-231">Den här vyn innehåller som standard ett diagram och en data tabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4c51c-231">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="4c51c-232">**Datum**: de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="4c51c-232">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="4c51c-233">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="4c51c-233">**Direction**:</span></span>

  - <span data-ttu-id="4c51c-234">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="4c51c-234">**Inbound**</span></span>
  - <span data-ttu-id="4c51c-235">**Gående**</span><span class="sxs-lookup"><span data-stu-id="4c51c-235">**Outbound**</span></span>
  - <span data-ttu-id="4c51c-236">**Inom organisationen** (räknas separat från **inkommande** och **utgående**)</span><span class="sxs-lookup"><span data-stu-id="4c51c-236">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="4c51c-237">**Skriv**:</span><span class="sxs-lookup"><span data-stu-id="4c51c-237">**Type**:</span></span>

  - <span data-ttu-id="4c51c-238">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="4c51c-238">**Good mail**</span></span>
  - <span data-ttu-id="4c51c-239">**Program**</span><span class="sxs-lookup"><span data-stu-id="4c51c-239">**Malware**</span></span>
  - <span data-ttu-id="4c51c-240">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="4c51c-240">**Spam**</span></span>
  - <span data-ttu-id="4c51c-241">**Edge Protection**</span><span class="sxs-lookup"><span data-stu-id="4c51c-241">**Edge protection**</span></span>
  - <span data-ttu-id="4c51c-242">**Regel meddelanden**</span><span class="sxs-lookup"><span data-stu-id="4c51c-242">**Rule messages**</span></span>
  - <span data-ttu-id="4c51c-243">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="4c51c-243">**Phishing email**</span></span>

<span data-ttu-id="4c51c-244">Diagrammet är ordnat efter **textvärdena** .</span><span class="sxs-lookup"><span data-stu-id="4c51c-244">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="4c51c-245">Du kan ändra filtren genom att klicka på **filter** eller genom att klicka på ett värde i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-245">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="4c51c-246">Data tabellen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="4c51c-246">The data table contains the following information:</span></span>

- <span data-ttu-id="4c51c-247">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="4c51c-247">**Direction**</span></span>
- <span data-ttu-id="4c51c-248">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4c51c-248">**Type**</span></span>
- <span data-ttu-id="4c51c-249">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="4c51c-249">**24 hours**</span></span>
- <span data-ttu-id="4c51c-250">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="4c51c-250">**3 days**</span></span>
- <span data-ttu-id="4c51c-251">**sju dagar**</span><span class="sxs-lookup"><span data-stu-id="4c51c-251">**7 days**</span></span>
- <span data-ttu-id="4c51c-252">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="4c51c-252">**15 days**</span></span>
- <span data-ttu-id="4c51c-253">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="4c51c-253">**30 days**</span></span>

<span data-ttu-id="4c51c-254">Om du klickar på **Välj en kategori för mer information**kan du välja bland följande värden:</span><span class="sxs-lookup"><span data-stu-id="4c51c-254">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="4c51c-255">**Nät fiske meddelande**: den här markeringen tar dig till [status rapporten för hotets skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="4c51c-255">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="4c51c-256">**Skadlig program vara i e-post**: den här markeringen tar dig till [status rapporten för hotets skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="4c51c-256">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="4c51c-257">**Skräp identifiering**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="4c51c-257">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="4c51c-258">**Edge blockera skräp post**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="4c51c-258">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="4c51c-259">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="4c51c-259">**Export**:</span></span>

<span data-ttu-id="4c51c-260">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="4c51c-260">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="4c51c-261">Om du till exempel vill exportera data i 7 dagar måste du göra 7 olika export åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4c51c-261">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="4c51c-262">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="4c51c-262">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4c51c-263">Om data för den dagen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="4c51c-263">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="4c51c-264">Skriv vy i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="4c51c-264">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="4c51c-265">Visnings läge för vyn flödes schema</span><span class="sxs-lookup"><span data-stu-id="4c51c-265">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="4c51c-266">Om du klickar på fliken **riktning** används samma standard filter från **typ** vyn.</span><span class="sxs-lookup"><span data-stu-id="4c51c-266">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="4c51c-267">Diagrammet är ordnat efter **riktnings** värden.</span><span class="sxs-lookup"><span data-stu-id="4c51c-267">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="4c51c-268">Du kan ändra dessa filter genom att klicka på **filter** eller genom att klicka på ett värde i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-268">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="4c51c-269">Samma filter i vyn **typ** används.</span><span class="sxs-lookup"><span data-stu-id="4c51c-269">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="4c51c-270">Data tabellen innehåller samma information från **typen** vy.</span><span class="sxs-lookup"><span data-stu-id="4c51c-270">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="4c51c-271">**Välj en kategori om** du vill se fler val och beteendet är samma som i **textfältet.**</span><span class="sxs-lookup"><span data-stu-id="4c51c-271">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="4c51c-272">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="4c51c-272">**Export**:</span></span>

<span data-ttu-id="4c51c-273">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="4c51c-273">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="4c51c-274">Om du till exempel vill exportera data i 7 dagar måste du göra 7 olika export åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4c51c-274">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="4c51c-275">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="4c51c-275">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4c51c-276">Om data för den dagen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="4c51c-276">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="4c51c-277">Vyn riktning i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="4c51c-277">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="4c51c-278">Skicka och ta emot e-postrapport</span><span class="sxs-lookup"><span data-stu-id="4c51c-278">Sent and received email report</span></span>

<span data-ttu-id="4c51c-279">Rapporten **skickat och mottaget e-postmeddelande** är en Smart rapport som visar information om inkommande och utgående e-post, inklusive skräp identifiering, skadlig program vara och e-postmeddelanden som identifieras som "bra".</span><span class="sxs-lookup"><span data-stu-id="4c51c-279">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="4c51c-280">Skillnaden mellan den här rapporten och [flödet flödes status](#mailflow-status-report) är: den här rapporten innehåller inte data om meddelanden som blockeras av Edge Protection.</span><span class="sxs-lookup"><span data-stu-id="4c51c-280">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="4c51c-281">I den aggregerade vyn och detaljvyn för rapporten får du 90 dagar på filtreringen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-281">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="4c51c-282">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **skickade och mottagna e-postmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-282">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="4c51c-283">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="4c51c-283">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget för skicka och ta emot e-post i instrument panelen rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="4c51c-285">Rapportvy för rapporten för skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="4c51c-285">Report view for the Sent and received email report</span></span>

<span data-ttu-id="4c51c-286">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="4c51c-286">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4c51c-287">**Bryt ned per: typ**: diagrammet visar alla tillgängliga kategorier:</span><span class="sxs-lookup"><span data-stu-id="4c51c-287">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="4c51c-288">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="4c51c-288">**Total**</span></span>
  - <span data-ttu-id="4c51c-289">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="4c51c-289">**Good mail**</span></span>
  - <span data-ttu-id="4c51c-290">**Skadlig program vara (antivirus program)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="4c51c-290">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="4c51c-291">**Skräp identifiering**</span><span class="sxs-lookup"><span data-stu-id="4c51c-291">**Spam detections**</span></span>
  - <span data-ttu-id="4c51c-292">**Regel meddelanden**</span><span class="sxs-lookup"><span data-stu-id="4c51c-292">**Rule messages**</span></span>
  - <span data-ttu-id="4c51c-293">**Avancerad skadlig program vara** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="4c51c-293">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="4c51c-294">När du hovrar över en dag (data punkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-294">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Skriv vy i rapporten för skickad och mottagen e-post](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="4c51c-296">**Bryt ned efter: riktning**: diagrammet visar **totalt**, **inkommande**och **utgående** data.</span><span class="sxs-lookup"><span data-stu-id="4c51c-296">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="4c51c-297">När du hovrar över en dag (data punkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-297">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vyn riktning i e-postrapporten för skicka och ta emot](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="4c51c-299">**Öka detalj nivån med** \> **Skadlig program vara (skadlig program vara)**: den här markeringen tar dig till [identifieringar av skadlig program vara i e-postrapporten](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="4c51c-299">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="4c51c-300">**Öka detalj nivån med** \> **Skräp identifiering)**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="4c51c-300">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="4c51c-301">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4c51c-301">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4c51c-302">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4c51c-302">**Start date** and **End date**</span></span>
- <span data-ttu-id="4c51c-303">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="4c51c-303">Direction values</span></span>
- <span data-ttu-id="4c51c-304">Ange värden</span><span class="sxs-lookup"><span data-stu-id="4c51c-304">Type values</span></span>

<span data-ttu-id="4c51c-305">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-305">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="4c51c-306">Vyn detaljerad tabell för den skickade och mottagna e-postrapporten</span><span class="sxs-lookup"><span data-stu-id="4c51c-306">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="4c51c-307">Om du klickar på **Visa informations tabell** i **Bryt ned efter: riktning** eller **Bryt ned efter: vyn riktning** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="4c51c-307">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="4c51c-308">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="4c51c-308">**Date (UTC)**</span></span>
- <span data-ttu-id="4c51c-309">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4c51c-309">**Type**</span></span>
- <span data-ttu-id="4c51c-310">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="4c51c-310">**Direction**</span></span>
- <span data-ttu-id="4c51c-311">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="4c51c-311">**Message count**</span></span>

<span data-ttu-id="4c51c-312">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4c51c-312">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4c51c-313">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4c51c-313">**Start date** and **End date**</span></span>
- <span data-ttu-id="4c51c-314">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="4c51c-314">Direction values</span></span>
- <span data-ttu-id="4c51c-315">Ange värden</span><span class="sxs-lookup"><span data-stu-id="4c51c-315">Type values</span></span>

<span data-ttu-id="4c51c-316">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-316">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="4c51c-317">Rapporter för högsta avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="4c51c-317">Top senders and recipients report</span></span>

<span data-ttu-id="4c51c-318">Den **översta rapporten avsändare och mottagare** är ett cirkel diagram som visar dina e-postmeddelanden och mottagare.</span><span class="sxs-lookup"><span data-stu-id="4c51c-318">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="4c51c-319">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **de översta avsändaren och mottagarna**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-319">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="4c51c-320">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="4c51c-320">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgeten vanliga avsändare och mottagare i instrument panelen rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="4c51c-322">Rapportvy för rapporten högsta avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="4c51c-322">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="4c51c-323">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="4c51c-323">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4c51c-324">**Visa data för \> de flesta e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="4c51c-324">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="4c51c-325">**Visa data för \> högsta antal e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="4c51c-325">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="4c51c-326">**Visa data för \> mottagare av reklam**</span><span class="sxs-lookup"><span data-stu-id="4c51c-326">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="4c51c-327">**Visa data för \> Högsta antal mottagare av skadlig program vara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="4c51c-327">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="4c51c-328">**Visa data för \> Högsta antal mottagare av skadlig program vara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="4c51c-328">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="4c51c-329">Sammansättningen för cirkel diagrammet ändras utifrån de här valen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-329">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="4c51c-330">När du hovrar över en sektor i cirkel diagrammet kan du se antalet meddelanden som skickats eller tagits emot.</span><span class="sxs-lookup"><span data-stu-id="4c51c-330">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="4c51c-331">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-331">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkel diagram i rapportvyn i rapporten överst avsändare och mottagare](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="4c51c-333">Vyn detaljerad lista för rapporten överst avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="4c51c-333">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="4c51c-334">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="4c51c-334">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="4c51c-335">**Visa data för \> de flesta e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="4c51c-335">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="4c51c-336">**Vanligaste e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="4c51c-336">**Top mail senders**</span></span>
  - <span data-ttu-id="4c51c-337">**Öka**</span><span class="sxs-lookup"><span data-stu-id="4c51c-337">**Count**</span></span>

- <span data-ttu-id="4c51c-338">**Visa data för \> högsta antal e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="4c51c-338">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="4c51c-339">**Vanligaste e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="4c51c-339">**Top mail recipients**</span></span>
  - <span data-ttu-id="4c51c-340">**Öka**</span><span class="sxs-lookup"><span data-stu-id="4c51c-340">**Count**</span></span>

- <span data-ttu-id="4c51c-341">**Visa data för \> mottagare av reklam**</span><span class="sxs-lookup"><span data-stu-id="4c51c-341">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="4c51c-342">**Populära skräp mottagare**</span><span class="sxs-lookup"><span data-stu-id="4c51c-342">**Top spam recipients**</span></span>
  - <span data-ttu-id="4c51c-343">**Öka**</span><span class="sxs-lookup"><span data-stu-id="4c51c-343">**Count**</span></span>

- <span data-ttu-id="4c51c-344">**Visa data för \> Högsta antal mottagare av skadlig program vara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="4c51c-344">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="4c51c-345">**Högsta antal mottagare av skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="4c51c-345">**Top malware recipients**</span></span>
  - <span data-ttu-id="4c51c-346">**Öka**</span><span class="sxs-lookup"><span data-stu-id="4c51c-346">**Count**</span></span>

- <span data-ttu-id="4c51c-347">**Visa data för \> Högsta antal mottagare av skadlig program vara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="4c51c-347">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="4c51c-348">**Högsta antal mottagare av skadlig program vara (ATP)**</span><span class="sxs-lookup"><span data-stu-id="4c51c-348">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="4c51c-349">**Öka**</span><span class="sxs-lookup"><span data-stu-id="4c51c-349">**Count**</span></span>

<span data-ttu-id="4c51c-350">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-350">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4c51c-351">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="4c51c-351">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="4c51c-352">Vilka behörigheter behövs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="4c51c-352">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="4c51c-353">Om du vill visa och använda rapporterna måste du vara medlem i den angivna roll gruppen i säkerhets & efterföljandekrav **och** i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4c51c-353">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="4c51c-354">I säkerhets & Compliance Center måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="4c51c-354">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="4c51c-355">-Organisations hantering-säkerhets administratör (du kan också göra det i [Azure Active Directory Admin Center](https://aad.portal.azure.com) -säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="4c51c-355">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="4c51c-356">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="4c51c-356">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="4c51c-357">I Exchange Online måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="4c51c-357">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="4c51c-358">-Organisations hantering-Visa endast organisations hantering-endast Visa-mottagare-kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="4c51c-358">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="4c51c-359">Mer information finns i [behörigheter i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) och [Hantera roll grupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="4c51c-359">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c51c-360">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4c51c-360">Related topics</span></span>

[<span data-ttu-id="4c51c-361">Smarta rapporter och insikter i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="4c51c-361">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="4c51c-362">Insikter om e-postflöde i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4c51c-362">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="4c51c-363">Visa säkerhets rapporter för e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="4c51c-363">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="4c51c-364">Visa rapporter för Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="4c51c-364">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
