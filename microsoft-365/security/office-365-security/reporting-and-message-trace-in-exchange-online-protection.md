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
description: Microsoft Exchange Online Protection (EOP) innehåller många olika rapporter som kan hjälpa dig att avgöra organisationens övergripande status och hälsa. Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till dess avsedda mottagare) och granska rapporter för att hjälpa till med efterlevnadskraven. I följande tabell beskrivs de rapporter och felsökningsverktyg som är tillgängliga för EOP-administratörer.
ms.openlocfilehash: 282fd032e73ccb8217801a575f6029dbd9fadc9c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810386"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="e0ba1-105">Rapportering och meddelandespårning i Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e0ba1-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="e0ba1-106">Microsoft Exchange Online Protection (EOP) innehåller många olika rapporter som kan hjälpa dig att avgöra organisationens övergripande status och hälsa.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="e0ba1-107">Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till dess avsedda mottagare) och granska rapporter för att hjälpa till med efterlevnadskraven.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="e0ba1-108">Användningsrapporter</span><span class="sxs-lookup"><span data-stu-id="e0ba1-108">Usage reports</span></span>

<span data-ttu-id="e0ba1-109">**Aktivitet för Office 365-grupper**: Visa information om antalet Office 365-grupper som skapas och används.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-109">**Office 365 groups activity**: View information about the number of Office 365 groups that are created and used.</span></span>

