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
ms.openlocfilehash: acf74136fc61d38ea9aac47f36d96aa51a7b9905
ms.sourcegitcommit: 6319e73b3690b4cf1b7932f2b9f51c2c99e70eaa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2020
ms.locfileid: "46635040"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="18aa6-103">Visa rapporter om e-postflöden i instrument panelen för säkerhet &</span><span class="sxs-lookup"><span data-stu-id="18aa6-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="18aa6-104">Utöver de e-postflödes rapporter som är tillgängliga i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i säkerhets & Compliance Center finns det flera olika e-postflödes rapporter som hjälper dig att övervaka din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="18aa6-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="18aa6-105">Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-these-reports)kan du visa dessa rapporter i [säkerhets & Compliance Center](https://office.protection.com) genom att gå till **Reports** \> **instrument panelen**för rapporter.</span><span class="sxs-lookup"><span data-stu-id="18aa6-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="18aa6-106">Öppna för att gå direkt till instrument panelen rapporter <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="18aa6-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Instrument panel för rapporter i centret för säkerhets &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="18aa6-108">Kopplings rapport</span><span class="sxs-lookup"><span data-stu-id="18aa6-108">Connector report</span></span>

<span data-ttu-id="18aa6-109">**Kopplings rapporten** visar aktivitet för e-postflöde i de [inkommande och utgående kopplingarna](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) som har kon figurer ATS för organisationen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="18aa6-110">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **kopplings rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="18aa6-111">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="18aa6-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widgeten kopplings rapport i instrument panelen rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="18aa6-113">Rapportvy för kopplings rapporten</span><span class="sxs-lookup"><span data-stu-id="18aa6-113">Report view for the Connector report</span></span>

<span data-ttu-id="18aa6-114">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="18aa6-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="18aa6-115">**Visa data via: e-post**: det här diagrammet visar antalet inkommande och utgående meddelanden sorterade efter:</span><span class="sxs-lookup"><span data-stu-id="18aa6-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="18aa6-116">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="18aa6-116">**Total**</span></span>
  - <span data-ttu-id="18aa6-117">**Från Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="18aa6-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="18aa6-118">**Till Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="18aa6-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="18aa6-119">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="18aa6-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="18aa6-120">Om du vill isolera data i diagrammet använder du kryss rutan **Visa data för** kontroll och väljer ett av dessa alternativ eller **alla e-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visa data efter e-postflöde i kopplings rapporten](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="18aa6-122">**Visa data genom: TLS-användning**: det här diagrammet visar procent av TLS-version (Transport Layer Security) för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="18aa6-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="18aa6-123">Om du vill isolera data i diagrammet använder du alternativet **Visa data för** kontroll och väljer något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="18aa6-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="18aa6-124">**Alla e-postflöden**</span><span class="sxs-lookup"><span data-stu-id="18aa6-124">**All mail flow**</span></span>
  - <span data-ttu-id="18aa6-125">**Från Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="18aa6-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="18aa6-126">**Till Internet utan en koppling**</span><span class="sxs-lookup"><span data-stu-id="18aa6-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="18aa6-127">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="18aa6-127">A specific connector that you've configured.</span></span>

  ![Visa data efter TLS-användning i kopplings rapporten](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="18aa6-129">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="18aa6-130">Vyn detaljerad tabell för kopplings rapporten</span><span class="sxs-lookup"><span data-stu-id="18aa6-130">Details table view for the Connector report</span></span>

<span data-ttu-id="18aa6-131">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="18aa6-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="18aa6-132">**Datum**</span><span class="sxs-lookup"><span data-stu-id="18aa6-132">**Date**</span></span>
- <span data-ttu-id="18aa6-133">**Kopplingens riktning och namn**</span><span class="sxs-lookup"><span data-stu-id="18aa6-133">**Connector direction and name**</span></span>
- <span data-ttu-id="18aa6-134">**Kopplings typ**</span><span class="sxs-lookup"><span data-stu-id="18aa6-134">**Connector type**</span></span>
- <span data-ttu-id="18aa6-135">**Tvingad TLS?**: värdet **Sant** eller **falskt**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="18aa6-136">**Inget TLS** (procent)</span><span class="sxs-lookup"><span data-stu-id="18aa6-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="18aa6-137">**TLS 1,0** (procent)</span><span class="sxs-lookup"><span data-stu-id="18aa6-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="18aa6-138">**TLS 1,1** (procent)</span><span class="sxs-lookup"><span data-stu-id="18aa6-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="18aa6-139">**TLS 1,2** (procent)</span><span class="sxs-lookup"><span data-stu-id="18aa6-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="18aa6-140">**Volym**: antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="18aa6-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="18aa6-141">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="18aa6-142">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="18aa6-143">Rapport om Exchange-transportprovidern</span><span class="sxs-lookup"><span data-stu-id="18aa6-143">Exchange transport rule report</span></span>

<span data-ttu-id="18aa6-144">I **rapporten Exchange Transport Rule** visas resultatet av regler för e-postflöden (kallas även transport regler) i inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="18aa6-145">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **Exchange Transport Rule**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="18aa6-146">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="18aa6-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget för Exchange-transportläge i instrument panelen rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="18aa6-148">Rapportvy för rapporten om Exchange-transportprovidern</span><span class="sxs-lookup"><span data-stu-id="18aa6-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="18aa6-149">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="18aa6-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="18aa6-150">**Visa data genom att: Exchange-regler** \> **Bryt ned efter: riktning**: det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transport regler.</span><span class="sxs-lookup"><span data-stu-id="18aa6-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="18aa6-151">**Visa data genom att: Exchange-regler** \> **Bryt ned med: allvarlighets**grad: det här diagrammet visar antalet **högsta allvarlighets** **grad och mellanliggande och** **lågprioriterade** meddelanden.</span><span class="sxs-lookup"><span data-stu-id="18aa6-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="18aa6-152">Du anger allvarlighets nivån som en åtgärd i regeln (**Granska den här regeln med allvarlighets grad** eller _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="18aa6-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="18aa6-153">Mer information finns i [åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="18aa6-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="18aa6-154">**Visa data med: transport regler** \> för DLP Exchange **Bryt ned efter: riktning**: det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av transport reglerna för data förlust skydd (DLP).</span><span class="sxs-lookup"><span data-stu-id="18aa6-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="18aa6-155">Du kan förfina diagrammet ytterligare genom att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="18aa6-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="18aa6-156">**Visa data för: alla DLP transport regler**</span><span class="sxs-lookup"><span data-stu-id="18aa6-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="18aa6-157">**Visa data för: äventyrade användare**</span><span class="sxs-lookup"><span data-stu-id="18aa6-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="18aa6-158">**Visa data för: den billiga Patriot Act har identifierats**</span><span class="sxs-lookup"><span data-stu-id="18aa6-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="18aa6-159">**Visa data med: transport regler** \> för DLP Exchange **Bryt ned efter: riktning**: den här vyn visar antalet **högsta allvarlighets** **grad och mellanliggande och** **låg allvarlighets grad** meddelanden som påverkades av DLP transport regler.</span><span class="sxs-lookup"><span data-stu-id="18aa6-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="18aa6-160">Du kan förfina diagrammet ytterligare genom att välja något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="18aa6-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="18aa6-161">**Visa data för: alla DLP transport regler**</span><span class="sxs-lookup"><span data-stu-id="18aa6-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="18aa6-162">**Visa data för: äventyrade användare**</span><span class="sxs-lookup"><span data-stu-id="18aa6-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="18aa6-163">**Visa data för: den billiga Patriot Act har identifierats**</span><span class="sxs-lookup"><span data-stu-id="18aa6-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="18aa6-164">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter::</span><span class="sxs-lookup"><span data-stu-id="18aa6-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="18aa6-165">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="18aa6-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="18aa6-166">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="18aa6-166">Direction values</span></span>
- <span data-ttu-id="18aa6-167">Allvarlighets värden</span><span class="sxs-lookup"><span data-stu-id="18aa6-167">Severity values</span></span>

![Rapportvy i rapporten om Exchange-transportprovidern](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="18aa6-169">Vyn detaljerad tabell för rapporten Exchange-överföring</span><span class="sxs-lookup"><span data-stu-id="18aa6-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="18aa6-170">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="18aa6-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="18aa6-171">**Visa data genom: Exchange-transportläge**:</span><span class="sxs-lookup"><span data-stu-id="18aa6-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="18aa6-172">**Datum**</span><span class="sxs-lookup"><span data-stu-id="18aa6-172">**Date**</span></span>
  - <span data-ttu-id="18aa6-173">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="18aa6-173">**Transport rule**</span></span>
  - <span data-ttu-id="18aa6-174">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="18aa6-174">**Subject**</span></span>
  - <span data-ttu-id="18aa6-175">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="18aa6-175">**Sender address**</span></span>
  - <span data-ttu-id="18aa6-176">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="18aa6-176">**Recipient address**</span></span>
  - <span data-ttu-id="18aa6-177">**Allvarlighets grad**</span><span class="sxs-lookup"><span data-stu-id="18aa6-177">**Severity**</span></span>
  - <span data-ttu-id="18aa6-178">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="18aa6-178">**Direction**</span></span>

- <span data-ttu-id="18aa6-179">**Visa data med: transport regler för DLP Exchange**:</span><span class="sxs-lookup"><span data-stu-id="18aa6-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="18aa6-180">**Datum**</span><span class="sxs-lookup"><span data-stu-id="18aa6-180">**Date**</span></span>
  - <span data-ttu-id="18aa6-181">**DLP-princip**</span><span class="sxs-lookup"><span data-stu-id="18aa6-181">**DLP policy**</span></span>
  - <span data-ttu-id="18aa6-182">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="18aa6-182">**Transport rule**</span></span>
  - <span data-ttu-id="18aa6-183">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="18aa6-183">**Subject**</span></span>
  - <span data-ttu-id="18aa6-184">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="18aa6-184">**Sender address**</span></span>
  - <span data-ttu-id="18aa6-185">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="18aa6-185">**Recipient address**</span></span>
  - <span data-ttu-id="18aa6-186">**Allvarlighets grad**</span><span class="sxs-lookup"><span data-stu-id="18aa6-186">**Severity**</span></span>
  - <span data-ttu-id="18aa6-187">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="18aa6-187">**Direction**</span></span>

<span data-ttu-id="18aa6-188">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="18aa6-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="18aa6-189">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="18aa6-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="18aa6-190">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="18aa6-190">Direction values</span></span>
- <span data-ttu-id="18aa6-191">Allvarlighets värden</span><span class="sxs-lookup"><span data-stu-id="18aa6-191">Severity values</span></span>

<span data-ttu-id="18aa6-192">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="18aa6-193">Vidarebefordra rapport</span><span class="sxs-lookup"><span data-stu-id="18aa6-193">Forwarding report</span></span>

<span data-ttu-id="18aa6-194">I **vidarekoppling** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="18aa6-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="18aa6-195">Vidarebefordrade meddelanden kan utgöra en säkerhets-eller efterlevnad och kan tyda på ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="18aa6-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="18aa6-196">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **vidarebefordra rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="18aa6-197">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="18aa6-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget för vidarebefordrade rapporter i instrument panelen rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="18aa6-199">Rapportvy för rapport för vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="18aa6-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="18aa6-200">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="18aa6-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="18aa6-201">**Visa data för: metod för vidarekoppling**: följande metoder visas:</span><span class="sxs-lookup"><span data-stu-id="18aa6-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="18aa6-202">**Transport regel**: kallas även för [regler för e-postflöde](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="18aa6-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="18aa6-203">**Post lådans regel**: kallas även för [regler för Inkorgen](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="18aa6-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vyn för vidarebefordran av en rapport](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="18aa6-205">**Visa data för: vidarebefordrande domäner**: den här vyn visar de mottagare som är destinationer för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="18aa6-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vyn vidarebefordra domäner i rapport för vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="18aa6-207">**Visa data för: vidarebefordrare**: följande vidarebefordrare visas:</span><span class="sxs-lookup"><span data-stu-id="18aa6-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="18aa6-208">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="18aa6-208">**Transport rule**</span></span>
  - <span data-ttu-id="18aa6-209">Post lådan som innehåller inkorgen för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="18aa6-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vyn vidarebefordrare i rapporten vidarebefordran](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="18aa6-211">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="18aa6-212">Vyn detaljerad tabell för vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="18aa6-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="18aa6-213">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="18aa6-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="18aa6-214">**Vidarebefordrare**: värde **transport regeln** eller post lådan som innehåller regeln för vidarebefordran av Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="18aa6-215">**Typ av vidarekoppling**: regeln eller **transport regeln**för värde **post lådan** .</span><span class="sxs-lookup"><span data-stu-id="18aa6-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="18aa6-216">**Mottagarens namn**</span><span class="sxs-lookup"><span data-stu-id="18aa6-216">**Recipient name**</span></span>
- <span data-ttu-id="18aa6-217">**Mottagar domän**</span><span class="sxs-lookup"><span data-stu-id="18aa6-217">**Recipient domain**</span></span>
- <span data-ttu-id="18aa6-218">**Information**: det här är värdet på ett GUID-värde för regeln för e-postflöde, eller RuleIdentity-värdet i regeln för Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="18aa6-219">**Öka**</span><span class="sxs-lookup"><span data-stu-id="18aa6-219">**Count**</span></span>
- <span data-ttu-id="18aa6-220">**Första framåtriktade datum**</span><span class="sxs-lookup"><span data-stu-id="18aa6-220">**First forward date**</span></span>

<span data-ttu-id="18aa6-221">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="18aa6-222">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="18aa6-223">Flödes status rapport</span><span class="sxs-lookup"><span data-stu-id="18aa6-223">Mailflow status report</span></span>

<span data-ttu-id="18aa6-224">**Status rapporten** för [skicka och ta emot liknar e-](#sent-and-received-email-report)postmeddelandet, med ytterligare information om e-post som tillåts eller blockeras.</span><span class="sxs-lookup"><span data-stu-id="18aa6-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="18aa6-225">Det här är den enda rapporten som innehåller information om skydd och visar hur många e-postmeddelanden som blockeras innan de tillåts i tjänsten för utvärdering genom Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="18aa6-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="18aa6-226">Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="18aa6-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>  
<span data-ttu-id="18aa6-227">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **flödes status rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="18aa6-228">Om du vill gå direkt till **rapporten status för e-postflöde**öppnar du <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="18aa6-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget för status rapport för flödes schema i instrument panelen rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="18aa6-230">Skriv vy för status rapporten flödes schema</span><span class="sxs-lookup"><span data-stu-id="18aa6-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="18aa6-231">När du öppnar rapporten är fliken **typ** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="18aa6-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="18aa6-232">Den här vyn innehåller som standard ett diagram och en data tabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="18aa6-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="18aa6-233">**Datum**: de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="18aa6-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="18aa6-234">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="18aa6-234">**Direction**:</span></span>

  - <span data-ttu-id="18aa6-235">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="18aa6-235">**Inbound**</span></span>
  - <span data-ttu-id="18aa6-236">**Gående**</span><span class="sxs-lookup"><span data-stu-id="18aa6-236">**Outbound**</span></span>
  - <span data-ttu-id="18aa6-237">**Inom organisationen**: det här antalet är för meddelanden inom en klient organisation, d.v.s.</span><span class="sxs-lookup"><span data-stu-id="18aa6-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="18aa6-238">avsändarens abc@domain.com skickar till mottagaren xyz@domain.com (räknas separat från **inkommande** och **utgående**)</span><span class="sxs-lookup"><span data-stu-id="18aa6-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="18aa6-239">**Skriv**:</span><span class="sxs-lookup"><span data-stu-id="18aa6-239">**Type**:</span></span>

  - <span data-ttu-id="18aa6-240">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="18aa6-240">**Good mail**</span></span>
  - <span data-ttu-id="18aa6-241">**Program**</span><span class="sxs-lookup"><span data-stu-id="18aa6-241">**Malware**</span></span>
  - <span data-ttu-id="18aa6-242">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="18aa6-242">**Spam**</span></span>
  - <span data-ttu-id="18aa6-243">**Edge Protection**</span><span class="sxs-lookup"><span data-stu-id="18aa6-243">**Edge protection**</span></span>
  - <span data-ttu-id="18aa6-244">**Regel meddelanden**</span><span class="sxs-lookup"><span data-stu-id="18aa6-244">**Rule messages**</span></span>
  - <span data-ttu-id="18aa6-245">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="18aa6-245">**Phishing email**</span></span>

<span data-ttu-id="18aa6-246">Diagrammet är ordnat efter **textvärdena** .</span><span class="sxs-lookup"><span data-stu-id="18aa6-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="18aa6-247">Du kan ändra filtren genom att klicka på **filter** eller genom att klicka på ett värde i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-247">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="18aa6-248">Data tabellen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="18aa6-248">The data table contains the following information:</span></span>

- <span data-ttu-id="18aa6-249">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="18aa6-249">**Direction**</span></span>
- <span data-ttu-id="18aa6-250">**Typ**</span><span class="sxs-lookup"><span data-stu-id="18aa6-250">**Type**</span></span>
- <span data-ttu-id="18aa6-251">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="18aa6-251">**24 hours**</span></span>
- <span data-ttu-id="18aa6-252">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="18aa6-252">**3 days**</span></span>
- <span data-ttu-id="18aa6-253">**sju dagar**</span><span class="sxs-lookup"><span data-stu-id="18aa6-253">**7 days**</span></span>
- <span data-ttu-id="18aa6-254">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="18aa6-254">**15 days**</span></span>
- <span data-ttu-id="18aa6-255">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="18aa6-255">**30 days**</span></span>

<span data-ttu-id="18aa6-256">Om du klickar på **Välj en kategori för mer information**kan du välja bland följande värden:</span><span class="sxs-lookup"><span data-stu-id="18aa6-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="18aa6-257">**Nät fiske meddelande**: den här markeringen tar dig till [status rapporten för hotets skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="18aa6-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="18aa6-258">**Skadlig program vara i e-post**: den här markeringen tar dig till [status rapporten för hotets skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="18aa6-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="18aa6-259">**Skräp identifiering**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="18aa6-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="18aa6-260">**Edge blockera skräp post**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="18aa6-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="18aa6-261">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="18aa6-261">**Export**:</span></span>

<span data-ttu-id="18aa6-262">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="18aa6-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="18aa6-263">Om du till exempel vill exportera data i 7 dagar måste du göra 7 olika export åtgärder.</span><span class="sxs-lookup"><span data-stu-id="18aa6-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="18aa6-264">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="18aa6-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="18aa6-265">Om data för den dagen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="18aa6-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="18aa6-266">Skriv vy i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="18aa6-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="18aa6-267">Visnings läge för vyn flödes schema</span><span class="sxs-lookup"><span data-stu-id="18aa6-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="18aa6-268">Om du klickar på fliken **riktning** används samma standard filter från **typ** vyn.</span><span class="sxs-lookup"><span data-stu-id="18aa6-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="18aa6-269">Diagrammet är ordnat efter **riktnings** värden.</span><span class="sxs-lookup"><span data-stu-id="18aa6-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="18aa6-270">Du kan ändra dessa filter genom att klicka på **filter** eller genom att klicka på ett värde i diagram förklaringen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="18aa6-271">Samma filter i vyn **typ** används.</span><span class="sxs-lookup"><span data-stu-id="18aa6-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="18aa6-272">Data tabellen innehåller samma information från **typen** vy.</span><span class="sxs-lookup"><span data-stu-id="18aa6-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="18aa6-273">**Välj en kategori om** du vill se fler val och beteendet är samma som i **textfältet.**</span><span class="sxs-lookup"><span data-stu-id="18aa6-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="18aa6-274">**Exportera**:</span><span class="sxs-lookup"><span data-stu-id="18aa6-274">**Export**:</span></span>

<span data-ttu-id="18aa6-275">För detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="18aa6-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="18aa6-276">Om du till exempel vill exportera data i 7 dagar måste du göra 7 olika export åtgärder.</span><span class="sxs-lookup"><span data-stu-id="18aa6-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="18aa6-277">Alla exporterade CSV-filer är begränsade till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="18aa6-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="18aa6-278">Om data för den dagen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="18aa6-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="18aa6-279">Vyn riktning i rapporten flödes status</span><span class="sxs-lookup"><span data-stu-id="18aa6-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="18aa6-280">Skicka och ta emot e-postrapport</span><span class="sxs-lookup"><span data-stu-id="18aa6-280">Sent and received email report</span></span>

<span data-ttu-id="18aa6-281">Rapporten **skickat och mottaget e-postmeddelande** är en Smart rapport som visar information om inkommande och utgående e-post, inklusive skräp identifiering, skadlig program vara och e-postmeddelanden som identifieras som "bra".</span><span class="sxs-lookup"><span data-stu-id="18aa6-281">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="18aa6-282">Skillnaden mellan den här rapporten och [flödet flödes status](#mailflow-status-report) är: den här rapporten innehåller inte data om meddelanden som blockeras av Edge Protection.</span><span class="sxs-lookup"><span data-stu-id="18aa6-282">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="18aa6-283">I den aggregerade vyn och detaljvyn för rapporten får du 90 dagar på filtreringen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-283">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="18aa6-284">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **skickade och mottagna e-postmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-284">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="18aa6-285">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="18aa6-285">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget för skicka och ta emot e-post i instrument panelen rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="18aa6-287">Rapportvy för rapporten för skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="18aa6-287">Report view for the Sent and received email report</span></span>

<span data-ttu-id="18aa6-288">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="18aa6-288">The following charts are available in the report view:</span></span>

- <span data-ttu-id="18aa6-289">**Bryt ned per: typ**: diagrammet visar alla tillgängliga kategorier:</span><span class="sxs-lookup"><span data-stu-id="18aa6-289">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="18aa6-290">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="18aa6-290">**Total**</span></span>
  - <span data-ttu-id="18aa6-291">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="18aa6-291">**Good mail**</span></span>
  - <span data-ttu-id="18aa6-292">**Skadlig program vara (antivirus program)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="18aa6-292">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="18aa6-293">**Skräp identifiering**</span><span class="sxs-lookup"><span data-stu-id="18aa6-293">**Spam detections**</span></span>
  - <span data-ttu-id="18aa6-294">**Regel meddelanden**</span><span class="sxs-lookup"><span data-stu-id="18aa6-294">**Rule messages**</span></span>
  - <span data-ttu-id="18aa6-295">**Avancerad skadlig program vara** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="18aa6-295">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="18aa6-296">När du hovrar över en dag (data punkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-296">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Skriv vy i rapporten för skickad och mottagen e-post](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="18aa6-298">**Bryt ned efter: riktning**: diagrammet visar **totalt**, **inkommande**och **utgående** data.</span><span class="sxs-lookup"><span data-stu-id="18aa6-298">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="18aa6-299">När du hovrar över en dag (data punkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-299">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vyn riktning i e-postrapporten för skicka och ta emot](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="18aa6-301">**Öka detalj nivån med** \> **Skadlig program vara (skadlig program vara)**: den här markeringen tar dig till [identifieringar av skadlig program vara i e-postrapporten](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="18aa6-301">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="18aa6-302">**Öka detalj nivån med** \> **Skräp identifiering)**: den här markeringen tar dig till [rapporten skräp identifiering](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="18aa6-302">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="18aa6-303">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="18aa6-303">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="18aa6-304">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="18aa6-304">**Start date** and **End date**</span></span>
- <span data-ttu-id="18aa6-305">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="18aa6-305">Direction values</span></span>
- <span data-ttu-id="18aa6-306">Ange värden</span><span class="sxs-lookup"><span data-stu-id="18aa6-306">Type values</span></span>

<span data-ttu-id="18aa6-307">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-307">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="18aa6-308">Vyn detaljerad tabell för den skickade och mottagna e-postrapporten</span><span class="sxs-lookup"><span data-stu-id="18aa6-308">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="18aa6-309">Om du klickar på **Visa informations tabell** i **Bryt ned efter: riktning** eller **Bryt ned efter: vyn riktning** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="18aa6-309">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="18aa6-310">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="18aa6-310">**Date (UTC)**</span></span>
- <span data-ttu-id="18aa6-311">**Typ**</span><span class="sxs-lookup"><span data-stu-id="18aa6-311">**Type**</span></span>
- <span data-ttu-id="18aa6-312">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="18aa6-312">**Direction**</span></span>
- <span data-ttu-id="18aa6-313">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="18aa6-313">**Message count**</span></span>

<span data-ttu-id="18aa6-314">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="18aa6-314">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="18aa6-315">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="18aa6-315">**Start date** and **End date**</span></span>
- <span data-ttu-id="18aa6-316">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="18aa6-316">Direction values</span></span>
- <span data-ttu-id="18aa6-317">Ange värden</span><span class="sxs-lookup"><span data-stu-id="18aa6-317">Type values</span></span>

<span data-ttu-id="18aa6-318">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-318">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="18aa6-319">Rapporter för högsta avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="18aa6-319">Top senders and recipients report</span></span>

<span data-ttu-id="18aa6-320">Den **översta rapporten avsändare och mottagare** är ett cirkel diagram som visar dina e-postmeddelanden och mottagare.</span><span class="sxs-lookup"><span data-stu-id="18aa6-320">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="18aa6-321">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **de översta avsändaren och mottagarna**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-321">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="18aa6-322">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="18aa6-322">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgeten vanliga avsändare och mottagare i instrument panelen rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="18aa6-324">Rapportvy för rapporten högsta avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="18aa6-324">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="18aa6-325">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="18aa6-325">The following charts are available in the report view:</span></span>

- <span data-ttu-id="18aa6-326">**Visa data för \> de flesta e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="18aa6-326">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="18aa6-327">**Visa data för \> högsta antal e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="18aa6-327">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="18aa6-328">**Visa data för \> mottagare av reklam**</span><span class="sxs-lookup"><span data-stu-id="18aa6-328">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="18aa6-329">**Visa data för \> Högsta antal mottagare av skadlig program vara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="18aa6-329">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="18aa6-330">**Visa data för \> Högsta antal mottagare av skadlig program vara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="18aa6-330">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="18aa6-331">Sammansättningen för cirkel diagrammet ändras utifrån de här valen.</span><span class="sxs-lookup"><span data-stu-id="18aa6-331">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="18aa6-332">När du hovrar över en sektor i cirkel diagrammet kan du se antalet meddelanden som skickats eller tagits emot.</span><span class="sxs-lookup"><span data-stu-id="18aa6-332">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="18aa6-333">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-333">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkel diagram i rapportvyn i rapporten överst avsändare och mottagare](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="18aa6-335">Vyn detaljerad lista för rapporten överst avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="18aa6-335">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="18aa6-336">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="18aa6-336">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="18aa6-337">**Visa data för \> de flesta e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="18aa6-337">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="18aa6-338">**Vanligaste e-postutskick**</span><span class="sxs-lookup"><span data-stu-id="18aa6-338">**Top mail senders**</span></span>
  - <span data-ttu-id="18aa6-339">**Öka**</span><span class="sxs-lookup"><span data-stu-id="18aa6-339">**Count**</span></span>

- <span data-ttu-id="18aa6-340">**Visa data för \> högsta antal e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="18aa6-340">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="18aa6-341">**Vanligaste e-postmottagare**</span><span class="sxs-lookup"><span data-stu-id="18aa6-341">**Top mail recipients**</span></span>
  - <span data-ttu-id="18aa6-342">**Öka**</span><span class="sxs-lookup"><span data-stu-id="18aa6-342">**Count**</span></span>

- <span data-ttu-id="18aa6-343">**Visa data för \> mottagare av reklam**</span><span class="sxs-lookup"><span data-stu-id="18aa6-343">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="18aa6-344">**Populära skräp mottagare**</span><span class="sxs-lookup"><span data-stu-id="18aa6-344">**Top spam recipients**</span></span>
  - <span data-ttu-id="18aa6-345">**Öka**</span><span class="sxs-lookup"><span data-stu-id="18aa6-345">**Count**</span></span>

- <span data-ttu-id="18aa6-346">**Visa data för \> Högsta antal mottagare av skadlig program vara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="18aa6-346">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="18aa6-347">**Högsta antal mottagare av skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="18aa6-347">**Top malware recipients**</span></span>
  - <span data-ttu-id="18aa6-348">**Öka**</span><span class="sxs-lookup"><span data-stu-id="18aa6-348">**Count**</span></span>

- <span data-ttu-id="18aa6-349">**Visa data för \> Högsta antal mottagare av skadlig program vara (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="18aa6-349">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="18aa6-350">**Högsta antal mottagare av skadlig program vara (ATP)**</span><span class="sxs-lookup"><span data-stu-id="18aa6-350">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="18aa6-351">**Öka**</span><span class="sxs-lookup"><span data-stu-id="18aa6-351">**Count**</span></span>

<span data-ttu-id="18aa6-352">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-352">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="18aa6-353">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="18aa6-353">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="18aa6-354">Vilka behörigheter behövs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="18aa6-354">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="18aa6-355">Om du vill visa och använda rapporterna måste du vara medlem i den angivna roll gruppen i säkerhets & efterföljandekrav **och** i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="18aa6-355">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="18aa6-356">I säkerhets & Compliance Center måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="18aa6-356">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="18aa6-357">-Organisations hantering-säkerhets administratör (du kan också göra det i [Azure Active Directory Admin Center](https://aad.portal.azure.com) -säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="18aa6-357">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="18aa6-358">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="18aa6-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="18aa6-359">I Exchange Online måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="18aa6-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="18aa6-360">-Organisations hantering-Visa endast organisations hantering-endast Visa-mottagare-kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="18aa6-360">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="18aa6-361">Mer information finns i [behörigheter i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) och [Hantera roll grupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="18aa6-361">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="18aa6-362">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="18aa6-362">Related topics</span></span>

[<span data-ttu-id="18aa6-363">Smarta rapporter och insikter i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="18aa6-363">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="18aa6-364">Insikter om e-postflöde i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="18aa6-364">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="18aa6-365">Visa säkerhets rapporter för e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="18aa6-365">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="18aa6-366">Visa rapporter för Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="18aa6-366">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
