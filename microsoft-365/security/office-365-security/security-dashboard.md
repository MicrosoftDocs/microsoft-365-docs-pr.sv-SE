---
title: Översikt över instrumentpanelen för säkerhet
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: Använd den nya säkerhetsinstrumentpanelen för att granska Status för skydd mot hotskydd i Office 365 och visa och agera på säkerhetsaviseringar.
ms.openlocfilehash: 1ef61f2a5e59db5c45a37bd9f8995b8c70675f30
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032846"
---
# <a name="security-dashboard"></a><span data-ttu-id="616ef-103">Instrumentpanel för säkerhet</span><span class="sxs-lookup"><span data-stu-id="616ef-103">Security Dashboard</span></span>

## <a name="overview"></a><span data-ttu-id="616ef-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="616ef-104">Overview</span></span>

<span data-ttu-id="616ef-105">[Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) gör det möjligt för din organisation att hantera dataskydd och efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="616ef-105">The [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) enables your organization to manage data protection and compliance.</span></span> <span data-ttu-id="616ef-106">Förutsatt att du har de behörigheter som krävs kan du med säkerhetsinstrumentpanelen granska din hotskyddsstatus samt visa och agera på säkerhetsaviseringar.</span><span class="sxs-lookup"><span data-stu-id="616ef-106">Assuming you have the necessary permissions, the Security Dashboard enables you to review your Threat Protection Status, as well as view and act on security alerts.</span></span>

<span data-ttu-id="616ef-107">Titta på videon för att få en översikt och läs sedan den här artikeln om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="616ef-107">Watch the video to get an overview, and then read this article to learn more.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

<span data-ttu-id="616ef-108">Beroende på vad organisationens Office 365-prenumeration innehåller innehåller säkerhetsinstrumentpanelen flera widgetar, till exempel Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware med mera, enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="616ef-108">Depending on what your organization's Office 365 subscription includes, the Security Dashboard includes several widgets, such as Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware, and more, as described in the following sections.</span></span>

