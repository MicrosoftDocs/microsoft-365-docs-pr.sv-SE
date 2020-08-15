---
title: Microsoft 365 Network Assessment (för hands version)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Assessment (för hands version)
ms.openlocfilehash: aacbdf73da9552a12bde250e51544f1de533637c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696714"
---
# <a name="microsoft-365-network-assessment-preview"></a><span data-ttu-id="01037-103">Microsoft 365 Network Assessment (för hands version)</span><span class="sxs-lookup"><span data-stu-id="01037-103">Microsoft 365 network assessment (preview)</span></span>

<span data-ttu-id="01037-104">I Microsoft 365 Admin Center-anslutningen till Microsoft 365-sidan destillerar **nätverks utvärderingarna** en mängd av många nätverks prestanda mått till en ögonblicks bild av företagets nätverks hälsa, som representeras av ett Points-värde från 1-100.</span><span class="sxs-lookup"><span data-stu-id="01037-104">In the Microsoft 365 Admin Center's Connectivity to Microsoft 365 page, **network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network health, represented by a points value from 1 - 100.</span></span> <span data-ttu-id="01037-105">Nätverks utvärderingar bevaras till både hela klient organisationen och för varje geografisk plats där användare ansluter till din klient organisation och ger Microsoft 365-administratörer ett enkelt sätt att omedelbart förstå en gestalt av företagets nätverks tillstånd och snabbt öka detalj nivån till en detaljerad rapport för alla globala Office-platser.</span><span class="sxs-lookup"><span data-stu-id="01037-105">Network assessments are scoped to both the entire tenant and for each geographic location from which users connect to your tenant, providing Microsoft 365 administrators with an easy way to instantly grasp a gestalt of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="01037-106">Värdet för nätverks utvärderings punkter är ett genomsnittligt mått på fördröjning, bandbredd, nedladdnings hastighet och anslutnings kvalitet som kompileras Live när de visas.</span><span class="sxs-lookup"><span data-stu-id="01037-106">The network assessment points value is an average measurement of latency, bandwidth, download speed and connection quality metrics compiled live at the time they are viewed.</span></span> <span data-ttu-id="01037-107">Prestanda mått för Microsoft-ägda nätverk undantas från dessa mätningar för att säkerställa att bedömnings resultaten är entydiga och specifika för företagets nätverk.</span><span class="sxs-lookup"><span data-stu-id="01037-107">Performance metrics for Microsoft-owned networks are excluded from these measurements to ensure that assessment results are unambiguous and specific to the corporate network.</span></span>

