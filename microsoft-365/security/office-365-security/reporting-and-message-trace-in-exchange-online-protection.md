---
title: Rapportering och meddelandespårning
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
ms.openlocfilehash: b33d343d9b7f02e32619031d3ecf72ad12f891fd
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588174"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="0da91-103">Rapportering och meddelandespårning i EOP</span><span class="sxs-lookup"><span data-stu-id="0da91-103">Reporting and message trace in EOP</span></span>

<span data-ttu-id="0da91-104">I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor erbjuder EOP många olika rapporter som kan hjälpa dig att fastställa organisationens övergripande status och hälsa.</span><span class="sxs-lookup"><span data-stu-id="0da91-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="0da91-105">Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till de avsedda mottagarna) och granskningsrapporter som hjälper dig att uppfylla efterlevnadskraven.</span><span class="sxs-lookup"><span data-stu-id="0da91-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="0da91-106">Användningsrapporter</span><span class="sxs-lookup"><span data-stu-id="0da91-106">Usage reports</span></span>

<span data-ttu-id="0da91-107">**Aktivitet för Microsoft 365 grupper:** Visa information om antalet Microsoft 365-grupper som skapas och används.</span><span class="sxs-lookup"><span data-stu-id="0da91-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="0da91-108">**E-postaktivitet**: Visa information om antalet meddelanden som skickas, tas emot och läss i hela organisationen och av specifika användare.</span><span class="sxs-lookup"><span data-stu-id="0da91-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="0da91-109">**Användning av e-postappar**: Visa information om de e-postappar som används.</span><span class="sxs-lookup"><span data-stu-id="0da91-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="0da91-110">Detta inkluderar det totala antalet anslutningar för varje app och de versioner av Outlook som ansluter.</span><span class="sxs-lookup"><span data-stu-id="0da91-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="0da91-111">**Postlådeanvändning**: Visa information om lagring som används, kvotförbrukning, artikelantal och senaste aktivitet (skicka eller läsa aktivitet) för postlådor.</span><span class="sxs-lookup"><span data-stu-id="0da91-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="0da91-112">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="0da91-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="0da91-113">Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="0da91-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="0da91-114">Microsoft 365-rapporter i administrationscentret – E-postaktivitet</span><span class="sxs-lookup"><span data-stu-id="0da91-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="0da91-115">Microsoft 365-rapporter i administrationscentret – användning av e-postappar</span><span class="sxs-lookup"><span data-stu-id="0da91-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="0da91-116">Microsoft 365-rapporter i administrationscentret – användning av postlåda</span><span class="sxs-lookup"><span data-stu-id="0da91-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0da91-117">Säkerhetsrapporter & efterlevnad i microsoft 365-administrationscentret</span><span class="sxs-lookup"><span data-stu-id="0da91-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0da91-118">Dessa förbättrade rapporter ger en interaktiv rapporteringsupplevelse för EOP-administratörer, som innehåller sammanfattande information och möjligheten att öka detaljnivån för mer information.</span><span class="sxs-lookup"><span data-stu-id="0da91-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="0da91-119">**Advanced Threat Protection (ATP):** Visa information om säkra länkar och säkra bilagor som ingår i ATP.</span><span class="sxs-lookup"><span data-stu-id="0da91-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="0da91-120">**EOP**: Visa information om identifiering av skadlig programvara, förfalskad e-post, skräppostidentifieringar och e-postflöde till och från din organisation.</span><span class="sxs-lookup"><span data-stu-id="0da91-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="0da91-121">Visa rapporter för avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="0da91-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="0da91-122">Anpassade rapporter med Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="0da91-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="0da91-123">Skapa programmatiskt rapporter som är tillgängliga i administrationscentret med hjälp av Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="0da91-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="0da91-124">Mer information finns i [Översikt över Microsoft Graph](https://docs.microsoft.com/graph/overview) och Arbeta med [användningsrapporter för Office 365 i Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="0da91-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="0da91-125">Meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="0da91-125">Message trace</span></span>

