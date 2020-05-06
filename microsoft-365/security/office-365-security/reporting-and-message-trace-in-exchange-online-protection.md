---
title: Rapportering och meddelandespårning i Exchange Online Protection
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
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om rapporter och felsökningsverktyg som är tillgängliga för Microsoft Exchange Online Protection -administratörer (EOP).
ms.openlocfilehash: 44b4223b4310a2de1d90f99f8a7af23cc6054f94
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034386"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="851f8-103">Rapportering och meddelandespårning i Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="851f8-103">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="851f8-104">Microsoft Exchange Online Protection (EOP) innehåller många olika rapporter som kan hjälpa dig att fastställa organisationens övergripande status och hälsa.</span><span class="sxs-lookup"><span data-stu-id="851f8-104">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="851f8-105">Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till de avsedda mottagarna) och granskningsrapporter som hjälper dig att uppfylla efterlevnadskraven.</span><span class="sxs-lookup"><span data-stu-id="851f8-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="851f8-106">Användningsrapporter</span><span class="sxs-lookup"><span data-stu-id="851f8-106">Usage reports</span></span>

<span data-ttu-id="851f8-107">**Aktivitet för Microsoft 365 grupper:** Visa information om antalet Microsoft 365-grupper som skapas och används.</span><span class="sxs-lookup"><span data-stu-id="851f8-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="851f8-108">**E-postaktivitet**: Visa information om antalet meddelanden som skickas, tas emot och läss i hela organisationen och av specifika användare.</span><span class="sxs-lookup"><span data-stu-id="851f8-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="851f8-109">**Användning av e-postappar**: Visa information om de e-postappar som används.</span><span class="sxs-lookup"><span data-stu-id="851f8-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="851f8-110">Detta inkluderar det totala antalet anslutningar för varje app och de versioner av Outlook som ansluter.</span><span class="sxs-lookup"><span data-stu-id="851f8-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="851f8-111">**Postlådeanvändning**: Visa information om lagring som används, kvotförbrukning, artikelantal och senaste aktivitet (skicka eller läsa aktivitet) för postlådor.</span><span class="sxs-lookup"><span data-stu-id="851f8-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="851f8-112">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="851f8-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="851f8-113">Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="851f8-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="851f8-114">Microsoft 365-rapporter i administrationscentret – e-postaktivitet</span><span class="sxs-lookup"><span data-stu-id="851f8-114">Microsoft 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="851f8-115">Microsoft 365-rapporter i administrationscentret – användning av e-postappar</span><span class="sxs-lookup"><span data-stu-id="851f8-115">Microsoft 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="851f8-116">Microsoft 365-rapporter i administrationscentret – användning av postlåda</span><span class="sxs-lookup"><span data-stu-id="851f8-116">Microsoft 365 Reports in the Admin Center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="851f8-117">Säkerhetsrapporter & efterlevnad i microsoft 365-administrationscentret</span><span class="sxs-lookup"><span data-stu-id="851f8-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="851f8-118">Dessa förbättrade rapporter ger en interaktiv rapporteringsupplevelse för EOP-administratörer, som innehåller sammanfattande information och möjligheten att öka detaljnivån för mer information.</span><span class="sxs-lookup"><span data-stu-id="851f8-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="851f8-119">**Advanced Threat Protection (ATP):** Visa information om säkra länkar och säkra bilagor som ingår i ATP.</span><span class="sxs-lookup"><span data-stu-id="851f8-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="851f8-120">**EOP**: Visa information om identifiering av skadlig programvara, förfalskad e-post, skräppostidentifieringar och e-postflöde till och från din organisation.</span><span class="sxs-lookup"><span data-stu-id="851f8-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="851f8-121">Visa rapporter för avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="851f8-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="851f8-122">Anpassade rapporter med Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="851f8-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="851f8-123">Skapa programmatiskt rapporter som är tillgängliga i Microsoft 365-administrationscentret med hjälp av Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="851f8-123">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="851f8-124">Se undertopikerna för [användningsrapporter för Arbeta med Office 365 i Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="851f8-124">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="851f8-125">Anpassade rapporter med Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="851f8-125">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="851f8-126">Skapa programmatiskt rapporter.</span><span class="sxs-lookup"><span data-stu-id="851f8-126">Programmatically create reports.</span></span> <span data-ttu-id="851f8-127">Se [Översikt över Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="851f8-127">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="851f8-128">Meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="851f8-128">Message trace</span></span>

