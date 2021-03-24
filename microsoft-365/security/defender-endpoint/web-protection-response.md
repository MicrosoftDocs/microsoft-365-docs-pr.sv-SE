---
title: Svara på webbhot i Microsoft Defender ATP
description: Svara på aviseringar som rör skadliga och oönskade webbplatser. Förstå hur skydd mot webbhot informerar slutanvändarna via deras webbläsare och Windows-meddelanden
keywords: webbskydd, skydd mot webbhot, surfning, varningar, svar, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare, meddelanden, slutanvändare, Windows-meddelanden, blockeringssida,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 339944b94ca55c5d73fafaabfe3f7bc26dafe7bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071714"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="297c7-105">Svara på webbhot</span><span class="sxs-lookup"><span data-stu-id="297c7-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="297c7-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="297c7-106">**Applies to:**</span></span>
- [<span data-ttu-id="297c7-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="297c7-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="297c7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="297c7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="297c7-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="297c7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="297c7-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="297c7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="297c7-111">Med webbskydd i Microsoft Defender för Slutpunkt kan du effektivt undersöka och svara på aviseringar som rör skadliga webbplatser och webbplatser i din anpassade indikatorlista.</span><span class="sxs-lookup"><span data-stu-id="297c7-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="297c7-112">Visa varningar för webbhot</span><span class="sxs-lookup"><span data-stu-id="297c7-112">View web threat alerts</span></span>
<span data-ttu-id="297c7-113">Microsoft Defender för Slutpunkt genererar följande [aviseringar om](manage-alerts.md) skadlig eller misstänkt webbaktivitet:</span><span class="sxs-lookup"><span data-stu-id="297c7-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="297c7-114">**Misstänkt anslutning som blockeras** av nätverksskydd – den här aviseringen genereras när ett  försök att komma åt en skadlig webbplats eller en webbplats i den anpassade indikatorlistan stoppas av nätverksskydd i *blockeringsläge*</span><span class="sxs-lookup"><span data-stu-id="297c7-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="297c7-115">**Misstänkt anslutning som upptäckts** av nätverksskydd – den här varningen genereras när ett försök att komma åt en skadlig webbplats eller en webbplats i den anpassade indikatorlistan identifieras av nätverksskyddet i *granskningsläge*</span><span class="sxs-lookup"><span data-stu-id="297c7-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="297c7-116">Varje avisering ger följande information:</span><span class="sxs-lookup"><span data-stu-id="297c7-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="297c7-117">Enhet som försökte komma åt den blockerade webbplatsen</span><span class="sxs-lookup"><span data-stu-id="297c7-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="297c7-118">Program eller program som används för att skicka webbbegäran</span><span class="sxs-lookup"><span data-stu-id="297c7-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="297c7-119">Skadlig URL eller URL i den anpassade indikatorlistan</span><span class="sxs-lookup"><span data-stu-id="297c7-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="297c7-120">Rekommenderade åtgärder för svarare</span><span class="sxs-lookup"><span data-stu-id="297c7-120">Recommended actions for responders</span></span>

![Bild av en avisering som rör skydd mot webbhot](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="297c7-122">För att minska mängden aviseringar konsoliderar Microsoft Defender för Endpoint identifiering av webbhot för samma domän på samma enhet varje dag till en enda avisering.</span><span class="sxs-lookup"><span data-stu-id="297c7-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="297c7-123">Endast en avisering skapas och räknas in i [skyddsrapporten för webben.](web-protection-monitoring.md)</span><span class="sxs-lookup"><span data-stu-id="297c7-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="297c7-124">Kontrollera webbplatsinformation</span><span class="sxs-lookup"><span data-stu-id="297c7-124">Inspect website details</span></span>
<span data-ttu-id="297c7-125">Du kan visa mer genom att välja webbadressen eller domänen för webbplatsen i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="297c7-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="297c7-126">Då öppnas en sida om just den URL:en eller domänen med olika information, till exempel:</span><span class="sxs-lookup"><span data-stu-id="297c7-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="297c7-127">Enheter som försökte komma åt webbplatsen</span><span class="sxs-lookup"><span data-stu-id="297c7-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="297c7-128">Incidenter och aviseringar relaterade till webbplatsen</span><span class="sxs-lookup"><span data-stu-id="297c7-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="297c7-129">Hur ofta webbplatsen sågs i händelser i organisationen</span><span class="sxs-lookup"><span data-stu-id="297c7-129">How frequent the website was seen in events in your organization</span></span>

    ![Bild av informationssidan för domänen eller URL-adressen](images/wtp-website-details.png)

[<span data-ttu-id="297c7-131">Läs mer om sidorna för URL- eller domänentitet</span><span class="sxs-lookup"><span data-stu-id="297c7-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="297c7-132">Kontrollera enheten</span><span class="sxs-lookup"><span data-stu-id="297c7-132">Inspect the device</span></span>
<span data-ttu-id="297c7-133">Du kan också kontrollera vilken enhet som försökte komma åt en blockerad URL.</span><span class="sxs-lookup"><span data-stu-id="297c7-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="297c7-134">Om du väljer namnet på enheten på aviseringssidan öppnas en sida med omfattande information om enheten.</span><span class="sxs-lookup"><span data-stu-id="297c7-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="297c7-135">Läs mer om enhetsentitetssidor</span><span class="sxs-lookup"><span data-stu-id="297c7-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="297c7-136">Webbläsare och Windows-meddelanden för slutanvändare</span><span class="sxs-lookup"><span data-stu-id="297c7-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="297c7-137">Med webbskydd i Microsoft Defender för Endpoint hindras slutanvändarna från att besöka skadliga eller oönskade webbplatser med hjälp av Microsoft Edge eller andra webbläsare.</span><span class="sxs-lookup"><span data-stu-id="297c7-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="297c7-138">Eftersom blockering utförs av [nätverksskydd](network-protection.md)ser de ett allmänt fel från webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="297c7-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="297c7-139">De ser också ett meddelande från Windows.</span><span class="sxs-lookup"><span data-stu-id="297c7-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="297c7-140">![Bild på Microsoft Edge som visar ett 403-fel och Windows-meddelandet ](images/wtp-browser-blocking-page.png)
 *Webbhot blockeras i Microsoft Edge*</span><span class="sxs-lookup"><span data-stu-id="297c7-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="297c7-141">![Bild på Chrome-webbläsare som visar en varning om säker anslutning och Webbhotet i Windows ](images/wtp-chrome-browser-blocking-page.png)
 *blockeras i Chrome*</span><span class="sxs-lookup"><span data-stu-id="297c7-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="297c7-142">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="297c7-142">Related topics</span></span>
- [<span data-ttu-id="297c7-143">Översikt över webbskydd</span><span class="sxs-lookup"><span data-stu-id="297c7-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="297c7-144">Filtrering av webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="297c7-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="297c7-145">Skydd mot webbhot</span><span class="sxs-lookup"><span data-stu-id="297c7-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="297c7-146">Övervaka webbsäkerhet</span><span class="sxs-lookup"><span data-stu-id="297c7-146">Monitor web security</span></span>](web-protection-monitoring.md)
