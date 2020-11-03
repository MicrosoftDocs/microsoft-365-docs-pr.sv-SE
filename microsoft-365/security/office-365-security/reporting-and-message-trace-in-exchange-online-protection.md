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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln lär du dig mer om rapporter och fel söknings verktyg som är tillgängliga för Microsoft Exchange Online Protection (EOP)-administratörer.
ms.openlocfilehash: 9a8eb8e35ef73eb27604eef4bf701982b1d51710
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845558"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="4f287-103">Rapportering och meddelande spårning i EOP</span><span class="sxs-lookup"><span data-stu-id="4f287-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4f287-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor finns det många olika rapporter i EOP som hjälper dig att avgöra den övergripande statusen och tillståndet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="4f287-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="4f287-105">Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till dess avsedda mottagare) och gransknings rapporter med krav på efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="4f287-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="4f287-106">Användnings rapporter</span><span class="sxs-lookup"><span data-stu-id="4f287-106">Usage reports</span></span>

<span data-ttu-id="4f287-107">**Aktivitet i microsoft 365-grupper** : Visa information om antalet Microsoft 365-grupper som har skapats och använts.</span><span class="sxs-lookup"><span data-stu-id="4f287-107">**Microsoft 365 groups activity** : View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="4f287-108">**E-postaktivitet** : Visa information om antalet meddelanden som skickas, tas emot och läses i hela organisationen och av specifika användare.</span><span class="sxs-lookup"><span data-stu-id="4f287-108">**Email activity** : View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="4f287-109">**Användning av e-postprogram** : Visa information om de e-postappar som används.</span><span class="sxs-lookup"><span data-stu-id="4f287-109">**Email app usage** : View information about the email apps that are used.</span></span> <span data-ttu-id="4f287-110">Detta inkluderar totalt antal anslutningar för varje app och den version av Outlook som är ansluten.</span><span class="sxs-lookup"><span data-stu-id="4f287-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="4f287-111">**Användning av post låda** : Visa information om använt lagrings utrymme för kvot, antal objekt och senaste aktivitet (skicka eller läsa aktivitet) för post lådor.</span><span class="sxs-lookup"><span data-stu-id="4f287-111">**Mailbox usage** : View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="4f287-112">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="4f287-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="4f287-113">Microsoft 365-rapporter i administrations Center – Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="4f287-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="4f287-114">Microsoft 365-rapporter i administrations Center – e-postaktivitet</span><span class="sxs-lookup"><span data-stu-id="4f287-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="4f287-115">Microsoft 365-rapporter i administrations Center – användning av e-postprogram</span><span class="sxs-lookup"><span data-stu-id="4f287-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="4f287-116">Microsoft 365-rapporter i administrations Center – använde brev Låde användning</span><span class="sxs-lookup"><span data-stu-id="4f287-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="4f287-117">Säkerhets & rapporter om efterlevnad i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f287-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="4f287-118">De här förbättrade rapporterna ger en interaktiv rapport upplevelse för EOP-administratörer, som innehåller sammanfattnings information och möjlighet att detaljgranska ned för mer information.</span><span class="sxs-lookup"><span data-stu-id="4f287-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="4f287-119">**Defender för office 365** : Visa information om säkra länkar och säkra bifogade filer som ingår i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="4f287-119">**Defender for Office 365** : View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="4f287-120">**EOP** : Visa information om identifiering av skadlig program vara, falsk e-post, skräp identifiering och e-postflöde till och från din organisation.</span><span class="sxs-lookup"><span data-stu-id="4f287-120">**EOP** : View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="4f287-121">Visa rapporter för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4f287-121">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="4f287-122">Anpassade rapporter med Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="4f287-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="4f287-123">Program mässigt skapa rapporter som är tillgängliga i administrations centret med Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="4f287-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="4f287-124">Mer information finns i [Översikt över Microsoft Graph](https://docs.microsoft.com/graph/overview) och [arbeta med användnings rapporterna för Office 365 i Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="4f287-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="4f287-125">Meddelande spårning</span><span class="sxs-lookup"><span data-stu-id="4f287-125">Message trace</span></span>

<span data-ttu-id="4f287-126">Följer e-postmeddelanden när de går genom EOP.</span><span class="sxs-lookup"><span data-stu-id="4f287-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="4f287-127">Du kan bestämma om ett e-postmeddelande har tagits emot, nekats, uppskjuts eller levererats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4f287-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="4f287-128">Det visar också vilka åtgärder som vidtogs innan meddelandet nådde sin slutliga status.</span><span class="sxs-lookup"><span data-stu-id="4f287-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="4f287-129">Du kan använda den här informationen för att effektivt besvara användarnas frågor, felsöka e-postflöden, validera princip ändringar och minska behovet av att kontakta teknisk support för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="4f287-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="4f287-130">Se [meddelande spårning i säkerhets & Compliance Center](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="4f287-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="4f287-131">Gransknings loggning</span><span class="sxs-lookup"><span data-stu-id="4f287-131">Audit logging</span></span>

<span data-ttu-id="4f287-132">Spårar specifika ändringar som gjorts av administratörer till din organisation.</span><span class="sxs-lookup"><span data-stu-id="4f287-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="4f287-133">Dessa rapporter kan hjälpa dig att felsöka konfigurations problem eller hitta orsaken till problem med säkerhet eller efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="4f287-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="4f287-134">Se [granska rapporter i EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4f287-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="4f287-135">Tillgänglighet och svars tid för rapportering och spårning av meddelanden</span><span class="sxs-lookup"><span data-stu-id="4f287-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="4f287-136">I följande tabell beskrivs när EOP rapporter och spårnings data för meddelanden är tillgängliga och hur länge.</span><span class="sxs-lookup"><span data-stu-id="4f287-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="4f287-137">Rapport typ</span><span class="sxs-lookup"><span data-stu-id="4f287-137">Report type</span></span>|<span data-ttu-id="4f287-138">Tillgängliga data för (se bakgrunds perioden)</span><span class="sxs-lookup"><span data-stu-id="4f287-138">Data available for (look back period)</span></span>|<span data-ttu-id="4f287-139">Borttagning</span><span class="sxs-lookup"><span data-stu-id="4f287-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="4f287-140">Sammanfattnings rapporter för e-postskydd</span><span class="sxs-lookup"><span data-stu-id="4f287-140">Mail protection summary reports</span></span>|<span data-ttu-id="4f287-141">90 dagar</span><span class="sxs-lookup"><span data-stu-id="4f287-141">90 days</span></span>|<span data-ttu-id="4f287-142">Meddelande data agg regering är mest komplett inom 24-48 timmar.</span><span class="sxs-lookup"><span data-stu-id="4f287-142">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="4f287-143">Vissa mindre stegvisa sammanlagda ändringar kan uppkomma i upp till fem dagar.</span><span class="sxs-lookup"><span data-stu-id="4f287-143">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="4f287-144">Informations rapporter för e-postskydd</span><span class="sxs-lookup"><span data-stu-id="4f287-144">Mail protection detail reports</span></span>|<span data-ttu-id="4f287-145">90 dagar</span><span class="sxs-lookup"><span data-stu-id="4f287-145">90 days</span></span>|<span data-ttu-id="4f287-146">För detalj uppgifter som är mindre än 7 dagar gamla bör data visas inom 24 timmar, men inte förrän 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="4f287-146">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="4f287-147">Vissa mindre stegvisa ändringar kan uppstå i upp till fem dagar.</span><span class="sxs-lookup"><span data-stu-id="4f287-147">Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="4f287-148">Om du vill visa detalj rapporter för meddelanden som är äldre än 7 dagar gamla kan resultatet ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="4f287-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="4f287-149">Meddelande spårnings data</span><span class="sxs-lookup"><span data-stu-id="4f287-149">Message trace data</span></span>|<span data-ttu-id="4f287-150">90 dagar</span><span class="sxs-lookup"><span data-stu-id="4f287-150">90 days</span></span>|<span data-ttu-id="4f287-151">När du kör en meddelande spårning för meddelanden som är mindre än 7 dagar gamla visas meddelandena inom 5-30 minuter.</span><span class="sxs-lookup"><span data-stu-id="4f287-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="4f287-152">När du kör en meddelande spårning för meddelanden som är äldre än 7 dagar sedan kan resultatet ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="4f287-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="4f287-153">Data tillgänglighet och svars tid är desamma om de begärs via administrations centret eller Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f287-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
