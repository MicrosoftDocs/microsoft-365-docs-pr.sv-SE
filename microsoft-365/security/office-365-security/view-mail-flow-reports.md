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
description: Administratörer kan läsa mer om de e-postflödesrapporter som är tillgängliga på instrumentpanelen Rapporter i säkerhets- & efterlevnadscenter.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029483"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="fe414-103">Visa e-postflödesrapporter på instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="fe414-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fe414-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="fe414-104">**Applies to**</span></span>
- [<span data-ttu-id="fe414-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fe414-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fe414-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="fe414-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fe414-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe414-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="fe414-108">De flesta rapporter som beskrivs i det här avsnittet är tillgängliga i administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="fe414-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="fe414-109">Mer information finns i [E-postflödesrapporter i det nya administrationscentret för Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="fe414-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="fe414-110">[Exchange-transportregelrapporten](view-email-security-reports.md#exchange-transport-rule-report) är tillgänglig på Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="fe414-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="fe414-111">Utöver de e-postflödesrapporter som [](mail-flow-insights-v2.md) finns tillgängliga på instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & finns det en mängd andra e-postflödesrapporter på instrumentpanelen Rapporter som hjälper dig att övervaka din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="fe414-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="fe414-112">Om du har nödvändiga [behörigheter kan](#what-permissions-are-needed-to-view-these-reports)du visa de här rapporterna i Säkerhets- [& efterlevnadscenter genom](https://protection.office.com) att gå till **Instrumentpanelen** \> **rapporter.**</span><span class="sxs-lookup"><span data-stu-id="fe414-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="fe414-113">Gå direkt till instrumentpanelen Rapporter genom att öppna <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="fe414-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="fe414-115">Kopplingsrapport</span><span class="sxs-lookup"><span data-stu-id="fe414-115">Connector report</span></span>

<span data-ttu-id="fe414-116">Rapporten **Koppling visar** e-postflödesaktivitet för [inkommande och utgående anslutningar](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) som är konfigurerade för organisationen.</span><span class="sxs-lookup"><span data-stu-id="fe414-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="fe414-117">Om du vill visa rapporten öppnar du [säkerhets- & kompatibilitetscenter](https://protection.office.com), går till **instrumentpanelen** \> **rapporter** och väljer **Kopplingsrapport**.</span><span class="sxs-lookup"><span data-stu-id="fe414-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="fe414-118">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="fe414-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget för kopplingsrapport på instrumentpanelen Rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="fe414-120">Rapportvyn för kopplingsrapporten</span><span class="sxs-lookup"><span data-stu-id="fe414-120">Report view for the Connector report</span></span>

<span data-ttu-id="fe414-121">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="fe414-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="fe414-122">**Visa data efter: E-postflöde:** I det här diagrammet visas antalet inkommande och utgående meddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="fe414-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="fe414-123">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="fe414-123">**Total**</span></span>
  - <span data-ttu-id="fe414-124">**Från Internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="fe414-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="fe414-125">**Till Internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="fe414-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="fe414-126">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="fe414-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="fe414-127">Om du vill isolera data i diagrammet använder du visa data för kontroll **och** väljer ett av dessa alternativ eller All **e-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="fe414-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visa data via e-postflöde i kopplingsrapporten](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="fe414-129">**Visa data efter: TLS-användning:** I det här diagrammet visas procentandelen användning av TLS (Transport Layer Security) för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="fe414-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="fe414-130">Om du vill isolera data i diagrammet använder du **visa data för kontroll** och väljer något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="fe414-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="fe414-131">**Allt e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="fe414-131">**All mail flow**</span></span>
  - <span data-ttu-id="fe414-132">**Från Internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="fe414-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="fe414-133">**Till Internet utan anslutning**</span><span class="sxs-lookup"><span data-stu-id="fe414-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="fe414-134">En specifik koppling som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="fe414-134">A specific connector that you've configured.</span></span>

  ![Visa data efter TLS-användning i kopplingsrapporten](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="fe414-136">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="fe414-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="fe414-137">Detaljtabellvyn för kopplingsrapporten</span><span class="sxs-lookup"><span data-stu-id="fe414-137">Details table view for the Connector report</span></span>

<span data-ttu-id="fe414-138">Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="fe414-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fe414-139">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fe414-139">**Date**</span></span>
- <span data-ttu-id="fe414-140">**Kopplingsriktning och -namn**</span><span class="sxs-lookup"><span data-stu-id="fe414-140">**Connector direction and name**</span></span>
- <span data-ttu-id="fe414-141">**Kopplingstyp**</span><span class="sxs-lookup"><span data-stu-id="fe414-141">**Connector type**</span></span>
- <span data-ttu-id="fe414-142">**Tvingad TLS?**: Värdet **Sant** eller **Falskt.**</span><span class="sxs-lookup"><span data-stu-id="fe414-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="fe414-143">**Ingen TLS** (procent)</span><span class="sxs-lookup"><span data-stu-id="fe414-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="fe414-144">**TLS 1,0** (procent)</span><span class="sxs-lookup"><span data-stu-id="fe414-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="fe414-145">**TLS 1,1** (procent)</span><span class="sxs-lookup"><span data-stu-id="fe414-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="fe414-146">**TLS 1,2** (procent)</span><span class="sxs-lookup"><span data-stu-id="fe414-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="fe414-147">**Volym**: Antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="fe414-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="fe414-148">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="fe414-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fe414-149">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="fe414-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="fe414-150">Rapport över Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="fe414-150">Exchange transport rule report</span></span>

<span data-ttu-id="fe414-151">I **rapporten Exchange-transportregel** visas effekten av e-postflödesregler (kallas även transportregler) på inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fe414-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="fe414-152">Om du vill visa rapporten öppnar du [säkerhets- &,](https://protection.office.com)går till **instrumentpanelen** \> **Rapporter** och väljer **Exchange-transportregel**.</span><span class="sxs-lookup"><span data-stu-id="fe414-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="fe414-153">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="fe414-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget för Exchange-transportregel på instrumentpanelen Rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="fe414-155">Rapportvy för Exchange-transportregelrapporten</span><span class="sxs-lookup"><span data-stu-id="fe414-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="fe414-156">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="fe414-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="fe414-157">**Visa data efter: Exchange-transportregler** \> **Dela upp efter: Riktning**: I det här diagrammet visas antalet **inkommande** och **utgående** meddelanden som påverkades av transportreglerna.</span><span class="sxs-lookup"><span data-stu-id="fe414-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="fe414-158">**Visa data efter: Exchange-transportregler** \> **Dela upp efter: Allvarlighetsgrad**:  I det här diagrammet visas antalet meddelanden med hög allvarlighetsgrad och medel allvarlighetsgrad samt låg **allvarlighetsgrad.**</span><span class="sxs-lookup"><span data-stu-id="fe414-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="fe414-159">Du anger allvarlighetsnivån som en åtgärd i regeln **(Granska** denna regel med allvarlighetsnivå eller _AngeGranskningSalla_).</span><span class="sxs-lookup"><span data-stu-id="fe414-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="fe414-160">Mer information finns i Åtgärder för [e-postflödesregel i Exchange Online.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="fe414-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="fe414-161">**Visa data efter: DLP Exchange-transportregler** \> **Dela upp efter: Riktning**: I det  här diagrammet visas antalet **inkommande** och utgående meddelanden som påverkades av DLP-transportregler (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="fe414-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="fe414-162">Du kan förfina diagrammet ytterligare genom att välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="fe414-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="fe414-163">**Visa data för: Alla DLP-transportregler**</span><span class="sxs-lookup"><span data-stu-id="fe414-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="fe414-164">**Visa data för: Komprometterade användare**</span><span class="sxs-lookup"><span data-stu-id="fe414-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="fe414-165">**Visa data för: Låg mängd innehåll som identifierats av U.S. Act**</span><span class="sxs-lookup"><span data-stu-id="fe414-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="fe414-166">**Visa data efter: DLP Exchange-transportregler** \> **Dela upp efter: Riktning**: I  den här vyn visas  antalet meddelanden med hög allvarlighetsgrad och medel allvarlighetsgrad och meddelanden med låg allvarlighetsgrad som påverkades av DLP-transportregler. </span><span class="sxs-lookup"><span data-stu-id="fe414-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="fe414-167">Du kan förfina diagrammet ytterligare genom att välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="fe414-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="fe414-168">**Visa data för: Alla DLP-transportregler**</span><span class="sxs-lookup"><span data-stu-id="fe414-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="fe414-169">**Visa data för: Komprometterade användare**</span><span class="sxs-lookup"><span data-stu-id="fe414-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="fe414-170">**Visa data för: Låg mängd innehåll som identifierats av U.S. Act**</span><span class="sxs-lookup"><span data-stu-id="fe414-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="fe414-171">Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fe414-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="fe414-172">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fe414-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="fe414-173">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="fe414-173">Direction values</span></span>
- <span data-ttu-id="fe414-174">Värden för allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="fe414-174">Severity values</span></span>

![Rapportvyn i rapporten Exchange-transportregel](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="fe414-176">Detaljtabellvyn för Exchange-transportregelrapporten</span><span class="sxs-lookup"><span data-stu-id="fe414-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="fe414-177">Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:</span><span class="sxs-lookup"><span data-stu-id="fe414-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fe414-178">**Visa data efter: Exchange-transportregler:**</span><span class="sxs-lookup"><span data-stu-id="fe414-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="fe414-179">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fe414-179">**Date**</span></span>
  - <span data-ttu-id="fe414-180">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="fe414-180">**Transport rule**</span></span>
  - <span data-ttu-id="fe414-181">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="fe414-181">**Subject**</span></span>
  - <span data-ttu-id="fe414-182">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="fe414-182">**Sender address**</span></span>
  - <span data-ttu-id="fe414-183">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="fe414-183">**Recipient address**</span></span>
  - <span data-ttu-id="fe414-184">**Allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="fe414-184">**Severity**</span></span>
  - <span data-ttu-id="fe414-185">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="fe414-185">**Direction**</span></span>

- <span data-ttu-id="fe414-186">**Visa data efter: DLP-transportregler i Exchange:**</span><span class="sxs-lookup"><span data-stu-id="fe414-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="fe414-187">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fe414-187">**Date**</span></span>
  - <span data-ttu-id="fe414-188">**DLP-princip**</span><span class="sxs-lookup"><span data-stu-id="fe414-188">**DLP policy**</span></span>
  - <span data-ttu-id="fe414-189">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="fe414-189">**Transport rule**</span></span>
  - <span data-ttu-id="fe414-190">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="fe414-190">**Subject**</span></span>
  - <span data-ttu-id="fe414-191">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="fe414-191">**Sender address**</span></span>
  - <span data-ttu-id="fe414-192">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="fe414-192">**Recipient address**</span></span>
  - <span data-ttu-id="fe414-193">**Allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="fe414-193">**Severity**</span></span>
  - <span data-ttu-id="fe414-194">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="fe414-194">**Direction**</span></span>

<span data-ttu-id="fe414-195">Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fe414-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fe414-196">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fe414-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="fe414-197">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="fe414-197">Direction values</span></span>
- <span data-ttu-id="fe414-198">Värden för allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="fe414-198">Severity values</span></span>

<span data-ttu-id="fe414-199">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="fe414-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="fe414-200">Vidarebefordransrapport</span><span class="sxs-lookup"><span data-stu-id="fe414-200">Forwarding report</span></span>

<span data-ttu-id="fe414-201">I **vidarebefordransrapporten** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online postlådor.</span><span class="sxs-lookup"><span data-stu-id="fe414-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="fe414-202">Vidarebefordrade meddelanden kan vara en säkerhets- eller efterlevnadsrisk och kan ange ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="fe414-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="fe414-203">Om du vill visa rapporten öppnar du [säkerhets- & Kompatibilitetscenter](https://protection.office.com), går till  \> **instrumentpanelen rapporter** och väljer **Vidarebefordransrapport.**</span><span class="sxs-lookup"><span data-stu-id="fe414-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="fe414-204">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="fe414-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget för vidarebefordransrapport på instrumentpanelen Rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="fe414-206">Rapportvy för vidarebefordransrapporten</span><span class="sxs-lookup"><span data-stu-id="fe414-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="fe414-207">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="fe414-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fe414-208">**Visa data för: Metoder för vidarebefordran:** Följande metoder visas:</span><span class="sxs-lookup"><span data-stu-id="fe414-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="fe414-209">**Transportregel:** Kallas även [e-postflödesregler.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="fe414-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="fe414-210">**Postlåderegel:** Kallas även [inkorgsregler.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="fe414-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vy över vidarebefordransmetoder i rapporten om vidarebefordran](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="fe414-212">**Visa data för: Domäner för vidarebefordran:** I den här vyn visas de mottagardomäner som är destinationer för vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="fe414-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vy för vidarebefordran av domäner i rapporten Om vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="fe414-214">**Visa data för: Vidarebefordrare:** Följande vidarebefordrare visas:</span><span class="sxs-lookup"><span data-stu-id="fe414-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="fe414-215">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="fe414-215">**Transport rule**</span></span>
  - <span data-ttu-id="fe414-216">Postlådan som innehåller regeln för vidarebefordran av inkorg.</span><span class="sxs-lookup"><span data-stu-id="fe414-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vyn Vidarebefordrare i rapporten Vidarebefordran](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="fe414-218">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="fe414-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="fe414-219">Detaljtabellvyn för vidarebefordransrapporten</span><span class="sxs-lookup"><span data-stu-id="fe414-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="fe414-220">Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="fe414-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fe414-221">**Vidarebefordrare:** **Värdetransportregeln eller** postlådan som innehåller vidare vidarebefordrans inkorgsregeln.</span><span class="sxs-lookup"><span data-stu-id="fe414-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="fe414-222">**Vidarebefordranstyp:** **Värdepostlåderegel** eller **Transportregel.**</span><span class="sxs-lookup"><span data-stu-id="fe414-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="fe414-223">**Mottagarens namn**</span><span class="sxs-lookup"><span data-stu-id="fe414-223">**Recipient name**</span></span>
- <span data-ttu-id="fe414-224">**Mottagardomän**</span><span class="sxs-lookup"><span data-stu-id="fe414-224">**Recipient domain**</span></span>
- <span data-ttu-id="fe414-225">**Information:** Det här är GUID-värdet för e-postflödesregeln eller RuleIdentity-värdet för inkorgsregeln.</span><span class="sxs-lookup"><span data-stu-id="fe414-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="fe414-226">**Antal**</span><span class="sxs-lookup"><span data-stu-id="fe414-226">**Count**</span></span>
- <span data-ttu-id="fe414-227">**Första forwardsdatumet**</span><span class="sxs-lookup"><span data-stu-id="fe414-227">**First forward date**</span></span>

<span data-ttu-id="fe414-228">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="fe414-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fe414-229">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="fe414-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="fe414-230">Statusrapport för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="fe414-230">Mailflow status report</span></span>

<span data-ttu-id="fe414-231">Statusrapporten **E-postflöde** liknar rapporten [Skickad](#sent-and-received-email-report)och mottagen e-post, med ytterligare information om tillåtna eller blockerade e-postmeddelanden i kanten.</span><span class="sxs-lookup"><span data-stu-id="fe414-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="fe414-232">Det här är den enda rapporten som innehåller information om gränsskydd och som visar hur mycket e-post som blockeras innan den tillåts till tjänsten för utvärdering av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="fe414-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="fe414-233">Det är viktigt att vara säker på att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="fe414-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="fe414-234">Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter](https://protection.office.com), går till  \> **instrumentpanelen Rapporter** och väljer **Statusrapport för e-postflöde.**</span><span class="sxs-lookup"><span data-stu-id="fe414-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="fe414-235">Gå direkt till statusrapporten **E-postflöde genom att** öppna <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="fe414-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget för statusrapport för e-postflöde på instrumentpanelen Rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="fe414-237">Typvy för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="fe414-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="fe414-238">När du öppnar rapporten är **fliken Typ** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="fe414-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="fe414-239">Som standard innehåller den här vyn ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fe414-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="fe414-240">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="fe414-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="fe414-241">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="fe414-241">**Direction**:</span></span>

  - <span data-ttu-id="fe414-242">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="fe414-242">**Inbound**</span></span>
  - <span data-ttu-id="fe414-243">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="fe414-243">**Outbound**</span></span>
  - <span data-ttu-id="fe414-244">**Årsorganisation**: det här antalet gäller meddelanden inom en klientorganisation, dvs.</span><span class="sxs-lookup"><span data-stu-id="fe414-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="fe414-245">sender abc@domain.com skickar till mottagarens xyz@domain.com (räknas separat från **inkommande** **och utgående**)</span><span class="sxs-lookup"><span data-stu-id="fe414-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="fe414-246">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="fe414-246">**Type**:</span></span>

  - <span data-ttu-id="fe414-247">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="fe414-247">**Good mail**</span></span>
  - <span data-ttu-id="fe414-248">**Skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="fe414-248">**Malware**</span></span>
  - <span data-ttu-id="fe414-249">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="fe414-249">**Spam**</span></span>
  - <span data-ttu-id="fe414-250">**Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="fe414-250">**Edge protection**</span></span>
  - <span data-ttu-id="fe414-251">**Regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="fe414-251">**Rule messages**</span></span>
  - <span data-ttu-id="fe414-252">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="fe414-252">**Phishing email**</span></span>

<span data-ttu-id="fe414-253">Diagrammet ordnas efter **typvärdena.**</span><span class="sxs-lookup"><span data-stu-id="fe414-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="fe414-254">Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="fe414-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="fe414-255">Datatabellen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="fe414-255">The data table contains the following information:</span></span>

- <span data-ttu-id="fe414-256">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="fe414-256">**Direction**</span></span>
- <span data-ttu-id="fe414-257">**Typ**</span><span class="sxs-lookup"><span data-stu-id="fe414-257">**Type**</span></span>
- <span data-ttu-id="fe414-258">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="fe414-258">**24 hours**</span></span>
- <span data-ttu-id="fe414-259">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="fe414-259">**3 days**</span></span>
- <span data-ttu-id="fe414-260">**7 dagar**</span><span class="sxs-lookup"><span data-stu-id="fe414-260">**7 days**</span></span>
- <span data-ttu-id="fe414-261">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="fe414-261">**15 days**</span></span>
- <span data-ttu-id="fe414-262">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="fe414-262">**30 days**</span></span>

<span data-ttu-id="fe414-263">Om du klickar **på Välj en kategori för mer** information kan du välja bland följande värden:</span><span class="sxs-lookup"><span data-stu-id="fe414-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="fe414-264">**Nätfiskemeddelande:** Det här valet tar dig till [rapporten status för skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="fe414-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="fe414-265">**Skadlig programvara i** e-post: Det här valet tar dig till [statusrapporten Skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="fe414-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="fe414-266">**Identifiering av skräppost:** Det här valet tar dig till [rapporten Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="fe414-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="fe414-267">**Edge blockerad skräppost:** Det här valet tar dig till rapporten [Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="fe414-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="fe414-268">**Exportera:**</span><span class="sxs-lookup"><span data-stu-id="fe414-268">**Export**:</span></span>

<span data-ttu-id="fe414-269">I detaljvyn kan du bara exportera data under en dag.</span><span class="sxs-lookup"><span data-stu-id="fe414-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="fe414-270">Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="fe414-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="fe414-271">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="fe414-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="fe414-272">Om dagens data innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="fe414-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Typvy i statusrapporten För e-postflöde](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="fe414-274">Riktningsvyn för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="fe414-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="fe414-275">Om du klickar **på** fliken Riktning används samma standardfilter **från** vyn Typ.</span><span class="sxs-lookup"><span data-stu-id="fe414-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="fe414-276">Diagrammet är ordnat efter **riktningsvärden.**</span><span class="sxs-lookup"><span data-stu-id="fe414-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="fe414-277">Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="fe414-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="fe414-278">Samma filter från **vyn** Typ används.</span><span class="sxs-lookup"><span data-stu-id="fe414-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="fe414-279">Datatabellen innehåller samma information från **vyn** Typ.</span><span class="sxs-lookup"><span data-stu-id="fe414-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="fe414-280">Vyn **Välj en kategori för mer information** om tillgängliga val och beteenden är samma som **vyn** Typ.</span><span class="sxs-lookup"><span data-stu-id="fe414-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="fe414-281">**Exportera:**</span><span class="sxs-lookup"><span data-stu-id="fe414-281">**Export**:</span></span>

<span data-ttu-id="fe414-282">I detaljvyn kan du bara exportera data under en dag.</span><span class="sxs-lookup"><span data-stu-id="fe414-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="fe414-283">Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="fe414-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="fe414-284">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="fe414-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="fe414-285">Om dagens data innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="fe414-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Riktningsvyn i statusrapporten E-postflöde](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="fe414-287">Trattvyn för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="fe414-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="fe414-288">I **vyn Tratt** kan du se hur Microsofts skyddsfunktioner för e-posthot filtrerar inkommande och utgående e-post i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fe414-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="fe414-289">Här finns information om totalt antal e-postmeddelanden och hur de konfigurerade funktionerna för skydd mot hot, inklusive gränsskydd, skydd mot skadlig programvara, skydd mot nätfiske, skräppost och förfalskning, påverkar antalet.</span><span class="sxs-lookup"><span data-stu-id="fe414-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="fe414-290">Om du klickar **på fliken Tratt** innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fe414-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="fe414-291">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="fe414-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="fe414-292">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="fe414-292">**Direction**:</span></span>

  - <span data-ttu-id="fe414-293">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="fe414-293">**Inbound**</span></span>
  - <span data-ttu-id="fe414-294">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="fe414-294">**Outbound**</span></span>
  - <span data-ttu-id="fe414-295">**Årsorganisation:** Antalet är för meddelanden som skickas inom en klientorganisation. det vill säga att avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från inkommande och utgående).</span><span class="sxs-lookup"><span data-stu-id="fe414-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="fe414-296">För aggregerad vy och datatabellvy kan du filtrera i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="fe414-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="fe414-297">Om du klickar **på** Filter kan du filtrera både diagrammet och datatabellen.</span><span class="sxs-lookup"><span data-stu-id="fe414-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="fe414-298">I det här diagrammet visas antalet e-postmeddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="fe414-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="fe414-299">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="fe414-299">**Total email**</span></span>
- <span data-ttu-id="fe414-300">**E-post efter gränsskydd**</span><span class="sxs-lookup"><span data-stu-id="fe414-300">**Email after edge protection**</span></span>
- <span data-ttu-id="fe414-301">**E-post efter skadlig programvara, rykte, filtypsblockering**</span><span class="sxs-lookup"><span data-stu-id="fe414-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="fe414-302">**E-post efter hot, URL-rykte, varumärkespersonifiering, skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="fe414-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="fe414-303">**E-post efter skräppost, massfiltrering**</span><span class="sxs-lookup"><span data-stu-id="fe414-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="fe414-304">**E-post efter personifiering av användare och domän**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fe414-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="fe414-305">**E-post efter fil och URL detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fe414-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="fe414-306">**E-post identifierades som därefter skydd efter leverans (URL klicka på tidsskydd)**</span><span class="sxs-lookup"><span data-stu-id="fe414-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="fe414-307"><sup>1</sup> Defender för Office 365 endast</span><span class="sxs-lookup"><span data-stu-id="fe414-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="fe414-308">Om du vill visa e-post som filtrerats efter EOP eller Defender Office 365 separat klickar du på värdet i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="fe414-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="fe414-309">Datatabellen innehåller följande information, visad i fallande datumordning:</span><span class="sxs-lookup"><span data-stu-id="fe414-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="fe414-310">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fe414-310">**Date**</span></span>
- <span data-ttu-id="fe414-311">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="fe414-311">**Total email**</span></span>
- <span data-ttu-id="fe414-312">**Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="fe414-312">**Edge protection**</span></span>
- <span data-ttu-id="fe414-313">**Skydd mot skadlig programvara, rykte för filen, filtypsblockering:**</span><span class="sxs-lookup"><span data-stu-id="fe414-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="fe414-314">**Rykte:** Meddelanden filtrerade på grund av identifiering av en bifogad fil av andra Microsoft-kunder.</span><span class="sxs-lookup"><span data-stu-id="fe414-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="fe414-315">**Filtypsblock:** Meddelanden filtreras på grund av vilken typ av skadlig fil som identifieras i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="fe414-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="fe414-316">**Antifras, URL-rykte, varumärkespersonifiering, skydd mot förfalskning:**</span><span class="sxs-lookup"><span data-stu-id="fe414-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="fe414-317">**URL-rykte:** Meddelanden filtreras på grund av identifiering av URL-adressen av andra Microsoft-kunder.</span><span class="sxs-lookup"><span data-stu-id="fe414-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="fe414-318">**Profilering:** Meddelanden filtrerade på grund av meddelanden från välkända varumärkespersonifieringsavsändare.</span><span class="sxs-lookup"><span data-stu-id="fe414-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="fe414-319">**Skydd mot förfalskning:** Meddelanden filtreras på grund av ett meddelande som försöker kapa en domän som mottagaren tillhör eller en domän som meddelandets avsändare inte äger.</span><span class="sxs-lookup"><span data-stu-id="fe414-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="fe414-320">**Skräppostskydd, massfiltrering:**</span><span class="sxs-lookup"><span data-stu-id="fe414-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="fe414-321">**Massfiltrering:** Meddelanden filtreras på grund av ett försök att leverera massutskick till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="fe414-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="fe414-322">**Användar- och domänpersonifiering (Defender för Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="fe414-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="fe414-323">**Personifiering för användare:** Filtrerade meddelanden på grund av ett försök att utge sig för att vara en användare (meddelandeavsändare) som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="fe414-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="fe414-324">**Domänpersonifiering:** Meddelanden filtrerade på grund av ett försök att utge sig för att vara en domän som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="fe414-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="fe414-325">**Detonation av fil och URL (Defender för Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="fe414-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="fe414-326">**Detonation för filer:** Meddelanden filtrerade efter Valv princip för bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="fe414-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="fe414-327">**URL-detonation**: Meddelande filtrerat av Valv princip för länkar.</span><span class="sxs-lookup"><span data-stu-id="fe414-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="fe414-328">**Post-delivery protection and ZAP (ATP) or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span><span class="sxs-lookup"><span data-stu-id="fe414-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="fe414-329">Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällklienten.</span><span class="sxs-lookup"><span data-stu-id="fe414-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="fe414-330">**Exportera:**</span><span class="sxs-lookup"><span data-stu-id="fe414-330">**Export**:</span></span>

<span data-ttu-id="fe414-331">När du har **klickat** **på Exportera** under Alternativ kan du välja något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="fe414-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="fe414-332">**Sammanfattning (med data för de senaste 90 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="fe414-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="fe414-333">**Information (med data för de senaste 30 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="fe414-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="fe414-334">Välj **ett** område under Datum och klicka sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="fe414-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="fe414-335">Data för de aktuella filtren exporteras till en .csv fil.</span><span class="sxs-lookup"><span data-stu-id="fe414-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="fe414-336">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="fe414-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="fe414-337">Om informationen innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="fe414-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Trattvyn i statusrapporten För e-postflöde](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="fe414-339">Tech view for the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="fe414-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="fe414-340">**Tech-vyn** liknar vyn **Tratt, med** mer detaljerad information om de konfigurerade funktionerna för skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="fe414-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="fe414-341">Från diagrammet kan du se hur meddelanden kategoriseras i olika faser av skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="fe414-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="fe414-342">Om du klickar **på fliken Teknisk** vy innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fe414-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="fe414-343">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="fe414-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="fe414-344">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="fe414-344">**Direction**:</span></span>

  - <span data-ttu-id="fe414-345">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="fe414-345">**Inbound**</span></span>
  - <span data-ttu-id="fe414-346">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="fe414-346">**Outbound**</span></span>
  - <span data-ttu-id="fe414-347">**Årsorganisation**: det här antalet gäller meddelanden inom en klientorganisation, dvs.</span><span class="sxs-lookup"><span data-stu-id="fe414-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="fe414-348">sender abc@domain.com skickar till mottagarens xyz@domain.com (räknas separat från inkommande och utgående)</span><span class="sxs-lookup"><span data-stu-id="fe414-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="fe414-349">För aggregerad vy och datatabellvy kan du filtrera i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="fe414-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="fe414-350">Om du klickar **på** Filter kan du filtrera både diagrammet och datatabellen.</span><span class="sxs-lookup"><span data-stu-id="fe414-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="fe414-351">Det här diagrammet visar meddelanden ordnade i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="fe414-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="fe414-352">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="fe414-352">**Total email**</span></span>
- <span data-ttu-id="fe414-353">**Tillåt i Edge** **och Filtrerad Edge**</span><span class="sxs-lookup"><span data-stu-id="fe414-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="fe414-354">**Inte skadlig programvara**, **Valv identifiering av bifogade filer,** identifiering av skadlig <sup>\*</sup> **programvara** och **regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="fe414-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="fe414-355">**Inte phish**, **DMARC-fel,** **personidentifiering,** **förfalskning och** **phish-identifiering**</span><span class="sxs-lookup"><span data-stu-id="fe414-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="fe414-356">**Ingen identifiering med URL-detonation och** **URL-detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fe414-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="fe414-357">**Inte** skräppost </span><span class="sxs-lookup"><span data-stu-id="fe414-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="fe414-358">**Icke-skadlig e-post** **, Valv identifiering av länkar** och <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="fe414-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="fe414-359"><sup>\*</sup>Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fe414-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="fe414-360">När du hovrar över en kategori i diagrammet visas antalet meddelanden i den kategorin.</span><span class="sxs-lookup"><span data-stu-id="fe414-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="fe414-361">Datatabellen innehåller följande information, visad i fallande datumordning:</span><span class="sxs-lookup"><span data-stu-id="fe414-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="fe414-362">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fe414-362">**Date**</span></span>
- <span data-ttu-id="fe414-363">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="fe414-363">**Total email**</span></span>
- <span data-ttu-id="fe414-364">**Edge filtrerad**</span><span class="sxs-lookup"><span data-stu-id="fe414-364">**Edge filtered**</span></span>
- <span data-ttu-id="fe414-365">**Motor mot skadlig programvara, Valv bifogade filer, regel filtrerad:**</span><span class="sxs-lookup"><span data-stu-id="fe414-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="fe414-366">**Regel filtrerad:** Meddelanden filtrerade på grund av e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="fe414-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="fe414-367">**DMARC, personifiering, förfalskning, nätfiske filtrerat:**</span><span class="sxs-lookup"><span data-stu-id="fe414-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="fe414-368">**DMARC:** Meddelanden filtreras på grund av att meddelandet inte klarar sin DMARC-autentiseringskontroll.</span><span class="sxs-lookup"><span data-stu-id="fe414-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="fe414-369">**Identifiering av URL-adresser**</span><span class="sxs-lookup"><span data-stu-id="fe414-369">**URL detonation detection**</span></span>
- <span data-ttu-id="fe414-370">**Skräppostskydd filtreras**</span><span class="sxs-lookup"><span data-stu-id="fe414-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="fe414-371">**ZAP har tagits bort**</span><span class="sxs-lookup"><span data-stu-id="fe414-371">**ZAP removed**</span></span>
- <span data-ttu-id="fe414-372">**Identifiering av Valv länkar**</span><span class="sxs-lookup"><span data-stu-id="fe414-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="fe414-373">Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällklienten.</span><span class="sxs-lookup"><span data-stu-id="fe414-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="fe414-374">**Exportera:**</span><span class="sxs-lookup"><span data-stu-id="fe414-374">**Export**:</span></span>

<span data-ttu-id="fe414-375">När du **klickar** på Exportera **kan** du välja något av följande värden under Alternativ:</span><span class="sxs-lookup"><span data-stu-id="fe414-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="fe414-376">**Sammanfattning (med data för de senaste 90 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="fe414-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="fe414-377">**Information (med data för de senaste 30 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="fe414-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="fe414-378">Välj **ett** område under Datum och klicka sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="fe414-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="fe414-379">Data för de aktuella filtren exporteras till en .csv fil.</span><span class="sxs-lookup"><span data-stu-id="fe414-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="fe414-380">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="fe414-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="fe414-381">Om informationen innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="fe414-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Tech view in the Mailflow status report](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="fe414-383">Rapport om skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="fe414-383">Sent and received email report</span></span>

<span data-ttu-id="fe414-384">Rapporten **Skickad och mottagen** e-post är en smart rapport som visar information om inkommande och utgående e-post, inklusive identifiering av skräppost, skadlig programvara och e-post som identifieras som "bra".</span><span class="sxs-lookup"><span data-stu-id="fe414-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="fe414-385">Skillnaden mellan den här rapporten och [statusrapporten](#mailflow-status-report) E-postflöde är: den här rapporten innehåller inga data om meddelanden som blockeras av edge-skydd.</span><span class="sxs-lookup"><span data-stu-id="fe414-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="fe414-386">**Obs!** Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="fe414-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="fe414-387">Mängdvyn och detaljvyn för rapporten tillåter 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="fe414-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="fe414-388">Om du vill visa rapporten öppnar du [säkerhets- &,](https://protection.office.com)går till **instrumentpanelen** rapporter \> **och** väljer Skickad och **mottagen e-post.**</span><span class="sxs-lookup"><span data-stu-id="fe414-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="fe414-389">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="fe414-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget för skickad och mottagen e-post i instrumentpanelen Rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="fe414-391">Rapportvy för rapporten Skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="fe414-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="fe414-392">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="fe414-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fe414-393">**Dela upp efter: Typ:** Diagrammet visar alla tillgängliga kategorier:</span><span class="sxs-lookup"><span data-stu-id="fe414-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="fe414-394">**Totalt**</span><span class="sxs-lookup"><span data-stu-id="fe414-394">**Total**</span></span>
  - <span data-ttu-id="fe414-395">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="fe414-395">**Good mail**</span></span>
  - <span data-ttu-id="fe414-396">**Skadlig programvara (skydd mot skadlig programvara)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="fe414-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="fe414-397">**Identifiering av skräppost**</span><span class="sxs-lookup"><span data-stu-id="fe414-397">**Spam detections**</span></span>
  - <span data-ttu-id="fe414-398">**Regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="fe414-398">**Rule messages**</span></span>
  - <span data-ttu-id="fe414-399">**Avancerad skadlig programvara** (Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="fe414-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="fe414-400">När du hovrar över en dag (datapunkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="fe414-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Skriv i rapporten Skickad och mottagen e-post](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="fe414-402">**Dela upp efter: Riktning:** Diagrammet visar **data för Totalt,** **Inkommande** **och Utgående.**</span><span class="sxs-lookup"><span data-stu-id="fe414-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="fe414-403">När du hovrar över en dag (datapunkt) i diagrammet kan du se information om den dagen.</span><span class="sxs-lookup"><span data-stu-id="fe414-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Riktningsvyn i rapporten Skickat och mottaget e-postmeddelande](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="fe414-405">**Öka detalj detalj detalj för** \> **Skadlig programvara (skadlig programvara)**: Det här valet tar dig till rapporten [om identifiering av skadlig programvara.](view-email-security-reports.md#malware-detections-report)</span><span class="sxs-lookup"><span data-stu-id="fe414-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="fe414-406">**Öka detalj detalj detalj för** \> **Identifiering av skräppost)**: Det här valet tar dig till [rapporten Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="fe414-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="fe414-407">Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fe414-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fe414-408">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fe414-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="fe414-409">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="fe414-409">Direction values</span></span>
- <span data-ttu-id="fe414-410">Ange värden</span><span class="sxs-lookup"><span data-stu-id="fe414-410">Type values</span></span>

<span data-ttu-id="fe414-411">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="fe414-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="fe414-412">Tabellvyn Information för rapporten Skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="fe414-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="fe414-413">Om du **klickar på Visa informationstabell** i Brytning ned **efter: Riktning** eller Dela upp **efter:** Riktningsvy, visas följande information:</span><span class="sxs-lookup"><span data-stu-id="fe414-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="fe414-414">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="fe414-414">**Date (UTC)**</span></span>
- <span data-ttu-id="fe414-415">**Typ**</span><span class="sxs-lookup"><span data-stu-id="fe414-415">**Type**</span></span>
- <span data-ttu-id="fe414-416">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="fe414-416">**Direction**</span></span>
- <span data-ttu-id="fe414-417">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="fe414-417">**Message count**</span></span>

<span data-ttu-id="fe414-418">Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fe414-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fe414-419">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fe414-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="fe414-420">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="fe414-420">Direction values</span></span>
- <span data-ttu-id="fe414-421">Ange värden</span><span class="sxs-lookup"><span data-stu-id="fe414-421">Type values</span></span>

<span data-ttu-id="fe414-422">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="fe414-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="fe414-423">Rapport om de största avsändarna och mottagarna</span><span class="sxs-lookup"><span data-stu-id="fe414-423">Top senders and recipients report</span></span>

<span data-ttu-id="fe414-424">Rapporten **De bästa avsändarna och mottagarna** är ett cirkeldiagram som visar dina främsta e-postavsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="fe414-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="fe414-425">Om du vill visa rapporten öppnar [du säkerhets- & Efterlevnadscenter](https://protection.office.com), går till **instrumentpanelen** \> **Rapporter** och **väljer De främsta avsändarna och mottagarna.**</span><span class="sxs-lookup"><span data-stu-id="fe414-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="fe414-426">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="fe414-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget för de främsta avsändarna och mottagarna på instrumentpanelen Rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="fe414-428">Rapportvy för rapporten Betrodda avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="fe414-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="fe414-429">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="fe414-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fe414-430">**Visa data för \> de viktigaste e-postavsändarna**</span><span class="sxs-lookup"><span data-stu-id="fe414-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="fe414-431">**Visa data för de \> viktigaste e-postmottagarna**</span><span class="sxs-lookup"><span data-stu-id="fe414-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="fe414-432">**Visa data för \> de mest populära skräppostmottagarna**</span><span class="sxs-lookup"><span data-stu-id="fe414-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="fe414-433">**Visa data för \> Populära mottagare av skadlig programvara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="fe414-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="fe414-434">**Visa data för \> de viktigaste mottagarna av skadlig programvara (Defender för Office 365)**</span><span class="sxs-lookup"><span data-stu-id="fe414-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="fe414-435">Sammansättning av cirkeldiagrammet ändras baserat på dessa val.</span><span class="sxs-lookup"><span data-stu-id="fe414-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="fe414-436">När du hovrar över en kil i cirkeldiagrammet visas antalet meddelanden som skickats eller tagits emot.</span><span class="sxs-lookup"><span data-stu-id="fe414-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="fe414-437">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="fe414-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram i rapportvyn i rapporten Betrodda avsändare och mottagare](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="fe414-439">Tabellvyn Information för rapporten Betrodda avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="fe414-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="fe414-440">Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:</span><span class="sxs-lookup"><span data-stu-id="fe414-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fe414-441">**Visa data för \> de viktigaste e-postavsändarna**</span><span class="sxs-lookup"><span data-stu-id="fe414-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="fe414-442">**De mest populära e-postavsändarna**</span><span class="sxs-lookup"><span data-stu-id="fe414-442">**Top mail senders**</span></span>
  - <span data-ttu-id="fe414-443">**Antal**</span><span class="sxs-lookup"><span data-stu-id="fe414-443">**Count**</span></span>

- <span data-ttu-id="fe414-444">**Visa data för de \> viktigaste e-postmottagarna**</span><span class="sxs-lookup"><span data-stu-id="fe414-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="fe414-445">**De populäraste e-postmottagarna**</span><span class="sxs-lookup"><span data-stu-id="fe414-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="fe414-446">**Antal**</span><span class="sxs-lookup"><span data-stu-id="fe414-446">**Count**</span></span>

- <span data-ttu-id="fe414-447">**Visa data för \> de mest populära skräppostmottagarna**</span><span class="sxs-lookup"><span data-stu-id="fe414-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="fe414-448">**Mest populära skräppostmottagare**</span><span class="sxs-lookup"><span data-stu-id="fe414-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="fe414-449">**Antal**</span><span class="sxs-lookup"><span data-stu-id="fe414-449">**Count**</span></span>

- <span data-ttu-id="fe414-450">**Visa data för \> Populära mottagare av skadlig programvara** (EOP)</span><span class="sxs-lookup"><span data-stu-id="fe414-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="fe414-451">**Populära mottagare av skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="fe414-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="fe414-452">**Antal**</span><span class="sxs-lookup"><span data-stu-id="fe414-452">**Count**</span></span>

- <span data-ttu-id="fe414-453">**Visa data för \> de viktigaste mottagarna av skadlig programvara (Defender för Office 365)**</span><span class="sxs-lookup"><span data-stu-id="fe414-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="fe414-454">**Populära mottagare av skadlig programvara (Defender för Office 365)**</span><span class="sxs-lookup"><span data-stu-id="fe414-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="fe414-455">**Antal**</span><span class="sxs-lookup"><span data-stu-id="fe414-455">**Count**</span></span>

<span data-ttu-id="fe414-456">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="fe414-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fe414-457">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="fe414-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="fe414-458">Vilka behörigheter krävs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="fe414-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="fe414-459">För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Säkerhets- och & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="fe414-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="fe414-460">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="fe414-460">**Organization Management**</span></span>
- <span data-ttu-id="fe414-461">**Säkerhetsadministratör**</span><span class="sxs-lookup"><span data-stu-id="fe414-461">**Security Administrator**</span></span>
- <span data-ttu-id="fe414-462">**Säkerhetsläsare**</span><span class="sxs-lookup"><span data-stu-id="fe414-462">**Security Reader**</span></span>
- <span data-ttu-id="fe414-463">**Global Reader**</span><span class="sxs-lookup"><span data-stu-id="fe414-463">**Global Reader**</span></span>

<span data-ttu-id="fe414-464">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fe414-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fe414-465">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fe414-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fe414-466">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fe414-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe414-467">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fe414-467">Related topics</span></span>

[<span data-ttu-id="fe414-468">Smarta rapporter och insikter i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="fe414-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="fe414-469">Insikter om e-postflöde i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="fe414-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="fe414-470">Visa e-postsäkerhetsrapporter i Säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="fe414-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="fe414-471">Visa rapporter för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fe414-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
