---
title: Visa säkerhetsrapporter för e-post
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
description: Administratörer kan ta reda på hur de e-postsäkerhetsrapporter som finns i Microsoft 365 Defender-portalen hittar och använder.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022955"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="f82fd-103">Visa e-postsäkerhetsrapporter på Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="f82fd-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f82fd-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f82fd-104">**Applies to**</span></span>
- [<span data-ttu-id="f82fd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f82fd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f82fd-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f82fd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f82fd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f82fd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f82fd-108">Det finns flera olika rapporter på Microsoft 365 Defender-portalen som hjälper dig se hur säkerhetsfunktioner för e-post, till exempel skydd mot skräppost, skadlig programvara och kryptering i <https://security.microsoft.com> Microsoft 365, skyddar organisationen.</span><span class="sxs-lookup"><span data-stu-id="f82fd-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="f82fd-109">Om du har [nödvändiga](#what-permissions-are-needed-to-view-these-reports)behörigheter kan du visa de här rapporterna i  Microsoft 365 Defender-portalen genom att gå till Rapporterar \> **e-&-postsamarbete** \> **E& och samarbetsrapporter**.</span><span class="sxs-lookup"><span data-stu-id="f82fd-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-110">Om du vill gå direkt **till sidan & e-post och** samarbetsrapporter öppnar du <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Skicka & via e-post och samarbetsrapporter i Microsoft 365 Defender-portalen](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="f82fd-112">Vissa av rapporterna på sidan **e& och samarbetsrapporter** kräver Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="f82fd-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f82fd-113">Mer information om de här rapporterna finns [i Visa Defender för Office 365-rapporter i Microsoft 365 Defender-portalen.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="f82fd-114">Rapporter som är relaterade till e-postflödet finns nu i administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="f82fd-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f82fd-115">Mer information om rapporterna finns i [E-postflödesrapporter i det nya administrationscentret för Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="f82fd-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="f82fd-116">Rapport om komprometterade användare</span><span class="sxs-lookup"><span data-stu-id="f82fd-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="f82fd-117">Den här rapporten är tillgänglig i Microsoft 365-organisationer med Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="f82fd-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="f82fd-118">Det är inte tillgängligt i fristående EOP-organisationer (Exchange Online Protection).</span><span class="sxs-lookup"><span data-stu-id="f82fd-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="f82fd-119">I **rapporten Komprometterade** användare visas antalet användarkonton som har markerats **som misstänkta eller** begränsade **under** de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f82fd-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="f82fd-120">Konton i något av dessa tillstånd är problematiska eller till och med komprometterade.</span><span class="sxs-lookup"><span data-stu-id="f82fd-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="f82fd-121">Med regelbunden användning kan du använda rapporten för att upptäcka ökningar och även trender i misstänkta eller begränsade konton.</span><span class="sxs-lookup"><span data-stu-id="f82fd-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="f82fd-122">Mer information om komprometterade användare finns i [Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget för komprometterade användare på sidan & för e-post och samarbetsrapporter](../../media/compromised-users-report-widget.png)

<span data-ttu-id="f82fd-124">I mängdvyn visas data för de senaste 90 dagarna och i detaljvyn visas data för de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f82fd-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="f82fd-125">Om du vill visa rapporten i Microsoft 365 Defender-portalen går du till E-& för  \> **& med** \> **e-& för samarbete.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-126">På sidan **E& och samarbetsrapporter** går du till **Komprometterade användare** och klickar sedan **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="f82fd-127">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="f82fd-128">På sidan **Komprometterade** användare kan du filtrera både diagrammet och informationstabellen genom att klicka på **Filtrera** och välja ett eller flera av följande värden i den utfällda listan som visas:</span><span class="sxs-lookup"><span data-stu-id="f82fd-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f82fd-129">**Datum (UTC)**: **Startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="f82fd-130">**Aktivitet**:</span><span class="sxs-lookup"><span data-stu-id="f82fd-130">**Activity**:</span></span>
  - <span data-ttu-id="f82fd-131">**Misstänkt:** Användarkontot har skickat misstänkt e-postmeddelande och riskerar att bli begränsat från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="f82fd-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="f82fd-132">**Begränsad:** Användarkontot har begränsats från att skicka e-post på grund av mycket misstänkta mönster.</span><span class="sxs-lookup"><span data-stu-id="f82fd-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="f82fd-133">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Rapportvyn i rapporten Komprometterade användare](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="f82fd-135">I informationstabellen under diagrammet kan du se följande information:</span><span class="sxs-lookup"><span data-stu-id="f82fd-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="f82fd-136">**Tid då det skapades**</span><span class="sxs-lookup"><span data-stu-id="f82fd-136">**Creation time**</span></span>
- <span data-ttu-id="f82fd-137">**Användar-ID**</span><span class="sxs-lookup"><span data-stu-id="f82fd-137">**User ID**</span></span>
- <span data-ttu-id="f82fd-138">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="f82fd-139">Rapport över Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="f82fd-139">Exchange transport rule report</span></span>

<span data-ttu-id="f82fd-140">I **rapporten Exchange-transportregel** visas effekten av e-postflödesregler (kallas även transportregler) på inkommande och utgående meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f82fd-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="f82fd-141">Om du vill visa rapporten i Microsoft 365 Defender-portalen går du till E-& för  \> **& med** \> **e-& för samarbete.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-142">På sidan **E& och samarbetsrapporter** hittar du **Exchange-transportregel** och klickar sedan på **Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="f82fd-143">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Widget för Exchange-transportregel på sidan E& och samarbetsrapporter](../../media/transport-rule-report-widget.png)

<span data-ttu-id="f82fd-145">Tillgängliga diagram **och data beskrivs** i följande avsnitt på sidan Exchange-transportregelrapport.</span><span class="sxs-lookup"><span data-stu-id="f82fd-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="f82fd-146">Diagramfördelning efter riktning</span><span class="sxs-lookup"><span data-stu-id="f82fd-146">Chart breakdown by Direction</span></span>

![Riktningsvyn för Exchange-transportregler i exchange-transportregelrapporten](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="f82fd-148">Om du väljer **Diagramfördelning efter riktning** är följande diagram tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="f82fd-149">**Visa data enligt Exchange-transportregler:** Antalet **inkommande** och **utgående** meddelanden som påverkades av e-postflödesregler.</span><span class="sxs-lookup"><span data-stu-id="f82fd-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="f82fd-150">**Visa data med DLP-transportregler** för Exchange: Antalet **inkommande** och utgående meddelanden som påverkades av DLP-e-postflödesregler (Data Loss Prevention). </span><span class="sxs-lookup"><span data-stu-id="f82fd-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="f82fd-151">Följande information visas i detaljtabellen under diagrammet:</span><span class="sxs-lookup"><span data-stu-id="f82fd-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="f82fd-152">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-152">**Date**</span></span>
- <span data-ttu-id="f82fd-153">**DLP-princip** (**endast visa data efter DLP-transportregler i Exchange)**</span><span class="sxs-lookup"><span data-stu-id="f82fd-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="f82fd-154">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="f82fd-154">**Transport rule**</span></span>
- <span data-ttu-id="f82fd-155">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f82fd-155">**Subject**</span></span>
- <span data-ttu-id="f82fd-156">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="f82fd-156">**Sender address**</span></span>
- <span data-ttu-id="f82fd-157">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="f82fd-157">**Recipient address**</span></span>
- <span data-ttu-id="f82fd-158">**Allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-158">**Severity**</span></span>
- <span data-ttu-id="f82fd-159">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-159">**Direction**</span></span>

<span data-ttu-id="f82fd-160">Du kan filtrera både diagrammet och informationstabellen genom att klicka på **Filtrera** och markera ett eller flera av följande värden i den utfällo som visas:</span><span class="sxs-lookup"><span data-stu-id="f82fd-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f82fd-161">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-162">**Riktning**: **Utgående** och **inkommande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="f82fd-163">**Allvarlighetsgrad**: **Hög allvarlighetsgrad,** **medel allvarlighetsgrad** och **låg allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="f82fd-164">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="f82fd-165">Diagramfördelning per allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="f82fd-165">Chart breakdown by Severity</span></span>

![Vyn Allvarlighetsgrad för Exchange-transportregler i rapporten Exchange-transportregel](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="f82fd-167">Om du väljer **Diagramfördelning efter allvarlighetsgrad** är följande diagram tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="f82fd-168">**Visa data efter Exchange-transportregler:** Antalet **meddelanden** med hög allvarlighetsgrad, medel allvarlighetsgrad och låg **allvarlighetsgrad.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="f82fd-169">Du anger allvarlighetsnivån som en åtgärd i regeln **(Granska** denna regel med allvarlighetsnivå eller _AngeGranskningSalla_).</span><span class="sxs-lookup"><span data-stu-id="f82fd-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="f82fd-170">Mer information finns i Åtgärder för [e-postflödesregel i Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="f82fd-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="f82fd-171">**Visa data med DLP-transportregler** i Exchange: Antalet hög  allvarlighetsgrad **,** **Medel** allvarlighetsgrad och Meddelanden med låg allvarlighetsgrad som påverkades av DLP-e-postflödesregler.</span><span class="sxs-lookup"><span data-stu-id="f82fd-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="f82fd-172">Följande information visas i detaljtabellen under diagrammet:</span><span class="sxs-lookup"><span data-stu-id="f82fd-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="f82fd-173">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-173">**Date**</span></span>
- <span data-ttu-id="f82fd-174">**DLP-princip** (**endast visa data efter DLP-transportregler i Exchange)**</span><span class="sxs-lookup"><span data-stu-id="f82fd-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="f82fd-175">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="f82fd-175">**Transport rule**</span></span>
- <span data-ttu-id="f82fd-176">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f82fd-176">**Subject**</span></span>
- <span data-ttu-id="f82fd-177">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="f82fd-177">**Sender address**</span></span>
- <span data-ttu-id="f82fd-178">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="f82fd-178">**Recipient address**</span></span>
- <span data-ttu-id="f82fd-179">**Allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-179">**Severity**</span></span>
- <span data-ttu-id="f82fd-180">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-180">**Direction**</span></span>

<span data-ttu-id="f82fd-181">Du kan filtrera både diagrammet och informationstabellen genom att klicka på **Filtrera** och markera ett eller flera av följande värden i den utfällo som visas:</span><span class="sxs-lookup"><span data-stu-id="f82fd-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f82fd-182">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-183">**Riktning**: **Utgående** och **inkommande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="f82fd-184">**Allvarlighetsgrad**: **Hög allvarlighetsgrad,** **medel allvarlighetsgrad** och **låg allvarlighetsgrad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="f82fd-185">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="f82fd-186">Vidarebefordransrapport</span><span class="sxs-lookup"><span data-stu-id="f82fd-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="f82fd-187">**Vidarebefordransrapporten är** nu tillgänglig i EAC.</span><span class="sxs-lookup"><span data-stu-id="f82fd-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="f82fd-188">Mer information finns i [Rapporten om automatiska vidarebefordrade meddelanden i nya EAC.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)</span><span class="sxs-lookup"><span data-stu-id="f82fd-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="f82fd-189">Statusrapport för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="f82fd-189">Mailflow status report</span></span>

<span data-ttu-id="f82fd-190">Statusrapporten **E-postflöde** är en smart rapport som visar information om inkommande och utgående e-post, identifiering av skräppost, skadlig programvara, e-post som identifieras som "bra" och information om e-post som är tillåten eller blockerad i kanten.</span><span class="sxs-lookup"><span data-stu-id="f82fd-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="f82fd-191">Det här är den enda rapporten som innehåller information om gränsskydd och som visar hur mycket e-post som blockeras innan de tillåts till tjänsten för utvärdering av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="f82fd-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="f82fd-192">Det är viktigt att vara säker på att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="f82fd-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="f82fd-193">Om du vill visa rapporten i Microsoft 365 Defender-portalen går du till E-& för  \> **& med** \> **e-& för samarbete.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-194">På sidan **E& och samarbetsrapporter hittar** du **Statussammanfattning av E-postflöde** och klickar sedan **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="f82fd-195">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget för statussammanfattning av e-postflöde på sidan & för e-postsamarbete](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="f82fd-197">Typvy för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="f82fd-197">Type view for the Mailflow status report</span></span>

<span data-ttu-id="f82fd-198">När du öppnar rapporten är **fliken Typ** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="f82fd-198">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="f82fd-199">Som standard innehåller den här vyn ett diagram och en informationstabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="f82fd-199">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="f82fd-200">**Datum (UTC)** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="f82fd-200">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="f82fd-201">**E-postriktning:**</span><span class="sxs-lookup"><span data-stu-id="f82fd-201">**Mail direction**:</span></span>
  - <span data-ttu-id="f82fd-202">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-202">**Inbound**</span></span>
  - <span data-ttu-id="f82fd-203">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="f82fd-203">**Outbound**</span></span>
  - <span data-ttu-id="f82fd-204">**Årsorganisation**: det här antalet gäller meddelanden inom en klientorganisation, dvs.</span><span class="sxs-lookup"><span data-stu-id="f82fd-204">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f82fd-205">sender abc@domain.com skickar till mottagarens xyz@domain.com (räknas separat från **inkommande** **och utgående**)</span><span class="sxs-lookup"><span data-stu-id="f82fd-205">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="f82fd-206">**Typ:**</span><span class="sxs-lookup"><span data-stu-id="f82fd-206">**Type**:</span></span>
  - <span data-ttu-id="f82fd-207">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="f82fd-207">**Good mail**</span></span>
  - <span data-ttu-id="f82fd-208">**Skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="f82fd-208">**Malware**</span></span>
  - <span data-ttu-id="f82fd-209">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="f82fd-209">**Spam**</span></span>
  - <span data-ttu-id="f82fd-210">**Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-210">**Edge protection**</span></span>
  - <span data-ttu-id="f82fd-211">**Regelmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="f82fd-211">**Rule messages**</span></span>
  - <span data-ttu-id="f82fd-212">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="f82fd-212">**Phishing email**</span></span>
- <span data-ttu-id="f82fd-213">**Domän:** **Alla**</span><span class="sxs-lookup"><span data-stu-id="f82fd-213">**Domain**: **All**</span></span>

<span data-ttu-id="f82fd-214">Diagrammet ordnas efter **typvärdena.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-214">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="f82fd-215">Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="f82fd-215">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="f82fd-216">Följande information visas i detaljtabellen under diagrammet:</span><span class="sxs-lookup"><span data-stu-id="f82fd-216">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="f82fd-217">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-217">**Direction**</span></span>
- <span data-ttu-id="f82fd-218">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f82fd-218">**Type**</span></span>
- <span data-ttu-id="f82fd-219">**24 timmar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-219">**24 hours**</span></span>
- <span data-ttu-id="f82fd-220">**3 dagar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-220">**3 days**</span></span>
- <span data-ttu-id="f82fd-221">**7 dagar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-221">**7 days**</span></span>
- <span data-ttu-id="f82fd-222">**15 dagar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-222">**15 days**</span></span>
- <span data-ttu-id="f82fd-223">**30 dagar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-223">**30 days**</span></span>

<span data-ttu-id="f82fd-224">Om du klickar **på Välj en kategori för mer** information kan du välja bland följande värden:</span><span class="sxs-lookup"><span data-stu-id="f82fd-224">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="f82fd-225">**Nätfiskemeddelande:** Det här valet tar dig till [rapporten status för skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f82fd-225">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f82fd-226">**Skadlig programvara i** e-post: Det här valet tar dig till [statusrapporten Skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f82fd-226">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f82fd-227">**Identifiering av skräppost:** Det här valet tar dig till [rapporten Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f82fd-227">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="f82fd-228">**Edge blockerad skräppost:** Det här valet tar dig till rapporten [Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f82fd-228">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="f82fd-229">Exportera i vyn Typ</span><span class="sxs-lookup"><span data-stu-id="f82fd-229">Export from Type view</span></span>

<span data-ttu-id="f82fd-230">I detaljvyn kan du bara exportera data under en dag.</span><span class="sxs-lookup"><span data-stu-id="f82fd-230">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f82fd-231">Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="f82fd-231">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f82fd-232">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="f82fd-232">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f82fd-233">Om dagens data innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="f82fd-233">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Typvy i statusrapporten För e-postflöde](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="f82fd-235">Riktningsvyn för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="f82fd-235">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="f82fd-236">Om du klickar **på** fliken Riktning används samma standardfilter **från** vyn Typ.</span><span class="sxs-lookup"><span data-stu-id="f82fd-236">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="f82fd-237">Diagrammet är ordnat efter **riktningsvärden.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-237">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="f82fd-238">Du kan ändra filtren genom att klicka på **Filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-238">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="f82fd-239">Samma filter från **vyn** Typ används.</span><span class="sxs-lookup"><span data-stu-id="f82fd-239">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f82fd-240">Informationstabellen innehåller samma information från **vyn** Typ.</span><span class="sxs-lookup"><span data-stu-id="f82fd-240">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="f82fd-241">Vyn **Välj en kategori för mer information** om tillgängliga val och beteenden är samma som **vyn** Typ.</span><span class="sxs-lookup"><span data-stu-id="f82fd-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="f82fd-242">Exportera från riktningsvyn</span><span class="sxs-lookup"><span data-stu-id="f82fd-242">Export from Direction view</span></span>

<span data-ttu-id="f82fd-243">I detaljvyn kan du bara exportera data under en dag.</span><span class="sxs-lookup"><span data-stu-id="f82fd-243">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f82fd-244">Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.</span><span class="sxs-lookup"><span data-stu-id="f82fd-244">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f82fd-245">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="f82fd-245">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f82fd-246">Om dagens data innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="f82fd-246">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Riktningsvyn i statusrapporten E-postflöde](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="f82fd-248">Trattvyn för statusrapporten E-postflöde</span><span class="sxs-lookup"><span data-stu-id="f82fd-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="f82fd-249">I **vyn Tratt** kan du se hur Microsofts skyddsfunktioner för e-posthot filtrerar inkommande och utgående e-post i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f82fd-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="f82fd-250">Här finns information om totalt antal e-postmeddelanden och hur de konfigurerade funktionerna för skydd mot hot, inklusive gränsskydd, skydd mot skadlig programvara, skydd mot nätfiske, skräppost och förfalskning, påverkar antalet.</span><span class="sxs-lookup"><span data-stu-id="f82fd-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="f82fd-251">Om du klickar **på fliken Tratt** innehåller den här vyn som standard ett diagram och en informationstabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="f82fd-251">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="f82fd-252">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="f82fd-252">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f82fd-253">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="f82fd-253">**Direction**:</span></span>
  - <span data-ttu-id="f82fd-254">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-254">**Inbound**</span></span>
  - <span data-ttu-id="f82fd-255">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="f82fd-255">**Outbound**</span></span>
  - <span data-ttu-id="f82fd-256">**Årsorganisation:** Antalet är för meddelanden som skickas inom en klientorganisation. det vill säga att avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från inkommande och utgående).</span><span class="sxs-lookup"><span data-stu-id="f82fd-256">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="f82fd-257">Den samlade vyn och detaljtabellvyn ger 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="f82fd-257">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f82fd-258">Du kan ändra filtren genom att klicka på **Filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-258">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="f82fd-259">Samma filter från **vyn** Typ används.</span><span class="sxs-lookup"><span data-stu-id="f82fd-259">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f82fd-260">I det här diagrammet visas antalet e-postmeddelanden ordnade efter:</span><span class="sxs-lookup"><span data-stu-id="f82fd-260">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="f82fd-261">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="f82fd-261">**Total email**</span></span>
- <span data-ttu-id="f82fd-262">**E-post efter gränsskydd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-262">**Email after edge protection**</span></span>
- <span data-ttu-id="f82fd-263">**E-post efter transportregel** (e-postflödesregel)</span><span class="sxs-lookup"><span data-stu-id="f82fd-263">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="f82fd-264">**E-post efter skadlig programvara, rykte, filtypsblockering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-264">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="f82fd-265">**E-post efter hot, URL-rykte, varumärkespersonifiering, skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="f82fd-266">**E-post efter skräppost, massfiltrering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-266">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="f82fd-267">**E-post efter personifiering av användare och domän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-267">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-268">**E-post efter fil- och URL-detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-268">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-269">**E-post identifierades som därefter skydd efter leverans (URL klicka på tidsskydd)**</span><span class="sxs-lookup"><span data-stu-id="f82fd-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="f82fd-270"><sup>\*</sup>Endast Defender Office 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f82fd-270"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="f82fd-271">Om du vill visa e-post som filtrerats efter EOP eller Defender Office 365 separat klickar du på värdet i diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="f82fd-271">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="f82fd-272">Informationstabellen innehåller följande information, visad i fallande datumordning:</span><span class="sxs-lookup"><span data-stu-id="f82fd-272">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f82fd-273">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-273">**Date**</span></span>
- <span data-ttu-id="f82fd-274">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="f82fd-274">**Total email**</span></span>
- <span data-ttu-id="f82fd-275">**Edge-skydd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-275">**Edge protection**</span></span>
- <span data-ttu-id="f82fd-276">**Skydd mot skadlig programvara, rykte för filen, filtypsblockering:**</span><span class="sxs-lookup"><span data-stu-id="f82fd-276">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="f82fd-277">**Rykte:** Meddelanden filtrerade på grund av identifiering av en bifogad fil av andra Microsoft-kunder.</span><span class="sxs-lookup"><span data-stu-id="f82fd-277">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="f82fd-278">**Filtypsblock:** Meddelanden filtreras på grund av vilken typ av skadlig fil som identifieras i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f82fd-278">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="f82fd-279">**Antifras, URL-rykte, varumärkespersonifiering, skydd mot förfalskning:**</span><span class="sxs-lookup"><span data-stu-id="f82fd-279">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="f82fd-280">**URL-rykte:** Meddelanden filtreras på grund av identifiering av URL-adressen av andra Microsoft-kunder.</span><span class="sxs-lookup"><span data-stu-id="f82fd-280">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="f82fd-281">**Profilering:** Meddelanden filtrerade på grund av meddelanden från välkända varumärkespersonifieringsavsändare.</span><span class="sxs-lookup"><span data-stu-id="f82fd-281">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="f82fd-282">**Skydd mot förfalskning:** Meddelanden filtreras på grund av ett meddelande som försöker kapa en domän som mottagaren tillhör eller en domän som meddelandets avsändare inte äger.</span><span class="sxs-lookup"><span data-stu-id="f82fd-282">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="f82fd-283">**Skräppostskydd, massfiltrering:**</span><span class="sxs-lookup"><span data-stu-id="f82fd-283">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="f82fd-284">**Filtrering av** massutskick: Meddelanden filtreras baserat på tröskelvärdet för masskrekrektör (BCL) i en princip mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="f82fd-284">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="f82fd-285">**Användar- och domänpersonifiering (Defender för Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="f82fd-285">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f82fd-286">**Personifiering för användare:** Filtrerade meddelanden på grund av ett försök att utge sig för att vara en användare (meddelandeavsändare) som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f82fd-286">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="f82fd-287">**Domänpersonifiering:** Meddelanden filtrerade på grund av ett försök att utge sig för att vara en domän som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f82fd-287">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="f82fd-288">**Detonation av fil och URL (Defender för Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="f82fd-288">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f82fd-289">**Detonation för filer:** Meddelanden filtrerade efter Valv princip för bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="f82fd-289">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="f82fd-290">**URL-detonation**: Meddelande filtrerat av Valv princip för länkar.</span><span class="sxs-lookup"><span data-stu-id="f82fd-290">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="f82fd-291">**Post-delivery protection and ZAP (ATP) or ZAP (EOP) : Zero-hour** auto purge (ZAP) for malware, spam, and phishing.</span><span class="sxs-lookup"><span data-stu-id="f82fd-291">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="f82fd-292">Om du markerar en rad i informationstabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällade listan.</span><span class="sxs-lookup"><span data-stu-id="f82fd-292">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="f82fd-293">Exportera från trattvyn</span><span class="sxs-lookup"><span data-stu-id="f82fd-293">Export from Funnel view</span></span>

<span data-ttu-id="f82fd-294">När du har **klickat** **på Exportera** under Alternativ kan du välja något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f82fd-294">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="f82fd-295">**Sammanfattning (med data för de senaste 90 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="f82fd-295">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f82fd-296">**Information (med data för de senaste 30 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="f82fd-296">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f82fd-297">Välj **ett** område under Datum och klicka sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="f82fd-297">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f82fd-298">Data för de aktuella filtren exporteras till en .csv fil.</span><span class="sxs-lookup"><span data-stu-id="f82fd-298">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f82fd-299">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="f82fd-299">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f82fd-300">Om informationen innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="f82fd-300">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Trattvyn i statusrapporten För e-postflöde](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="f82fd-302">Tech view for the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="f82fd-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="f82fd-303">**Tech-vyn** liknar vyn **Tratt, med** mer detaljerad information om de konfigurerade funktionerna för skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="f82fd-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="f82fd-304">Från diagrammet kan du se hur meddelanden kategoriseras i olika faser av skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="f82fd-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="f82fd-305">Om du klickar **på fliken Teknisk** vy innehåller den här vyn som standard ett diagram och en informationstabell som är konfigurerad med följande filter:</span><span class="sxs-lookup"><span data-stu-id="f82fd-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="f82fd-306">**Datum:** De senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="f82fd-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f82fd-307">**Riktning**:</span><span class="sxs-lookup"><span data-stu-id="f82fd-307">**Direction**:</span></span>
  - <span data-ttu-id="f82fd-308">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-308">**Inbound**</span></span>
  - <span data-ttu-id="f82fd-309">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="f82fd-309">**Outbound**</span></span>
  - <span data-ttu-id="f82fd-310">**Årsorganisation**: det här antalet gäller meddelanden inom en klientorganisation, dvs.</span><span class="sxs-lookup"><span data-stu-id="f82fd-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f82fd-311">sender abc@domain.com skickar till mottagarens xyz@domain.com (räknas separat från inkommande och utgående)</span><span class="sxs-lookup"><span data-stu-id="f82fd-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="f82fd-312">Den samlade vyn och detaljtabellvyn ger 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="f82fd-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f82fd-313">Du kan ändra filtren genom att klicka på **Filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="f82fd-314">Samma filter från **vyn** Typ används.</span><span class="sxs-lookup"><span data-stu-id="f82fd-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f82fd-315">Det här diagrammet visar meddelanden ordnade i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="f82fd-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f82fd-316">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="f82fd-316">**Total email**</span></span>
- <span data-ttu-id="f82fd-317">**Tillåt i Edge** **och Filtrerad Edge**</span><span class="sxs-lookup"><span data-stu-id="f82fd-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="f82fd-318">**Transportregel tillåt och** **transportregel filtrerad** (e-postflödesregler)</span><span class="sxs-lookup"><span data-stu-id="f82fd-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="f82fd-319">**Inte skadlig programvara**, **Valv identifiering av bifogade filer** och <sup>\*</sup> **motoridentifiering mot skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="f82fd-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="f82fd-320">**Inte phish**, **DMARC-fel,** **personidentifiering,** <sup>\*</sup> **förfalskning och** **phish-identifiering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="f82fd-321">**Ingen identifiering med URL-detonation och** **URL-detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-322">**Inte** skräppost </span><span class="sxs-lookup"><span data-stu-id="f82fd-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="f82fd-323">**Icke-skadlig e-post** **, Valv identifiering av länkar** och <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="f82fd-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="f82fd-324"><sup>\*</sup>Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="f82fd-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="f82fd-325">När du hovrar över en kategori i diagrammet visas antalet meddelanden i den kategorin.</span><span class="sxs-lookup"><span data-stu-id="f82fd-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="f82fd-326">Informationstabellen innehåller följande information, visad i fallande datumordning:</span><span class="sxs-lookup"><span data-stu-id="f82fd-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f82fd-327">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="f82fd-327">**Date (UTC)**</span></span>
- <span data-ttu-id="f82fd-328">**Totalt antal e-postmeddelanden**</span><span class="sxs-lookup"><span data-stu-id="f82fd-328">**Total email**</span></span>
- <span data-ttu-id="f82fd-329">**Edge filtrerad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-329">**Edge filtered**</span></span>
- <span data-ttu-id="f82fd-330">**Regelmeddelanden:** Meddelanden filtrerade på grund av e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="f82fd-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="f82fd-331">**Motor för skydd mot skadlig programvara** Valv bifogade **filer:** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="f82fd-332">**DMARC, personifiering** <sup>\*</sup> , **spoof**, **nätfiske filtrerat:**</span><span class="sxs-lookup"><span data-stu-id="f82fd-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="f82fd-333">**DMARC:** Meddelanden filtreras på grund av att meddelandet inte klarar sin DMARC-autentiseringskontroll.</span><span class="sxs-lookup"><span data-stu-id="f82fd-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="f82fd-334">**Identifiering av URL-adresser**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-335">**Skräppostskydd filtreras**</span><span class="sxs-lookup"><span data-stu-id="f82fd-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="f82fd-336">**ZAP har tagits bort**</span><span class="sxs-lookup"><span data-stu-id="f82fd-336">**ZAP removed**</span></span>
- <span data-ttu-id="f82fd-337">**Identifiering av Valv länkar**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="f82fd-338"><sup>\*</sup>Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="f82fd-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="f82fd-339">Om du markerar en rad i informationstabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällade listan.</span><span class="sxs-lookup"><span data-stu-id="f82fd-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="f82fd-340">Exportera från teknisk vy</span><span class="sxs-lookup"><span data-stu-id="f82fd-340">Export from Tech view</span></span>

<span data-ttu-id="f82fd-341">När du **klickar** på Exportera **kan** du välja något av följande värden under Alternativ:</span><span class="sxs-lookup"><span data-stu-id="f82fd-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="f82fd-342">**Sammanfattning (med data för de senaste 90 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="f82fd-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f82fd-343">**Information (med data för de senaste 30 dagarna som mest)**</span><span class="sxs-lookup"><span data-stu-id="f82fd-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f82fd-344">Välj **ett** område under Datum och klicka sedan på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="f82fd-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f82fd-345">Data för de aktuella filtren exporteras till en .csv fil.</span><span class="sxs-lookup"><span data-stu-id="f82fd-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f82fd-346">Varje exporterad .csv är begränsad till 150 000 rader.</span><span class="sxs-lookup"><span data-stu-id="f82fd-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f82fd-347">Om informationen innehåller mer än 150 000 rader skapas .csv filer.</span><span class="sxs-lookup"><span data-stu-id="f82fd-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Tech view in the Mailflow status report](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="f82fd-349">Rapport om identifiering av skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="f82fd-349">Malware detections report</span></span>

<span data-ttu-id="f82fd-350">Rapporten **Om identifiering av skadlig programvara visar** information om identifiering av skadlig programvara i inkommande och utgående e-postmeddelanden (skadlig programvara som Exchange Online Protection eller EOP).</span><span class="sxs-lookup"><span data-stu-id="f82fd-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="f82fd-351">Mer information om skydd mot skadlig programvara i EOP finns [i Skydd mot skadlig programvara i EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="f82fd-352">Mängdvyfiltret tillåter 90 dagar, medan filtret i detaljtabellen bara tillåter 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="f82fd-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="f82fd-353">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-354">På sidan **E& och samarbetsrapporter hittar** du Skadlig **programvara som upptäckts i e-post** och klickar sedan **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="f82fd-355">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Identifiering av skadlig programvara i widgeten för e-& för e-& och samarbetsrapporter](../../media/malware-detections-widget.png)

<span data-ttu-id="f82fd-357">På **rapportsidan Identifiering av skadlig** programvara kan du filtrera både diagrammet och informationstabellen genom att klicka på **Filtrera** och välja något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f82fd-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="f82fd-358">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-359">**Riktning:** **Inkommande** **och utgående**</span><span class="sxs-lookup"><span data-stu-id="f82fd-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Rapportvyn i rapporten om identifiering av skadlig programvara i e-post](../../media/malware-detections-report-view.png)

<span data-ttu-id="f82fd-361">I informationstabellen under diagrammet kan du se följande information:</span><span class="sxs-lookup"><span data-stu-id="f82fd-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="f82fd-362">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-362">**Date**</span></span>
- <span data-ttu-id="f82fd-363">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="f82fd-363">**Sender address**</span></span>
- <span data-ttu-id="f82fd-364">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="f82fd-364">**Recipient address**</span></span>
- <span data-ttu-id="f82fd-365">**Meddelande-ID:** Tillgängligt i **sidhuvudet för meddelande-ID** i meddelandehuvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="f82fd-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="f82fd-366">Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observera vinkelparenteserna).</span><span class="sxs-lookup"><span data-stu-id="f82fd-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="f82fd-367">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f82fd-367">**Subject**</span></span>
- <span data-ttu-id="f82fd-368">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="f82fd-368">**Filename**</span></span>
- <span data-ttu-id="f82fd-369">**Namn på skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="f82fd-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="f82fd-370">E-postsvarstid – rapport</span><span class="sxs-lookup"><span data-stu-id="f82fd-370">Mail latency report</span></span>

<span data-ttu-id="f82fd-371">Rapporten **Om E-postfördröjning** i Defender för Office 365 innehåller information om den e-postleverans och den tidsfördröjning som uppgers i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f82fd-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="f82fd-372">Mer information finns i [E-postsvarstidsrapport](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="f82fd-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="f82fd-373">Rapport om identifiering av skräppost</span><span class="sxs-lookup"><span data-stu-id="f82fd-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="f82fd-374">Rapporten **om identifiering av skräppost** försvinner så småningom.</span><span class="sxs-lookup"><span data-stu-id="f82fd-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="f82fd-375">Samma information är tillgänglig i rapporten [om skydd mot hot.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f82fd-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="f82fd-376">Rapport om identifieringar av förfalskning</span><span class="sxs-lookup"><span data-stu-id="f82fd-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="f82fd-377">Rapporten om förbättrade identifieringar av förfalskning som beskrivs i den här artikeln är en förhandsversion, kan komma att ändras och är inte tillgänglig i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="f82fd-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="f82fd-378">I den äldre versionen av rapporten visas bara **Bra e-post** **och Fångad som skräppost.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="f82fd-379">I **rapporten Identifieringar av förfalskning** visas information om meddelanden som har blockerats eller tillåts på grund av förfalskning.</span><span class="sxs-lookup"><span data-stu-id="f82fd-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="f82fd-380">Mer information om förfalskning finns i [Skydd mot förfalskning i EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="f82fd-381">I den samlade vyn för rapporten kan du filtrera i 45 dagar, medan <sup>\*</sup> detaljvyn bara tillåter tio dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="f82fd-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="f82fd-382"><sup>\*</sup> Till slut kan du använda upp till 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="f82fd-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="f82fd-383">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-384">På sidan **E& och samarbetsrapporter** hittar du **Identifieringar av förfalskning** och klickar sedan **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="f82fd-385">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget för identifiering av förfalskning på sidan & för e-post och samarbete](../../media/spoof-detections-widget.png)

<span data-ttu-id="f82fd-387">Diagrammet visar följande information:</span><span class="sxs-lookup"><span data-stu-id="f82fd-387">The chart shows the following information:</span></span>

- <span data-ttu-id="f82fd-388">**Godkänd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-388">**Pass**</span></span>
- <span data-ttu-id="f82fd-389">**Fel**</span><span class="sxs-lookup"><span data-stu-id="f82fd-389">**Fail**</span></span>
- <span data-ttu-id="f82fd-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="f82fd-390">**SoftPass**</span></span>
- <span data-ttu-id="f82fd-391">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="f82fd-391">**None**</span></span>
- <span data-ttu-id="f82fd-392">**Annat**</span><span class="sxs-lookup"><span data-stu-id="f82fd-392">**Other**</span></span>

<span data-ttu-id="f82fd-393">När du hovrar över en dag (datapunkt) i diagrammet kan du se hur många falska meddelanden som påträffades och varför.</span><span class="sxs-lookup"><span data-stu-id="f82fd-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="f82fd-394">På sidan **Förfalskningsrapport kan** du filtrera både diagrammet och informationstabellen genom att klicka på **Filtrera** och markera ett eller flera av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f82fd-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="f82fd-395">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-396">**Resultat:**</span><span class="sxs-lookup"><span data-stu-id="f82fd-396">**Result**:</span></span>
  - <span data-ttu-id="f82fd-397">**Godkänd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-397">**Pass**</span></span>
  - <span data-ttu-id="f82fd-398">**Fel**</span><span class="sxs-lookup"><span data-stu-id="f82fd-398">**Fail**</span></span>
  - <span data-ttu-id="f82fd-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="f82fd-399">**SoftPass**</span></span>
  - <span data-ttu-id="f82fd-400">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="f82fd-400">**None**</span></span>
  - <span data-ttu-id="f82fd-401">**Annat**</span><span class="sxs-lookup"><span data-stu-id="f82fd-401">**Other**</span></span>
- <span data-ttu-id="f82fd-402">**Förfalskningstyp:** **Intern** och **Extern**</span><span class="sxs-lookup"><span data-stu-id="f82fd-402">**Spoof type**: **Internal** and **External**</span></span>

![Sidan Förfalskningsrapport på Microsoft 365 Defender portalen](../../media/spoof-detections-report-page.png)

<span data-ttu-id="f82fd-404">I informationstabellen under diagrammet kan du se följande information:</span><span class="sxs-lookup"><span data-stu-id="f82fd-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="f82fd-405">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-405">**Date**</span></span>
- <span data-ttu-id="f82fd-406">**Spoofed användare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-406">**Spoofed user**</span></span>
- <span data-ttu-id="f82fd-407">**Skicka infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="f82fd-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="f82fd-408">**Förfalskningstyp**</span><span class="sxs-lookup"><span data-stu-id="f82fd-408">**Spoof type**</span></span>
- <span data-ttu-id="f82fd-409">**Result**</span><span class="sxs-lookup"><span data-stu-id="f82fd-409">**Result**</span></span>
- <span data-ttu-id="f82fd-410">**Resultatkod**</span><span class="sxs-lookup"><span data-stu-id="f82fd-410">**Result code**</span></span>
- <span data-ttu-id="f82fd-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="f82fd-411">**SPF**</span></span>
- <span data-ttu-id="f82fd-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="f82fd-412">**DKIM**</span></span>
- <span data-ttu-id="f82fd-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="f82fd-413">**DMARC**</span></span>
- <span data-ttu-id="f82fd-414">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="f82fd-414">**Message count**</span></span>

<span data-ttu-id="f82fd-415">Mer information om sammansatta resultatkoder för autentisering finns i Rubriker mot skräppost [i Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="f82fd-416">Rapport över inskickade uppgifter</span><span class="sxs-lookup"><span data-stu-id="f82fd-416">Submissions report</span></span>

<span data-ttu-id="f82fd-417">Rapporten **Över inlämningar** visar information om objekt som administratörer har rapporterat till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="f82fd-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="f82fd-418">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f82fd-419">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-420">På sidan **E& och samarbetsrapporter** hittar du **Inlämningar** och klickar sedan **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="f82fd-421">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="f82fd-422">Om du vill [gå till administrationsinskick i Microsoft 365 Defender klickar](admin-submission.md)du på Gå till **inskickade material.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget för inlämningar på sidan & för e-post och samarbetsrapporter](../../media/submissions-report-widget.png)

<span data-ttu-id="f82fd-424">Diagrammet visar följande information:</span><span class="sxs-lookup"><span data-stu-id="f82fd-424">The chart shows the following information:</span></span>

- <span data-ttu-id="f82fd-425">**Väntande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-425">**Pending**</span></span>
- <span data-ttu-id="f82fd-426">**Slutförd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-426">**Completed**</span></span>

<span data-ttu-id="f82fd-427">På sidan **Inskickade** data kan du filtrera både diagrammet och detaljtabellen genom att klicka på **Filtrera** och välja ett eller flera av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f82fd-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="f82fd-428">**Rapporterad** datum : **Starttid** **och Sluttid**</span><span class="sxs-lookup"><span data-stu-id="f82fd-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="f82fd-429">**Inskickingstyp:** **E-post, URL** eller **fil** </span><span class="sxs-lookup"><span data-stu-id="f82fd-429">**Submission type**: **Email**, **URL**, or **File**</span></span>
- <span data-ttu-id="f82fd-430">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="f82fd-430">**Submission ID**</span></span>
- <span data-ttu-id="f82fd-431">**Id för nätverksmeddelande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-431">**Network Message ID**</span></span>
- <span data-ttu-id="f82fd-432">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-432">**Sender**</span></span>
- <span data-ttu-id="f82fd-433">**Namn**</span><span class="sxs-lookup"><span data-stu-id="f82fd-433">**Name**</span></span>
- <span data-ttu-id="f82fd-434">**Skickat av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-434">**Submitted by**</span></span>
- <span data-ttu-id="f82fd-435">**Orsak till att skicka:** **Inte skräppost,** **phish,** **skadlig** programvara eller **skräppost**</span><span class="sxs-lookup"><span data-stu-id="f82fd-435">**Reason for submitting**: **Not junk**, **Phish**, **Malware**, or **Spam**</span></span>
- <span data-ttu-id="f82fd-436">**Rescan-status:** **Väntande** eller **Slutförd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-436">**Rescan status**: **Pending** or **Completed**</span></span>

<span data-ttu-id="f82fd-437">Detaljtabellen under diagrammet visar samma information  och har samma alternativ  för Gruppera eller Anpassa kolumner som på fliken Skickat för analys i Skicka e-& **med** samarbete –  \> **inskickade.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-437">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="f82fd-438">Mer information finns i [Visa inskickade administratörer till Microsoft.](admin-submission.md#view-admin-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f82fd-438">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Rapportsida för inlämningar i Microsoft 365 Defender portalen](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="f82fd-440">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="f82fd-440">Threat protection status report</span></span>

<span data-ttu-id="f82fd-441">Statusrapporten **för skydd** mot hot är tillgänglig i både EOP och Defender för Office 365. Rapporterna innehåller däremot olika data.</span><span class="sxs-lookup"><span data-stu-id="f82fd-441">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="f82fd-442">Till exempel kan EOP-kunder visa information om skadlig programvara som upptäckts i e-post, men inte information om skadliga filer som upptäckts av [Valv-bifogade](mdo-for-spo-odb-and-teams.md)filer för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f82fd-442">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="f82fd-443">Rapporten innehåller antalet e-postmeddelanden med skadligt innehåll, till exempel filer eller webbadresser (URL:er) som har blockerats av antivirusmotorn, nolltimmars automatisk rensning [(ZAP)](zero-hour-auto-purge.md)och Defender för [Office 365-funktioner](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)som [Valv-länkar,](safe-links.md) [Valv-bilagor](safe-attachments.md)och personifieringsskyddsfunktioner i principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f82fd-443">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="f82fd-444">Du kan använda den här informationen för att identifiera trender eller avgöra om organisationens principer behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="f82fd-444">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="f82fd-445">**Obs!** Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="f82fd-445">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="f82fd-446">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-447">På sidan **E& och samarbetsrapporter** hittar du **status för skydd mot hot** och klickar sedan på Visa **information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-447">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="f82fd-448">Öppna någon av följande URL:er för att gå direkt till rapporten:</span><span class="sxs-lookup"><span data-stu-id="f82fd-448">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="f82fd-449">Defender för Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="f82fd-449">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="f82fd-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="f82fd-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget för hotskyddsstatus på sidan & och samarbetsrapporter](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="f82fd-452">Som standard visas data för de senaste 7 dagarna i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="f82fd-452">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="f82fd-453">Om du klickar **på Filter** **på** sidan för skydd mot hotstatus kan du välja ett datumintervall på 90 dagar (utvärderingsprenumerationer kan vara begränsat till 30 dagar).</span><span class="sxs-lookup"><span data-stu-id="f82fd-453">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="f82fd-454">I detaljtabellen filtreras data i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="f82fd-454">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="f82fd-455">De tillgängliga vyerna beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f82fd-455">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="f82fd-456">Visa data per översikt</span><span class="sxs-lookup"><span data-stu-id="f82fd-456">View data by Overview</span></span>

![Översiktsvy i rapporten om skydd mot hot](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="f82fd-458">I **vyn Visa data efter** översikt visas följande identifieringsinformation i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="f82fd-458">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="f82fd-459">**Skadlig programvara för e-post**</span><span class="sxs-lookup"><span data-stu-id="f82fd-459">**Email malware**</span></span>
- <span data-ttu-id="f82fd-460">**E-post phish**</span><span class="sxs-lookup"><span data-stu-id="f82fd-460">**Email phish**</span></span>
- <span data-ttu-id="f82fd-461">**Skadlig programvara för innehåll**</span><span class="sxs-lookup"><span data-stu-id="f82fd-461">**Content malware**</span></span>

<span data-ttu-id="f82fd-462">Ingen informationstabell är tillgänglig under diagrammet.</span><span class="sxs-lookup"><span data-stu-id="f82fd-462">No details table is available below the chart.</span></span>

<span data-ttu-id="f82fd-463">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-463">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f82fd-464">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-464">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-465">**Identifiering:** Skadlig programvara för **e-post, e-post phish** eller **skadlig programvara för innehåll** </span><span class="sxs-lookup"><span data-stu-id="f82fd-465">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="f82fd-466">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="f82fd-466">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f82fd-467">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="f82fd-467">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f82fd-468">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-468">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f82fd-469">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-469">**Direction**</span></span>
- <span data-ttu-id="f82fd-470">**Domän**</span><span class="sxs-lookup"><span data-stu-id="f82fd-470">**Domain**</span></span>
- <span data-ttu-id="f82fd-471">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="f82fd-471">**Policy type**</span></span>

<span data-ttu-id="f82fd-472">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-472">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="f82fd-473">Visa data efter \> e-post phish och diagramfördelning efter identifieringsteknik</span><span class="sxs-lookup"><span data-stu-id="f82fd-473">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Vy för identifieringsteknik för nätfiske i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="f82fd-475">I vyn **Visa data via \> e-post phish** **och diagram** som ligger i detalj efter vyn Identifieringsteknik visas följande information i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="f82fd-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="f82fd-476">**URL-skadligt** <sup>\*</sup> rykte: Skadligt URL-rykte skapat av Defender för Office 365 av detonationer i andra Microsoft 365 kunder.</span><span class="sxs-lookup"><span data-stu-id="f82fd-476">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="f82fd-477">**Avancerat filter:** Nätfiskesignaler baserade på maskininlärning.</span><span class="sxs-lookup"><span data-stu-id="f82fd-477">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="f82fd-478">**Allmänt filter:** Nätfiskesignaler baserade på analysregler.</span><span class="sxs-lookup"><span data-stu-id="f82fd-478">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="f82fd-479">**Förfalskning av årsorganisation**: Avsändaren försöker kapa mottagardomänen.</span><span class="sxs-lookup"><span data-stu-id="f82fd-479">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="f82fd-480">**Förfalskning av extern domän**: Avsändaren försöker kapa en annan domän.</span><span class="sxs-lookup"><span data-stu-id="f82fd-480">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="f82fd-481">**Förfalskning DMARC**: DMARC-autentiseringsfel på meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f82fd-481">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="f82fd-482">**Personifieringsmärke**: Personifiering av välkända varumärken baserat på avsändare.</span><span class="sxs-lookup"><span data-stu-id="f82fd-482">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="f82fd-483">**Identifiering av blandad analys**</span><span class="sxs-lookup"><span data-stu-id="f82fd-483">**Mixed analysis detection**</span></span>
- <span data-ttu-id="f82fd-484">**Beryknat fil**</span><span class="sxs-lookup"><span data-stu-id="f82fd-484">**File reputation**</span></span>
- <span data-ttu-id="f82fd-485">**Fingeravtrycksmatchning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-485">**Fingerprint matching**</span></span>
- <span data-ttu-id="f82fd-486">**URL-detonationsrekt**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-486">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-487">**URL-detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-487">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-488">**Personifieringsanvändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-488">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-489">**Personifieringsdomän:** <sup>\*</sup> Personifiering av domäner som kunden äger eller definierar.</span><span class="sxs-lookup"><span data-stu-id="f82fd-489">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="f82fd-490">**Postlådeintelligens** <sup>\*</sup> : Personifiering av användare som definierats av administratören eller som lärt sig via postlådeintelligens.</span><span class="sxs-lookup"><span data-stu-id="f82fd-490">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="f82fd-491">**Fil detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-491">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-492">**Kampanj**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-492">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="f82fd-493">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="f82fd-493">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f82fd-494">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-494">**Date**</span></span>
- <span data-ttu-id="f82fd-495">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f82fd-495">**Subject**</span></span>
- <span data-ttu-id="f82fd-496">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-496">**Sender**</span></span>
- <span data-ttu-id="f82fd-497">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-497">**Recipients**</span></span>
- <span data-ttu-id="f82fd-498">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-498">**Detected by**</span></span>
- <span data-ttu-id="f82fd-499">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="f82fd-499">**Delivery Status**</span></span>
- <span data-ttu-id="f82fd-500">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="f82fd-500">**Source of Compromise**</span></span>
- <span data-ttu-id="f82fd-501">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-501">**Tags**</span></span>

<span data-ttu-id="f82fd-502">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-502">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f82fd-503">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-503">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-504">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-504">**Detection**</span></span>
- <span data-ttu-id="f82fd-505">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="f82fd-505">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f82fd-506">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-506">**Direction**</span></span>
- <span data-ttu-id="f82fd-507">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="f82fd-507">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f82fd-508">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-508">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f82fd-509">**Domän**</span><span class="sxs-lookup"><span data-stu-id="f82fd-509">**Domain**</span></span>
- <span data-ttu-id="f82fd-510">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="f82fd-510">**Policy type**</span></span>
- <span data-ttu-id="f82fd-511">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="f82fd-511">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f82fd-512">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-512">**Recipients**</span></span>

<span data-ttu-id="f82fd-513">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-513">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="f82fd-514">Visa data efter skadlig programvara \> för e-post och diagramfördelning med identifieringsteknik</span><span class="sxs-lookup"><span data-stu-id="f82fd-514">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Vy för identifieringsteknik för skadlig programvara i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="f82fd-516">I vyn **Visa data efter \> e-post** **skadlig** programvara och diagram som ligger i detalj i vyn Identifieringsteknik visas följande information i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="f82fd-516">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="f82fd-517">**Detonation för filen:** <sup>\*</sup> Identifiering av Valv bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="f82fd-517">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="f82fd-518">**Rykte för fil detonation** <sup>\*</sup> : Allt skadligt filrynde som genererats av Defender för Office 365 detonationer.</span><span class="sxs-lookup"><span data-stu-id="f82fd-518">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="f82fd-519">**Beryknat fil**</span><span class="sxs-lookup"><span data-stu-id="f82fd-519">**File reputation**</span></span>
- <span data-ttu-id="f82fd-520">**Motor mot skadlig programvara:** <sup>\*</sup> Identifiering från sökmotorer mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="f82fd-520">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="f82fd-521">**Filtypsblockering mot skadlig programvara:** Det här är e-postmeddelanden som filtrerats bort på grund av vilken typ av skadlig fil som identifieras i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f82fd-521">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="f82fd-522">**URL-skadligt rykte**</span><span class="sxs-lookup"><span data-stu-id="f82fd-522">**URL malicious reputation**</span></span>
- <span data-ttu-id="f82fd-523">**URL-detonation**</span><span class="sxs-lookup"><span data-stu-id="f82fd-523">**URL detonation**</span></span>
- <span data-ttu-id="f82fd-524">**URL-detonationsrekt**</span><span class="sxs-lookup"><span data-stu-id="f82fd-524">**URL detonation reputation**</span></span>
- <span data-ttu-id="f82fd-525">**Kampanj**</span><span class="sxs-lookup"><span data-stu-id="f82fd-525">**Campaign**</span></span>

<span data-ttu-id="f82fd-526">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="f82fd-526">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f82fd-527">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-527">**Date**</span></span>
- <span data-ttu-id="f82fd-528">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f82fd-528">**Subject**</span></span>
- <span data-ttu-id="f82fd-529">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-529">**Sender**</span></span>
- <span data-ttu-id="f82fd-530">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-530">**Recipients**</span></span>
- <span data-ttu-id="f82fd-531">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-531">**Detected by**</span></span>
- <span data-ttu-id="f82fd-532">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="f82fd-532">**Delivery Status**</span></span>
- <span data-ttu-id="f82fd-533">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="f82fd-533">**Source of Compromise**</span></span>
- <span data-ttu-id="f82fd-534">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-534">**Tags**</span></span>

<span data-ttu-id="f82fd-535">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-535">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f82fd-536">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-536">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-537">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-537">**Detection**</span></span>
- <span data-ttu-id="f82fd-538">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="f82fd-538">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f82fd-539">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-539">**Direction**</span></span>
- <span data-ttu-id="f82fd-540">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="f82fd-540">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f82fd-541">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-541">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f82fd-542">**Domän**</span><span class="sxs-lookup"><span data-stu-id="f82fd-542">**Domain**</span></span>
- <span data-ttu-id="f82fd-543">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="f82fd-543">**Policy type**</span></span>
- <span data-ttu-id="f82fd-544">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="f82fd-544">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f82fd-545">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-545">**Recipients**</span></span>

<span data-ttu-id="f82fd-546">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-546">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="f82fd-547">Diagramfördelning efter typ av princip och Visa data efter e-post \> phish eller Visa data efter e-postprogram \></span><span class="sxs-lookup"><span data-stu-id="f82fd-547">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Vy av principtyp för nätfiskemeddelande eller skadlig e-post i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="f82fd-549">I **diagramfördelningen efter typ av princip** och Visa data efter e-postfras eller **Visa data \>** efter e-post för skadlig programvara visas följande information i diagrammen: **\>**</span><span class="sxs-lookup"><span data-stu-id="f82fd-549">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="f82fd-550">**Skydd mot skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="f82fd-550">**Anti-malware**</span></span>
- <span data-ttu-id="f82fd-551">**Valv Bifogade filer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f82fd-551">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="f82fd-552">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="f82fd-552">**Anti-phish**</span></span>
- <span data-ttu-id="f82fd-553">**Skräppostskydd**</span><span class="sxs-lookup"><span data-stu-id="f82fd-553">**Anti-spam**</span></span>
- <span data-ttu-id="f82fd-554">**E-postflödesregel** (kallas även transportregel)</span><span class="sxs-lookup"><span data-stu-id="f82fd-554">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="f82fd-555">**Andra**</span><span class="sxs-lookup"><span data-stu-id="f82fd-555">**Others**</span></span>

<span data-ttu-id="f82fd-556">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="f82fd-556">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f82fd-557">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-557">**Date**</span></span>
- <span data-ttu-id="f82fd-558">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f82fd-558">**Subject**</span></span>
- <span data-ttu-id="f82fd-559">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-559">**Sender**</span></span>
- <span data-ttu-id="f82fd-560">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-560">**Recipients**</span></span>
- <span data-ttu-id="f82fd-561">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-561">**Detected by**</span></span>
- <span data-ttu-id="f82fd-562">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="f82fd-562">**Delivery Status**</span></span>
- <span data-ttu-id="f82fd-563">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="f82fd-563">**Source of Compromise**</span></span>
- <span data-ttu-id="f82fd-564">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-564">**Tags**</span></span>

<span data-ttu-id="f82fd-565">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-565">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f82fd-566">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-566">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-567">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-567">**Detection**</span></span>
- <span data-ttu-id="f82fd-568">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="f82fd-568">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f82fd-569">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-569">**Direction**</span></span>
- <span data-ttu-id="f82fd-570">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="f82fd-570">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f82fd-571">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-571">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f82fd-572">**Domän**</span><span class="sxs-lookup"><span data-stu-id="f82fd-572">**Domain**</span></span>
- <span data-ttu-id="f82fd-573">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="f82fd-573">**Policy type**</span></span>
- <span data-ttu-id="f82fd-574">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="f82fd-574">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f82fd-575">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-575">**Recipients**</span></span>

<span data-ttu-id="f82fd-576">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-576">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="f82fd-577">Diagram efter leveransstatus och Visa data efter e-post \> phish eller Visa data efter e-post skadlig \> programvara</span><span class="sxs-lookup"><span data-stu-id="f82fd-577">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Leveransstatusvy för nätfiskemeddelande och skadlig e-post i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="f82fd-579">I **diagramfördelningen efter leveransstatus** och Visa data efter e-postfras eller **Visa data \>** efter e-post för skadlig programvara visas följande information i diagrammen: **\>**</span><span class="sxs-lookup"><span data-stu-id="f82fd-579">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="f82fd-580">**Värdpostlåda: Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="f82fd-580">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="f82fd-581">**Värdpostlåda: Skräppost**</span><span class="sxs-lookup"><span data-stu-id="f82fd-581">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="f82fd-582">**Värdpostlåda: Anpassad mapp**</span><span class="sxs-lookup"><span data-stu-id="f82fd-582">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="f82fd-583">**Värdpostlåda: Borttagna objekt**</span><span class="sxs-lookup"><span data-stu-id="f82fd-583">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="f82fd-584">**Vidarebefordrad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-584">**Forwarded**</span></span>
- <span data-ttu-id="f82fd-585">**Lokal server: Levererad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-585">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="f82fd-586">**Karantän**</span><span class="sxs-lookup"><span data-stu-id="f82fd-586">**Quarantine**</span></span>
- <span data-ttu-id="f82fd-587">**Leveransen misslyckades**</span><span class="sxs-lookup"><span data-stu-id="f82fd-587">**Delivery failed**</span></span>
- <span data-ttu-id="f82fd-588">**Nedsnad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-588">**Dropped**</span></span>

<span data-ttu-id="f82fd-589">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="f82fd-589">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f82fd-590">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-590">**Date**</span></span>
- <span data-ttu-id="f82fd-591">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f82fd-591">**Subject**</span></span>
- <span data-ttu-id="f82fd-592">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-592">**Sender**</span></span>
- <span data-ttu-id="f82fd-593">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-593">**Recipients**</span></span>
- <span data-ttu-id="f82fd-594">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-594">**Detected by**</span></span>
- <span data-ttu-id="f82fd-595">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="f82fd-595">**Delivery Status**</span></span>
- <span data-ttu-id="f82fd-596">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="f82fd-596">**Source of Compromise**</span></span>
- <span data-ttu-id="f82fd-597">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-597">**Tags**</span></span>

<span data-ttu-id="f82fd-598">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-598">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f82fd-599">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-599">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-600">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-600">**Detection**</span></span>
- <span data-ttu-id="f82fd-601">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="f82fd-601">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f82fd-602">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-602">**Direction**</span></span>
- <span data-ttu-id="f82fd-603">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="f82fd-603">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f82fd-604">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-604">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f82fd-605">**Domän**</span><span class="sxs-lookup"><span data-stu-id="f82fd-605">**Domain**</span></span>
- <span data-ttu-id="f82fd-606">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="f82fd-606">**Policy type**</span></span>
- <span data-ttu-id="f82fd-607">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="f82fd-607">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f82fd-608">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-608">**Recipients**</span></span>

<span data-ttu-id="f82fd-609">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-609">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="f82fd-610">Visa data efter skadlig programvara för \> innehåll</span><span class="sxs-lookup"><span data-stu-id="f82fd-610">View data by Content \> Malware</span></span>

![Vyn För skadlig programvara för innehåll i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="f82fd-612">I vyn **Visa data efter skadlig \>** programvara för innehåll visas följande information i diagrammet för Microsoft Defender för Office 365 organisationer:</span><span class="sxs-lookup"><span data-stu-id="f82fd-612">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="f82fd-613">**Motor mot skadlig programvara:** Skadliga filer som upptäckts i Sharepoint, OneDrive och Microsoft Teams av den [inbyggda virusidentifieringen i Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-613">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="f82fd-614">**Fildeonation:** Skadliga filer som upptäckts [Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f82fd-614">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="f82fd-615">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="f82fd-615">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f82fd-616">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-616">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-617">**Plats**</span><span class="sxs-lookup"><span data-stu-id="f82fd-617">**Location**</span></span>
- <span data-ttu-id="f82fd-618">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-618">**Detected by**</span></span>
- <span data-ttu-id="f82fd-619">**Namn på skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="f82fd-619">**Malware name**</span></span>

<span data-ttu-id="f82fd-620">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-620">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f82fd-621">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-621">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-622">**Identifiering:** **Motor mot skadlig programvara** eller **detonation av filer**</span><span class="sxs-lookup"><span data-stu-id="f82fd-622">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="f82fd-623">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-623">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="f82fd-624">Visa data efter åsidosättning av system</span><span class="sxs-lookup"><span data-stu-id="f82fd-624">View data by System override</span></span>

![Vy för åsidosättning av meddelande i rapporten om skydd mot hot](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="f82fd-626">I vyn **För visning av data efter** system, visas följande orsak till åsidosättning i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="f82fd-626">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="f82fd-627">**Lokal hoppa över**</span><span class="sxs-lookup"><span data-stu-id="f82fd-627">**On-premises skip**</span></span>
- <span data-ttu-id="f82fd-628">**IP tillåt**</span><span class="sxs-lookup"><span data-stu-id="f82fd-628">**IP allow**</span></span>
- <span data-ttu-id="f82fd-629">**Exchange för e-posttransport** (e-postflödesregel)</span><span class="sxs-lookup"><span data-stu-id="f82fd-629">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="f82fd-630">**Organisationen tillät avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-630">**Organization allowed senders**</span></span>
- <span data-ttu-id="f82fd-631">**Tillåtna domäner för organisationen**</span><span class="sxs-lookup"><span data-stu-id="f82fd-631">**Organization allowed domains**</span></span>
- <span data-ttu-id="f82fd-632">**ZAP inte aktiverat**</span><span class="sxs-lookup"><span data-stu-id="f82fd-632">**ZAP not enabled**</span></span>
- <span data-ttu-id="f82fd-633">**Mappen Skräppost är inte aktiverad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-633">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="f82fd-634">**Användare Valv avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-634">**User Safe Sender**</span></span>
- <span data-ttu-id="f82fd-635">**User Valv Domain**</span><span class="sxs-lookup"><span data-stu-id="f82fd-635">**User Safe Domain**</span></span>

<span data-ttu-id="f82fd-636">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="f82fd-636">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f82fd-637">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-637">**Date**</span></span>
- <span data-ttu-id="f82fd-638">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f82fd-638">**Subject**</span></span>
- <span data-ttu-id="f82fd-639">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-639">**Sender**</span></span>
- <span data-ttu-id="f82fd-640">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-640">**Recipients**</span></span>
- <span data-ttu-id="f82fd-641">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-641">**Detected by**</span></span>
- <span data-ttu-id="f82fd-642">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="f82fd-642">**Delivery Status**</span></span>
- <span data-ttu-id="f82fd-643">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="f82fd-643">**Source of Compromise**</span></span>
- <span data-ttu-id="f82fd-644">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-644">**Tags**</span></span>

<span data-ttu-id="f82fd-645">Om du **klickar på** Filter är följande filter tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f82fd-645">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f82fd-646">**Datum (UTC)** **startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f82fd-646">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f82fd-647">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-647">**Detection**</span></span>
- <span data-ttu-id="f82fd-648">**Skyddad av**: **MDO** (Defender för Office 365) eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="f82fd-648">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f82fd-649">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-649">**Direction**</span></span>
- <span data-ttu-id="f82fd-650">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="f82fd-650">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f82fd-651">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-651">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f82fd-652">**Domän**</span><span class="sxs-lookup"><span data-stu-id="f82fd-652">**Domain**</span></span>
- <span data-ttu-id="f82fd-653">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="f82fd-653">**Policy type**</span></span>
- <span data-ttu-id="f82fd-654">**Principnamn** (endast informationstabell)</span><span class="sxs-lookup"><span data-stu-id="f82fd-654">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f82fd-655">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-655">**Recipients**</span></span>

<span data-ttu-id="f82fd-656">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-656">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f82fd-657"><sup>\*</sup>Endast Defender Office 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f82fd-657"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="f82fd-658">Den viktigaste rapporten om skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="f82fd-658">Top malware report</span></span>

<span data-ttu-id="f82fd-659">Den **viktigaste rapporten om** skadlig programvara visar de olika typer av skadlig programvara som identifierats av skydd mot skadlig programvara i [EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-659">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="f82fd-660">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-661">På sidan **E& och samarbetsrapporter** hittar du **Den största skadlig programvara** och klickar sedan på Visa **information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-661">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="f82fd-662">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-662">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Populära widget för skadlig programvara på sidan & och samarbetsrapporter](../../media/top-malware-report-widget.png)

<span data-ttu-id="f82fd-664">När du hovrar över en kil i cirkeldiagrammet kan du se namnet på en typ av skadlig programvara och hur många meddelanden som identifierats som har den skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="f82fd-664">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="f82fd-665">På **sidan Den översta rapporten** om skadlig programvara visas en större version av cirkeldiagrammet på rapportsidan. I detaljtabellen under diagrammet visas följande information:</span><span class="sxs-lookup"><span data-stu-id="f82fd-665">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="f82fd-666">**Populära skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="f82fd-666">**Top malware**</span></span>
- <span data-ttu-id="f82fd-667">**Antal**</span><span class="sxs-lookup"><span data-stu-id="f82fd-667">**Count**</span></span>

<span data-ttu-id="f82fd-668">Om du klickar **på** Filter kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-668">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Den övre vyn för skadlig programvara](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="f82fd-670">Rapport om skydd mot URL-hot</span><span class="sxs-lookup"><span data-stu-id="f82fd-670">URL threat protection report</span></span>

<span data-ttu-id="f82fd-671">Rapporten **om skydd mot URL-hot** är tillgänglig i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="f82fd-671">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f82fd-672">Mer information finns i Rapporten [om url-skydd mot hot.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="f82fd-672">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="f82fd-673">Rapport över användarrapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="f82fd-673">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f82fd-674">För att rapporten **över användarrapporter ska** fungera korrekt måste granskningsloggning **vara aktiverad** i din Microsoft 365 miljö.</span><span class="sxs-lookup"><span data-stu-id="f82fd-674">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="f82fd-675">Det görs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f82fd-675">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="f82fd-676">Mer information finns i aktivera [Microsoft 365 eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-676">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="f82fd-677">Rapporten **Om användarrapporter** visar information om e-postmeddelanden som användare har rapporterat som skräppost, nätfiskeförsök eller bra [e-post](enable-the-report-message-add-in.md) med hjälp av tilläggen Rapportmeddelande eller [Rapport nätfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-677">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="f82fd-678">Om du vill visa rapporten i Microsoft 365 Defender  går du till Rapporterar \> **e-& samarbete** \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f82fd-679">På sidan **E& och samarbetsrapporter** hittar du användarrapporterade **meddelanden** och klickar sedan **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-679">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="f82fd-680">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="f82fd-680">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="f82fd-681">Om du vill [gå till administrationsinskick i Microsoft 365 Defender klickar](admin-submission.md)du på Gå till **inskickade material.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-681">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget för användarrapporter på sidan e& och samarbetsrapporter](../../media/user-reported-messages-widget.png)

<span data-ttu-id="f82fd-683">På sidan **Användarrapporterade** meddelanden kan du filtrera både diagrammet och informationstabellen genom att klicka på **Filtrera** och välja ett eller flera av följande värden i den utfäll plats som visas:</span><span class="sxs-lookup"><span data-stu-id="f82fd-683">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f82fd-684">**Rapporterad** datum : **Starttid** **och Sluttid**</span><span class="sxs-lookup"><span data-stu-id="f82fd-684">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="f82fd-685">**Rapporterad av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-685">**Reported by**</span></span>
- <span data-ttu-id="f82fd-686">**Ämne för e-post**</span><span class="sxs-lookup"><span data-stu-id="f82fd-686">**Email subject**</span></span>
- <span data-ttu-id="f82fd-687">**Rapporterat ID för meddelande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-687">**Message reported ID**</span></span>
- <span data-ttu-id="f82fd-688">**Id för nätverksmeddelande**</span><span class="sxs-lookup"><span data-stu-id="f82fd-688">**Network Message ID**</span></span>
- <span data-ttu-id="f82fd-689">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-689">**Sender**</span></span>
- <span data-ttu-id="f82fd-690">**Rapporterad orsak**</span><span class="sxs-lookup"><span data-stu-id="f82fd-690">**Reported reason**</span></span>
  - <span data-ttu-id="f82fd-691">**Inte skräppost**</span><span class="sxs-lookup"><span data-stu-id="f82fd-691">**Not junk**</span></span>
  - <span data-ttu-id="f82fd-692">**Nätfiske**</span><span class="sxs-lookup"><span data-stu-id="f82fd-692">**Phish**</span></span>
  - <span data-ttu-id="f82fd-693">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="f82fd-693">**Spam**</span></span>
- <span data-ttu-id="f82fd-694">**Phish simulering**: **Ja** eller **Nej**</span><span class="sxs-lookup"><span data-stu-id="f82fd-694">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="f82fd-695">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f82fd-695">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f82fd-696">Om du vill gruppera posterna **klickar du** på Gruppera och väljer något av följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="f82fd-696">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="f82fd-697">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="f82fd-697">**None**</span></span>
- <span data-ttu-id="f82fd-698">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="f82fd-698">**Reason**</span></span>
- <span data-ttu-id="f82fd-699">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-699">**Sender**</span></span>
- <span data-ttu-id="f82fd-700">**Rapporterad av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-700">**Reported by**</span></span>
- <span data-ttu-id="f82fd-701">**Rescan-resultat**</span><span class="sxs-lookup"><span data-stu-id="f82fd-701">**Rescan result**</span></span>
- <span data-ttu-id="f82fd-702">**Phish-simulering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-702">**Phish simulation**</span></span>

![Rapport över användarrapporterade meddelanden](../../media/user-reported-messages-report.png)

<span data-ttu-id="f82fd-704">I informationstabellen under diagrammet kan du se följande information:</span><span class="sxs-lookup"><span data-stu-id="f82fd-704">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="f82fd-705">**Ämne för e-post**</span><span class="sxs-lookup"><span data-stu-id="f82fd-705">**Email subject**</span></span>
- <span data-ttu-id="f82fd-706">**Rapporterad av**</span><span class="sxs-lookup"><span data-stu-id="f82fd-706">**Reported by**</span></span>
- <span data-ttu-id="f82fd-707">**Rapporterad**</span><span class="sxs-lookup"><span data-stu-id="f82fd-707">**Date reported**</span></span>
- <span data-ttu-id="f82fd-708">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-708">**Sender**</span></span>
- <span data-ttu-id="f82fd-709">**Rapporterad orsak**</span><span class="sxs-lookup"><span data-stu-id="f82fd-709">**Reported reason**</span></span>
- <span data-ttu-id="f82fd-710">**Rescan-resultat**</span><span class="sxs-lookup"><span data-stu-id="f82fd-710">**Rescan result**</span></span>
- <span data-ttu-id="f82fd-711">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="f82fd-711">**Tags**</span></span>

<span data-ttu-id="f82fd-712">Om du vill skicka ett meddelande till Microsoft för analys markerar du meddelandeposten i tabellen, klickar på Skicka till **Microsoft** för analys och väljer sedan något av följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="f82fd-712">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="f82fd-713">**Rapportrensning**</span><span class="sxs-lookup"><span data-stu-id="f82fd-713">**Report clean**</span></span>
- <span data-ttu-id="f82fd-714">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="f82fd-714">**Report phishing**</span></span>
- <span data-ttu-id="f82fd-715">**Rapportera skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="f82fd-715">**Report malware**</span></span>
- <span data-ttu-id="f82fd-716">**Rapportera skräppost**'</span><span class="sxs-lookup"><span data-stu-id="f82fd-716">**Report spam**'</span></span>
- <span data-ttu-id="f82fd-717">**Undersökning av utlösare** (Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="f82fd-717">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f82fd-718">Vilka behörigheter krävs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="f82fd-718">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f82fd-719">För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Microsoft 365 Defender portalen:</span><span class="sxs-lookup"><span data-stu-id="f82fd-719">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f82fd-720">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="f82fd-720">**Organization Management**</span></span>
- <span data-ttu-id="f82fd-721">**Säkerhetsadministratör**</span><span class="sxs-lookup"><span data-stu-id="f82fd-721">**Security Administrator**</span></span>
- <span data-ttu-id="f82fd-722">**Säkerhetsläsare**</span><span class="sxs-lookup"><span data-stu-id="f82fd-722">**Security Reader**</span></span>
- <span data-ttu-id="f82fd-723">**Global Reader**</span><span class="sxs-lookup"><span data-stu-id="f82fd-723">**Global Reader**</span></span>

<span data-ttu-id="f82fd-724">Mer information finns i [Behörigheter i Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f82fd-724">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f82fd-725">**Obs!** Om du lägger till användare i motsvarande Azure Active Directory-roll i Administrationscenter för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f82fd-725">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f82fd-726">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f82fd-726">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f82fd-727">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="f82fd-727">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f82fd-728">Om du inte ser data i rapporterna kan du kontrollera att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="f82fd-728">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f82fd-729">Mer information finns i [Skydda mot hot.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="f82fd-729">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f82fd-730">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f82fd-730">Related topics</span></span>

[<span data-ttu-id="f82fd-731">Skydd mot skräppost och skadlig programvara i EOP</span><span class="sxs-lookup"><span data-stu-id="f82fd-731">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="f82fd-732">Smarta rapporter och insikter i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="f82fd-732">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f82fd-733">Visa e-postflödesrapporter i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="f82fd-733">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="f82fd-734">Visa rapporter för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="f82fd-734">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
