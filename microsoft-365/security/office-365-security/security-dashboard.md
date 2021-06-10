---
title: Översikt över säkerhetsinstrumentpanel
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Använd den nya säkerhetspanelen för att Office 365 status för skydd mot hot, och visa och agera på säkerhetsvarningar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c9a49b9b8fc1edd9b2928250e8cae135acb75f4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274418"
---
# <a name="security-dashboard"></a><span data-ttu-id="99068-103">Säkerhetsinstrumentpanel</span><span class="sxs-lookup"><span data-stu-id="99068-103">Security Dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a><span data-ttu-id="99068-104">Grundläggande funktioner och hur du öppnar Säkerhetsinstrumentpanel</span><span class="sxs-lookup"><span data-stu-id="99068-104">Basic functions and how to open Security Dashboard</span></span>

<span data-ttu-id="99068-105">Säkerhets- [& efterlevnadscenter](../../compliance/microsoft-365-compliance-center.md) gör det möjligt för organisationen att hantera dataskydd och efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="99068-105">The [Security & Compliance Center](../../compliance/microsoft-365-compliance-center.md) enables your organization to manage data protection and compliance.</span></span> <span data-ttu-id="99068-106">Om du har de behörigheter som krävs kan du med hjälp av instrumentpanelen för säkerhet granska din status för skydd mot hot samt visa och agera på säkerhetsvarningar.</span><span class="sxs-lookup"><span data-stu-id="99068-106">Assuming you have the necessary permissions, the Security Dashboard enables you to review your Threat Protection Status, as well as view and act on security alerts.</span></span>

<span data-ttu-id="99068-107">Titta på videon för att få en översikt och läs sedan den här artikeln om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="99068-107">Watch the video to get an overview, and then read this article to learn more.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

<span data-ttu-id="99068-108">Beroende på vad din organisations prenumeration inkluderar innehåller instrumentpanelen för säkerhet flera widgetar, till exempel Sammanfattning av hothantering, Hotskyddsstatus, Global veckovis identifiering av hot, skadlig programvara med mera, som beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="99068-108">Depending on what your organization's subscription includes, the Security Dashboard includes several widgets, such as Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware, and more, as described in the following sections.</span></span>

<span data-ttu-id="99068-109">Om du vill visa Säkerhetsinstrumentpanel går [du & Säkerhets- och efterlevnadscenter](../../compliance/microsoft-365-compliance-center.md)på **Instrumentpanelen för hantering av** \> **hot.**</span><span class="sxs-lookup"><span data-stu-id="99068-109">To view the Security Dashboard, in the [Security & Compliance Center](../../compliance/microsoft-365-compliance-center.md), go to **Threat management** \> **Dashboard**.</span></span>