<span data-ttu-id="616ef-109">Om du vill visa säkerhetsinstrumentpanelen går du till **instrumentpanelen** **för hothantering** \> i [Office 365 Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="616ef-109">To view the Security Dashboard, in the [Office 365 Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md), go to **Threat management** \> **Dashboard**.</span></span>

> [!NOTE]
> <span data-ttu-id="616ef-110">Du måste vara en global Office 365-administratör, en säkerhetsadministratör eller en säkerhetsläsare för att kunna visa säkerhetsinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="616ef-110">You must be an Office 365 global administrator, a security administrator, or a security reader to view the Security Dashboard.</span></span> <span data-ttu-id="616ef-111">Vissa widgetar kräver ytterligare behörigheter för att kunna visa.</span><span class="sxs-lookup"><span data-stu-id="616ef-111">Some widgets require additional permissions to view.</span></span> <span data-ttu-id="616ef-112">Mer information finns [i Behörigheter i Säkerhetsorganisationscenter för Office 365 &](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="616ef-112">To learn more, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="threat-management-summary"></a><span data-ttu-id="616ef-113">Sammanfattning av hothantering</span><span class="sxs-lookup"><span data-stu-id="616ef-113">Threat Management Summary</span></span>

<span data-ttu-id="616ef-114">Widgeten Sammanfattning av hot ger dig en överblick över hur din organisation har skyddats från hot under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="616ef-114">The Threat Management Summary widget tells you at a glance how your organization was protected from threats over the past seven (7) days.</span></span>

![Säkerhetsinstrumentpanel – sammanfattningswidget för hothantering](../../media/SecDash-ThreatMgmtSummary.png)

<span data-ttu-id="616ef-116">Vilken information du ser i sammanfattningen av hothantering beror på vad du prenumererar på.</span><span class="sxs-lookup"><span data-stu-id="616ef-116">The information you'll see in the Threat Management Summary depends on what you subscription includes.</span></span> <span data-ttu-id="616ef-117">I följande tabell beskrivs vilken information som ingår för Office 365 E3 och Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="616ef-117">The following table describes what information is included for Office 365 E3 and Office 365 E5.</span></span>
|||
|---|---|
|<span data-ttu-id="616ef-118">**Office 365 E3**</span><span class="sxs-lookup"><span data-stu-id="616ef-118">**Office 365 E3**</span></span>|<span data-ttu-id="616ef-119">**Office 365 E5**</span><span class="sxs-lookup"><span data-stu-id="616ef-119">**Office 365 E5**</span></span>|
|<span data-ttu-id="616ef-120">Blockerade meddelanden om skadlig kod</span><span class="sxs-lookup"><span data-stu-id="616ef-120">Malware messages blocked</span></span><br/><span data-ttu-id="616ef-121">Nätfiskemeddelanden blockerade</span><span class="sxs-lookup"><span data-stu-id="616ef-121">Phishing messages blocked</span></span><br><span data-ttu-id="616ef-122">Meddelanden som rapporterats av användare</span><span class="sxs-lookup"><span data-stu-id="616ef-122">Messages reported by users</span></span><br><br><br><br>|<span data-ttu-id="616ef-123">Blockerade meddelanden om skadlig kod</span><span class="sxs-lookup"><span data-stu-id="616ef-123">Malware messages blocked</span></span><br><span data-ttu-id="616ef-124">Nätfiskemeddelanden blockerade</span><span class="sxs-lookup"><span data-stu-id="616ef-124">Phishing messages blocked</span></span><br><span data-ttu-id="616ef-125">Meddelanden som rapporterats av användare</span><span class="sxs-lookup"><span data-stu-id="616ef-125">Messages reported by users</span></span><br><span data-ttu-id="616ef-126">Zero-day malware blockerad</span><span class="sxs-lookup"><span data-stu-id="616ef-126">Zero-day malware blocked</span></span><br><span data-ttu-id="616ef-127">Avancerade nätfiskemeddelanden har upptäckts</span><span class="sxs-lookup"><span data-stu-id="616ef-127">Advanced phishing messages detected</span></span><br><span data-ttu-id="616ef-128">Blockerade skadliga webbadresser</span><span class="sxs-lookup"><span data-stu-id="616ef-128">Malicious URLs blocked</span></span>|
|

<span data-ttu-id="616ef-129">Om du vill visa eller komma åt widgeten Sammanfattning av hothantering måste du ha behörighet för att kunna visa rapporter om avancerat skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="616ef-129">To view or access the Threat Management Summary widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="616ef-130">Mer information finns i [Vilka behörigheter som behövs för att visa ATP-rapporterna?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span><span class="sxs-lookup"><span data-stu-id="616ef-130">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span></span>

## <a name="threat-protection-status"></a><span data-ttu-id="616ef-131">Status för skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="616ef-131">Threat Protection Status</span></span>

<span data-ttu-id="616ef-132">Widgeten Hot Protection Status visar hotskyddseffektivitet med en trendig och detaljerad vy över phish och skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="616ef-132">The Threat Protection Status widget shows threat protection effectiveness with a trending and detailed view of phish and malware.</span></span>

![Widget för status för hotskydd](../../media/tpswidget.png)

<span data-ttu-id="616ef-134">Informationen beror på om din Office 365-prenumeration innehåller [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) med eller utan Office [365 Advanced Threat Protection](office-365-atp.md) (ATP).</span><span class="sxs-lookup"><span data-stu-id="616ef-134">The details depend on whether your Office 365 subscription includes [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) with or without [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).</span></span>

|||
|---|---|
|<span data-ttu-id="616ef-135">**Om din prenumeration innehåller...**</span><span class="sxs-lookup"><span data-stu-id="616ef-135">**If your subscription includes...**</span></span>|<span data-ttu-id="616ef-136">**Du ser dessa detaljer**</span><span class="sxs-lookup"><span data-stu-id="616ef-136">**You'll see these details**</span></span>|
|<span data-ttu-id="616ef-137">EOP men inte Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="616ef-137">EOP but not Office 365 ATP</span></span>|<span data-ttu-id="616ef-138">Skadlig e-post som upptäcktes och blockerades av EOP.</span><span class="sxs-lookup"><span data-stu-id="616ef-138">Malicious email that was detected and blocked by EOP.</span></span><br><br> <span data-ttu-id="616ef-139">Se [rapporten Status för hotskydd (EOP).](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="616ef-139">See [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="616ef-140">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="616ef-140">Office 365 ATP</span></span>|<span data-ttu-id="616ef-141">Skadligt innehåll och skadlig e-post som upptäckts och blockerats av EOP och Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="616ef-141">Malicious content and malicious email detected and blocked by EOP and Office 365 ATP</span></span><br><br><span data-ttu-id="616ef-142">Aggregerat antal unika e-postmeddelanden med skadligt innehåll som blockerats av anti-malware-motorn, [nolltimmars automatisk rensning](zero-hour-auto-purge.md)och ATP-funktioner (inklusive [säkra länkar,](atp-safe-links.md) [säkra bilagor](atp-safe-attachments.md)och [ATP-anti-phishing).](atp-anti-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="616ef-142">Aggregated count of unique email messages with malicious content blocked by the anti-malware engine, [zero-hour auto purge](zero-hour-auto-purge.md), and ATP features (including [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](atp-anti-phishing.md)).</span></span><br><br><span data-ttu-id="616ef-143">Se [rapporten Status för hotskydd (ATP).](view-reports-for-atp.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="616ef-143">See [Threat Protection Status report (ATP)](view-reports-for-atp.md#threat-protection-status-report).</span></span>|
|

<span data-ttu-id="616ef-144">Om du vill visa eller komma åt widgeten Status för hotskydd måste du ha behörighet att visa rapporter om avancerat skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="616ef-144">To view or access the Threat Protection Status widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="616ef-145">Mer information finns i [Vilka behörigheter som behövs för att visa ATP-rapporterna?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span><span class="sxs-lookup"><span data-stu-id="616ef-145">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span></span>

## <a name="global-weekly-threat-detections"></a><span data-ttu-id="616ef-146">Globala hotidentifieringar varje vecka</span><span class="sxs-lookup"><span data-stu-id="616ef-146">Global Weekly Threat Detections</span></span>

<span data-ttu-id="616ef-147">Widgeten Global Weekly Threat Detections visar hur många hot som upptäckts i e-postmeddelanden under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="616ef-147">The Global Weekly Threat Detections widget shows how many threats were detected in email messages over the past seven (7) days.</span></span>

![Widgeten Globala veckovisa hotidentifieringar](../../media/globalweeklythreatdetections.png)

<span data-ttu-id="616ef-149">Måtten beräknas enligt beskrivningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="616ef-149">The metrics are calculated as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="616ef-150">**Metriska**</span><span class="sxs-lookup"><span data-stu-id="616ef-150">**Metric**</span></span>|<span data-ttu-id="616ef-151">**Hur det beräknas**</span><span class="sxs-lookup"><span data-stu-id="616ef-151">**How it's calculated**</span></span>|
|<span data-ttu-id="616ef-152">Skannade meddelanden</span><span class="sxs-lookup"><span data-stu-id="616ef-152">Messages scanned</span></span>|<span data-ttu-id="616ef-153">Antal skannade e-postmeddelanden multiplicerat med antalet mottagare</span><span class="sxs-lookup"><span data-stu-id="616ef-153">Number of email messages scanned multiplied by the number of recipients</span></span>|
|<span data-ttu-id="616ef-154">Hot stoppas</span><span class="sxs-lookup"><span data-stu-id="616ef-154">Threats stopped</span></span>|<span data-ttu-id="616ef-155">Antal e-postmeddelanden som identifierats som innehållande skadlig kod multiplicerat med antalet mottagare</span><span class="sxs-lookup"><span data-stu-id="616ef-155">Number of email messages identified as containing malware multiplied by the number of recipients</span></span>|
|<span data-ttu-id="616ef-156">Blockerad av [ATP](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="616ef-156">Blocked by [ATP](office-365-atp.md)</span></span>|<span data-ttu-id="616ef-157">Antal e-postmeddelanden som blockerats av ATP multiplicerat med antalet mottagare</span><span class="sxs-lookup"><span data-stu-id="616ef-157">Number of email messages blocked by ATP multiplied by the number of recipients</span></span>|
|<span data-ttu-id="616ef-158">Tas bort efter leverans</span><span class="sxs-lookup"><span data-stu-id="616ef-158">Removed after delivery</span></span>|<span data-ttu-id="616ef-159">Antal meddelanden som tagits bort med [automatisk rensning](zero-hour-auto-purge.md) noll timmar multiplicerat med antalet mottagare</span><span class="sxs-lookup"><span data-stu-id="616ef-159">Number of messages removed by [zero-hour auto purge](zero-hour-auto-purge.md) multiplied by the number of recipients</span></span>|
|

## <a name="malware"></a><span data-ttu-id="616ef-160">Malware</span><span class="sxs-lookup"><span data-stu-id="616ef-160">Malware</span></span>

<span data-ttu-id="616ef-161">Malware widgets visar information om malware trender och malware familjetyper under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="616ef-161">Malware widgets show details about malware trends and malware family types over the past seven (7) days.</span></span>

![Malware trender och familjetyper](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a><span data-ttu-id="616ef-163">Insikter</span><span class="sxs-lookup"><span data-stu-id="616ef-163">Insights</span></span>

<span data-ttu-id="616ef-164">Insikter inte bara yta viktiga frågor som du bör granska, de innehåller också rekommendationer och åtgärder att överväga.</span><span class="sxs-lookup"><span data-stu-id="616ef-164">Insights not only surface key issues you should review, they also include recommendations and actions to consider.</span></span>

![Smarta insikter](../../media/smartinsights.png)

<span data-ttu-id="616ef-166">Du kan till exempel se att nätfiskemeddelanden levereras eftersom vissa användare har inaktiverat sina skräppostalternativ.</span><span class="sxs-lookup"><span data-stu-id="616ef-166">For example, you might see that phishing email messages are being delivered because some users have disabled their junk mail options.</span></span> <span data-ttu-id="616ef-167">Mer information om hur insikter fungerar finns [i Rapporter och insikter i Office 365 Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="616ef-167">To learn more about how insights work, see [Reports and insights in the Office 365 Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

## <a name="threat-investigation-and-response"></a><span data-ttu-id="616ef-168">Hotutredning och hothantering</span><span class="sxs-lookup"><span data-stu-id="616ef-168">Threat investigation and response</span></span>

<span data-ttu-id="616ef-169">Om organisationens prenumeration innehåller [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)har säkerhetsinstrumentpanelen ett avsnitt som innehåller avancerade verktyg för utredning och svar av hot.</span><span class="sxs-lookup"><span data-stu-id="616ef-169">If your organization's subscription includes  [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), your Security Dashboard has a section that includes advanced threat investigation and response tools.</span></span> <span data-ttu-id="616ef-170">Organisationens säkerhetsteam kan använda informationen i det här avsnittet för att förstå nya kampanjer, undersöka hot och hantera incidenter.</span><span class="sxs-lookup"><span data-stu-id="616ef-170">Your organization's security team can use the information in this section to understand emerging campaigns, investigate threats and manage incidents.</span></span>

![Hotinformation hjälper dig att förstå attacker riktade mot din organisation](../../media/threatintelwidget.png)

## <a name="trends"></a><span data-ttu-id="616ef-172">Trender</span><span class="sxs-lookup"><span data-stu-id="616ef-172">Trends</span></span>

<span data-ttu-id="616ef-173">Längst ned på säkerhetsinstrumentpanelen finns ett **avsnittet Trender** som sammanfattar trender för e-postflödet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="616ef-173">Near the bottom of the Security Dashboard is a **Trends** section, which summarizes email flow trends for your organization.</span></span> <span data-ttu-id="616ef-174">Rapporter innehåller information om e-post som kategoriseras som skräppost, skadlig kod, nätfiskeförsök och bra e-post.</span><span class="sxs-lookup"><span data-stu-id="616ef-174">Reports provide information about email categorized as spam, malware, phishing attempts, and good email.</span></span> <span data-ttu-id="616ef-175">Klicka på en panel om du vill visa mer detaljerad information i rapporten.</span><span class="sxs-lookup"><span data-stu-id="616ef-175">Click a tile to view more detailed information in the report.</span></span>

![Avsnittet Trender sammanfattar trender för e-postflödet för organisationen](../../media/trends.png)

<span data-ttu-id="616ef-177">Och om organisationens Office 365-prenumeration innehåller [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)har du också en rapport om aviseringar om **hothantering nyligen** i det här avsnittet som gör det möjligt för säkerhetsteamet att visa och vidta åtgärder för säkerhetsaviseringar med hög prioritet.</span><span class="sxs-lookup"><span data-stu-id="616ef-177">And, if your organization's Office 365 subscription includes [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), you will also have a **Recent threat management alerts** report in this section that enables your security team to view and take action on high-priority security alerts.</span></span>

<span data-ttu-id="616ef-178">Om du vill visa eller komma åt widgeten Skickat och mottaget e-post måste du ha behörighet för att kunna visa rapporter om avancerat skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="616ef-178">To view or access the Sent and Received Email widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="616ef-179">Mer information finns i [Vilka behörigheter som behövs för att visa ATP-rapporterna?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span><span class="sxs-lookup"><span data-stu-id="616ef-179">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span></span>

<span data-ttu-id="616ef-180">Om du vill visa eller komma åt widgeten Senaste hothanteringsaviseringar måste du ha behörighet att visa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="616ef-180">To view or access the Recent Threat Management Alerts widget, you must have permissions to view alerts.</span></span> <span data-ttu-id="616ef-181">Mer information finns i [RBAC-behörigheter som krävs för att visa aviseringar](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).</span><span class="sxs-lookup"><span data-stu-id="616ef-181">To learn more, see [RBAC permissions required to view alerts](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).</span></span>

## <a name="related-topics"></a><span data-ttu-id="616ef-182">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="616ef-182">Related topics</span></span>

[<span data-ttu-id="616ef-183">Visa säkerhetsrapporter för e-post i Säkerhets- & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="616ef-183">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="616ef-184">Visa rapporter för avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="616ef-184">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="616ef-185">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="616ef-185">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="616ef-186">Office 365 Hotutredning och hothantering</span><span class="sxs-lookup"><span data-stu-id="616ef-186">Office 365 Threat investigation and response</span></span>](office-365-ti.md)
