---
title: Microsoft 365 Nätverksplatstjänster
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Nätverksplatstjänster
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470454"
---
# <a name="microsoft-365-network-connectivity-location-services"></a><span data-ttu-id="26e6d-103">Microsoft 365 Nätverksplatstjänster</span><span class="sxs-lookup"><span data-stu-id="26e6d-103">Microsoft 365 Network Connectivity Location Services</span></span>

<span data-ttu-id="26e6d-104">I Microsoft 365 Administrationscenter visas nu Nätverksinsikter och prestandarekommendationer, som är prestandamätvärden i realtid som samlas in från Microsoft 365 klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="26e6d-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics that are collected from your Microsoft 365 tenant.</span></span> <span data-ttu-id="26e6d-105">De här måtten kan endast visas av administrativa användare i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="26e6d-105">These metrics can be viewed only by administrative users in your tenant.</span></span> <span data-ttu-id="26e6d-106">Organisationsnätverksanslutningen är utformad per kontorsplats genom en utgående nätverksplats till Internet.</span><span class="sxs-lookup"><span data-stu-id="26e6d-106">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="26e6d-107">Microsoft 365 en klientanslutning använder den vägen och sedan via Internet till Microsofts serviceservrar.</span><span class="sxs-lookup"><span data-stu-id="26e6d-107">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="26e6d-108">Att identifiera kontor är avgörande för att kunna visa dessa nätverksinsikter.</span><span class="sxs-lookup"><span data-stu-id="26e6d-108">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="26e6d-109">Plats i nätverksmått</span><span class="sxs-lookup"><span data-stu-id="26e6d-109">Location in network measurements</span></span>

<span data-ttu-id="26e6d-110">Organisationens administratör kan registrera sig för att inkludera plats i nätverksmåtten som används av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="26e6d-110">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="26e6d-111">På så sätt kan du automatiskt identifiera den stad där varje kontor ligger.</span><span class="sxs-lookup"><span data-stu-id="26e6d-111">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="26e6d-112">Platsinformationen är inte exakt och är obfuscated till 300m och kategoriseras efter ort.</span><span class="sxs-lookup"><span data-stu-id="26e6d-112">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="26e6d-113">Vid den tidpunkt då platsen fångas på en Windows enhet  visas ikonen Plats i användning i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="26e6d-113">At the time when location is captured on a Windows device, the device will show a **Location In-Use** icon in the tool tray.</span></span> <span data-ttu-id="26e6d-114">Administratörer kan vilja meddela användarna om ikonens utseende.</span><span class="sxs-lookup"><span data-stu-id="26e6d-114">Administrators may want to notify users of the appearance of this icon.</span></span> <span data-ttu-id="26e6d-115">Med denna bearbetning behandlas platsen som organisationens kontorsplats och inte som plats för en person eller en enhet.</span><span class="sxs-lookup"><span data-stu-id="26e6d-115">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="26e6d-116">Nätverksinsikter kan visas i dessa identifierade städer på kontor.</span><span class="sxs-lookup"><span data-stu-id="26e6d-116">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="26e6d-117">Om du vill ha högre precision i rekommendationerna kan du ange specifika kontorsadresser.</span><span class="sxs-lookup"><span data-stu-id="26e6d-117">If you want higher accuracy in the recommendations, you can enter specific office location addresses.</span></span> <span data-ttu-id="26e6d-118">I stället aggregeras nätverksinsikter till de platserna.</span><span class="sxs-lookup"><span data-stu-id="26e6d-118">The network insights will be aggregated to those locations instead.</span></span> <span data-ttu-id="26e6d-119">Office kan inte aggregeras närmare än 300 meter.</span><span class="sxs-lookup"><span data-stu-id="26e6d-119">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="26e6d-120">Plats i Microsoft 365 Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="26e6d-120">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="26e6d-121">I Microsoft 365 administrationscentret används Bing för att visa var organisationens kontor finns.</span><span class="sxs-lookup"><span data-stu-id="26e6d-121">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are.</span></span> <span data-ttu-id="26e6d-122">Kontrollerna visar även nätverks perimetertopologi för en vald kontorsplats.</span><span class="sxs-lookup"><span data-stu-id="26e6d-122">The controls also show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="26e6d-123">När en administratör lägger till specifik adressinformation för kontorsplatser används Bing-kartor för att föreslå adresser för att göra det lättare att lägga till data.</span><span class="sxs-lookup"><span data-stu-id="26e6d-123">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="26e6d-124">Användningsvillkor</span><span class="sxs-lookup"><span data-stu-id="26e6d-124">Terms of Use</span></span>

<span data-ttu-id="26e6d-125">Allt innehåll som Bing-kartor via e-post, inklusive geokoder, kan endast användas i den produkt som innehållet tillhandahålls från.</span><span class="sxs-lookup"><span data-stu-id="26e6d-125">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="26e6d-126">Kundens användning av platstjänster i Microsoft 365 Admin Center, som drivs av Bing-kartor, styrs av de användningsvillkor _för Bing-kartor End-User_ som finns tillgängliga på och <https://go.microsoft.com/?linkid=9710837> [Microsofts sekretesspolicy.](https://go.microsoft.com/fwlink/?LinkID=248686)</span><span class="sxs-lookup"><span data-stu-id="26e6d-126">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End-User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkID=248686).</span></span>

<span data-ttu-id="26e6d-127">Den här funktionen, som Bing-kartor, stöds också av **TomTom.**</span><span class="sxs-lookup"><span data-stu-id="26e6d-127">This feature, provided through Bing Maps, is also supported by **TomTom**.</span></span> <span data-ttu-id="26e6d-128">Mer information om TomToms produkter och tjänster finns på [https://www.tomtom.com/legal](https://www.tomtom.com/legal) .</span><span class="sxs-lookup"><span data-stu-id="26e6d-128">More information about TomTom's products and services may be found at [https://www.tomtom.com/legal](https://www.tomtom.com/legal).</span></span>

## <a name="related-topics"></a><span data-ttu-id="26e6d-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="26e6d-129">Related topics</span></span>

[<span data-ttu-id="26e6d-130">Nätverksanslutningen i Microsoft 365 (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="26e6d-130">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="26e6d-131">Microsoft 365 nätverksprestandainsikter (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="26e6d-131">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="26e6d-132">Microsoft 365 nätverksutvärdering (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="26e6d-132">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="26e6d-133">Microsoft 365 anslutningstest i Microsoft 365 (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="26e6d-133">Microsoft 365 connectivity test in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
