---
title: Tidszonsinställningar i Microsoft Defender Säkerhetscenter
description: Använd informationen här om du vill konfigurera tidszonsinställningarna för säkerhetscentret i Microsoft Defender och visa licensinformation.
keywords: inställningar, Microsoft Defender, hotintelligens för cybersäkerhet, avancerat skydd mot hot, tidszon, utc, lokal tid, licens
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e395420b92c29977f1c802d1c10683492c1aba10
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470471"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="b5ad0-104">Tidszonsinställningar i Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="b5ad0-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5ad0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-105">**Applies to:**</span></span>
- [<span data-ttu-id="b5ad0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b5ad0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="b5ad0-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b5ad0-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5ad0-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="b5ad0-109">Använd menyn **Tidszon inställningar** ![ Tidszon inställningar1 för att konfigurera tidszon och ](images/atp-time-zone.png) visa licensinformation.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-109">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="b5ad0-110">Tidszonsinställningar</span><span class="sxs-lookup"><span data-stu-id="b5ad0-110">Time zone settings</span></span>
<span data-ttu-id="b5ad0-111">Tidsaspekten är viktig i bedömningen och analysen av uppfattas och faktiska cyberattacker.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-111">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="b5ad0-112">Cyberforensic undersökningar förlitar sig ofta på tidsstämplar för att skapa händelsesekvenser.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-112">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="b5ad0-113">Det är viktigt att ditt system återspeglar rätt tidszonsinställningar.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-113">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="b5ad0-114">Microsoft Defender för Endpoint kan visa antingen Coordinated Universal Time (UTC) eller lokal tid.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-114">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="b5ad0-115">Din aktuella tidszon visas på menyn Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-115">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="b5ad0-116">Du kan ändra den tidszon som visas på **menyn Tidszon.**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-116">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Ikon för tidszonsinställningar2](images/atp-time-zone-menu.png)<span data-ttu-id="b5ad0-118">.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-118">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="b5ad0-119">UTC-tidszon</span><span class="sxs-lookup"><span data-stu-id="b5ad0-119">UTC time zone</span></span>
<span data-ttu-id="b5ad0-120">Microsoft Defender för Slutpunkt använder UTC-tid som standard.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-120">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="b5ad0-121">Om du ställer in Microsoft Defender för slutpunktens tidszon på UTC visas alla systemtidsstämplar (aviseringar, händelser och andra) i UTC för alla användare.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-121">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="b5ad0-122">Det kan hjälpa säkerhetsanalytiker som arbetar på olika platser över hela världen att använda samma tidsstämplar vid undersökning av händelser.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-122">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="b5ad0-123">Lokal tidszon</span><span class="sxs-lookup"><span data-stu-id="b5ad0-123">Local time zone</span></span>
<span data-ttu-id="b5ad0-124">Du kan välja att Microsoft Defender för Endpoint ska använda lokala tidszonsinställningar.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-124">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="b5ad0-125">Alla aviseringar och händelser visas med din lokala tidszon.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-125">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="b5ad0-126">Den lokala tidszonen tas från enhetens nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-126">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="b5ad0-127">Om du ändrar de nationella inställningarna ändras även tidszonen för Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-127">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="b5ad0-128">Om du väljer den här inställningen innebär det att tidsstämplar som visas i Microsoft Defender för Slutpunkt justeras efter lokal tid för alla Microsoft Defender för slutpunktsanvändare.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-128">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="b5ad0-129">Analytiker som befinner sig på olika globala platser ser nu Microsoft Defender för Endpoint-aviseringar i enlighet med sina nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-129">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="b5ad0-130">Att välja att använda lokal tid kan vara användbart om analytikerna finns på en enda plats.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-130">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="b5ad0-131">I det här fallet kan det vara enklare att korrelera händelser till lokal tid, till exempel när en lokal användare klickade på en länk till ett misstänkt e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-131">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="b5ad0-132">Ange tidszon</span><span class="sxs-lookup"><span data-stu-id="b5ad0-132">Set the time zone</span></span>
<span data-ttu-id="b5ad0-133">Tidszonen för Microsoft Defender för slutpunkt är som standard utc.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-133">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="b5ad0-134">Om du anger tidszonen ändras även tiderna för alla Microsoft Defender för slutpunktsvyer.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-134">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="b5ad0-135">Så här anger du tidszon:</span><span class="sxs-lookup"><span data-stu-id="b5ad0-135">To set the time zone:</span></span>