![Nätverkets utvärderings värde](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

<span data-ttu-id="01037-109">Ett lågt värde för utvärdering av nätverk ger förslag på att Microsoft 365-klienter har viktiga problem med att ansluta till klient organisationen eller att det finns en fungerande användar upplevelse, medan ett riktigt konfigurerat nätverk med få kontinuerliga prestanda problem uppstår.</span><span class="sxs-lookup"><span data-stu-id="01037-109">A very low network assessment value suggests that Microsoft 365 clients will have significant problems connecting to the tenant or maintaining a responsive user experience, while a high value indicates a properly configured network with few ongoing performance issues.</span></span> <span data-ttu-id="01037-110">Ett värde på 80% representerar en felfri original plan där du inte bör förvänta dig regelbundna klagomål om Microsoft 365-anslutning eller svars tid på grund av nätverks prestanda.</span><span class="sxs-lookup"><span data-stu-id="01037-110">A value of 80% represents a healthy baseline where you should not expect to receive regular user complaints about Microsoft 365 connectivity or responsiveness due to network performance.</span></span> <span data-ttu-id="01037-111">När du gör en iterativ nätverks förbindelse förbättras det här värdet tillsammans med användar upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="01037-111">As iterative network connectivity improvements are made, this value will increase along with user experience.</span></span>

>[!IMPORTANT]
><span data-ttu-id="01037-112">Nätverks insikter, prestanda rekommendationer och utvärderingar i administrations centret för Microsoft 365 är för närvarande förhands gransknings status och är bara tillgänglig för Microsoft 365-klient organisationer som har registrerats i funktionen för förhands granskning.</span><span class="sxs-lookup"><span data-stu-id="01037-112">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="network-assessment-panel"></a><span data-ttu-id="01037-113">Panelen nätverks utvärdering</span><span class="sxs-lookup"><span data-stu-id="01037-113">Network assessment panel</span></span>

<span data-ttu-id="01037-114">Varje nätverks utvärdering, oavsett om det gäller innehavaren eller till en viss Office-plats, visar en panel med information om utvärderingen.</span><span class="sxs-lookup"><span data-stu-id="01037-114">Each network assessment, whether scoped to the tenant or to a specific office location, shows a panel with details about the assessment.</span></span> <span data-ttu-id="01037-115">I den här panelen visas ett stapeldiagram över bedömningen, både som en procents ATS och totalt antal poäng för varje komponent arbets börda, inklusive endast arbets belastningar där mätnings data mottogs.</span><span class="sxs-lookup"><span data-stu-id="01037-115">This panel shows a bar chart of the assessment both as a percentage and as the total points for each component workload including only workloads where measurement data was received.</span></span> <span data-ttu-id="01037-116">För utvärdering av en Office-plats visas ett riktmärke som är median för alla Microsoft 365-klienter som rapporterade data i samma stad som din Office-plats.</span><span class="sxs-lookup"><span data-stu-id="01037-116">For an office location network assessment, we also show a benchmark which is the median of all Microsoft 365 clients that reported data in the same city as your office location.</span></span>

![Exempel på nätverkets utvärderings värde](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

<span data-ttu-id="01037-118">**Utvärderings detalj nivån** i panelen visar bedömningen för varje komponent arbets börda.</span><span class="sxs-lookup"><span data-stu-id="01037-118">The **Assessment breakdown** in the panel shows the assessment for each of the component workloads.</span></span>

<span data-ttu-id="01037-119">**Utvärderings historiken** visar de senaste 30 dagarna av utvärderingen och benchmark.</span><span class="sxs-lookup"><span data-stu-id="01037-119">The **Assessment history** shows the past 30 days of the assessment and the benchmark.</span></span>

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a><span data-ttu-id="01037-120">Bedömningar av klient organisations nätverk och utvärderingar av Office-plats nätverk</span><span class="sxs-lookup"><span data-stu-id="01037-120">Tenant network assessments and office location network assessments</span></span>

<span data-ttu-id="01037-121">En nätverks utvärdering mäter utformningen av nätverks omkretsen för en Office-plats till Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="01037-121">A network assessment measures the design of the network perimeter of an office location to Microsoft's network.</span></span> <span data-ttu-id="01037-122">Förbättringar av nätverks omkretsen är bäst på varje Office-plats, eller där nätverks anslutningen är aggregerad kan det påverka flera olika platser.</span><span class="sxs-lookup"><span data-stu-id="01037-122">Improvements to the network perimeter is best done at each office location, or where network connectivity is aggregated there may be improvements that impact multiple locations.</span></span>

<span data-ttu-id="01037-123">Vi visar ett utvärderings värde för nätverk för hela Microsoft 365-klienten på sidan för översikt över nätverks prestanda och ett specifikt värde för varje identifierad Office-plats på den platsens sammanfattnings sida.</span><span class="sxs-lookup"><span data-stu-id="01037-123">We show a network assessment value for the whole Microsoft 365 tenant on the network performance overview page and a specific value for each detected office location on that location's summary page.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="01037-124">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="01037-124">Exchange Online</span></span>

<span data-ttu-id="01037-125">För Exchange Online mäts TCP-fördröjning från klient datorn till Exchange-frontend-servern.</span><span class="sxs-lookup"><span data-stu-id="01037-125">For Exchange Online the TCP latency from the client machine to the Exchange front end server is measured.</span></span> <span data-ttu-id="01037-126">Detta kan påverkas av avståndet mellan nätverket och WAN.</span><span class="sxs-lookup"><span data-stu-id="01037-126">This can be impacted by the distance the network travels over the customers LAN and WAN.</span></span> <span data-ttu-id="01037-127">Det kan också påverkas av nätverks mellanliggande enheter eller tjänster som fördröjer anslutningen eller orsakar att paket skickas igen.</span><span class="sxs-lookup"><span data-stu-id="01037-127">It can also be impacted by network intermediary devices or services which delay the connectivity or cause packets to be resent.</span></span>

## <a name="sharepoint-online"></a><span data-ttu-id="01037-128">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="01037-128">SharePoint Online</span></span>

<span data-ttu-id="01037-129">För SharePoint Online mäts nedladdnings hastigheten för en användare till ett dokument.</span><span class="sxs-lookup"><span data-stu-id="01037-129">For SharePoint Online the download speed available for a user to access a document is measured.</span></span> <span data-ttu-id="01037-130">Detta kan påverka bandbredden som är tillgänglig för nätverks kretsar mellan klient datorn och Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="01037-130">This can be impacted by the bandwidth available on network circuits between the client machine and Microsoft's network.</span></span> <span data-ttu-id="01037-131">Det påverkar också ofta nätverks överbelastning som finns i Flask halsar i komplexa nätverks enheter eller i en dåligt räckvidd.</span><span class="sxs-lookup"><span data-stu-id="01037-131">It is also often impacted by network congestion that exists in bottlenecks in complex network devices or in poor coverage Wi-Fi areas.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="01037-132">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01037-132">Microsoft Teams</span></span>

<span data-ttu-id="01037-133">För Microsoft Teams mäts nätverks kvaliteten som UDP-fördröjning, UDP-Darr och förlust av UDP-paket.</span><span class="sxs-lookup"><span data-stu-id="01037-133">For Microsoft Teams the Network quality is measured as UDP latency, UDP jitter, and UDP packet loss.</span></span> <span data-ttu-id="01037-134">UDP används för samtal och konferens ljud-och video anslutnings medie anslutningar för Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="01037-134">UDP is used for call and conferencing audio and video media connectivity for Microsoft Teams.</span></span> <span data-ttu-id="01037-135">Detta kan påverkas av samma faktorer som för fördröjning och nedladdnings hastighet utöver anslutnings luckor i nätverkets UDP-support eftersom UDP är konfigurerat separat för det vanliga TCP-protokollet.</span><span class="sxs-lookup"><span data-stu-id="01037-135">This can be impacted by the same factors as for latency and download speed in addition to connectivity gaps in a network's UDP support since UDP is configured separately to the more common TCP protocol.</span></span>

## <a name="related-topics"></a><span data-ttu-id="01037-136">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="01037-136">Related topics</span></span>

[<span data-ttu-id="01037-137">Rekommendationer för nätverks prestanda i Microsoft 365 Admin Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="01037-137">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="01037-138">Microsoft 365 nätverks prestanda (för hands version)</span><span class="sxs-lookup"><span data-stu-id="01037-138">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="01037-139">Microsoft 365 anslutnings test i M365 administrations Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="01037-139">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="01037-140">Microsoft 365 nätverks anslutningar (för hands version)</span><span class="sxs-lookup"><span data-stu-id="01037-140">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