> [!NOTE]
> <span data-ttu-id="99068-110">Du måste vara global administratör, säkerhetsadministratör eller säkerhetsläsare för att kunna visa instrumentpanelen för säkerhet.</span><span class="sxs-lookup"><span data-stu-id="99068-110">You must be a global administrator, a security administrator, or a security reader to view the Security Dashboard.</span></span> <span data-ttu-id="99068-111">Vissa widgetar kräver ytterligare behörigheter för att visa.</span><span class="sxs-lookup"><span data-stu-id="99068-111">Some widgets require additional permissions to view.</span></span> <span data-ttu-id="99068-112">Mer information finns i [Behörigheter i Säkerhets- & Kompatibilitetscenter.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="99068-112">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="threat-management-summary"></a><span data-ttu-id="99068-113">Sammanfattning av hothantering</span><span class="sxs-lookup"><span data-stu-id="99068-113">Threat Management Summary</span></span>

<span data-ttu-id="99068-114">Widgeten Sammanfattning av hothantering visar direkt hur organisationen har skyddats mot hot under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="99068-114">The Threat Management Summary widget tells you at a glance how your organization was protected from threats over the past seven (7) days.</span></span>

![Instrumentpanel för säkerhet – widget för sammanfattning av hothantering](../../media/SecDash-ThreatMgmtSummary.png)

<span data-ttu-id="99068-116">Vilken information du ser i sammanfattningen av hothanteringen beror på vad din prenumeration innehåller.</span><span class="sxs-lookup"><span data-stu-id="99068-116">The information you'll see in the Threat Management Summary depends on what you subscription includes.</span></span> <span data-ttu-id="99068-117">I följande tabell beskrivs vilken information som ingår i Office 365 E3 och Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="99068-117">The following table describes what information is included for Office 365 E3 and Office 365 E5.</span></span>

|<span data-ttu-id="99068-118">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="99068-118">Office 365 E3</span></span>|<span data-ttu-id="99068-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="99068-119">Office 365 E5</span></span>|
|---|---|
|<span data-ttu-id="99068-120">Skadliga meddelanden blockerade</span><span class="sxs-lookup"><span data-stu-id="99068-120">Malware messages blocked</span></span><br><span data-ttu-id="99068-121">Nätfiskemeddelanden är blockerade</span><span class="sxs-lookup"><span data-stu-id="99068-121">Phishing messages blocked</span></span><br><span data-ttu-id="99068-122">Meddelanden som rapporterats av användare</span><span class="sxs-lookup"><span data-stu-id="99068-122">Messages reported by users</span></span><br><br><br><br>|<span data-ttu-id="99068-123">Skadliga meddelanden blockerade</span><span class="sxs-lookup"><span data-stu-id="99068-123">Malware messages blocked</span></span><br><span data-ttu-id="99068-124">Nätfiskemeddelanden är blockerade</span><span class="sxs-lookup"><span data-stu-id="99068-124">Phishing messages blocked</span></span><br><span data-ttu-id="99068-125">Meddelanden som rapporterats av användare</span><span class="sxs-lookup"><span data-stu-id="99068-125">Messages reported by users</span></span><br><span data-ttu-id="99068-126">Nolldagars skadlig programvara blockerad</span><span class="sxs-lookup"><span data-stu-id="99068-126">Zero-day malware blocked</span></span><br><span data-ttu-id="99068-127">Avancerade nätfiskemeddelanden har upptäckts</span><span class="sxs-lookup"><span data-stu-id="99068-127">Advanced phishing messages detected</span></span><br><span data-ttu-id="99068-128">Skadliga URL:er blockeras</span><span class="sxs-lookup"><span data-stu-id="99068-128">Malicious URLs blocked</span></span>|

<span data-ttu-id="99068-129">Om du vill visa eller komma åt widgeten Sammanfattning av hothantering måste du ha behörighet att visa Defender Office 365.</span><span class="sxs-lookup"><span data-stu-id="99068-129">To view or access the Threat Management Summary widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="99068-130">Mer information finns i [Vilka behörigheter krävs för att visa Defender för Office 365 rapporter?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).</span><span class="sxs-lookup"><span data-stu-id="99068-130">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).</span></span>

## <a name="threat-protection-status"></a><span data-ttu-id="99068-131">Status för skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="99068-131">Threat Protection Status</span></span>

<span data-ttu-id="99068-132">Widgeten Hotskyddsstatus visar hur effektivt skyddet för hot är med en trendande och detaljerad vy över nätt och skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="99068-132">The Threat Protection Status widget shows threat protection effectiveness with a trending and detailed view of phish and malware.</span></span>

![Widget för hotskyddsstatus](../../media/tpswidget.png)