1. <span data-ttu-id="b5ad0-136">Klicka på **tidszonsmenyn** ![ Tidszoninställningar ikon3 ](images/atp-time-zone.png) .</span><span class="sxs-lookup"><span data-stu-id="b5ad0-136">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="b5ad0-137">Välj TIDSZON **UTC-indikatorn.**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-137">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="b5ad0-138">Välj **Tidszon UTC** eller din lokala tidszon, till exempel -07:00.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-138">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="b5ad0-139">Nationella inställningar</span><span class="sxs-lookup"><span data-stu-id="b5ad0-139">Regional settings</span></span>
<span data-ttu-id="b5ad0-140">Om du vill använda olika datumformat för Microsoft Defender för Endpoint använder du nationella inställningar för Internet Explorer (IE) och Microsoft Edge (Edge).</span><span class="sxs-lookup"><span data-stu-id="b5ad0-140">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="b5ad0-141">Om du använder en annan webbläsare, till exempel Google Chrome, följer du anvisningarna för att ändra tid och datum för den webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-141">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="b5ad0-142">**Internet Explorer (IE) och Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-142">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="b5ad0-143">IE och Microsoft Edge använder **inställningarna för Region** som konfigurerats med alternativen **Klocka, språk** och region på Kontrollpanelen.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-143">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="b5ad0-144">Kända problem med nationella format</span><span class="sxs-lookup"><span data-stu-id="b5ad0-144">Known issues with regional formats</span></span>

<span data-ttu-id="b5ad0-145">**Datum- och tidsformat**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-145">**Date and time formats**</span></span><br>
<span data-ttu-id="b5ad0-146">Det finns några kända problem med tids- och datumformat.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-146">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="b5ad0-147">Om du konfigurerar dina nationella inställningar till något annat än de format som stöds kanske portalen inte återspeglar dina inställningar på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-147">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="b5ad0-148">Följande datum- och tidsformat stöds:</span><span class="sxs-lookup"><span data-stu-id="b5ad0-148">The following date and time formats are supported:</span></span>
- <span data-ttu-id="b5ad0-149">Datumformat MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="b5ad0-149">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="b5ad0-150">Datumformat dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="b5ad0-150">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="b5ad0-151">Tidsformat hh:mm:ss (12-timmarsformat)</span><span class="sxs-lookup"><span data-stu-id="b5ad0-151">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="b5ad0-152">Följande datum- och tidsformat stöds för närvarande inte:</span><span class="sxs-lookup"><span data-stu-id="b5ad0-152">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="b5ad0-153">Datumformat yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="b5ad0-153">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="b5ad0-154">Datumformat dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="b5ad0-154">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="b5ad0-155">Datumformat dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="b5ad0-155">Date format dd/MM/yy</span></span>
- <span data-ttu-id="b5ad0-156">Datumformat MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="b5ad0-156">Date format MM/dd/yy</span></span>
- <span data-ttu-id="b5ad0-157">Datumformat med yy.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-157">Date format with yy.</span></span> <span data-ttu-id="b5ad0-158">Kommer bara att visa yyyy.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-158">Will only show yyyy.</span></span>
- <span data-ttu-id="b5ad0-159">Tidsformat HH:mm:ss (24-timmarsformat)</span><span class="sxs-lookup"><span data-stu-id="b5ad0-159">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="b5ad0-160">**Decimalsymbol som används i tal**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-160">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="b5ad0-161">Decimalsymbol som används är alltid en punkt, även om ett kommatecken har markerats i inställningarna **för** Talformat i **inställningarna för** Region.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-161">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="b5ad0-162">Till exempel visas 15,5K som 15,5K.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-162">For example, 15,5K is displayed as 15.5K.</span></span>