<span data-ttu-id="e0ba1-110">**E-postaktivitet**: Visa information om antalet meddelanden som skickas, tas emot och läses i hela organisationen och av specifika användare.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="e0ba1-111">**Användning av e-postappar**: Visa information om de e-postappar som används.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="e0ba1-112">Detta inkluderar det totala antalet anslutningar för varje app och de versioner av Outlook som ansluter.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="e0ba1-113">**Postlådeanvändning**: Visa information om lagring som används, kvotförbrukning, artikelantal och senaste aktivitet (skicka eller läsa aktivitet) för postlådor.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="e0ba1-114">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="e0ba1-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="e0ba1-115">Office 365-rapporter i administrationscentret – Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="e0ba1-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="e0ba1-116">Office 365-rapporter i administrationscentret – e-postaktivitet</span><span class="sxs-lookup"><span data-stu-id="e0ba1-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="e0ba1-117">Office 365-rapporter i Administrationscentret – användning av e-postappar</span><span class="sxs-lookup"><span data-stu-id="e0ba1-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="e0ba1-118">Office 365-rapporter i administrationscentret – postlådeanvändning</span><span class="sxs-lookup"><span data-stu-id="e0ba1-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e0ba1-119">Säkerhets- & efterlevnadsrapporter i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0ba1-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="e0ba1-120">Dessa förbättrade rapporter ger en interaktiv rapporteringsupplevelse för EOP-administratörer, som innehåller sammanfattande information, och möjligheten att öka detaljnivån för mer information.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="e0ba1-121">**Avancerat hotskydd (ATP):** Visa information om säkra länkar och säkra bilagor som ingår i ATP.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="e0ba1-122">**EOP**: Visa information om upptäcktav skadlig kod, falsk e-post, skräppostidentifieringar och e-postflöde till och från din organisation.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="e0ba1-123">Visa rapporter för Avancerad hotskydd i Office 365</span><span class="sxs-lookup"><span data-stu-id="e0ba1-123">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="e0ba1-124">Anpassade rapporter med Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="e0ba1-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="e0ba1-125">Skapa programmatiskt rapporter som är tillgängliga i administrationscentret för Microsoft 365 med hjälp av Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="e0ba1-126">Se underavsnitten [i Användningsrapporter för Arbeta med Office 365 i Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="e0ba1-126">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="e0ba1-127">Anpassade rapporter med Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="e0ba1-127">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="e0ba1-128">Skapa programmässigt rapporter.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-128">Programmatically create reports.</span></span> <span data-ttu-id="e0ba1-129">Se [Översikt över Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="e0ba1-129">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="e0ba1-130">Meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="e0ba1-130">Message trace</span></span>

<span data-ttu-id="e0ba1-131">Följer e-postmeddelanden när de färdas via EOP.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-131">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="e0ba1-132">Du kan avgöra om ett e-postmeddelande togs emot, avvisades, sköts upp eller levererades av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-132">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="e0ba1-133">Den visar också vilka åtgärder som vidtogs på meddelandet innan det nådde sin slutliga status.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-133">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="e0ba1-134">Du kan använda den här informationen för att effektivt svara på användarens frågor, felsöka problem med e-postflödet, validera principändringar och lindra behovet av att kontakta teknisk support för hjälp.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-134">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="e0ba1-135">Se [Spåra ett e-postmeddelande](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="e0ba1-135">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="e0ba1-136">Granska loggning</span><span class="sxs-lookup"><span data-stu-id="e0ba1-136">Audit logging</span></span>

<span data-ttu-id="e0ba1-137">Spårar specifika ändringar som gjorts av administratörer i din organisation.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-137">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="e0ba1-138">Dessa rapporter kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-138">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="e0ba1-139">Se [Granskningsrapporter i EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e0ba1-139">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="e0ba1-140">Rapportering och meddelandespårningsdatatillgänglighet och svarstid</span><span class="sxs-lookup"><span data-stu-id="e0ba1-140">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="e0ba1-141">I följande tabell beskrivs när EOP-rapporterings- och meddelandespårningsdata är tillgängliga och hur länge.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-141">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="e0ba1-142">**Rapporttyp**</span><span class="sxs-lookup"><span data-stu-id="e0ba1-142">**Report type**</span></span>|<span data-ttu-id="e0ba1-143">**Tillgängliga data för (tillbakablicksperiod)**</span><span class="sxs-lookup"><span data-stu-id="e0ba1-143">**Data available for (look back period)**</span></span>|<span data-ttu-id="e0ba1-144">**Latens**</span><span class="sxs-lookup"><span data-stu-id="e0ba1-144">**Latency**</span></span>|
|<span data-ttu-id="e0ba1-145">Sammanfattningsrapporter för e-postskydd</span><span class="sxs-lookup"><span data-stu-id="e0ba1-145">Mail protection summary reports</span></span>|<span data-ttu-id="e0ba1-146">90 dagar</span><span class="sxs-lookup"><span data-stu-id="e0ba1-146">90 days</span></span>|<span data-ttu-id="e0ba1-147">Meddelandedataaggregering är mestadels klar inom 24-48 timmar.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-147">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="e0ba1-148">Vissa mindre inkrementella aggregerade ändringar kan inträffa i upp till 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-148">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="e0ba1-149">Informationsrapporter för e-postskydd</span><span class="sxs-lookup"><span data-stu-id="e0ba1-149">Mail protection detail reports</span></span>|<span data-ttu-id="e0ba1-150">90 dagar</span><span class="sxs-lookup"><span data-stu-id="e0ba1-150">90 days</span></span>|<span data-ttu-id="e0ba1-151">För detaljdata som är kortare än 7 dagar ska data visas inom 24 timmar men kanske inte är fullständiga förrän 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-151">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="e0ba1-152">Vissa mindre inkrementella ändringar kan inträffa i upp till 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-152">Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="e0ba1-153">Om du vill visa detaljrapporter för meddelanden som är större än 7 dagar kan det ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-153">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="e0ba1-154">Meddelandespårningsdata</span><span class="sxs-lookup"><span data-stu-id="e0ba1-154">Message trace data</span></span>|<span data-ttu-id="e0ba1-155">90 dagar</span><span class="sxs-lookup"><span data-stu-id="e0ba1-155">90 days</span></span>|<span data-ttu-id="e0ba1-156">När du kör en meddelandespårning för meddelanden som är mindre än 7 dagar gamla ska meddelandena visas inom 5-30 minuter.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-156">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="e0ba1-157">När du kör en meddelandespårning för meddelanden som är större än 7 dagar kan resultaten ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-157">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="e0ba1-158">Datatillgänglighet och svarstid är desamma oavsett om de begärs via administrationscentret för Microsoft 365 eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0ba1-158">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