<span data-ttu-id="99068-134">Informationen beror på om EOP (Microsoft 365 Subscription includes [Exchange Online Protection)](exchange-online-protection-overview.md) med eller utan [Microsoft Defender för Office 365.](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="99068-134">The details depend on whether your Microsoft 365 subscription includes [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) with or without [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span>

|<span data-ttu-id="99068-135">Om din prenumeration inkluderar...</span><span class="sxs-lookup"><span data-stu-id="99068-135">If your subscription includes...</span></span>|<span data-ttu-id="99068-136">Den här informationen visas</span><span class="sxs-lookup"><span data-stu-id="99068-136">You'll see these details</span></span>|
|---|---|
|<span data-ttu-id="99068-137">EOP men inte Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="99068-137">EOP but not Microsoft Defender for Office 365</span></span>|<span data-ttu-id="99068-138">Skadlig e-post som har upptäckts och blockerats av EOP.</span><span class="sxs-lookup"><span data-stu-id="99068-138">Malicious email that was detected and blocked by EOP.</span></span><p> <span data-ttu-id="99068-139">Se [Statusrapport för skydd mot hot (EOP).](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="99068-139">See [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="99068-140">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="99068-140">Microsoft Defender for Office 365</span></span>|<span data-ttu-id="99068-141">Skadligt innehåll och skadlig e-post som identifieras och blockeras av EOP och Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="99068-141">Malicious content and malicious email detected and blocked by EOP and Defender for Office 365</span></span> <p> <span data-ttu-id="99068-142">Aggregerat antal unika e-postmeddelanden med skadligt innehåll som [](zero-hour-auto-purge.md)blockerats av antivirusmotorn, automatisk rensning utan timme och Defender för Office 365-funktioner (inklusive [Valv-länkar,](safe-links.md) [Valv-bilagor](safe-attachments.md)och skydd mot nätfiske i Defender för [Office 365).](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="99068-142">Aggregated count of unique email messages with malicious content blocked by the anti-malware engine, [zero-hour auto purge](zero-hour-auto-purge.md), and Defender for Office 365 features (including [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing in Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span> <p> <span data-ttu-id="99068-143">Se [statusrapport om skydd mot hot.](view-reports-for-mdo.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="99068-143">See [Threat protection status report](view-reports-for-mdo.md#threat-protection-status-report).</span></span>|

<span data-ttu-id="99068-144">Om du vill visa eller komma åt widgeten Hotskyddsstatus måste du ha behörighet att visa Defender Office 365 rapporter.</span><span class="sxs-lookup"><span data-stu-id="99068-144">To view or access the Threat Protection Status widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="99068-145">Mer information finns i [Vilka behörigheter krävs för att visa Defender för Office 365 rapporter?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)</span><span class="sxs-lookup"><span data-stu-id="99068-145">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)</span></span>

## <a name="global-weekly-threat-detections"></a><span data-ttu-id="99068-146">Global veckovis identifiering av hot</span><span class="sxs-lookup"><span data-stu-id="99068-146">Global Weekly Threat Detections</span></span>

<span data-ttu-id="99068-147">Widgeten Global Weekly Threat Detections visar hur många hot som har upptäckts i e-postmeddelanden under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="99068-147">The Global Weekly Threat Detections widget shows how many threats were detected in email messages over the past seven (7) days.</span></span>

![Widget för global veckovis identifiering av hot](../../media/globalweeklythreatdetections.png)

<span data-ttu-id="99068-149">Måtten beräknas enligt beskrivningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="99068-149">The metrics are calculated as described in the following table:</span></span>

|<span data-ttu-id="99068-150">Metrisk</span><span class="sxs-lookup"><span data-stu-id="99068-150">Metric</span></span>|<span data-ttu-id="99068-151">Så här beräknas det</span><span class="sxs-lookup"><span data-stu-id="99068-151">How it's calculated</span></span>|
|---|---|
|<span data-ttu-id="99068-152">Meddelanden skannade</span><span class="sxs-lookup"><span data-stu-id="99068-152">Messages scanned</span></span>|<span data-ttu-id="99068-153">Antalet e-postmeddelanden som genomsöks multiplicerat med antalet mottagare</span><span class="sxs-lookup"><span data-stu-id="99068-153">Number of email messages scanned multiplied by the number of recipients</span></span>|
|<span data-ttu-id="99068-154">Hot har stoppats</span><span class="sxs-lookup"><span data-stu-id="99068-154">Threats stopped</span></span>|<span data-ttu-id="99068-155">Antalet e-postmeddelanden som identifierats som innehåller skadlig programvara multiplicerat med antalet mottagare</span><span class="sxs-lookup"><span data-stu-id="99068-155">Number of email messages identified as containing malware multiplied by the number of recipients</span></span>|
|<span data-ttu-id="99068-156">Blockeras av [Defender för Office 365](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="99068-156">Blocked by [Defender for Office 365](defender-for-office-365.md)</span></span>|<span data-ttu-id="99068-157">Antalet e-postmeddelanden som blockeras av Defender för Office 365 multiplicerat med antalet mottagare</span><span class="sxs-lookup"><span data-stu-id="99068-157">Number of email messages blocked by Defender for Office 365 multiplied by the number of recipients</span></span>|
|<span data-ttu-id="99068-158">Tas bort efter leverans</span><span class="sxs-lookup"><span data-stu-id="99068-158">Removed after delivery</span></span>|<span data-ttu-id="99068-159">Antalet meddelanden som tagits [bort med en automatisk rensning på nolltimmar](zero-hour-auto-purge.md) multiplicerat med antalet mottagare</span><span class="sxs-lookup"><span data-stu-id="99068-159">Number of messages removed by [zero-hour auto purge](zero-hour-auto-purge.md) multiplied by the number of recipients</span></span>|

## <a name="malware"></a><span data-ttu-id="99068-160">Skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="99068-160">Malware</span></span>

<span data-ttu-id="99068-161">Widgetar för skadlig programvara visar information om trender och familjetyper för skadlig programvara under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="99068-161">Malware widgets show details about malware trends and malware family types over the past seven (7) days.</span></span>

![Trender och familjetyper för skadlig programvara](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a><span data-ttu-id="99068-163">Insikter</span><span class="sxs-lookup"><span data-stu-id="99068-163">Insights</span></span>

<span data-ttu-id="99068-164">Insikter tar inte bara upp viktiga problem som du bör granska, de innehåller även rekommendationer och åtgärder att överväga.</span><span class="sxs-lookup"><span data-stu-id="99068-164">Insights not only surface key issues you should review, they also include recommendations and actions to consider.</span></span>

![Smarta insikter](../../media/smartinsights.png)

<span data-ttu-id="99068-166">Du kan till exempel se att nätfiskemeddelanden levereras eftersom vissa användare har inaktiverat sina skräppostalternativ.</span><span class="sxs-lookup"><span data-stu-id="99068-166">For example, you might see that phishing email messages are being delivered because some users have disabled their junk mail options.</span></span> <span data-ttu-id="99068-167">Mer information om hur insikter fungerar finns i Rapporter och insikter i Säkerhets- & [Efterlevnadscenter.](reports-and-insights-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="99068-167">To learn more about how insights work, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

## <a name="threat-investigation-and-response"></a><span data-ttu-id="99068-168">Undersökning och svar på hot</span><span class="sxs-lookup"><span data-stu-id="99068-168">Threat investigation and response</span></span>

<span data-ttu-id="99068-169">Om din organisations prenumeration omfattar Microsoft Defender för [Office 365 abonnemang 2](office-365-ti.md)har din säkerhetsinstrumentpanel ett avsnitt som innehåller avancerade undersöknings- och svarsverktyg för hot.</span><span class="sxs-lookup"><span data-stu-id="99068-169">If your organization's subscription includes  [Microsoft Defender for Office 365 Plan 2](office-365-ti.md), your Security Dashboard has a section that includes advanced threat investigation and response tools.</span></span> <span data-ttu-id="99068-170">Dessa verktyg innehåller [automatiserad undersökning och svarsfunktioner.](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="99068-170">These tools include [automated investigation and response capabilities](automated-investigation-response-office.md).</span></span> <span data-ttu-id="99068-171">Automatisk undersökning och svar kan vara användbart i scenarier som att [hantera komprometterade användarkonton snabbt.](address-compromised-users-quickly.md)</span><span class="sxs-lookup"><span data-stu-id="99068-171">Automated investigation and response can be helpful in scenarios such as [addressing compromised user accounts quickly](address-compromised-users-quickly.md).</span></span>

<span data-ttu-id="99068-172">Mer information finns i [Komma igång med automatiserad undersökning och svar (AIR) i Office 365.](office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="99068-172">To learn more, see [Get started using Automated investigation and response (AIR) in Office 365](office-365-air.md).</span></span>

## <a name="trends"></a><span data-ttu-id="99068-173">Trender</span><span class="sxs-lookup"><span data-stu-id="99068-173">Trends</span></span>

<span data-ttu-id="99068-174">Längst ned på instrumentpanelen för säkerhet finns avsnittet **Trender,** som sammanfattar e-postflödestrender för din organisation.</span><span class="sxs-lookup"><span data-stu-id="99068-174">Near the bottom of the Security Dashboard is a **Trends** section, which summarizes email flow trends for your organization.</span></span> <span data-ttu-id="99068-175">Med rapporter får du information om e-post som kategoriserats som skräppost, skadlig kod, försök till nätfiske och bra e-post.</span><span class="sxs-lookup"><span data-stu-id="99068-175">Reports provide information about email categorized as spam, malware, phishing attempts, and good email.</span></span> <span data-ttu-id="99068-176">Klicka på en panel om du vill visa mer detaljerad information i rapporten.</span><span class="sxs-lookup"><span data-stu-id="99068-176">Click a tile to view more detailed information in the report.</span></span>

![I avsnittet Trender sammanfattas e-postflödestrender för organisationen](../../media/trends.png)

<span data-ttu-id="99068-178">Om din organisations prenumeration omfattar Defender för [Office 365 abonnemang 2](office-365-ti.md)har du  även en rapport om händelser för hantering av hot i det här avsnittet som gör att säkerhetsteamet kan se och vidta åtgärder för högprioriterade säkerhetsvarningar.</span><span class="sxs-lookup"><span data-stu-id="99068-178">And, if your organization's subscription includes [Defender for Office 365 Plan 2](office-365-ti.md), you will also have a **Recent threat management alerts** report in this section that enables your security team to view and take action on high-priority security alerts.</span></span>

<span data-ttu-id="99068-179">Om du vill visa eller komma åt widgeten Skickad och mottagen e-post måste du ha behörighet att visa Defender Office 365 rapporter.</span><span class="sxs-lookup"><span data-stu-id="99068-179">To view or access the Sent and Received Email widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="99068-180">Mer information finns i [Vilka behörigheter krävs för att visa Defender för Office 365 rapporter?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).</span><span class="sxs-lookup"><span data-stu-id="99068-180">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).</span></span>

<span data-ttu-id="99068-181">Om du vill visa eller komma åt widgeten Senaste hothanteringsvarningar måste du ha behörighet att visa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="99068-181">To view or access the Recent Threat Management Alerts widget, you must have permissions to view alerts.</span></span> <span data-ttu-id="99068-182">Mer information finns i [RBAC-behörigheter som krävs för att visa aviseringar.](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)</span><span class="sxs-lookup"><span data-stu-id="99068-182">To learn more, see [RBAC permissions required to view alerts](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).</span></span>

## <a name="related-topics"></a><span data-ttu-id="99068-183">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="99068-183">Related topics</span></span>

[<span data-ttu-id="99068-184">Visa e-postsäkerhetsrapporter i Säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="99068-184">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="99068-185">Visa rapporter för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="99068-185">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)

[<span data-ttu-id="99068-186">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="99068-186">Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="99068-187">Office 365 Undersökning och svar på hot</span><span class="sxs-lookup"><span data-stu-id="99068-187">Office 365 Threat investigation and response</span></span>](office-365-ti.md)