<span data-ttu-id="851f8-129">Följer e-postmeddelanden när de färdas via EOP.</span><span class="sxs-lookup"><span data-stu-id="851f8-129">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="851f8-130">Du kan avgöra om ett e-postmeddelande togs emot, avvisades, sköts upp eller levererades av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="851f8-130">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="851f8-131">Den visar också vilka åtgärder som vidtogs på meddelandet innan det nådde sin slutliga status.</span><span class="sxs-lookup"><span data-stu-id="851f8-131">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="851f8-132">Du kan använda den här informationen för att effektivt svara på användarens frågor, felsöka problem med e-postflödet, validera principändringar och minska behovet av att kontakta teknisk support för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="851f8-132">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="851f8-133">Se [Spåra ett e-postmeddelande](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="851f8-133">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="851f8-134">Granskningsloggning</span><span class="sxs-lookup"><span data-stu-id="851f8-134">Audit logging</span></span>

<span data-ttu-id="851f8-135">Spårar specifika ändringar som gjorts av administratörer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="851f8-135">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="851f8-136">Dessa rapporter kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem.</span><span class="sxs-lookup"><span data-stu-id="851f8-136">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="851f8-137">Se [Granskningsrapporter i EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="851f8-137">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="851f8-138">Rapportering och meddelandespårning datatillgänglighet och svarstid</span><span class="sxs-lookup"><span data-stu-id="851f8-138">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="851f8-139">I följande tabell beskrivs när EOP-rapportering och meddelandespårningsdata är tillgängliga och hur länge.</span><span class="sxs-lookup"><span data-stu-id="851f8-139">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="851f8-140">**Rapporttyp**</span><span class="sxs-lookup"><span data-stu-id="851f8-140">**Report type**</span></span>|<span data-ttu-id="851f8-141">**Tillgängliga data för (tillbakablicksperiod)**</span><span class="sxs-lookup"><span data-stu-id="851f8-141">**Data available for (look back period)**</span></span>|<span data-ttu-id="851f8-142">**Latens**</span><span class="sxs-lookup"><span data-stu-id="851f8-142">**Latency**</span></span>|
|<span data-ttu-id="851f8-143">Sammanfattningsrapporter för e-postskydd</span><span class="sxs-lookup"><span data-stu-id="851f8-143">Mail protection summary reports</span></span>|<span data-ttu-id="851f8-144">90 dagar</span><span class="sxs-lookup"><span data-stu-id="851f8-144">90 days</span></span>|<span data-ttu-id="851f8-145">Aggregering av meddelandedata är mestadels klar inom 24-48 timmar.</span><span class="sxs-lookup"><span data-stu-id="851f8-145">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="851f8-146">Vissa mindre inkrementella aggregerade ändringar kan förekomma i upp till 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="851f8-146">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="851f8-147">Informationsrapporter för e-postskydd</span><span class="sxs-lookup"><span data-stu-id="851f8-147">Mail protection detail reports</span></span>|<span data-ttu-id="851f8-148">90 dagar</span><span class="sxs-lookup"><span data-stu-id="851f8-148">90 days</span></span>|<span data-ttu-id="851f8-149">För detaljdata som är mindre än 7 dagar gamla ska data visas inom 24 timmar men kanske inte vara klara förrän 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="851f8-149">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="851f8-150">Vissa mindre inkrementella ändringar kan förekomma i upp till 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="851f8-150">Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="851f8-151">Om du vill visa detaljerade rapporter för meddelanden som är större än 7 dagar gamla kan resultatet ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="851f8-151">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="851f8-152">Data för meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="851f8-152">Message trace data</span></span>|<span data-ttu-id="851f8-153">90 dagar</span><span class="sxs-lookup"><span data-stu-id="851f8-153">90 days</span></span>|<span data-ttu-id="851f8-154">När du kör en meddelandespårning för meddelanden som är mindre än 7 dagar gamla ska meddelandena visas inom 5-30 minuter.</span><span class="sxs-lookup"><span data-stu-id="851f8-154">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="851f8-155">När du kör en meddelandespårning för meddelanden som är längre än 7 dagar gamla kan resultatet ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="851f8-155">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="851f8-156">Datatillgänglighet och svarstid är desamma oavsett om de begärs via Microsoft 365 admin center eller fjärr PowerShell.</span><span class="sxs-lookup"><span data-stu-id="851f8-156">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
