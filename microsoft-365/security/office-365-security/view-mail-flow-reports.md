---
title: Visa e-postflödesrapporter på instrumentpanelen Rapporter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om e-postflödesrapporterna som är tillgängliga i instrumentpanelen Rapporter i säkerhets- & Efterlevnadscenter.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286723"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="79ccf-103">Visa e-postflödesrapporter i instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="79ccf-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="79ccf-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="79ccf-104">**Applies to**</span></span>
- [<span data-ttu-id="79ccf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="79ccf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="79ccf-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="79ccf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="79ccf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79ccf-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="79ccf-108">Förutom e-postflödesrapporterna som är [](mail-flow-insights-v2.md) tillgängliga på instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & finns det flera olika e-postflödesrapporter på instrumentpanelen Rapporter som hjälper dig att övervaka Din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="79ccf-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="79ccf-109">Om du har nödvändiga [behörigheter kan](#what-permissions-are-needed-to-view-these-reports)du visa de här rapporterna i Säkerhets- och [& genom](https://protection.office.com) att gå till  \> **instrumentpanelen Rapporter.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="79ccf-110">Om du vill gå direkt till instrumentpanelen Rapporter öppnar du <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="79ccf-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="79ccf-112">Kopplingsrapport</span><span class="sxs-lookup"><span data-stu-id="79ccf-112">Connector report</span></span>

<span data-ttu-id="79ccf-113">Kopplingsrapporten **visar** e-postflödesaktivitet [för inkommande och](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) utgående anslutningar som är konfigurerade för din organisation.</span><span class="sxs-lookup"><span data-stu-id="79ccf-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="79ccf-114">Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går **till** instrumentpanelen \> **Rapporter** och väljer **Kopplingsrapport.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="79ccf-115">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="79ccf-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget för kopplingsrapport på instrumentpanelen Rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="79ccf-117">Rapportvy för kopplingsrapporten</span><span class="sxs-lookup"><span data-stu-id="79ccf-117">Report view for the Connector report</span></span>

<span data-ttu-id="79ccf-118">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="79ccf-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="79ccf-119">**Visa data efter: E-postflöde:** I det här diagrammet visas antalet inkommande och utgående meddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="79ccf-120">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="79ccf-120">**Total**</span></span>
  - <span data-ttu-id="79ccf-121">**Från Internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="79ccf-122">**Till Internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="79ccf-123">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="79ccf-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="79ccf-124">Om du vill isolera data i diagrammet använder du Visa data för kontroll **och** väljer ett av de här alternativen eller **Allt e-postflöde.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visa data efter e-postflöde i kopplingsrapporten](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="79ccf-126">**Visa data efter: TLS-användning:** Det här diagrammet visar procentandelen TLS-versionsanvändning (Transport Layer Security) för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="79ccf-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="79ccf-127">Om du vill isolera data i diagrammet använder du **Visa data för kontroll** och väljer ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="79ccf-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="79ccf-128">**Allt e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="79ccf-128">**All mail flow**</span></span>
  - <span data-ttu-id="79ccf-129">**Från Internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="79ccf-130">**Till Internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="79ccf-131">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="79ccf-131">A specific connector that you've configured.</span></span>

  ![Visa data efter TLS-användning i kopplingsrapporten](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="79ccf-133">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="79ccf-134">Detaljtabellvy för kopplingsrapporten</span><span class="sxs-lookup"><span data-stu-id="79ccf-134">Details table view for the Connector report</span></span>

<span data-ttu-id="79ccf-135">Om du **klickar på Tabellen Visa** information i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="79ccf-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="79ccf-136">**Datum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-136">**Date**</span></span>
- <span data-ttu-id="79ccf-137">**Kopplingsriktning och namn**</span><span class="sxs-lookup"><span data-stu-id="79ccf-137">**Connector direction and name**</span></span>
- <span data-ttu-id="79ccf-138">**Kopplingstyp**</span><span class="sxs-lookup"><span data-stu-id="79ccf-138">**Connector type**</span></span>
- <span data-ttu-id="79ccf-139">**Tvingad TLS?**: Värdet **Sant** eller **Falskt.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="79ccf-140">**Ingen TLS** (procent)</span><span class="sxs-lookup"><span data-stu-id="79ccf-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="79ccf-141">**TLS 1,0** (procent)</span><span class="sxs-lookup"><span data-stu-id="79ccf-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="79ccf-142">**TLS 1,1** (procent)</span><span class="sxs-lookup"><span data-stu-id="79ccf-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="79ccf-143">**TLS 1,2** (procent)</span><span class="sxs-lookup"><span data-stu-id="79ccf-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="79ccf-144">**Volym:** Antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="79ccf-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="79ccf-145">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="79ccf-146">Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="79ccf-147">Regelrapport för Exchange-transport</span><span class="sxs-lookup"><span data-stu-id="79ccf-147">Exchange transport rule report</span></span>

<span data-ttu-id="79ccf-148">I **regelrapporten för Exchange-transport** visas effekten av e-postflödesregler (kallas även transportregler) på inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="79ccf-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="79ccf-149">Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går **till** instrumentpanelen \> **Rapporter** och väljer **Exchange-transportregel.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="79ccf-150">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="79ccf-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget för Exchange-transportregel på instrumentpanelen Rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="79ccf-152">Rapportvy för Exchange-transportregelrapporten</span><span class="sxs-lookup"><span data-stu-id="79ccf-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="79ccf-153">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="79ccf-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="79ccf-154">**Visa data efter: Exchange-transportregler** \> **Radbryt för: Riktning:** Det här diagrammet visar antalet **ingående** och **utgående** meddelanden som påverkades av transportreglerna.</span><span class="sxs-lookup"><span data-stu-id="79ccf-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="79ccf-155">**Visa data efter: Exchange-transportregler** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span><span class="sxs-lookup"><span data-stu-id="79ccf-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="79ccf-156">Du anger allvarlighetsnivån som en åtgärd i regeln (Granska den här regeln med **allvarlighetsnivå** eller _AngeAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="79ccf-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="79ccf-157">Mer information finns i Åtgärder för [e-postflödesregel i Exchange Online.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="79ccf-157">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="79ccf-158">**Visa data efter: DLP Exchange-transportregler** \> **Åtser sig: Riktning:** I det här  diagrammet visas antalet **ingående** och utgående meddelanden som påverkades av DLP-transportregler (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="79ccf-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="79ccf-159">Du kan förfina diagrammet ytterligare genom att välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="79ccf-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="79ccf-160">**Visa data för: Alla DLP-transportregler**</span><span class="sxs-lookup"><span data-stu-id="79ccf-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="79ccf-161">**Visa data för: Komprometterade användare**</span><span class="sxs-lookup"><span data-stu-id="79ccf-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="79ccf-162">**Visa data för: Låg mängd innehåll upptäckt av U.S. Act**</span><span class="sxs-lookup"><span data-stu-id="79ccf-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="79ccf-163">**Visa data efter: DLP Exchange-transportregler** \> **Break down by: Direction:** This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="79ccf-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="79ccf-164">Du kan förfina diagrammet ytterligare genom att välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="79ccf-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="79ccf-165">**Visa data för: Alla DLP-transportregler**</span><span class="sxs-lookup"><span data-stu-id="79ccf-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="79ccf-166">**Visa data för: Komprometterade användare**</span><span class="sxs-lookup"><span data-stu-id="79ccf-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="79ccf-167">**Visa data för: Låg mängd innehåll upptäckt av U.S. Act**</span><span class="sxs-lookup"><span data-stu-id="79ccf-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="79ccf-168">Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="79ccf-169">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="79ccf-170">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="79ccf-170">Direction values</span></span>
- <span data-ttu-id="79ccf-171">Allvarlighetsvärden</span><span class="sxs-lookup"><span data-stu-id="79ccf-171">Severity values</span></span>

![Rapportvy i exchange-transportregelrapporten](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="79ccf-173">Detaljtabellvy för rapporten Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="79ccf-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="79ccf-174">Om du **klickar på Tabellen** Visa information beror den information som visas på det diagram som du visade:</span><span class="sxs-lookup"><span data-stu-id="79ccf-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="79ccf-175">**Visa data efter: Exchange-transportregler:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="79ccf-176">**Datum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-176">**Date**</span></span>
  - <span data-ttu-id="79ccf-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="79ccf-177">**Transport rule**</span></span>
  - <span data-ttu-id="79ccf-178">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="79ccf-178">**Subject**</span></span>
  - <span data-ttu-id="79ccf-179">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="79ccf-179">**Sender address**</span></span>
  - <span data-ttu-id="79ccf-180">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="79ccf-180">**Recipient address**</span></span>
  - <span data-ttu-id="79ccf-181">**Allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="79ccf-181">**Severity**</span></span>
  - <span data-ttu-id="79ccf-182">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-182">**Direction**</span></span>

- <span data-ttu-id="79ccf-183">**Visa data efter: DLP Exchange-transportregler:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="79ccf-184">**Datum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-184">**Date**</span></span>
  - <span data-ttu-id="79ccf-185">**DLP-princip**</span><span class="sxs-lookup"><span data-stu-id="79ccf-185">**DLP policy**</span></span>
  - <span data-ttu-id="79ccf-186">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="79ccf-186">**Transport rule**</span></span>
  - <span data-ttu-id="79ccf-187">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="79ccf-187">**Subject**</span></span>
  - <span data-ttu-id="79ccf-188">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="79ccf-188">**Sender address**</span></span>
  - <span data-ttu-id="79ccf-189">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="79ccf-189">**Recipient address**</span></span>
  - <span data-ttu-id="79ccf-190">**Allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="79ccf-190">**Severity**</span></span>
  - <span data-ttu-id="79ccf-191">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-191">**Direction**</span></span>

<span data-ttu-id="79ccf-192">Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="79ccf-193">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="79ccf-194">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="79ccf-194">Direction values</span></span>
- <span data-ttu-id="79ccf-195">Allvarlighetsvärden</span><span class="sxs-lookup"><span data-stu-id="79ccf-195">Severity values</span></span>

<span data-ttu-id="79ccf-196">Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="79ccf-197">Vidarebefordransrapport</span><span class="sxs-lookup"><span data-stu-id="79ccf-197">Forwarding report</span></span>

<span data-ttu-id="79ccf-198">I **vidarebefordransrapporten** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="79ccf-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="79ccf-199">Vidarebefordrade meddelanden kan utgöra en säkerhets- eller efterlevnadsrisk och kan ange ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="79ccf-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="79ccf-200">Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går till **instrumentpanelen** \> **Rapporter** och väljer **Vidarebefordransrapport.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="79ccf-201">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="79ccf-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget för vidarebefordransrapport på instrumentpanelen Rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="79ccf-203">Rapportvy för vidarebefordransrapporten</span><span class="sxs-lookup"><span data-stu-id="79ccf-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="79ccf-204">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="79ccf-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="79ccf-205">**Visa data för: Vidarebefordransmetoder:** Följande metoder visas:</span><span class="sxs-lookup"><span data-stu-id="79ccf-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="79ccf-206">**Transportregel:** Kallas även [e-postflödesregler.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="79ccf-206">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="79ccf-207">**Postlåderegel:** Kallas även [inkorgsregler.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="79ccf-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vyn Vidarebefordransmetoder i rapporten om vidarebefordran](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="79ccf-209">**Visa data för: Domäner för vidarebefordran:** I den här vyn visas de mottagardomäner som är destinationer för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="79ccf-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vyn Vidarebefordra domäner i rapporten Om vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="79ccf-211">**Visa data för: Vidarebefordrare:** Följande vidarebefordrare visas:</span><span class="sxs-lookup"><span data-stu-id="79ccf-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="79ccf-212">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="79ccf-212">**Transport rule**</span></span>
  - <span data-ttu-id="79ccf-213">Postlådan som innehåller vidare vidarebefordrans inkorgsregeln.</span><span class="sxs-lookup"><span data-stu-id="79ccf-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vyn Vidarebefordrare i rapporten Vidarebefordran](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="79ccf-215">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="79ccf-216">Tabellvyn Information för vidarebefordransrapporten</span><span class="sxs-lookup"><span data-stu-id="79ccf-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="79ccf-217">Om du **klickar på Tabellen Visa** information i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="79ccf-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="79ccf-218">**Vidarebefordrare:** Värdet **Transport-regeln eller** postlådan som innehåller vidare vidarebefordrans inkorgsregeln.</span><span class="sxs-lookup"><span data-stu-id="79ccf-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="79ccf-219">**Vidarebefordranstyp:** **Värdepostlåderegel** eller **transportregel.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="79ccf-220">**Mottagarens namn**</span><span class="sxs-lookup"><span data-stu-id="79ccf-220">**Recipient name**</span></span>
- <span data-ttu-id="79ccf-221">**Mottagardomän**</span><span class="sxs-lookup"><span data-stu-id="79ccf-221">**Recipient domain**</span></span>
- <span data-ttu-id="79ccf-222">**Information:** Det här är GUID-värdet för e-postflödesregeln eller RuleIdentity-värdet för inkorgsregeln.</span><span class="sxs-lookup"><span data-stu-id="79ccf-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="79ccf-223">**Antal**</span><span class="sxs-lookup"><span data-stu-id="79ccf-223">**Count**</span></span>
- <span data-ttu-id="79ccf-224">**Första vidarebefordransdatum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-224">**First forward date**</span></span>

<span data-ttu-id="79ccf-225">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="79ccf-226">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="79ccf-227">Statusrapport för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="79ccf-227">Mailflow status report</span></span>

<span data-ttu-id="79ccf-228">Statusrapporten **e-postflöde** liknar [](#sent-and-received-email-report)rapporten Skickad och mottagen e-post, med ytterligare information om tillåtna eller blockerade e-postmeddelanden i edge.</span><span class="sxs-lookup"><span data-stu-id="79ccf-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="79ccf-229">Det här är den enda rapporten som innehåller information om gränsskydd och visar hur mycket e-post som blockeras innan de tillåts i tjänsten för utvärdering av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="79ccf-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="79ccf-230">Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="79ccf-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="79ccf-231">Om du vill visa rapporten öppnar du [Säkerhets- &](https://protection.office.com)Efterlevnadscenter, går till **instrumentpanelen** \> **Rapporter** och väljer **Statusrapport för e-postflöde.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="79ccf-232">Gå direkt till statusrapporten **för e-postflödet** genom att <https://protection.office.com/mailflowStatusReport> öppna.</span><span class="sxs-lookup"><span data-stu-id="79ccf-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget för statusrapport i e-postflöde på instrumentpanelen Rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="79ccf-234">Typvy för statusrapporten För e-postflöde</span><span class="sxs-lookup"><span data-stu-id="79ccf-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="79ccf-235">När du öppnar rapporten är **fliken** Typ markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="79ccf-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="79ccf-236">Som standard innehåller den här vyn ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="79ccf-237">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="79ccf-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="79ccf-238">**Riktning:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-238">**Direction**:</span></span>

  - <span data-ttu-id="79ccf-239">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="79ccf-239">**Inbound**</span></span>
  - <span data-ttu-id="79ccf-240">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="79ccf-240">**Outbound**</span></span>
  - <span data-ttu-id="79ccf-241">**Årsantal:** antalet är för meddelanden inom en klientorganisation, dvs.</span><span class="sxs-lookup"><span data-stu-id="79ccf-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="79ccf-242">avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från **Inkommande** och **Utgående)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="79ccf-243">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-243">**Type**:</span></span>

  - <span data-ttu-id="79ccf-244">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="79ccf-244">**Good mail**</span></span>
  - <span data-ttu-id="79ccf-245">**Skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="79ccf-245">**Malware**</span></span>
  - <span data-ttu-id="79ccf-246">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="79ccf-246">**Spam**</span></span>
  - <span data-ttu-id="79ccf-247">**Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="79ccf-247">**Edge protection**</span></span>
  - <span data-ttu-id="79ccf-248">**Regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="79ccf-248">**Rule messages**</span></span>
  - <span data-ttu-id="79ccf-249">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="79ccf-249">**Phishing email**</span></span>

<span data-ttu-id="79ccf-250">Diagrammet är ordnat efter **typvärdena.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="79ccf-251">Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="79ccf-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="79ccf-252">Datatabellen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="79ccf-252">The data table contains the following information:</span></span>

- <span data-ttu-id="79ccf-253">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-253">**Direction**</span></span>
- <span data-ttu-id="79ccf-254">**Typ**</span><span class="sxs-lookup"><span data-stu-id="79ccf-254">**Type**</span></span>
- <span data-ttu-id="79ccf-255">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="79ccf-255">**24 hours**</span></span>
- <span data-ttu-id="79ccf-256">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="79ccf-256">**3 days**</span></span>
- <span data-ttu-id="79ccf-257">**7 dagar**</span><span class="sxs-lookup"><span data-stu-id="79ccf-257">**7 days**</span></span>
- <span data-ttu-id="79ccf-258">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="79ccf-258">**15 days**</span></span>
- <span data-ttu-id="79ccf-259">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="79ccf-259">**30 days**</span></span>

<span data-ttu-id="79ccf-260">Om du klickar **på Välj en kategori för mer** information kan du välja bland följande värden:</span><span class="sxs-lookup"><span data-stu-id="79ccf-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="79ccf-261">**Nätfiskemeddelande:** Det här valet tar dig till [statusrapporten om skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="79ccf-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="79ccf-262">**Skadlig programvara i** e-postmeddelanden: Det här valet tar dig [till statusrapporten om skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="79ccf-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="79ccf-263">**Identifiering av skräppost:** Det här valet tar dig till [rapporten Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="79ccf-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="79ccf-264">**Blockerad skräppost i Edge:** Det här valet tar dig till rapporten [Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="79ccf-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="79ccf-265">**Exportera:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-265">**Export**:</span></span>

<span data-ttu-id="79ccf-266">I detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="79ccf-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="79ccf-267">Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="79ccf-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="79ccf-268">Varje exporterad CSV-fil är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="79ccf-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="79ccf-269">Om dagens data innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="79ccf-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="79ccf-270">Typvy i statusrapporten för E-postflöde</span><span class="sxs-lookup"><span data-stu-id="79ccf-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="79ccf-271">Vyn Riktning för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="79ccf-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="79ccf-272">Om du klickar **på** fliken Riktning används samma standardfilter **från** vyn Typ.</span><span class="sxs-lookup"><span data-stu-id="79ccf-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="79ccf-273">Diagrammet är ordnat efter **riktningsvärden.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="79ccf-274">Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="79ccf-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="79ccf-275">Samma filter används **i** vyn Typ.</span><span class="sxs-lookup"><span data-stu-id="79ccf-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="79ccf-276">Datatabellen innehåller samma information från **vyn** Typ.</span><span class="sxs-lookup"><span data-stu-id="79ccf-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="79ccf-277">Välj **en kategori om du vill ha mer** information om tillgängliga val och beteenden är samma som **vyn** Typ.</span><span class="sxs-lookup"><span data-stu-id="79ccf-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="79ccf-278">**Exportera:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-278">**Export**:</span></span>

<span data-ttu-id="79ccf-279">I detaljvyn kan du bara exportera data för en dag.</span><span class="sxs-lookup"><span data-stu-id="79ccf-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="79ccf-280">Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="79ccf-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="79ccf-281">Varje exporterad CSV-fil är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="79ccf-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="79ccf-282">Om dagens data innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="79ccf-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="79ccf-283">Vyn Riktning i statusrapporten för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="79ccf-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="79ccf-284">Trattvy för statusrapporten för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="79ccf-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="79ccf-285">I **vyn Tratt** kan du se hur Microsofts skyddsfunktioner för e-posthot filtrerar inkommande och utgående e-post i din organisation.</span><span class="sxs-lookup"><span data-stu-id="79ccf-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="79ccf-286">Här finns information om totalt antal e-postmeddelanden och hur de konfigurerade skyddsfunktionerna för hot, inklusive gränsskydd, skadlig programvara, skydd mot nätfiske, skräppostskydd och förfalskning påverkar antalet.</span><span class="sxs-lookup"><span data-stu-id="79ccf-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="79ccf-287">Om du klickar **på fliken** Tratt innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="79ccf-288">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="79ccf-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="79ccf-289">**Riktning:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-289">**Direction**:</span></span>

  - <span data-ttu-id="79ccf-290">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="79ccf-290">**Inbound**</span></span>
  - <span data-ttu-id="79ccf-291">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="79ccf-291">**Outbound**</span></span>
  - <span data-ttu-id="79ccf-292">**Årsantal:** Antalet är för meddelanden som skickas inom en klientorganisation. Det vill säga att avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från inkommande och utgående).</span><span class="sxs-lookup"><span data-stu-id="79ccf-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="79ccf-293">Mängdvyn och datatabellvyn tillåter 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="79ccf-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="79ccf-294">Om du klickar **på Filter** kan du filtrera både diagrammet och datatabellen.</span><span class="sxs-lookup"><span data-stu-id="79ccf-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="79ccf-295">I det här diagrammet visas antalet e-postmeddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="79ccf-296">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="79ccf-296">**Total email**</span></span>
- <span data-ttu-id="79ccf-297">**E-post efter gränsskydd**</span><span class="sxs-lookup"><span data-stu-id="79ccf-297">**Email after edge protection**</span></span>
- <span data-ttu-id="79ccf-298">**E-post efter skadlig programvara, rykte, filtypsblock**</span><span class="sxs-lookup"><span data-stu-id="79ccf-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="79ccf-299">**E-post efter anfing, URL-rykte, varumärkespersonifiering, förfalskning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="79ccf-300">**E-post efter skräppostskydd, massfiltrering**</span><span class="sxs-lookup"><span data-stu-id="79ccf-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="79ccf-301">**E-post efter användare och domänpersonifiering**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="79ccf-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="79ccf-302">**E-post efter fil och URL-detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="79ccf-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="79ccf-303">**E-post identifieras som hotad efter leveransskydd (URL-klicktidsskydd)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="79ccf-304"><sup>1</sup> Endast Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="79ccf-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="79ccf-305">Om du vill visa e-post som filtreras separat med EOP eller Defender för Office 365 klickar du på värdet i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="79ccf-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="79ccf-306">Datatabellen innehåller följande information, som visas i fallande datumordning:</span><span class="sxs-lookup"><span data-stu-id="79ccf-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="79ccf-307">**Datum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-307">**Date**</span></span>
- <span data-ttu-id="79ccf-308">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="79ccf-308">**Total email**</span></span>
- <span data-ttu-id="79ccf-309">**Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="79ccf-309">**Edge protection**</span></span>
- <span data-ttu-id="79ccf-310">**Skydd mot skadlig programvara, rykte, filtypsblock:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="79ccf-311">**Rykte:** Meddelanden filtrerade på grund av identifiering av en bifogad fil av andra Microsoft-kunder.</span><span class="sxs-lookup"><span data-stu-id="79ccf-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="79ccf-312">**Filtypsblock:** Meddelanden filtrerade på grund av den typ av skadlig fil som identifieras i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="79ccf-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="79ccf-313">**Skydd mot phish, URL-rykte, varumärkespersonifiering, skydd mot förfalskning:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="79ccf-314">**Rykte:** Meddelanden filtrerade på grund av identifiering av WEBBADRESSen av andra Microsoft-kunder.</span><span class="sxs-lookup"><span data-stu-id="79ccf-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="79ccf-315">**Profilering:** Meddelanden filtrerade på grund av meddelandet från välkända avsändare som utger sig för att vara avsändare.</span><span class="sxs-lookup"><span data-stu-id="79ccf-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="79ccf-316">Skydd mot **förfalskning:** Meddelanden filtrerade på grund av meddelandet som försöker kapa en domän som mottagaren tillhör eller en domän som meddelandets avsändare inte äger.</span><span class="sxs-lookup"><span data-stu-id="79ccf-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="79ccf-317">**Skydd mot skräppost och massfiltrering:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="79ccf-318">**Massfiltrering:** Filtrerade meddelanden på grund av ett försök att leverera massutskick till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="79ccf-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="79ccf-319">**Personifiering av användare och domän (Defender för Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="79ccf-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="79ccf-320">**Användarpersonifiering:** Filtrerade meddelanden på grund av ett försök att personifiera en användare (meddelandeavsändare) som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="79ccf-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="79ccf-321">**Domänpersonifiering:** Meddelanden filtrerade på grund av ett försök att personifiera en domän som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="79ccf-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="79ccf-322">**Detonation för fil och URL (Defender för Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="79ccf-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="79ccf-323">**Detonation för filer:** Meddelanden filtrerade med en princip för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="79ccf-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="79ccf-324">**URL-detonation:** Meddelande filtrerat med en princip för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="79ccf-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="79ccf-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span><span class="sxs-lookup"><span data-stu-id="79ccf-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="79ccf-326">Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällna listan.</span><span class="sxs-lookup"><span data-stu-id="79ccf-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="79ccf-327">**Exportera:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-327">**Export**:</span></span>

<span data-ttu-id="79ccf-328">När du har **klickat** **på Exportera** under Alternativ kan du välja något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="79ccf-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="79ccf-329">**Sammanfattning (med data för de senaste 90 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="79ccf-330">**Information (med data för de senaste 30 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="79ccf-331">Välj **ett** område under Datum och klicka sedan på **Använd.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="79ccf-332">Data för de aktuella filtren exporteras till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="79ccf-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="79ccf-333">Varje exporterad CSV-fil är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="79ccf-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="79ccf-334">Om informationen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="79ccf-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="79ccf-335">Trattvyn i statusrapporten för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="79ccf-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="79ccf-336">Tech view for the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="79ccf-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="79ccf-337">**Tech-vyn** liknar vyn **Tratt,** med mer detaljerad information om funktionerna för konfigurerade skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="79ccf-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="79ccf-338">I diagrammet kan du se hur meddelanden kategoriseras i olika faser av skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="79ccf-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="79ccf-339">Om du klickar **på fliken Teknisk** vy innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="79ccf-340">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="79ccf-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="79ccf-341">**Riktning:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-341">**Direction**:</span></span>

  - <span data-ttu-id="79ccf-342">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="79ccf-342">**Inbound**</span></span>
  - <span data-ttu-id="79ccf-343">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="79ccf-343">**Outbound**</span></span>
  - <span data-ttu-id="79ccf-344">**Årsantal:** antalet är för meddelanden inom en klientorganisation, dvs.</span><span class="sxs-lookup"><span data-stu-id="79ccf-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="79ccf-345">avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från inkommande och utgående)</span><span class="sxs-lookup"><span data-stu-id="79ccf-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="79ccf-346">Mängdvyn och datatabellvyn tillåter 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="79ccf-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="79ccf-347">Om du klickar **på Filter** kan du filtrera både diagrammet och datatabellen.</span><span class="sxs-lookup"><span data-stu-id="79ccf-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="79ccf-348">I det här diagrammet visas meddelanden ordnade i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="79ccf-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="79ccf-349">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="79ccf-349">**Total email**</span></span>
- <span data-ttu-id="79ccf-350">**Tillåtna Edge** **och Filtrerad Edge**</span><span class="sxs-lookup"><span data-stu-id="79ccf-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="79ccf-351">**Inte skadlig programvara,** **identifiering av säkra bifogade** <sup>\*</sup> **filer, identifiering av skadlig programvara** och **regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="79ccf-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="79ccf-352">**Inte phish,** **DMARC-fel,** identifiering **av personifiering,** identifiering **av förfalskning** och **phish**</span><span class="sxs-lookup"><span data-stu-id="79ccf-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="79ccf-353">**Ingen identifiering med URL-detonation och** **URL-detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="79ccf-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="79ccf-354">**Inte** skräppost </span><span class="sxs-lookup"><span data-stu-id="79ccf-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="79ccf-355">**Icke-skadlig e-post,** **identifiering av säkra** länkar och <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="79ccf-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="79ccf-356"><sup>\*</sup> Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="79ccf-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="79ccf-357">När du hovrar över en kategori i diagrammet visas antalet meddelanden i den kategorin.</span><span class="sxs-lookup"><span data-stu-id="79ccf-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="79ccf-358">Datatabellen innehåller följande information, som visas i fallande datumordning:</span><span class="sxs-lookup"><span data-stu-id="79ccf-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="79ccf-359">**Datum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-359">**Date**</span></span>
- <span data-ttu-id="79ccf-360">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="79ccf-360">**Total email**</span></span>
- <span data-ttu-id="79ccf-361">**Filtrerad Edge**</span><span class="sxs-lookup"><span data-stu-id="79ccf-361">**Edge filtered**</span></span>
- <span data-ttu-id="79ccf-362">**Motor mot skadlig programvara, säkra bifogade filer, regel filtrerad:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="79ccf-363">**Regel filtrerad:** Meddelanden filtrerade på grund av e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="79ccf-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="79ccf-364">**DMARC, personifiering, förfalskning, nätfiske filtrerat:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="79ccf-365">**DMARC:** Meddelanden filtrerade på grund av att meddelandet inte klarar sin DMARC-autentiseringskontroll.</span><span class="sxs-lookup"><span data-stu-id="79ccf-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="79ccf-366">**Identifiering av URL-detonation**</span><span class="sxs-lookup"><span data-stu-id="79ccf-366">**URL detonation detection**</span></span>
- <span data-ttu-id="79ccf-367">**Skräppostskydd filtreras**</span><span class="sxs-lookup"><span data-stu-id="79ccf-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="79ccf-368">**ZAP har tagits bort**</span><span class="sxs-lookup"><span data-stu-id="79ccf-368">**ZAP removed**</span></span>
- <span data-ttu-id="79ccf-369">**Identifiering av säkra länkar**</span><span class="sxs-lookup"><span data-stu-id="79ccf-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="79ccf-370">Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällna listan.</span><span class="sxs-lookup"><span data-stu-id="79ccf-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="79ccf-371">**Exportera:**</span><span class="sxs-lookup"><span data-stu-id="79ccf-371">**Export**:</span></span>

<span data-ttu-id="79ccf-372">När du **klickar** på Exportera **kan** du välja något av följande värden under Alternativ:</span><span class="sxs-lookup"><span data-stu-id="79ccf-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="79ccf-373">**Sammanfattning (med data för de senaste 90 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="79ccf-374">**Information (med data för de senaste 30 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="79ccf-375">Välj **ett** område under Datum och klicka sedan på **Använd.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="79ccf-376">Data för de aktuella filtren exporteras till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="79ccf-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="79ccf-377">Varje exporterad CSV-fil är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="79ccf-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="79ccf-378">Om informationen innehåller fler än 150 000 rader skapas flera CSV-filer.</span><span class="sxs-lookup"><span data-stu-id="79ccf-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="79ccf-379">Teknisk vy i statusrapporten för E-postflöde</span><span class="sxs-lookup"><span data-stu-id="79ccf-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="79ccf-380">Rapport om skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="79ccf-380">Sent and received email report</span></span>

<span data-ttu-id="79ccf-381">Rapporten **skickad och mottagen** e-post är en smart rapport som visar information om inkommande och utgående e-post, inklusive identifiering av skräppost, skadlig programvara och e-post som identifieras som "bra".</span><span class="sxs-lookup"><span data-stu-id="79ccf-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="79ccf-382">Skillnaden mellan den här rapporten och [statusrapporten](#mailflow-status-report) för E-postflöde är: den här rapporten innehåller inte data om meddelanden som blockeras av Edge Protection. Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="79ccf-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="79ccf-383">Mängdvyn och detaljvyn för rapporten tillåter 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="79ccf-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="79ccf-384">Om du vill visa rapporten öppnar du [säkerhets- & Efterlevnadscenter,](https://protection.office.com)går till instrumentpanelen Rapporter och väljer  \>  **Skickad och mottagen e-post.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="79ccf-385">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="79ccf-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget för skickad och mottagen e-post på instrumentpanelen Rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="79ccf-387">Rapportvy för rapporten Skickat och mottaget e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="79ccf-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="79ccf-388">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="79ccf-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="79ccf-389">**Dela upp efter: Typ:** I diagrammet visas alla tillgängliga kategorier:</span><span class="sxs-lookup"><span data-stu-id="79ccf-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="79ccf-390">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="79ccf-390">**Total**</span></span>
  - <span data-ttu-id="79ccf-391">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="79ccf-391">**Good mail**</span></span>
  - <span data-ttu-id="79ccf-392">**Skadlig programvara (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="79ccf-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="79ccf-393">**Identifiering av skräppost**</span><span class="sxs-lookup"><span data-stu-id="79ccf-393">**Spam detections**</span></span>
  - <span data-ttu-id="79ccf-394">**Regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="79ccf-394">**Rule messages**</span></span>
  - <span data-ttu-id="79ccf-395">**Avancerad skadlig programvara** (Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="79ccf-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="79ccf-396">När du hovrar över en dag (datapunkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="79ccf-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vyn Typ i rapporten Skickat och mottaget e-postmeddelande](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="79ccf-398">**Dela upp efter: Riktning:** Diagrammet visar **data för summa,** **inkommande** **och utgående** trafik.</span><span class="sxs-lookup"><span data-stu-id="79ccf-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="79ccf-399">När du hovrar över en dag (datapunkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="79ccf-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vyn Riktning i rapporten Skickat och mottaget e-postmeddelande](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="79ccf-401">**Öka detalj detalj för** \> **Skadlig programvara (skadlig kod)**: Med det här valet kommer du till identifieringar av skadlig programvara [i e-postrapporten.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="79ccf-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="79ccf-402">**Öka detalj detalj för** \> **Identifiering av skräppost)**: Det här valet tar dig till rapporten [Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="79ccf-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="79ccf-403">Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="79ccf-404">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="79ccf-405">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="79ccf-405">Direction values</span></span>
- <span data-ttu-id="79ccf-406">Typvärden</span><span class="sxs-lookup"><span data-stu-id="79ccf-406">Type values</span></span>

<span data-ttu-id="79ccf-407">Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="79ccf-408">Tabellvyn Information för rapporten skickat och mottaget e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="79ccf-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="79ccf-409">Om du **klickar på tabellen Visa** information i tabellen Dela upp **efter:** Riktning eller Dela upp **efter:** Riktningsvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="79ccf-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="79ccf-410">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-410">**Date (UTC)**</span></span>
- <span data-ttu-id="79ccf-411">**Typ**</span><span class="sxs-lookup"><span data-stu-id="79ccf-411">**Type**</span></span>
- <span data-ttu-id="79ccf-412">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="79ccf-412">**Direction**</span></span>
- <span data-ttu-id="79ccf-413">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="79ccf-413">**Message count**</span></span>

<span data-ttu-id="79ccf-414">Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="79ccf-415">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="79ccf-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="79ccf-416">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="79ccf-416">Direction values</span></span>
- <span data-ttu-id="79ccf-417">Typvärden</span><span class="sxs-lookup"><span data-stu-id="79ccf-417">Type values</span></span>

<span data-ttu-id="79ccf-418">Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="79ccf-419">Rapport om de viktigaste avsändarna och mottagarna</span><span class="sxs-lookup"><span data-stu-id="79ccf-419">Top senders and recipients report</span></span>

<span data-ttu-id="79ccf-420">Rapporten **De bästa avsändarna och mottagarna** är ett cirkeldiagram som visar dina mest populära e-postavsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="79ccf-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="79ccf-421">Om du vill visa rapporten öppnar [du säkerhets- &](https://protection.office.com)Efterlevnadscenter, går till **instrumentpanelen** Rapporter \>  och väljer De **främsta avsändarna och mottagarna.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="79ccf-422">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="79ccf-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget för de bästa avsändarna och mottagarna på instrumentpanelen Rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="79ccf-424">Rapportvy för rapporten Mest om avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="79ccf-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="79ccf-425">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="79ccf-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="79ccf-426">**Visa data för \> de viktigaste e-postavsändarna**</span><span class="sxs-lookup"><span data-stu-id="79ccf-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="79ccf-427">**Visa data för de \> viktigaste e-postmottagarna**</span><span class="sxs-lookup"><span data-stu-id="79ccf-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="79ccf-428">**Visa data för \> de viktigaste skräppostmottagarna**</span><span class="sxs-lookup"><span data-stu-id="79ccf-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="79ccf-429">**Visa data för \> Populära mottagare av skadlig programvara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="79ccf-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="79ccf-430">**Visa data för \> de viktigaste mottagarna av skadlig programvara (Defender för Office 365)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="79ccf-431">Sammansättning av cirkeldiagrammet ändras baserat på dessa val.</span><span class="sxs-lookup"><span data-stu-id="79ccf-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="79ccf-432">När du hovrar över en kil i cirkeldiagrammet visas antalet meddelanden som skickats eller tagits emot.</span><span class="sxs-lookup"><span data-stu-id="79ccf-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="79ccf-433">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram i rapportvyn i rapporten De största avsändarna och mottagarna](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="79ccf-435">Tabellvyn Information för rapporten om de viktigaste avsändarna och mottagaren</span><span class="sxs-lookup"><span data-stu-id="79ccf-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="79ccf-436">Om du **klickar på Tabellen** Visa information beror den information som visas på det diagram som du visade:</span><span class="sxs-lookup"><span data-stu-id="79ccf-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="79ccf-437">**Visa data för \> de viktigaste e-postavsändarna**</span><span class="sxs-lookup"><span data-stu-id="79ccf-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="79ccf-438">**Mest populära e-postavsändare**</span><span class="sxs-lookup"><span data-stu-id="79ccf-438">**Top mail senders**</span></span>
  - <span data-ttu-id="79ccf-439">**Antal**</span><span class="sxs-lookup"><span data-stu-id="79ccf-439">**Count**</span></span>

- <span data-ttu-id="79ccf-440">**Visa data för de \> viktigaste e-postmottagarna**</span><span class="sxs-lookup"><span data-stu-id="79ccf-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="79ccf-441">**De viktigaste e-postmottagarna**</span><span class="sxs-lookup"><span data-stu-id="79ccf-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="79ccf-442">**Antal**</span><span class="sxs-lookup"><span data-stu-id="79ccf-442">**Count**</span></span>

- <span data-ttu-id="79ccf-443">**Visa data för \> de viktigaste skräppostmottagarna**</span><span class="sxs-lookup"><span data-stu-id="79ccf-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="79ccf-444">**Populära mottagare av skräppost**</span><span class="sxs-lookup"><span data-stu-id="79ccf-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="79ccf-445">**Antal**</span><span class="sxs-lookup"><span data-stu-id="79ccf-445">**Count**</span></span>

- <span data-ttu-id="79ccf-446">**Visa data för \> Populära mottagare av skadlig** programvara (EOP)</span><span class="sxs-lookup"><span data-stu-id="79ccf-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="79ccf-447">**De viktigaste mottagarna av skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="79ccf-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="79ccf-448">**Antal**</span><span class="sxs-lookup"><span data-stu-id="79ccf-448">**Count**</span></span>

- <span data-ttu-id="79ccf-449">**Visa data för \> de viktigaste mottagarna av skadlig programvara (Defender för Office 365)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="79ccf-450">**De viktigaste mottagarna av skadlig programvara (Defender för Office 365)**</span><span class="sxs-lookup"><span data-stu-id="79ccf-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="79ccf-451">**Antal**</span><span class="sxs-lookup"><span data-stu-id="79ccf-451">**Count**</span></span>

<span data-ttu-id="79ccf-452">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="79ccf-453">Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**</span><span class="sxs-lookup"><span data-stu-id="79ccf-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="79ccf-454">Vilka behörigheter krävs för att visa de här rapporterna?</span><span class="sxs-lookup"><span data-stu-id="79ccf-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="79ccf-455">För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Säkerhets- och & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="79ccf-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="79ccf-456">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="79ccf-456">**Organization Management**</span></span>
- <span data-ttu-id="79ccf-457">**Säkerhetsadministratör**</span><span class="sxs-lookup"><span data-stu-id="79ccf-457">**Security Administrator**</span></span>
- <span data-ttu-id="79ccf-458">**Säkerhetsläsare**</span><span class="sxs-lookup"><span data-stu-id="79ccf-458">**Security Reader**</span></span>
- <span data-ttu-id="79ccf-459">**Global Reader**</span><span class="sxs-lookup"><span data-stu-id="79ccf-459">**Global Reader**</span></span>

<span data-ttu-id="79ccf-460">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="79ccf-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="79ccf-461">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79ccf-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="79ccf-462">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="79ccf-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="79ccf-463">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="79ccf-463">Related topics</span></span>

[<span data-ttu-id="79ccf-464">Smarta rapporter och insikter i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="79ccf-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="79ccf-465">Insikter i e-postflöde i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="79ccf-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="79ccf-466">Visa e-postsäkerhetsrapporter i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="79ccf-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="79ccf-467">Visa rapporter för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="79ccf-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