<span data-ttu-id="0da91-126">Följer e-postmeddelanden när de färdas via EOP.</span><span class="sxs-lookup"><span data-stu-id="0da91-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="0da91-127">Du kan avgöra om ett e-postmeddelande togs emot, avvisades, sköts upp eller levererades av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0da91-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="0da91-128">Den visar också vilka åtgärder som vidtogs på meddelandet innan det nådde sin slutliga status.</span><span class="sxs-lookup"><span data-stu-id="0da91-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="0da91-129">Du kan använda den här informationen för att effektivt svara på användarens frågor, felsöka problem med e-postflödet, validera principändringar och minska behovet av att kontakta teknisk support för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="0da91-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="0da91-130">Visa [meddelandespårning i Säkerhets- & Compliance Center](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="0da91-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="0da91-131">Granskningsloggning</span><span class="sxs-lookup"><span data-stu-id="0da91-131">Audit logging</span></span>

<span data-ttu-id="0da91-132">Spårar specifika ändringar som gjorts av administratörer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0da91-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="0da91-133">Dessa rapporter kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem.</span><span class="sxs-lookup"><span data-stu-id="0da91-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="0da91-134">Se [Granskningsrapporter i EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0da91-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="0da91-135">Rapportering och meddelandespårning datatillgänglighet och svarstid</span><span class="sxs-lookup"><span data-stu-id="0da91-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="0da91-136">I följande tabell beskrivs när EOP-rapportering och meddelandespårningsdata är tillgängliga och hur länge.</span><span class="sxs-lookup"><span data-stu-id="0da91-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="0da91-137">**Rapporttyp**</span><span class="sxs-lookup"><span data-stu-id="0da91-137">**Report type**</span></span>|<span data-ttu-id="0da91-138">**Tillgängliga data för (tillbakablicksperiod)**</span><span class="sxs-lookup"><span data-stu-id="0da91-138">**Data available for (look back period)**</span></span>|<span data-ttu-id="0da91-139">**Latens**</span><span class="sxs-lookup"><span data-stu-id="0da91-139">**Latency**</span></span>|
|<span data-ttu-id="0da91-140">Sammanfattningsrapporter för e-postskydd</span><span class="sxs-lookup"><span data-stu-id="0da91-140">Mail protection summary reports</span></span>|<span data-ttu-id="0da91-141">90 dagar</span><span class="sxs-lookup"><span data-stu-id="0da91-141">90 days</span></span>|<span data-ttu-id="0da91-142">Aggregering av meddelandedata är mestadels klar inom 24-48 timmar.</span><span class="sxs-lookup"><span data-stu-id="0da91-142">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="0da91-143">Vissa mindre inkrementella aggregerade ändringar kan förekomma i upp till 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="0da91-143">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="0da91-144">Informationsrapporter för e-postskydd</span><span class="sxs-lookup"><span data-stu-id="0da91-144">Mail protection detail reports</span></span>|<span data-ttu-id="0da91-145">90 dagar</span><span class="sxs-lookup"><span data-stu-id="0da91-145">90 days</span></span>|<span data-ttu-id="0da91-146">För detaljdata som är mindre än 7 dagar gamla ska data visas inom 24 timmar men kanske inte vara klara förrän 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="0da91-146">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="0da91-147">Vissa mindre inkrementella ändringar kan förekomma i upp till 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="0da91-147">Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="0da91-148">Om du vill visa detaljerade rapporter för meddelanden som är större än 7 dagar gamla kan resultatet ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="0da91-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="0da91-149">Data för meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="0da91-149">Message trace data</span></span>|<span data-ttu-id="0da91-150">90 dagar</span><span class="sxs-lookup"><span data-stu-id="0da91-150">90 days</span></span>|<span data-ttu-id="0da91-151">När du kör en meddelandespårning för meddelanden som är mindre än 7 dagar gamla ska meddelandena visas inom 5-30 minuter.</span><span class="sxs-lookup"><span data-stu-id="0da91-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="0da91-152">När du kör en meddelandespårning för meddelanden som är längre än 7 dagar gamla kan resultatet ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="0da91-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="0da91-153">Datatillgänglighet och svarstid är desamma oavsett om de begärs via administrationscentret eller fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0da91-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
