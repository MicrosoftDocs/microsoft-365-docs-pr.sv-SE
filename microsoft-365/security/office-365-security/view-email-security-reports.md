---
title: Visa e-postsäkerhetsrapporter på Microsoft 365 Defender-portalen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Lär dig hur du hittar och använder e-postsäkerhetsrapporter för din organisation. Säkerhetsrapporter för e-post finns tillgängliga på Microsoft 365 Defender-portalen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985309"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="9ada3-104">Visa e-postsäkerhetsrapporter på Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="9ada3-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9ada3-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="9ada3-105">**Applies to**</span></span>
- [<span data-ttu-id="9ada3-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9ada3-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9ada3-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="9ada3-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9ada3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ada3-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9ada3-109">Det finns flera olika rapporter på Microsoft 365 Defender-portalen som hjälper dig se hur säkerhetsfunktioner för e-post, till exempel skydd mot skräppost, skadlig programvara och kryptering i <https://security.microsoft.com> Microsoft 365, skyddar organisationen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="9ada3-110">Om du har [nödvändiga](#what-permissions-are-needed-to-view-these-reports)behörigheter kan du visa de här rapporterna i  Microsoft 365 Defender-portalen genom att gå till Rapporterar \> **e-&-postsamarbete** \> **E& och samarbetsrapporter**.</span><span class="sxs-lookup"><span data-stu-id="9ada3-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="9ada3-111">Om du vill gå direkt **till sidan & e-post och** samarbetsrapporter öppnar du <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="9ada3-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Skicka & via e-post och samarbetsrapporter i Microsoft 365 Defender-portalen](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="9ada3-113">Vissa av rapporterna på sidan **e& och samarbetsrapporter** kräver Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ada3-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9ada3-114">Mer information om de här rapporterna finns [i Visa Defender för Office 365-rapporter i Microsoft 365 Defender-portalen.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="9ada3-115">Rapporter som är relaterade till e-postflödet finns nu i administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="9ada3-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="9ada3-116">Mer information om rapporterna finns i [E-postflödesrapporter i det nya administrationscentret för Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="9ada3-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="9ada3-117">Rapport om komprometterade användare</span><span class="sxs-lookup"><span data-stu-id="9ada3-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="9ada3-118">Den här rapporten är tillgänglig i Microsoft 365-organisationer med Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="9ada3-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="9ada3-119">Det är inte tillgängligt i fristående EOP-organisationer (Exchange Online Protection).</span><span class="sxs-lookup"><span data-stu-id="9ada3-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="9ada3-120">I **rapporten Komprometterade** användare visas antalet användarkonton som har markerats **som misstänkta eller** begränsade **under** de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="9ada3-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="9ada3-121">Konton i något av dessa tillstånd är problematiska eller till och med komprometterade.</span><span class="sxs-lookup"><span data-stu-id="9ada3-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="9ada3-122">Med regelbunden användning kan du använda rapporten för att upptäcka ökningar och även trender i misstänkta eller begränsade konton.</span><span class="sxs-lookup"><span data-stu-id="9ada3-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="9ada3-123">Mer information om komprometterade användare finns i [Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget för komprometterade användare på sidan & för e-post och samarbetsrapporter](../../media/compromised-users-report-widget.png)

<span data-ttu-id="9ada3-125">I mängdvyn visas data för de senaste 90 dagarna och i detaljvyn visas data för de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="9ada3-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="9ada3-126">Om du vill visa rapporten i Microsoft 365 Defender-portalen går du till E-& för  \> **& med** \> **e-& för samarbete.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="9ada3-127">På **komprometterade** användare klickar **du på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="9ada3-128">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="9ada3-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="9ada3-129">När du har **klickat på** Visa information kan du filtrera både diagrammet och detaljtabellen genom att klicka på **Filtrera** och välja ett eller flera av följande värden i den utfäll vy som visas:</span><span class="sxs-lookup"><span data-stu-id="9ada3-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="9ada3-130">**Datum (UTC)**: **Startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="9ada3-131">**Aktivitet**:</span><span class="sxs-lookup"><span data-stu-id="9ada3-131">**Activity**:</span></span>
  - <span data-ttu-id="9ada3-132">**Misstänkt:** Användarkontot har skickat misstänkt e-postmeddelande och riskerar att bli begränsat från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="9ada3-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="9ada3-133">**Begränsad:** Användarkontot har begränsats från att skicka e-post på grund av mycket misstänkta mönster.</span><span class="sxs-lookup"><span data-stu-id="9ada3-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="9ada3-134">När du är klar med filtreringen klickar du på **Använd** eller **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="9ada3-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![Rapportvyn i rapporten Komprometterade användare](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="9ada3-136">I tabellen nedanför diagrammet kan du se följande information:</span><span class="sxs-lookup"><span data-stu-id="9ada3-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="9ada3-137">**Tid då det skapades**</span><span class="sxs-lookup"><span data-stu-id="9ada3-137">**Creation time**</span></span>
- <span data-ttu-id="9ada3-138">**Användar-ID**</span><span class="sxs-lookup"><span data-stu-id="9ada3-138">**User ID**</span></span>
- <span data-ttu-id="9ada3-139">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="9ada3-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="9ada3-140">Rapport över Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="9ada3-140">Exchange transport rule report</span></span>

<span data-ttu-id="9ada3-141">I **rapporten Exchange-transportregel** visas effekten av e-postflödesregler (kallas även transportregler) på inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="9ada3-142">Om du vill visa rapporten i Microsoft 365 Defender-portalen går du till E-& för  \> **& med** \> **e-& för samarbete.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="9ada3-143">Klicka **på Visa information i Exchange-transportregel.** </span><span class="sxs-lookup"><span data-stu-id="9ada3-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="9ada3-144">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="9ada3-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Widget för Exchange-transportregel på sidan E& och samarbetsrapporter](../../media/transport-rule-report-widget.png)

<span data-ttu-id="9ada3-146">När du klickar **på Visa** information är följande diagram och data tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9ada3-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="9ada3-147">**Visa data enligt Exchange-transportregler** \> **Diagram i detalj efter riktning:** Det här diagrammet visar antalet **inkommande** och **utgående** meddelanden som påverkades av e-postflödesregler.</span><span class="sxs-lookup"><span data-stu-id="9ada3-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="9ada3-148">**Visa data enligt Exchange-transportregler** \> **Diagramfördelning efter allvarlighetsgrad**: Det här diagrammet visar antalet meddelanden med hög allvarlighetsgrad, **medel** allvarlighetsgrad och **låg allvarlighetsgrad.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="9ada3-149">Du anger allvarlighetsnivån som en åtgärd i regeln **(Granska** denna regel med allvarlighetsnivå eller _AngeGranskningSalla_).</span><span class="sxs-lookup"><span data-stu-id="9ada3-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="9ada3-150">Mer information finns i Åtgärder för [e-postflödesregel i Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="9ada3-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="9ada3-151">**Visa data efter DLP Exchange-transportregler** \> **Diagramfördelning efter riktning:** Det här diagrammet  visar antalet **inkommande** och utgående meddelanden som påverkades av DLP-e-postflödesregler (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="9ada3-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="9ada3-152">**Visa data efter DLP Exchange-transportregler** \> **Diagramfördelning efter allvarlighetsgrad**: I den här vyn visas  antalet meddelanden med hög allvarlighetsgrad, medel allvarlighetsgrad och låg allvarlighetsgrad som påverkades av DLP-e-postflödesregler.</span><span class="sxs-lookup"><span data-stu-id="9ada3-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="9ada3-153">För **val av Visa data efter Exchange-transportregler** visas följande information i detaljtabellen under diagrammet:</span><span class="sxs-lookup"><span data-stu-id="9ada3-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="9ada3-154">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-154">**Date**</span></span>
- <span data-ttu-id="9ada3-155">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="9ada3-155">**Transport rule**</span></span>
- <span data-ttu-id="9ada3-156">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="9ada3-156">**Subject**</span></span>
- <span data-ttu-id="9ada3-157">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="9ada3-157">**Sender address**</span></span>
- <span data-ttu-id="9ada3-158">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="9ada3-158">**Recipient address**</span></span>
- <span data-ttu-id="9ada3-159">**Allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-159">**Severity**</span></span>
- <span data-ttu-id="9ada3-160">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-160">**Direction**</span></span>

<span data-ttu-id="9ada3-161">När **du väljer visningsdata för DLP-transportregler** för DLP visas följande information i detaljtabellen under diagrammet:</span><span class="sxs-lookup"><span data-stu-id="9ada3-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="9ada3-162">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-162">**Date**</span></span>
- <span data-ttu-id="9ada3-163">**DLP-princip**</span><span class="sxs-lookup"><span data-stu-id="9ada3-163">**DLP policy**</span></span>
- <span data-ttu-id="9ada3-164">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="9ada3-164">**Transport rule**</span></span>
- <span data-ttu-id="9ada3-165">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="9ada3-165">**Subject**</span></span>
- <span data-ttu-id="9ada3-166">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="9ada3-166">**Sender address**</span></span>
- <span data-ttu-id="9ada3-167">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="9ada3-167">**Recipient address**</span></span>
- <span data-ttu-id="9ada3-168">**Allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-168">**Severity**</span></span>
- <span data-ttu-id="9ada3-169">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-169">**Direction**</span></span>

<span data-ttu-id="9ada3-170">Du kan filtrera både diagrammet och informationstabellen genom att klicka på **Filtrera** och markera ett eller flera av följande värden i den utfällo som visas:</span><span class="sxs-lookup"><span data-stu-id="9ada3-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="9ada3-171">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-172">**Riktning**: **Utgående** och **inkommande**</span><span class="sxs-lookup"><span data-stu-id="9ada3-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="9ada3-173">**Allvarlighetsgrad**: **Hög allvarlighetsgrad,** **medel allvarlighetsgrad** och **låg allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Rapportvyn i rapporten Exchange-transportregel](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="9ada3-175">Statusrapport för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="9ada3-175">Mailflow status report</span></span>

<span data-ttu-id="9ada3-176">Statusrapporten **E-postflöde** är en smart rapport som visar information om inkommande och utgående e-post, identifiering av skräppost, skadlig programvara, e-post som identifieras som "bra" och information om e-post som är tillåten eller blockerad i kanten.</span><span class="sxs-lookup"><span data-stu-id="9ada3-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="9ada3-177">Det här är den enda rapporten som innehåller information om gränsskydd och som visar hur mycket e-post som blockeras innan de tillåts till tjänsten för utvärdering av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="9ada3-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="9ada3-178">Det är viktigt att vara säker på att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="9ada3-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="9ada3-179">Om du vill visa rapporten i Microsoft 365 Defender-portalen går du till E-& för  \> **& med** \> **e-& för samarbete.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="9ada3-180">Klicka **på Visa information i statussammanfattningen** för **E-postflöde.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="9ada3-181">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="9ada3-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget för statussammanfattning av e-postflöde på sidan & för e-postsamarbete](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="9ada3-183">Typvy för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="9ada3-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="9ada3-184">När du öppnar rapporten är **fliken Typ** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="9ada3-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="9ada3-185">Som standard innehåller den här vyn ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="9ada3-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="9ada3-186">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="9ada3-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="9ada3-187">**E-postriktning:**</span><span class="sxs-lookup"><span data-stu-id="9ada3-187">**Mail direction**:</span></span>
  - <span data-ttu-id="9ada3-188">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="9ada3-188">**Inbound**</span></span>
  - <span data-ttu-id="9ada3-189">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="9ada3-189">**Outbound**</span></span>
  - <span data-ttu-id="9ada3-190">**Årsorganisation**: det här antalet gäller meddelanden inom en klientorganisation, dvs.</span><span class="sxs-lookup"><span data-stu-id="9ada3-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="9ada3-191">sender abc@domain.com skickar till mottagarens xyz@domain.com (räknas separat från **inkommande** **och utgående**)</span><span class="sxs-lookup"><span data-stu-id="9ada3-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="9ada3-192">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="9ada3-192">**Type**:</span></span>
  - <span data-ttu-id="9ada3-193">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="9ada3-193">**Good mail**</span></span>
  - <span data-ttu-id="9ada3-194">**Skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="9ada3-194">**Malware**</span></span>
  - <span data-ttu-id="9ada3-195">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="9ada3-195">**Spam**</span></span>
  - <span data-ttu-id="9ada3-196">**Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="9ada3-196">**Edge protection**</span></span>
  - <span data-ttu-id="9ada3-197">**Regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="9ada3-197">**Rule messages**</span></span>
  - <span data-ttu-id="9ada3-198">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="9ada3-198">**Phishing email**</span></span>
- <span data-ttu-id="9ada3-199">**Domän:** **Alla**</span><span class="sxs-lookup"><span data-stu-id="9ada3-199">**Domain**: **All**</span></span>

<span data-ttu-id="9ada3-200">Diagrammet ordnas efter **typvärdena.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="9ada3-201">Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="9ada3-202">Datatabellen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="9ada3-202">The data table contains the following information:</span></span>

- <span data-ttu-id="9ada3-203">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-203">**Direction**</span></span>
- <span data-ttu-id="9ada3-204">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9ada3-204">**Type**</span></span>
- <span data-ttu-id="9ada3-205">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-205">**24 hours**</span></span>
- <span data-ttu-id="9ada3-206">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-206">**3 days**</span></span>
- <span data-ttu-id="9ada3-207">**7 dagar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-207">**7 days**</span></span>
- <span data-ttu-id="9ada3-208">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-208">**15 days**</span></span>
- <span data-ttu-id="9ada3-209">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-209">**30 days**</span></span>

<span data-ttu-id="9ada3-210">Om du klickar **på Välj en kategori för mer** information kan du välja bland följande värden:</span><span class="sxs-lookup"><span data-stu-id="9ada3-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="9ada3-211">**Nätfiskemeddelande:** Det här valet tar dig till [rapporten status för skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="9ada3-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="9ada3-212">**Skadlig programvara i** e-post: Det här valet tar dig till [statusrapporten Skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="9ada3-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="9ada3-213">**Identifiering av skräppost:** Det här valet tar dig till [rapporten Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="9ada3-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="9ada3-214">**Edge blockerad skräppost:** Det här valet tar dig till rapporten [Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="9ada3-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="9ada3-215">Exportera i vyn Typ</span><span class="sxs-lookup"><span data-stu-id="9ada3-215">Export from Type view</span></span>

<span data-ttu-id="9ada3-216">I detaljvyn kan du bara exportera data under en dag.</span><span class="sxs-lookup"><span data-stu-id="9ada3-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="9ada3-217">Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="9ada3-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="9ada3-218">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="9ada3-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="9ada3-219">Om dagens data innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="9ada3-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Typvy i statusrapporten För e-postflöde](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="9ada3-221">Riktningsvyn för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="9ada3-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="9ada3-222">Om du klickar **på** fliken Riktning används samma standardfilter **från** vyn Typ.</span><span class="sxs-lookup"><span data-stu-id="9ada3-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="9ada3-223">Diagrammet är ordnat efter **riktningsvärden.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="9ada3-224">Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="9ada3-225">Samma filter från **vyn** Typ används.</span><span class="sxs-lookup"><span data-stu-id="9ada3-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="9ada3-226">Datatabellen innehåller samma information från **vyn** Typ.</span><span class="sxs-lookup"><span data-stu-id="9ada3-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="9ada3-227">Vyn **Välj en kategori för mer information** om tillgängliga val och beteenden är samma som **vyn** Typ.</span><span class="sxs-lookup"><span data-stu-id="9ada3-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="9ada3-228">Exportera från riktningsvyn</span><span class="sxs-lookup"><span data-stu-id="9ada3-228">Export from Direction view</span></span>

<span data-ttu-id="9ada3-229">I detaljvyn kan du bara exportera data under en dag.</span><span class="sxs-lookup"><span data-stu-id="9ada3-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="9ada3-230">Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="9ada3-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="9ada3-231">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="9ada3-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="9ada3-232">Om dagens data innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="9ada3-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Riktningsvyn i statusrapporten E-postflöde](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="9ada3-234">Trattvyn för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="9ada3-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="9ada3-235">I **vyn Tratt** kan du se hur Microsofts skyddsfunktioner för e-posthot filtrerar inkommande och utgående e-post i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="9ada3-236">Här finns information om totalt antal e-postmeddelanden och hur de konfigurerade funktionerna för skydd mot hot, inklusive gränsskydd, skydd mot skadlig programvara, skydd mot nätfiske, skräppost och förfalskning, påverkar antalet.</span><span class="sxs-lookup"><span data-stu-id="9ada3-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="9ada3-237">Om du klickar **på fliken Tratt** innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="9ada3-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="9ada3-238">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="9ada3-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="9ada3-239">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="9ada3-239">**Direction**:</span></span>

  - <span data-ttu-id="9ada3-240">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="9ada3-240">**Inbound**</span></span>
  - <span data-ttu-id="9ada3-241">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="9ada3-241">**Outbound**</span></span>
  - <span data-ttu-id="9ada3-242">**Årsorganisation:** Antalet är för meddelanden som skickas inom en klientorganisation. det vill säga att avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från inkommande och utgående).</span><span class="sxs-lookup"><span data-stu-id="9ada3-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="9ada3-243">För aggregerad vy och datatabellvy kan du filtrera i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="9ada3-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="9ada3-244">Om du klickar **på** Filter kan du filtrera både diagrammet och datatabellen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="9ada3-245">I det här diagrammet visas antalet e-postmeddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="9ada3-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="9ada3-246">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="9ada3-246">**Total email**</span></span>
- <span data-ttu-id="9ada3-247">**E-post efter gränsskydd**</span><span class="sxs-lookup"><span data-stu-id="9ada3-247">**Email after edge protection**</span></span>
- <span data-ttu-id="9ada3-248">**E-post efter transportregel** (e-postflödesregel)</span><span class="sxs-lookup"><span data-stu-id="9ada3-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="9ada3-249">**E-post efter skadlig programvara, rykte, filtypsblockering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="9ada3-250">**E-post efter hot, URL-rykte, varumärkespersonifiering, skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="9ada3-251">**E-post efter skräppost, massfiltrering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="9ada3-252">**E-post efter personifiering av användare och domän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-253">**E-post efter fil- och URL-detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-254">**E-post identifierades som därefter skydd efter leverans (URL klicka på tidsskydd)**</span><span class="sxs-lookup"><span data-stu-id="9ada3-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="9ada3-255"><sup>\*</sup>Endast Defender Office 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ada3-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="9ada3-256">Om du vill visa e-post som filtrerats efter EOP eller Defender Office 365 separat klickar du på värdet i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="9ada3-257">Datatabellen innehåller följande information, visad i fallande datumordning:</span><span class="sxs-lookup"><span data-stu-id="9ada3-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="9ada3-258">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-258">**Date**</span></span>
- <span data-ttu-id="9ada3-259">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="9ada3-259">**Total email**</span></span>
- <span data-ttu-id="9ada3-260">**Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="9ada3-260">**Edge protection**</span></span>
- <span data-ttu-id="9ada3-261">**Skydd mot skadlig programvara, rykte för filen, filtypsblockering:**</span><span class="sxs-lookup"><span data-stu-id="9ada3-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="9ada3-262">**Rykte:** Meddelanden filtrerade på grund av identifiering av en bifogad fil av andra Microsoft-kunder.</span><span class="sxs-lookup"><span data-stu-id="9ada3-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="9ada3-263">**Filtypsblock:** Meddelanden filtreras på grund av vilken typ av skadlig fil som identifieras i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="9ada3-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="9ada3-264">**Antifras, URL-rykte, varumärkespersonifiering, skydd mot förfalskning:**</span><span class="sxs-lookup"><span data-stu-id="9ada3-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="9ada3-265">**URL-rykte:** Meddelanden filtreras på grund av identifiering av URL-adressen av andra Microsoft-kunder.</span><span class="sxs-lookup"><span data-stu-id="9ada3-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="9ada3-266">**Profilering:** Meddelanden filtrerade på grund av meddelanden från välkända varumärkespersonifieringsavsändare.</span><span class="sxs-lookup"><span data-stu-id="9ada3-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="9ada3-267">**Skydd mot förfalskning:** Meddelanden filtreras på grund av ett meddelande som försöker kapa en domän som mottagaren tillhör eller en domän som meddelandets avsändare inte äger.</span><span class="sxs-lookup"><span data-stu-id="9ada3-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="9ada3-268">**Skräppostskydd, massfiltrering:**</span><span class="sxs-lookup"><span data-stu-id="9ada3-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="9ada3-269">**Filtrering av** massutskick: Meddelanden filtreras baserat på tröskelvärdet för masskrekrektör (BCL) i en princip mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="9ada3-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="9ada3-270">**Användar- och domänpersonifiering (Defender för Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="9ada3-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="9ada3-271">**Personifiering för användare:** Filtrerade meddelanden på grund av ett försök att utge sig för att vara en användare (meddelandeavsändare) som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="9ada3-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="9ada3-272">**Domänpersonifiering:** Meddelanden filtrerade på grund av ett försök att utge sig för att vara en domän som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="9ada3-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="9ada3-273">**Detonation av fil och URL (Defender för Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="9ada3-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="9ada3-274">**Detonation för filer:** Meddelanden filtrerade efter Valv princip för bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="9ada3-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="9ada3-275">**URL-detonation**: Meddelande filtrerat av Valv princip för länkar.</span><span class="sxs-lookup"><span data-stu-id="9ada3-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="9ada3-276">**Post-delivery protection and ZAP (ATP) or ZAP (EOP) : Zero-hour** auto purge (ZAP) for malware, spam, and phishing.</span><span class="sxs-lookup"><span data-stu-id="9ada3-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="9ada3-277">Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällklienten.</span><span class="sxs-lookup"><span data-stu-id="9ada3-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="9ada3-278">Exportera från trattvyn</span><span class="sxs-lookup"><span data-stu-id="9ada3-278">Export from Funnel view</span></span>

<span data-ttu-id="9ada3-279">När du har **klickat** **på Exportera** under Alternativ kan du välja något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="9ada3-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="9ada3-280">**Sammanfattning (med data för de senaste 90 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="9ada3-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="9ada3-281">**Information (med data för de senaste 30 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="9ada3-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="9ada3-282">Välj **ett** område under Datum och klicka sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="9ada3-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="9ada3-283">Data för de aktuella filtren exporteras till en .csv fil.</span><span class="sxs-lookup"><span data-stu-id="9ada3-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="9ada3-284">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="9ada3-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="9ada3-285">Om informationen innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="9ada3-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Trattvyn i statusrapporten För e-postflöde](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="9ada3-287">Tech view for the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="9ada3-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="9ada3-288">**Tech-vyn** liknar vyn **Tratt, med** mer detaljerad information om de konfigurerade funktionerna för skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="9ada3-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="9ada3-289">Från diagrammet kan du se hur meddelanden kategoriseras i olika faser av skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="9ada3-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="9ada3-290">Om du klickar **på fliken Teknisk** vy innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="9ada3-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="9ada3-291">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="9ada3-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="9ada3-292">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="9ada3-292">**Direction**:</span></span>

  - <span data-ttu-id="9ada3-293">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="9ada3-293">**Inbound**</span></span>
  - <span data-ttu-id="9ada3-294">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="9ada3-294">**Outbound**</span></span>
  - <span data-ttu-id="9ada3-295">**Årsorganisation**: det här antalet gäller meddelanden inom en klientorganisation, dvs.</span><span class="sxs-lookup"><span data-stu-id="9ada3-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="9ada3-296">sender abc@domain.com skickar till mottagarens xyz@domain.com (räknas separat från inkommande och utgående)</span><span class="sxs-lookup"><span data-stu-id="9ada3-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="9ada3-297">För aggregerad vy och datatabellvy kan du filtrera i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="9ada3-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="9ada3-298">Om du klickar **på** Filter kan du filtrera både diagrammet och datatabellen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="9ada3-299">Det här diagrammet visar meddelanden ordnade i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="9ada3-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="9ada3-300">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="9ada3-300">**Total email**</span></span>
- <span data-ttu-id="9ada3-301">**Tillåt i Edge** **och Filtrerad Edge**</span><span class="sxs-lookup"><span data-stu-id="9ada3-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="9ada3-302">**Transportregel tillåt och** **transportregel filtrerad** (e-postflödesregler)</span><span class="sxs-lookup"><span data-stu-id="9ada3-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="9ada3-303">**Inte skadlig programvara**, **Valv identifiering av bifogade filer** och <sup>\*</sup> **motoridentifiering mot skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="9ada3-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="9ada3-304">**Inte phish**, **DMARC-fel,** **personidentifiering,** <sup>\*</sup> **förfalskning och** **phish-identifiering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="9ada3-305">**Ingen identifiering med URL-detonation och** **URL-detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-306">**Inte** skräppost </span><span class="sxs-lookup"><span data-stu-id="9ada3-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="9ada3-307">**Icke-skadlig e-post** **, Valv identifiering av länkar** och <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="9ada3-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="9ada3-308"><sup>\*</sup>Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="9ada3-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="9ada3-309">När du hovrar över en kategori i diagrammet visas antalet meddelanden i den kategorin.</span><span class="sxs-lookup"><span data-stu-id="9ada3-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="9ada3-310">Datatabellen innehåller följande information, visad i fallande datumordning:</span><span class="sxs-lookup"><span data-stu-id="9ada3-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="9ada3-311">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-311">**Date**</span></span>
- <span data-ttu-id="9ada3-312">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="9ada3-312">**Total email**</span></span>
- <span data-ttu-id="9ada3-313">**Edge filtrerad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-313">**Edge filtered**</span></span>
- <span data-ttu-id="9ada3-314">**Regelmeddelanden:** Meddelanden filtrerade på grund av e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="9ada3-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="9ada3-315">**Motor för skydd mot skadlig programvara** Valv bifogade **filer:** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="9ada3-316">**DMARC, personifiering** <sup>\*</sup> , **spoof**, **nätfiske filtrerat:**</span><span class="sxs-lookup"><span data-stu-id="9ada3-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="9ada3-317">**DMARC:** Meddelanden filtreras på grund av att meddelandet inte klarar sin DMARC-autentiseringskontroll.</span><span class="sxs-lookup"><span data-stu-id="9ada3-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="9ada3-318">**Identifiering av URL-adresser**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-319">**Skräppostskydd filtreras**</span><span class="sxs-lookup"><span data-stu-id="9ada3-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="9ada3-320">**ZAP har tagits bort**</span><span class="sxs-lookup"><span data-stu-id="9ada3-320">**ZAP removed**</span></span>
- <span data-ttu-id="9ada3-321">**Identifiering av Valv länkar**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="9ada3-322"><sup>\*</sup>Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="9ada3-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="9ada3-323">Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällklienten.</span><span class="sxs-lookup"><span data-stu-id="9ada3-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="9ada3-324">Exportera från teknisk vy</span><span class="sxs-lookup"><span data-stu-id="9ada3-324">Export from Tech view</span></span>

<span data-ttu-id="9ada3-325">När du **klickar** på Exportera **kan** du välja något av följande värden under Alternativ:</span><span class="sxs-lookup"><span data-stu-id="9ada3-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="9ada3-326">**Sammanfattning (med data för de senaste 90 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="9ada3-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="9ada3-327">**Information (med data för de senaste 30 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="9ada3-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="9ada3-328">Välj **ett** område under Datum och klicka sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="9ada3-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="9ada3-329">Data för de aktuella filtren exporteras till en .csv fil.</span><span class="sxs-lookup"><span data-stu-id="9ada3-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="9ada3-330">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="9ada3-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="9ada3-331">Om informationen innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="9ada3-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Tech view in the Mailflow status report](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="9ada3-333">Rapport om identifiering av skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="9ada3-333">Malware detections report</span></span>

<span data-ttu-id="9ada3-334">Rapporten **Om identifiering av skadlig programvara visar** information om identifiering av skadlig programvara i inkommande och utgående e-postmeddelanden (skadlig programvara som Exchange Online Protection eller EOP).</span><span class="sxs-lookup"><span data-stu-id="9ada3-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="9ada3-335">Mer information om skydd mot skadlig programvara i EOP finns [i Skydd mot skadlig programvara i EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="9ada3-336">Mängdvyfiltret tillåter 90 dagar, medan filtret i detaljtabellen bara tillåter 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="9ada3-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="9ada3-337">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="9ada3-338">Vid **skadlig programvara som upptäckts i e-post** klickar du på Visa **information.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="9ada3-339">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="9ada3-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Identifiering av skadlig programvara i widgeten för e-& för e-& och samarbetsrapporter](../../media/malware-detections-widget.png)

<span data-ttu-id="9ada3-341">När du har **klickat på** Visa information kan du filtrera både diagrammet och detaljtabellen genom att klicka **på Filtrera** och välja:</span><span class="sxs-lookup"><span data-stu-id="9ada3-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="9ada3-342">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-343">**Riktning:** **Inkommande** **och utgående**</span><span class="sxs-lookup"><span data-stu-id="9ada3-343">**Direction**: **Inbound** and **Outbound**</span></span>

![Rapportvyn i rapporten om identifiering av skadlig programvara i e-post](../../media/malware-detections-report-view.png)

<span data-ttu-id="9ada3-345">I informationstabellen under diagrammet kan du se följande information:</span><span class="sxs-lookup"><span data-stu-id="9ada3-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="9ada3-346">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-346">**Date**</span></span>
- <span data-ttu-id="9ada3-347">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="9ada3-347">**Sender address**</span></span>
- <span data-ttu-id="9ada3-348">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="9ada3-348">**Recipient address**</span></span>
- <span data-ttu-id="9ada3-349">**Meddelande-ID:** Tillgängligt i **sidhuvudet för meddelande-ID** i meddelandehuvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="9ada3-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="9ada3-350">Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observera vinkelparenteserna).</span><span class="sxs-lookup"><span data-stu-id="9ada3-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="9ada3-351">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="9ada3-351">**Subject**</span></span>
- <span data-ttu-id="9ada3-352">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="9ada3-352">**Filename**</span></span>
- <span data-ttu-id="9ada3-353">**Namn på skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="9ada3-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="9ada3-354">E-postsvarstid – rapport</span><span class="sxs-lookup"><span data-stu-id="9ada3-354">Mail latency report</span></span>

<span data-ttu-id="9ada3-355">Rapporten **Om E-postfördröjning** i Defender för Office 365 innehåller information om den e-postleverans och den tidsfördröjning som uppgers i din organisation.</span><span class="sxs-lookup"><span data-stu-id="9ada3-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="9ada3-356">Mer information finns i [E-postsvarstidsrapport](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="9ada3-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="9ada3-357">Rapport om identifiering av skräppost</span><span class="sxs-lookup"><span data-stu-id="9ada3-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="9ada3-358">Rapporten **om identifiering av skräppost** försvinner den 30 juni 2021.</span><span class="sxs-lookup"><span data-stu-id="9ada3-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="9ada3-359">Samma information är tillgänglig i rapporten [om skydd mot hot.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="9ada3-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="9ada3-360">Rapport om identifieringar av förfalskning</span><span class="sxs-lookup"><span data-stu-id="9ada3-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="9ada3-361">Rapporten om förbättrade identifieringar av förfalskning som beskrivs i den här artikeln är en förhandsversion, kan komma att ändras och är inte tillgänglig i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="9ada3-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="9ada3-362">I den äldre versionen av rapporten visas bara **Bra e-post** **och Fångad som skräppost.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="9ada3-363">I **rapporten Identifieringar av förfalskning** visas information om meddelanden som har blockerats eller tillåts på grund av förfalskning.</span><span class="sxs-lookup"><span data-stu-id="9ada3-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="9ada3-364">Mer information om förfalskning finns i [Skydd mot förfalskning i EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="9ada3-365">I den samlade vyn för rapporten kan du filtrera i 45 dagar, medan <sup>\*</sup> detaljvyn bara tillåter tio dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="9ada3-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="9ada3-366"><sup>\*</sup> Till slut kan du använda upp till 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="9ada3-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="9ada3-367">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="9ada3-368">Vid **identifieringar av förfalskning klickar** du **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="9ada3-369">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="9ada3-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget för identifiering av förfalskning på sidan & för e-post och samarbete](../../media/spoof-detections-widget.png)

<span data-ttu-id="9ada3-371">När du hovrar över en dag (datapunkt) i diagrammet kan du se hur många falska meddelanden som påträffades och varför.</span><span class="sxs-lookup"><span data-stu-id="9ada3-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="9ada3-372">När du klickar **på Visa** information kan du filtrera både diagrammet och detaljtabellen genom att klicka på **Filtrera** och markera ett eller flera av följande värden:</span><span class="sxs-lookup"><span data-stu-id="9ada3-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="9ada3-373">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-374">**Resultat:**</span><span class="sxs-lookup"><span data-stu-id="9ada3-374">**Result**:</span></span>
  - <span data-ttu-id="9ada3-375">**Godkänd**</span><span class="sxs-lookup"><span data-stu-id="9ada3-375">**Pass**</span></span>
  - <span data-ttu-id="9ada3-376">**Fel**</span><span class="sxs-lookup"><span data-stu-id="9ada3-376">**Fail**</span></span>
  - <span data-ttu-id="9ada3-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="9ada3-377">**SoftPass**</span></span>
  - <span data-ttu-id="9ada3-378">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="9ada3-378">**None**</span></span>
  - <span data-ttu-id="9ada3-379">**Annat**</span><span class="sxs-lookup"><span data-stu-id="9ada3-379">**Other**</span></span>
- <span data-ttu-id="9ada3-380">**Förfalskningstyp:** **Intern** och **Extern**</span><span class="sxs-lookup"><span data-stu-id="9ada3-380">**Spoof type**: **Internal** and **External**</span></span>

![Sidan Förfalskningsrapport på Microsoft 365 Defender portalen](../../media/spoof-detections-report-page.png)

<span data-ttu-id="9ada3-382">I tabellen nedanför diagrammet kan du se följande information:</span><span class="sxs-lookup"><span data-stu-id="9ada3-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="9ada3-383">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-383">**Date**</span></span>
- <span data-ttu-id="9ada3-384">**Spoofed användare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-384">**Spoofed user**</span></span>
- <span data-ttu-id="9ada3-385">**Skicka infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="9ada3-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="9ada3-386">**Förfalskningstyp**</span><span class="sxs-lookup"><span data-stu-id="9ada3-386">**Spoof type**</span></span>
- <span data-ttu-id="9ada3-387">**Result**</span><span class="sxs-lookup"><span data-stu-id="9ada3-387">**Result**</span></span>
- <span data-ttu-id="9ada3-388">**Resultatkod**</span><span class="sxs-lookup"><span data-stu-id="9ada3-388">**Result code**</span></span>
- <span data-ttu-id="9ada3-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="9ada3-389">**SPF**</span></span>
- <span data-ttu-id="9ada3-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="9ada3-390">**DKIM**</span></span>
- <span data-ttu-id="9ada3-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="9ada3-391">**DMARC**</span></span>
- <span data-ttu-id="9ada3-392">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="9ada3-392">**Message count**</span></span>

<span data-ttu-id="9ada3-393">Mer information om sammansatta resultatkoder för autentisering finns i Rubriker mot skräppost [i Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="9ada3-394">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="9ada3-394">Threat protection status report</span></span>

<span data-ttu-id="9ada3-395">Statusrapporten **för skydd** mot hot är tillgänglig i både EOP och Defender för Office 365. Rapporterna innehåller däremot olika data.</span><span class="sxs-lookup"><span data-stu-id="9ada3-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="9ada3-396">Till exempel kan EOP-kunder visa information om skadlig programvara som upptäckts i e-post, men inte information om skadliga filer som upptäckts av [Valv-bifogade](mdo-for-spo-odb-and-teams.md)filer för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9ada3-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="9ada3-397">Rapporten innehåller antalet e-postmeddelanden med skadligt innehåll, till exempel filer eller webbadresser (URL:er) som har blockerats av antivirusmotorn, nolltimmars automatisk rensning [(ZAP)](zero-hour-auto-purge.md)och Defender för [Office 365-funktioner](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)som [Valv-länkar,](safe-links.md) [Valv-bilagor](safe-attachments.md)och personifieringsskyddsfunktioner i principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="9ada3-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="9ada3-398">Du kan använda den här informationen för att identifiera trender eller avgöra om organisationens principer behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="9ada3-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="9ada3-399">**Obs!** Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="9ada3-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="9ada3-400">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="9ada3-401">På **Status för skydd mot hot** klickar du på Visa **information.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="9ada3-402">Öppna någon av följande URL:er för att gå direkt till rapporten:</span><span class="sxs-lookup"><span data-stu-id="9ada3-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="9ada3-403">Defender för Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="9ada3-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="9ada3-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="9ada3-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget för hotskyddsstatus på sidan & och samarbetsrapporter](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="9ada3-406">När du har klickat på **Visa information visas** som standard data för de senaste 7 dagarna i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="9ada3-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="9ada3-407">Om du klickar **på Filter** kan du välja ett datumintervall på 90 dagar (utvärderingsprenumerationer kan vara begränsat till 30 dagar).</span><span class="sxs-lookup"><span data-stu-id="9ada3-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="9ada3-408">I detaljtabellen filtreras data i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="9ada3-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="9ada3-409">De tillgängliga vyerna beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="9ada3-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="9ada3-410">Visa data per översikt</span><span class="sxs-lookup"><span data-stu-id="9ada3-410">View data by Overview</span></span>

![Översiktsvy i rapporten om skydd mot hot](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="9ada3-412">I **vyn Visa data efter** översikt visas följande identifieringsinformation i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="9ada3-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="9ada3-413">**Skadlig programvara för e-post**</span><span class="sxs-lookup"><span data-stu-id="9ada3-413">**Email malware**</span></span>
- <span data-ttu-id="9ada3-414">**E-post phish**</span><span class="sxs-lookup"><span data-stu-id="9ada3-414">**Email phish**</span></span>
- <span data-ttu-id="9ada3-415">**Skadlig programvara för innehåll**</span><span class="sxs-lookup"><span data-stu-id="9ada3-415">**Content malware**</span></span>

<span data-ttu-id="9ada3-416">Ingen informationstabell är tillgänglig under diagrammet.</span><span class="sxs-lookup"><span data-stu-id="9ada3-416">No details table is available below the chart.</span></span>

<span data-ttu-id="9ada3-417">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9ada3-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="9ada3-418">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-419">**Identifiering:** Skadlig programvara för **e-post, e-post phish** eller **skadlig programvara för innehåll** </span><span class="sxs-lookup"><span data-stu-id="9ada3-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="9ada3-420">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="9ada3-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="9ada3-421">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="9ada3-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9ada3-422">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="9ada3-423">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-423">**Direction**</span></span>
- <span data-ttu-id="9ada3-424">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9ada3-424">**Domain**</span></span>
- <span data-ttu-id="9ada3-425">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="9ada3-425">**Policy type**</span></span>

<span data-ttu-id="9ada3-426">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="9ada3-427">Visa data efter \> e-post phish och diagramfördelning efter identifieringsteknik</span><span class="sxs-lookup"><span data-stu-id="9ada3-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Vy för identifieringsteknik för nätfiske i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="9ada3-429">I vyn **Visa data via \> e-post phish** **och diagram** som ligger i detalj efter vyn Identifieringsteknik visas följande information i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="9ada3-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="9ada3-430">**URL-skadligt** <sup>\*</sup> rykte: Skadligt URL-rykte skapat av Defender för Office 365 av detonationer i andra Microsoft 365 kunder.</span><span class="sxs-lookup"><span data-stu-id="9ada3-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="9ada3-431">**Avancerat filter:** Nätfiskesignaler baserade på maskininlärning.</span><span class="sxs-lookup"><span data-stu-id="9ada3-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="9ada3-432">**Allmänt filter:** Nätfiskesignaler baserade på analysregler.</span><span class="sxs-lookup"><span data-stu-id="9ada3-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="9ada3-433">**Förfalskning av årsorganisation**: Avsändaren försöker kapa mottagardomänen.</span><span class="sxs-lookup"><span data-stu-id="9ada3-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="9ada3-434">**Förfalskning av extern domän**: Avsändaren försöker kapa en annan domän.</span><span class="sxs-lookup"><span data-stu-id="9ada3-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="9ada3-435">**Förfalskning DMARC**: DMARC-autentiseringsfel på meddelanden.</span><span class="sxs-lookup"><span data-stu-id="9ada3-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="9ada3-436">**Personifieringsmärke**: Personifiering av välkända varumärken baserat på avsändare.</span><span class="sxs-lookup"><span data-stu-id="9ada3-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="9ada3-437">**Identifiering av blandad analys**</span><span class="sxs-lookup"><span data-stu-id="9ada3-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="9ada3-438">**Beryknat fil**</span><span class="sxs-lookup"><span data-stu-id="9ada3-438">**File reputation**</span></span>
- <span data-ttu-id="9ada3-439">**Fingeravtrycksmatchning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="9ada3-440">**URL-detonationsrekt**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-441">**URL-detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-442">**Personifieringsanvändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-443">**Personifieringsdomän:** <sup>\*</sup> Personifiering av domäner som kunden äger eller definierar.</span><span class="sxs-lookup"><span data-stu-id="9ada3-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="9ada3-444">**Postlådeintelligens** <sup>\*</sup> : Personifiering av användare som definierats av administratören eller som lärt sig via postlådeintelligens.</span><span class="sxs-lookup"><span data-stu-id="9ada3-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="9ada3-445">**Fil detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-446">**Kampanj**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="9ada3-447">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="9ada3-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="9ada3-448">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-448">**Date**</span></span>
- <span data-ttu-id="9ada3-449">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="9ada3-449">**Subject**</span></span>
- <span data-ttu-id="9ada3-450">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-450">**Sender**</span></span>
- <span data-ttu-id="9ada3-451">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-451">**Recipients**</span></span>
- <span data-ttu-id="9ada3-452">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-452">**Detected by**</span></span>
- <span data-ttu-id="9ada3-453">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="9ada3-453">**Delivery Status**</span></span>
- <span data-ttu-id="9ada3-454">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="9ada3-454">**Source of Compromise**</span></span>
- <span data-ttu-id="9ada3-455">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-455">**Tags**</span></span>

<span data-ttu-id="9ada3-456">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9ada3-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="9ada3-457">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-458">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-458">**Detection**</span></span>
- <span data-ttu-id="9ada3-459">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="9ada3-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="9ada3-460">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-460">**Direction**</span></span>
- <span data-ttu-id="9ada3-461">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="9ada3-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9ada3-462">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="9ada3-463">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9ada3-463">**Domain**</span></span>
- <span data-ttu-id="9ada3-464">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="9ada3-464">**Policy type**</span></span>
- <span data-ttu-id="9ada3-465">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="9ada3-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="9ada3-466">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-466">**Recipients**</span></span>

<span data-ttu-id="9ada3-467">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="9ada3-468">Visa data efter skadlig programvara \> för e-post och diagramfördelning med identifieringsteknik</span><span class="sxs-lookup"><span data-stu-id="9ada3-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Vy för identifieringsteknik för skadlig programvara i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="9ada3-470">I vyn **Visa data efter \> e-post** **skadlig** programvara och diagram som ligger i detalj i vyn Identifieringsteknik visas följande information i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="9ada3-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="9ada3-471">**Detonation för filen:** <sup>\*</sup> Identifiering av Valv bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="9ada3-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="9ada3-472">**Rykte för fil detonation** <sup>\*</sup> : Allt skadligt filrynde som genererats av Defender för Office 365 detonationer.</span><span class="sxs-lookup"><span data-stu-id="9ada3-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="9ada3-473">**Beryknat fil**</span><span class="sxs-lookup"><span data-stu-id="9ada3-473">**File reputation**</span></span>
- <span data-ttu-id="9ada3-474">**Motor mot skadlig programvara:** <sup>\*</sup> Identifiering från sökmotorer mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="9ada3-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="9ada3-475">**Filtypsblockering mot skadlig programvara:** Det här är e-postmeddelanden som filtrerats bort på grund av vilken typ av skadlig fil som identifieras i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="9ada3-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="9ada3-476">**URL-skadligt rykte**</span><span class="sxs-lookup"><span data-stu-id="9ada3-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="9ada3-477">**URL-detonation**</span><span class="sxs-lookup"><span data-stu-id="9ada3-477">**URL detonation**</span></span>
- <span data-ttu-id="9ada3-478">**URL-detonationsrekt**</span><span class="sxs-lookup"><span data-stu-id="9ada3-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="9ada3-479">**Kampanj**</span><span class="sxs-lookup"><span data-stu-id="9ada3-479">**Campaign**</span></span>

<span data-ttu-id="9ada3-480">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="9ada3-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="9ada3-481">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-481">**Date**</span></span>
- <span data-ttu-id="9ada3-482">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="9ada3-482">**Subject**</span></span>
- <span data-ttu-id="9ada3-483">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-483">**Sender**</span></span>
- <span data-ttu-id="9ada3-484">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-484">**Recipients**</span></span>
- <span data-ttu-id="9ada3-485">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-485">**Detected by**</span></span>
- <span data-ttu-id="9ada3-486">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="9ada3-486">**Delivery Status**</span></span>
- <span data-ttu-id="9ada3-487">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="9ada3-487">**Source of Compromise**</span></span>
- <span data-ttu-id="9ada3-488">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-488">**Tags**</span></span>

<span data-ttu-id="9ada3-489">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9ada3-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="9ada3-490">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-491">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-491">**Detection**</span></span>
- <span data-ttu-id="9ada3-492">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="9ada3-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="9ada3-493">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-493">**Direction**</span></span>
- <span data-ttu-id="9ada3-494">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="9ada3-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9ada3-495">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="9ada3-496">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9ada3-496">**Domain**</span></span>
- <span data-ttu-id="9ada3-497">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="9ada3-497">**Policy type**</span></span>
- <span data-ttu-id="9ada3-498">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="9ada3-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="9ada3-499">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-499">**Recipients**</span></span>

<span data-ttu-id="9ada3-500">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="9ada3-501">Diagramfördelning efter typ av princip och Visa data efter e-post \> phish eller Visa data efter e-postprogram \></span><span class="sxs-lookup"><span data-stu-id="9ada3-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Vy av principtyp för nätfiskemeddelande eller skadlig e-post i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="9ada3-503">I **diagramfördelningen efter typ av princip** och Visa data efter e-postfras eller **Visa data \>** efter e-post för skadlig programvara visas följande information i diagrammen: **\>**</span><span class="sxs-lookup"><span data-stu-id="9ada3-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="9ada3-504">**Skydd mot skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="9ada3-504">**Anti-malware**</span></span>
- <span data-ttu-id="9ada3-505">**Valv Bifogade filer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ada3-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="9ada3-506">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="9ada3-506">**Anti-phish**</span></span>
- <span data-ttu-id="9ada3-507">**Skräppostskydd**</span><span class="sxs-lookup"><span data-stu-id="9ada3-507">**Anti-spam**</span></span>
- <span data-ttu-id="9ada3-508">**E-postflödesregel** (kallas även transportregel)</span><span class="sxs-lookup"><span data-stu-id="9ada3-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="9ada3-509">**Andra**</span><span class="sxs-lookup"><span data-stu-id="9ada3-509">**Others**</span></span>

<span data-ttu-id="9ada3-510">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="9ada3-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="9ada3-511">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-511">**Date**</span></span>
- <span data-ttu-id="9ada3-512">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="9ada3-512">**Subject**</span></span>
- <span data-ttu-id="9ada3-513">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-513">**Sender**</span></span>
- <span data-ttu-id="9ada3-514">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-514">**Recipients**</span></span>
- <span data-ttu-id="9ada3-515">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-515">**Detected by**</span></span>
- <span data-ttu-id="9ada3-516">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="9ada3-516">**Delivery Status**</span></span>
- <span data-ttu-id="9ada3-517">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="9ada3-517">**Source of Compromise**</span></span>
- <span data-ttu-id="9ada3-518">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-518">**Tags**</span></span>

<span data-ttu-id="9ada3-519">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9ada3-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="9ada3-520">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-521">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-521">**Detection**</span></span>
- <span data-ttu-id="9ada3-522">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="9ada3-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="9ada3-523">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-523">**Direction**</span></span>
- <span data-ttu-id="9ada3-524">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="9ada3-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9ada3-525">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="9ada3-526">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9ada3-526">**Domain**</span></span>
- <span data-ttu-id="9ada3-527">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="9ada3-527">**Policy type**</span></span>
- <span data-ttu-id="9ada3-528">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="9ada3-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="9ada3-529">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-529">**Recipients**</span></span>

<span data-ttu-id="9ada3-530">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="9ada3-531">Diagram efter leveransstatus och Visa data efter e-post \> phish eller Visa data efter e-post skadlig \> programvara</span><span class="sxs-lookup"><span data-stu-id="9ada3-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Leveransstatusvy för nätfiskemeddelande och skadlig e-post i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="9ada3-533">I **diagramfördelningen efter leveransstatus** och Visa data efter e-postfras eller **Visa data \>** efter e-post för skadlig programvara visas följande information i diagrammen: **\>**</span><span class="sxs-lookup"><span data-stu-id="9ada3-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="9ada3-534">**Värdpostlåda: Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="9ada3-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="9ada3-535">**Värdpostlåda: Skräppost**</span><span class="sxs-lookup"><span data-stu-id="9ada3-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="9ada3-536">**Värdpostlåda: Anpassad mapp**</span><span class="sxs-lookup"><span data-stu-id="9ada3-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="9ada3-537">**Värdpostlåda: Borttagna objekt**</span><span class="sxs-lookup"><span data-stu-id="9ada3-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="9ada3-538">**Vidarebefordrad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-538">**Forwarded**</span></span>
- <span data-ttu-id="9ada3-539">**Lokal server: Levererad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="9ada3-540">**Karantän**</span><span class="sxs-lookup"><span data-stu-id="9ada3-540">**Quarantine**</span></span>
- <span data-ttu-id="9ada3-541">**Leveransen misslyckades**</span><span class="sxs-lookup"><span data-stu-id="9ada3-541">**Delivery failed**</span></span>
- <span data-ttu-id="9ada3-542">**Nedsnad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-542">**Dropped**</span></span>

<span data-ttu-id="9ada3-543">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="9ada3-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="9ada3-544">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-544">**Date**</span></span>
- <span data-ttu-id="9ada3-545">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="9ada3-545">**Subject**</span></span>
- <span data-ttu-id="9ada3-546">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-546">**Sender**</span></span>
- <span data-ttu-id="9ada3-547">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-547">**Recipients**</span></span>
- <span data-ttu-id="9ada3-548">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-548">**Detected by**</span></span>
- <span data-ttu-id="9ada3-549">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="9ada3-549">**Delivery Status**</span></span>
- <span data-ttu-id="9ada3-550">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="9ada3-550">**Source of Compromise**</span></span>
- <span data-ttu-id="9ada3-551">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-551">**Tags**</span></span>

<span data-ttu-id="9ada3-552">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9ada3-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="9ada3-553">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-554">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-554">**Detection**</span></span>
- <span data-ttu-id="9ada3-555">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="9ada3-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="9ada3-556">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-556">**Direction**</span></span>
- <span data-ttu-id="9ada3-557">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="9ada3-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9ada3-558">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="9ada3-559">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9ada3-559">**Domain**</span></span>
- <span data-ttu-id="9ada3-560">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="9ada3-560">**Policy type**</span></span>
- <span data-ttu-id="9ada3-561">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="9ada3-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="9ada3-562">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-562">**Recipients**</span></span>

<span data-ttu-id="9ada3-563">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="9ada3-564">Visa data efter skadlig programvara för \> innehåll</span><span class="sxs-lookup"><span data-stu-id="9ada3-564">View data by Content \> Malware</span></span>

![Vyn För skadlig programvara för innehåll i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="9ada3-566">I vyn **Visa data efter skadlig \>** programvara för innehåll visas följande information i diagrammet för Microsoft Defender för Office 365 organisationer:</span><span class="sxs-lookup"><span data-stu-id="9ada3-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="9ada3-567">**Motor mot skadlig programvara:** Skadliga filer som upptäckts i Sharepoint, OneDrive och Microsoft Teams av den [inbyggda virusidentifieringen i Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="9ada3-568">**Fildeonation:** Skadliga filer som upptäckts [Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9ada3-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="9ada3-569">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="9ada3-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="9ada3-570">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-571">**Plats**</span><span class="sxs-lookup"><span data-stu-id="9ada3-571">**Location**</span></span>
- <span data-ttu-id="9ada3-572">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-572">**Detected by**</span></span>
- <span data-ttu-id="9ada3-573">**Namn på skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="9ada3-573">**Malware name**</span></span>

<span data-ttu-id="9ada3-574">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9ada3-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="9ada3-575">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-576">**Identifiering:** **Motor mot skadlig programvara** eller **detonation av filer**</span><span class="sxs-lookup"><span data-stu-id="9ada3-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="9ada3-577">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="9ada3-578">Visa data efter åsidosättning av system</span><span class="sxs-lookup"><span data-stu-id="9ada3-578">View data by System override</span></span>

![Vy för åsidosättning av meddelande i rapporten om skydd mot hot](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="9ada3-580">I vyn **För visning av data efter** system, visas följande orsak till åsidosättning i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="9ada3-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="9ada3-581">**Lokal hoppa över**</span><span class="sxs-lookup"><span data-stu-id="9ada3-581">**On-premises skip**</span></span>
- <span data-ttu-id="9ada3-582">**IP tillåt**</span><span class="sxs-lookup"><span data-stu-id="9ada3-582">**IP allow**</span></span>
- <span data-ttu-id="9ada3-583">**Exchange för e-posttransport** (e-postflödesregel)</span><span class="sxs-lookup"><span data-stu-id="9ada3-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="9ada3-584">**Organisationen tillät avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="9ada3-585">**Tillåtna domäner för organisationen**</span><span class="sxs-lookup"><span data-stu-id="9ada3-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="9ada3-586">**ZAP inte aktiverat**</span><span class="sxs-lookup"><span data-stu-id="9ada3-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="9ada3-587">**Mappen Skräppost är inte aktiverad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="9ada3-588">**Användare Valv avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-588">**User Safe Sender**</span></span>
- <span data-ttu-id="9ada3-589">**User Valv Domain**</span><span class="sxs-lookup"><span data-stu-id="9ada3-589">**User Safe Domain**</span></span>

<span data-ttu-id="9ada3-590">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="9ada3-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="9ada3-591">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-591">**Date**</span></span>
- <span data-ttu-id="9ada3-592">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="9ada3-592">**Subject**</span></span>
- <span data-ttu-id="9ada3-593">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-593">**Sender**</span></span>
- <span data-ttu-id="9ada3-594">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-594">**Recipients**</span></span>
- <span data-ttu-id="9ada3-595">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-595">**Detected by**</span></span>
- <span data-ttu-id="9ada3-596">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="9ada3-596">**Delivery Status**</span></span>
- <span data-ttu-id="9ada3-597">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="9ada3-597">**Source of Compromise**</span></span>
- <span data-ttu-id="9ada3-598">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-598">**Tags**</span></span>

<span data-ttu-id="9ada3-599">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9ada3-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="9ada3-600">**Datum:** **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="9ada3-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="9ada3-601">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-601">**Detection**</span></span>
- <span data-ttu-id="9ada3-602">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="9ada3-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="9ada3-603">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-603">**Direction**</span></span>
- <span data-ttu-id="9ada3-604">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="9ada3-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9ada3-605">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="9ada3-606">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9ada3-606">**Domain**</span></span>
- <span data-ttu-id="9ada3-607">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="9ada3-607">**Policy type**</span></span>
- <span data-ttu-id="9ada3-608">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="9ada3-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="9ada3-609">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-609">**Recipients**</span></span>

<span data-ttu-id="9ada3-610">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="9ada3-611"><sup>\*</sup>Endast Defender Office 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ada3-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="9ada3-612">Den viktigaste rapporten om skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="9ada3-612">Top malware report</span></span>

<span data-ttu-id="9ada3-613">Den **viktigaste rapporten om** skadlig programvara visar de olika typer av skadlig programvara som identifierats av skydd mot skadlig programvara i [EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="9ada3-614">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="9ada3-615">Klicka **på Visa information** vid den översta skadlig **programvara.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="9ada3-616">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="9ada3-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Populära widget för skadlig programvara på sidan & och samarbetsrapporter](../../media/top-malware-report-widget.png)

<span data-ttu-id="9ada3-618">När du hovrar över en kil i cirkeldiagrammet kan du se namnet på en typ av skadlig programvara och hur många meddelanden som identifierats som har den skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="9ada3-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="9ada3-619">När du har **klickat på** Visa information visas en större version av cirkeldiagrammet på rapportsidan. I detaljtabellen under diagrammet visas följande information:</span><span class="sxs-lookup"><span data-stu-id="9ada3-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="9ada3-620">**Populära skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="9ada3-620">**Top malware**</span></span>
- <span data-ttu-id="9ada3-621">**Antal**</span><span class="sxs-lookup"><span data-stu-id="9ada3-621">**Count**</span></span>

<span data-ttu-id="9ada3-622">Om du klickar **på** Filter kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Den övre vyn för skadlig programvara](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="9ada3-624">Rapport om skydd mot URL-hot</span><span class="sxs-lookup"><span data-stu-id="9ada3-624">URL threat protection report</span></span>

<span data-ttu-id="9ada3-625">Rapporten **om skydd mot URL-hot** är tillgänglig i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ada3-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9ada3-626">Mer information finns i Rapporten [om url-skydd mot hot.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="9ada3-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="9ada3-627">Rapport över användarrapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="9ada3-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ada3-628">För att rapporten **över användarrapporter ska** fungera korrekt måste granskningsloggning **vara aktiverad** i din Microsoft 365 miljö.</span><span class="sxs-lookup"><span data-stu-id="9ada3-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="9ada3-629">Det görs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9ada3-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="9ada3-630">Mer information finns i aktivera [Microsoft 365 eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="9ada3-631">Rapporten **Om användarrapporter** visar information om e-postmeddelanden som användare har rapporterat som skräppost, nätfiskeförsök eller bra [e-post](enable-the-report-message-add-in.md) med hjälp av tilläggen Rapportmeddelande eller [Rapport nätfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="9ada3-632">Om du vill visa rapporten i Microsoft 365 Defender-portalen går du till Rapporterar  \> **e-& samarbete** \> **E& och** \> **samarbetsrapporter Användarrapporter .**</span><span class="sxs-lookup"><span data-stu-id="9ada3-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="9ada3-633">På **användarrapporterade meddelanden** klickar du **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="9ada3-634">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="9ada3-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="9ada3-635">Om du vill [gå till administrationsinskick i Microsoft 365 Defender klickar](admin-submission.md)du på Gå till **inskickade material.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget för användarrapporter på sidan e& och samarbetsrapporter](../../media/user-reported-messages-widget.png)

<span data-ttu-id="9ada3-637">När du har **klickat på** Visa information kan du filtrera både diagrammet och detaljtabellen genom att klicka på **Filtrera** och välja ett eller flera av följande värden i den utfäll vy som visas:</span><span class="sxs-lookup"><span data-stu-id="9ada3-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="9ada3-638">**Rapporterad** datum : **Starttid** **och Sluttid**</span><span class="sxs-lookup"><span data-stu-id="9ada3-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="9ada3-639">**Rapporterad av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-639">**Reported by**</span></span>
- <span data-ttu-id="9ada3-640">**Ämne för e-post**</span><span class="sxs-lookup"><span data-stu-id="9ada3-640">**Email subject**</span></span>
- <span data-ttu-id="9ada3-641">**Rapporterat ID för meddelande**</span><span class="sxs-lookup"><span data-stu-id="9ada3-641">**Message reported ID**</span></span>
- <span data-ttu-id="9ada3-642">**Id för nätverksmeddelande**</span><span class="sxs-lookup"><span data-stu-id="9ada3-642">**Network Message ID**</span></span>
- <span data-ttu-id="9ada3-643">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-643">**Sender**</span></span>
- <span data-ttu-id="9ada3-644">**Rapporterad orsak**</span><span class="sxs-lookup"><span data-stu-id="9ada3-644">**Reported reason**</span></span>
  - <span data-ttu-id="9ada3-645">**Inte skräppost**</span><span class="sxs-lookup"><span data-stu-id="9ada3-645">**Not junk**</span></span>
  - <span data-ttu-id="9ada3-646">**Nätfiske**</span><span class="sxs-lookup"><span data-stu-id="9ada3-646">**Phish**</span></span>
  - <span data-ttu-id="9ada3-647">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="9ada3-647">**Spam**</span></span>
- <span data-ttu-id="9ada3-648">**Phish simulering**: **Ja** eller **Nej**</span><span class="sxs-lookup"><span data-stu-id="9ada3-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="9ada3-649">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="9ada3-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="9ada3-650">Om du vill gruppera posterna **klickar du** på Gruppera och väljer något av följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="9ada3-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="9ada3-651">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="9ada3-651">**None**</span></span>
- <span data-ttu-id="9ada3-652">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="9ada3-652">**Reason**</span></span>
- <span data-ttu-id="9ada3-653">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-653">**Sender**</span></span>
- <span data-ttu-id="9ada3-654">**Rapporterad av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-654">**Reported by**</span></span>
- <span data-ttu-id="9ada3-655">**Rescan-resultat**</span><span class="sxs-lookup"><span data-stu-id="9ada3-655">**Rescan result**</span></span>
- <span data-ttu-id="9ada3-656">**Phish-simulering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-656">**Phish simulation**</span></span>

![Rapport över användarrapporterade meddelanden](../../media/user-reported-messages-report.png)

<span data-ttu-id="9ada3-658">I tabellen nedanför diagrammet kan du se följande information:</span><span class="sxs-lookup"><span data-stu-id="9ada3-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="9ada3-659">**Ämne för e-post**</span><span class="sxs-lookup"><span data-stu-id="9ada3-659">**Email subject**</span></span>
- <span data-ttu-id="9ada3-660">**Rapporterad av**</span><span class="sxs-lookup"><span data-stu-id="9ada3-660">**Reported by**</span></span>
- <span data-ttu-id="9ada3-661">**Rapporterad**</span><span class="sxs-lookup"><span data-stu-id="9ada3-661">**Date reported**</span></span>
- <span data-ttu-id="9ada3-662">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-662">**Sender**</span></span>
- <span data-ttu-id="9ada3-663">**Rapporterad orsak**</span><span class="sxs-lookup"><span data-stu-id="9ada3-663">**Reported reason**</span></span>
- <span data-ttu-id="9ada3-664">**Rescan-resultat**</span><span class="sxs-lookup"><span data-stu-id="9ada3-664">**Rescan result**</span></span>
- <span data-ttu-id="9ada3-665">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="9ada3-665">**Tags**</span></span>

<span data-ttu-id="9ada3-666">Om du vill skicka ett meddelande till Microsoft för analys markerar du meddelandeposten i tabellen, klickar på Skicka till **Microsoft** för analys och väljer sedan något av följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="9ada3-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="9ada3-667">**Rapportrensning**</span><span class="sxs-lookup"><span data-stu-id="9ada3-667">**Report clean**</span></span>
- <span data-ttu-id="9ada3-668">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="9ada3-668">**Report phishing**</span></span>
- <span data-ttu-id="9ada3-669">**Rapportera skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="9ada3-669">**Report malware**</span></span>
- <span data-ttu-id="9ada3-670">**Rapportera skräppost**'</span><span class="sxs-lookup"><span data-stu-id="9ada3-670">**Report spam**'</span></span>
- <span data-ttu-id="9ada3-671">**Undersökning av utlösare** (Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="9ada3-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="9ada3-672">Vilka behörigheter krävs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="9ada3-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="9ada3-673">För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Microsoft 365 Defender portalen:</span><span class="sxs-lookup"><span data-stu-id="9ada3-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="9ada3-674">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="9ada3-674">**Organization Management**</span></span>
- <span data-ttu-id="9ada3-675">**Säkerhetsadministratör**</span><span class="sxs-lookup"><span data-stu-id="9ada3-675">**Security Administrator**</span></span>
- <span data-ttu-id="9ada3-676">**Säkerhetsläsare**</span><span class="sxs-lookup"><span data-stu-id="9ada3-676">**Security Reader**</span></span>
- <span data-ttu-id="9ada3-677">**Global Reader**</span><span class="sxs-lookup"><span data-stu-id="9ada3-677">**Global Reader**</span></span>

<span data-ttu-id="9ada3-678">Mer information finns i [Behörigheter i Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9ada3-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="9ada3-679">**Obs!** Om du lägger till användare i motsvarande Azure Active Directory-roll i Administrationscenter för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ada3-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9ada3-680">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9ada3-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="9ada3-681">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="9ada3-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="9ada3-682">Om du inte ser data i rapporterna kan du kontrollera att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="9ada3-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="9ada3-683">Mer information finns i [Skydda mot hot.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="9ada3-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9ada3-684">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9ada3-684">Related topics</span></span>

[<span data-ttu-id="9ada3-685">Skydd mot skräppost och skadlig programvara i EOP</span><span class="sxs-lookup"><span data-stu-id="9ada3-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="9ada3-686">Smarta rapporter och insikter i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="9ada3-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="9ada3-687">Visa e-postflödesrapporter i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="9ada3-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="9ada3-688">Visa rapporter för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="9ada3-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
