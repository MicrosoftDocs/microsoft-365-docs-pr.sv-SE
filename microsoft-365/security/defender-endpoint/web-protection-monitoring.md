---
title: Övervaka webbsurfningssäkerhet i Microsoft Defender ATP
description: Använda webbskydd i Microsoft Defender ATP för att övervaka webbsurfningssäkerhet
keywords: webbskydd, skydd mot webbhot, surfning, övervakning, rapporter, kort, domänlista, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare
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
ms.openlocfilehash: 5d5cb89bccb0d7ea0fa4891c3b5b0d11a7244cf8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071745"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="ed348-104">Övervaka surfsäkerhet</span><span class="sxs-lookup"><span data-stu-id="ed348-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ed348-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ed348-105">**Applies to:**</span></span>
- [<span data-ttu-id="ed348-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ed348-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ed348-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed348-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ed348-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ed348-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ed348-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ed348-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="ed348-110">Med webbskydd kan du övervaka organisationens webbsurfningssäkerhet genom rapporter under **Rapporter > skydd på** webben i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="ed348-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="ed348-111">Rapporten innehåller kort som tillhandahåller statistik för identifiering av webbhot.</span><span class="sxs-lookup"><span data-stu-id="ed348-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="ed348-112">**Identifiering av skydd** mot webbhot med tiden – det här trendkortet visar antalet webbhot som upptäckts av typ under den valda tidsperioden (de senaste 30 dagarna, de senaste 3 månaderna, de senaste 6 månaderna)</span><span class="sxs-lookup"><span data-stu-id="ed348-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Bild på kortet som visar identifieringar av skydd mot webbhot över tid](images/wtp-blocks-over-time.png)

- <span data-ttu-id="ed348-114">**Sammanfattning av skydd** mot webbhot – det här kortet visar totalt antal identifieringar av webbhot under de senaste 30 dagarna, med distribution för olika typer av webbhot.</span><span class="sxs-lookup"><span data-stu-id="ed348-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="ed348-115">Om du väljer en sektor öppnas listan med domäner som hittades med skadliga eller oönskade webbplatser.</span><span class="sxs-lookup"><span data-stu-id="ed348-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Bild på kortet som visar en sammanfattning av skydd mot webbhot](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="ed348-117">Det kan ta upp till 12 timmar innan ett block visas på korten eller i domänlistan.</span><span class="sxs-lookup"><span data-stu-id="ed348-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="ed348-118">Typer av webbhot</span><span class="sxs-lookup"><span data-stu-id="ed348-118">Types of web threats</span></span>

<span data-ttu-id="ed348-119">Webbskydd kategoriserar skadliga och oönskade webbplatser som:</span><span class="sxs-lookup"><span data-stu-id="ed348-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="ed348-120">**Nätfiske** – webbplatser som innehåller falska webbformulär och andra former av nätfiske som designats för att lura användare att dela upp autentiseringsuppgifter och annan känslig information</span><span class="sxs-lookup"><span data-stu-id="ed348-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="ed348-121">**Skadlig** – webbplatser som är värd för skadlig programvara och sårbarhetskod</span><span class="sxs-lookup"><span data-stu-id="ed348-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="ed348-122">**Anpassad indikator** – webbplatser vars URL:er eller domäner du har lagt till i din [anpassade indikatorlista för](manage-indicators.md) blockering</span><span class="sxs-lookup"><span data-stu-id="ed348-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="ed348-123">Visa domänlistan</span><span class="sxs-lookup"><span data-stu-id="ed348-123">View the domain list</span></span>

<span data-ttu-id="ed348-124">Välj en specifik kategori för webbhot i **sammanfattningskortet för skydd mot webbhot** för att öppna **sidan** Domäner.</span><span class="sxs-lookup"><span data-stu-id="ed348-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="ed348-125">Den här sidan visar listan över domänerna under den hotkategorin.</span><span class="sxs-lookup"><span data-stu-id="ed348-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="ed348-126">Sidan innehåller följande information för varje domän:</span><span class="sxs-lookup"><span data-stu-id="ed348-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="ed348-127">**Antal åtkomst** – antal förfrågningar om URL-adresser i domänen</span><span class="sxs-lookup"><span data-stu-id="ed348-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="ed348-128">**Block** – antal gånger som förfrågningar har blockerats</span><span class="sxs-lookup"><span data-stu-id="ed348-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="ed348-129">**Access-trend** – ändra antalet åtkomstförsök</span><span class="sxs-lookup"><span data-stu-id="ed348-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="ed348-130">**Hotkategori** – typ av webbhot</span><span class="sxs-lookup"><span data-stu-id="ed348-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="ed348-131">**Enheter** – antal enheter med åtkomstförsök</span><span class="sxs-lookup"><span data-stu-id="ed348-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="ed348-132">Välj en domän för att visa listan över enheter som har försökt komma åt URL:er i den domänen och listan med URL:er.</span><span class="sxs-lookup"><span data-stu-id="ed348-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed348-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ed348-133">Related topics</span></span>

- [<span data-ttu-id="ed348-134">Översikt över webbskydd</span><span class="sxs-lookup"><span data-stu-id="ed348-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="ed348-135">Filtrering av webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="ed348-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="ed348-136">Skydd mot webbhot</span><span class="sxs-lookup"><span data-stu-id="ed348-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="ed348-137">Svara på webbhot</span><span class="sxs-lookup"><span data-stu-id="ed348-137">Respond to web threats</span></span>](web-protection-response.md)
