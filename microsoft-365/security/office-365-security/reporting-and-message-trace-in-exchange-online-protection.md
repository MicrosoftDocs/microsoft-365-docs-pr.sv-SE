---
title: Rapportering och meddelandespårning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om rapporter och felsökningsverktyg som är tillgängliga för EOP-administratörer (Exchange Online Protection).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5e5493925a17725bfb9d6698b3f94050960ccc7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207148"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="cab09-103">Rapportering och meddelandespårning i EOP</span><span class="sxs-lookup"><span data-stu-id="cab09-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cab09-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="cab09-104">**Applies to**</span></span>
- [<span data-ttu-id="cab09-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cab09-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cab09-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="cab09-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cab09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cab09-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cab09-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor erbjuder EOP många olika rapporter som kan hjälpa dig att avgöra organisationens övergripande status och status.</span><span class="sxs-lookup"><span data-stu-id="cab09-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="cab09-109">Det finns även verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till de avsedda mottagarna) och granskningsrapporter för att uppfylla efterlevnadskraven.</span><span class="sxs-lookup"><span data-stu-id="cab09-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="cab09-110">Användningsrapporter</span><span class="sxs-lookup"><span data-stu-id="cab09-110">Usage reports</span></span>

<span data-ttu-id="cab09-111">**Aktivitet i Microsoft 365-grupper**: Visa information om antalet Microsoft 365-grupper som skapas och används.</span><span class="sxs-lookup"><span data-stu-id="cab09-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="cab09-112">**E-postaktivitet:** Visa information om antalet meddelanden som skickas, tas emot och läses i hela organisationen och av specifika användare.</span><span class="sxs-lookup"><span data-stu-id="cab09-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="cab09-113">**Användning av e-postprogram:** Visa information om vilka e-postprogram som används.</span><span class="sxs-lookup"><span data-stu-id="cab09-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="cab09-114">Detta inkluderar det totala antalet anslutningar för varje app och de versioner av Outlook som ansluter.</span><span class="sxs-lookup"><span data-stu-id="cab09-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="cab09-115">**Postlådeanvändning:** Visa information om använt lagringsutrymme, kvotanvändning, antal objekt och senaste aktivitet (skicka eller läsaktivitet) för postlådor.</span><span class="sxs-lookup"><span data-stu-id="cab09-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="cab09-116">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="cab09-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="cab09-117">Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="cab09-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="cab09-118">Microsoft 365-rapporter i administrationscentret – E-postaktivitet</span><span class="sxs-lookup"><span data-stu-id="cab09-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="cab09-119">Microsoft 365-rapporter i administrationscentret – Användning av e-postprogram</span><span class="sxs-lookup"><span data-stu-id="cab09-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="cab09-120">Microsoft 365-rapporter i administrationscentret – Postlådeanvändning</span><span class="sxs-lookup"><span data-stu-id="cab09-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="cab09-121">Säkerhet & efterlevnadsrapporter i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cab09-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="cab09-122">De här förbättrade rapporterna ger en interaktiv rapporteringsupplevelse för EOP-administratörer, som innehåller sammanfattningsinformation och möjlighet att granska nedåt för mer information.</span><span class="sxs-lookup"><span data-stu-id="cab09-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="cab09-123">**Defender för Office 365:** Visa information om säkra länkar och säkra bifogade filer som ingår i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cab09-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="cab09-124">**EOP:** Visa information om identifiering av skadlig programvara, förfalskning, identifiering av skräppost och e-postflöde till och från organisationen.</span><span class="sxs-lookup"><span data-stu-id="cab09-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="cab09-125">Visa rapporter för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="cab09-125">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="cab09-126">Anpassade rapporter med Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="cab09-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="cab09-127">Programmässigt skapa rapporter som är tillgängliga i administrationscentret med hjälp av Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="cab09-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="cab09-128">Mer information finns i Översikt [över Microsoft Graph och](/graph/overview) Arbeta med Office [365-användningsrapporter i Microsoft Graph.](/graph/api/resources/report)</span><span class="sxs-lookup"><span data-stu-id="cab09-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="cab09-129">Meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="cab09-129">Message trace</span></span>

<span data-ttu-id="cab09-130">Följer upp e-postmeddelanden när de färdas genom EOP.</span><span class="sxs-lookup"><span data-stu-id="cab09-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="cab09-131">Du kan avgöra om ett e-postmeddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cab09-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="cab09-132">Det visar också vilka åtgärder som har vidtagits för meddelandet innan det nått sin slutgiltiga status.</span><span class="sxs-lookup"><span data-stu-id="cab09-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="cab09-133">Du kan använda den här informationen för att effektivt besvara användarnas frågor, felsöka problem i e-postflödet, verifiera principändringar och förbättra behovet av att kontakta teknisk support för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="cab09-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="cab09-134">Läs [Meddelandespårning i Säkerhets- & Säkerhets- och efterlevnadscenter.](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="cab09-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="cab09-135">Granskningsloggning</span><span class="sxs-lookup"><span data-stu-id="cab09-135">Audit logging</span></span>

<span data-ttu-id="cab09-136">Spårar specifika ändringar som gjorts av administratörer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cab09-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="cab09-137">De här rapporterna kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem.</span><span class="sxs-lookup"><span data-stu-id="cab09-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="cab09-138">Se [Granskningsrapporter i EOP.](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="cab09-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="cab09-139">Rapportering och meddelandespårning av datatillgänglighet och svarstid</span><span class="sxs-lookup"><span data-stu-id="cab09-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="cab09-140">I följande tabell beskrivs när EOP-rapportering och meddelandespårningsdata är tillgängliga och hur länge.</span><span class="sxs-lookup"><span data-stu-id="cab09-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="cab09-141">Rapporttyp</span><span class="sxs-lookup"><span data-stu-id="cab09-141">Report type</span></span>|<span data-ttu-id="cab09-142">Tillgängliga data för (bakåtperiod)</span><span class="sxs-lookup"><span data-stu-id="cab09-142">Data available for (look back period)</span></span>|<span data-ttu-id="cab09-143">Svarstid</span><span class="sxs-lookup"><span data-stu-id="cab09-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="cab09-144">Sammanfattningsrapporter om e-postskydd</span><span class="sxs-lookup"><span data-stu-id="cab09-144">Mail protection summary reports</span></span>|<span data-ttu-id="cab09-145">90 dagar</span><span class="sxs-lookup"><span data-stu-id="cab09-145">90 days</span></span>|<span data-ttu-id="cab09-146">Aggregeringen för meddelandedata slutförs oftast inom 24–48 timmar.</span><span class="sxs-lookup"><span data-stu-id="cab09-146">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="cab09-147">Vissa mindre stegvisa sammantagna ändringar kan inträffa i upp till 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="cab09-147">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="cab09-148">Detaljrapporter om e-postskydd</span><span class="sxs-lookup"><span data-stu-id="cab09-148">Mail protection detail reports</span></span>|<span data-ttu-id="cab09-149">90 dagar</span><span class="sxs-lookup"><span data-stu-id="cab09-149">90 days</span></span>|<span data-ttu-id="cab09-150">För detaljdata som är mindre än 7 dagar gamla bör data visas inom 24 timmar men kan vara fullständiga till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="cab09-150">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="cab09-151">Vissa mindre stegvisa ändringar kan inträffa i upp till 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="cab09-151">Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="cab09-152">Om du vill visa detaljrapporter för meddelanden som är äldre än 7 dagar kan resultatet ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="cab09-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="cab09-153">Meddelandespårningsdata</span><span class="sxs-lookup"><span data-stu-id="cab09-153">Message trace data</span></span>|<span data-ttu-id="cab09-154">90 dagar</span><span class="sxs-lookup"><span data-stu-id="cab09-154">90 days</span></span>|<span data-ttu-id="cab09-155">När du kör en meddelandespårning för meddelanden som är äldre än sju dagar bör meddelandena visas inom 5–30 minuter.</span><span class="sxs-lookup"><span data-stu-id="cab09-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="cab09-156">När du kör en meddelandespårning för meddelanden som är äldre än sju dagar kan resultatet ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="cab09-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="cab09-157">Datatillgänglighet och svarstid är samma oavsett om begärs via administrationscentret eller fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cab09-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>