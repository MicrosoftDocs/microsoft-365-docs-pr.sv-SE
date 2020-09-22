---
title: Microsoft 365 nätverks anslutningar (för hands version)
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
description: Microsoft 365 nätverks anslutningar (för hands version)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200787"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a><span data-ttu-id="684e9-103">Microsoft 365 nätverks anslutningar (för hands version)</span><span class="sxs-lookup"><span data-stu-id="684e9-103">Microsoft 365 Network Connectivity Location Services (preview)</span></span>

<span data-ttu-id="684e9-104">Administrations centret för Microsoft 365 visar nu **nätverks insikter och prestanda rekommendationer**, som är real tids värden som samlas in från din Microsoft 365-klient organisation och som endast kan visas av administrativa användare i din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="684e9-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics collected from your Microsoft 365 tenant and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="684e9-105">Organisatoriska nätverks anslutningar är utformat per Office-plats via ett nätverks utgångs läge till Internet.</span><span class="sxs-lookup"><span data-stu-id="684e9-105">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="684e9-106">Microsoft 365-klienten använder den vägen och sedan via Internet till Microsofts tjänst front dörr Server.</span><span class="sxs-lookup"><span data-stu-id="684e9-106">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="684e9-107">Att identifiera Office-platsen är viktig för att kunna visa dessa nätverks insikter.</span><span class="sxs-lookup"><span data-stu-id="684e9-107">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="684e9-108">Plats i nätverks mått</span><span class="sxs-lookup"><span data-stu-id="684e9-108">Location in network measurements</span></span>

<span data-ttu-id="684e9-109">En organisations administratör kan välja plats att ingå i nätverks måtten som används av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="684e9-109">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="684e9-110">Detta aktiverar automatisk identifiering av staden där varje kontor finns.</span><span class="sxs-lookup"><span data-stu-id="684e9-110">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="684e9-111">Plats informationen är inte exakt och är Obfuscated till 300 m och kategoriseras efter ort.</span><span class="sxs-lookup"><span data-stu-id="684e9-111">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="684e9-112">När platsen sparas på en Windows-enhet kommer den att visa en ikon för **användning i** verktyget och administratören kanske vill meddela användarna om det.</span><span class="sxs-lookup"><span data-stu-id="684e9-112">At the time when location is captured on a Windows device it will show a **Location In-Use** icon in the tool tray and administrators may want to notify users of this.</span></span> <span data-ttu-id="684e9-113">Med den här behandlingen behandlas platsen som organisationens Office-plats och inte till platsen för en person eller enhet.</span><span class="sxs-lookup"><span data-stu-id="684e9-113">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="684e9-114">Nätverks insikter kan visas på dessa upptäckta Office-städer.</span><span class="sxs-lookup"><span data-stu-id="684e9-114">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="684e9-115">Om du vill ha större rekommendationer kan administratören ange specifika Office-adresser och nätverks insikter aggregeras till dem i stället.</span><span class="sxs-lookup"><span data-stu-id="684e9-115">If greater accuracy of recommendations is desired, an administrator can enter specific office location addresses and the network insights will be aggregated to those instead.</span></span> <span data-ttu-id="684e9-116">Office-platserna kan inte aggregeras mer nära 300 meter.</span><span class="sxs-lookup"><span data-stu-id="684e9-116">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="684e9-117">Plats i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="684e9-117">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="684e9-118">I Microsoft 365 Admin Center används kart kart kontroller för att visa var organisationens Office-platser finns och för att Visa nätverkstopologi för en vald Office-plats.</span><span class="sxs-lookup"><span data-stu-id="684e9-118">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are and to show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="684e9-119">När en administratör lägger till specifik adress information för Office-platser används Bing Maps också för att föreslå adresser för att under lätta data inmatningen.</span><span class="sxs-lookup"><span data-stu-id="684e9-119">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="684e9-120">Användnings villkor</span><span class="sxs-lookup"><span data-stu-id="684e9-120">Terms of Use</span></span>

<span data-ttu-id="684e9-121">Allt innehåll som tillhandahålls via Bing Maps, inklusive koder, kan endast användas inom den produkt som innehåller innehållet.</span><span class="sxs-lookup"><span data-stu-id="684e9-121">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="684e9-122">Användning av plats tjänster för administrations Center för Microsoft 365, som drivs av Bing Maps, regleras av _slut användar användnings villkoren för Bing Maps_ <https://go.microsoft.com/?linkid=9710837> och _Microsofts sekretess policy_ finns på <https://go.microsoft.com/fwlink/?LinkID=248686.></span><span class="sxs-lookup"><span data-stu-id="684e9-122">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the _Microsoft Privacy Statement_ available at <https://go.microsoft.com/fwlink/?LinkID=248686.></span></span>

<span data-ttu-id="684e9-123">Den här funktionen, som tillhandahålls genom Bing Maps, stöds också av denna **teknik**.</span><span class="sxs-lookup"><span data-stu-id="684e9-123">This feature, provided through Bing Maps, is also supported by **Here Technologies**.</span></span> <span data-ttu-id="684e9-124">Så här fungerar Bing Maps-tjänster som tillhandahålls av denna teknik regleras av den _här teknik tjänst villkoren_ på <https://legal.here.com/en-gb/terms> .</span><span class="sxs-lookup"><span data-stu-id="684e9-124">How Bing Maps leverages location services provided by Here Technologies is governed by the _Here Technologies Service Terms_ available at <https://legal.here.com/en-gb/terms>.</span></span>

## <a name="related-topics"></a><span data-ttu-id="684e9-125">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="684e9-125">Related topics</span></span>

[<span data-ttu-id="684e9-126">Nätverks anslutning i Microsoft 365 Admin Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="684e9-126">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="684e9-127">Microsoft 365 nätverks prestanda (för hands version)</span><span class="sxs-lookup"><span data-stu-id="684e9-127">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="684e9-128">Microsoft 365 Network Assessment (för hands version)</span><span class="sxs-lookup"><span data-stu-id="684e9-128">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="684e9-129">Microsoft 365 anslutnings test i M365 administrations Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="684e9-129">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
