---
title: Konfigurera nätverket för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Hitta länkar till artiklar med information som hjälper dig att konfigurera nätverket för Microsoft 365, inklusive en översikt över nätverksanslutningen och en lista över slutpunkter.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694376"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="bb836-103">Konfigurera nätverket för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb836-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="bb836-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bb836-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bb836-105">En viktig del av Microsoft 365 är att se till att nätverks- och Internetanslutningar är konfigurerade för optimerad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="bb836-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="bb836-106">Att konfigurera ditt lokala nätverk för att få tillgång till ett globalt distribuerat SaaS-moln (programvara som en tjänst) skiljer sig från ett traditionellt nätverk som är optimerat för trafik till lokala datacenter och en central Internetanslutning.</span><span class="sxs-lookup"><span data-stu-id="bb836-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="bb836-107">Använd de här artiklarna för att förstå de viktigaste skillnaderna och för att ändra dina edge-enheter, klientdatorer och lokala nätverk för att få den bästa prestandan för dina lokala användare.</span><span class="sxs-lookup"><span data-stu-id="bb836-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="bb836-108">Så här Microsoft 365 nätverk fungerar</span><span class="sxs-lookup"><span data-stu-id="bb836-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="bb836-109">I de här artiklarna finns en översikt över anslutning för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="bb836-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="bb836-110">Översikt för Microsoft 365 nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="bb836-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="bb836-111">Microsoft 365 principer för nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="bb836-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="bb836-112">Utvärdera Microsoft 365 nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="bb836-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="bb836-113">Råd om förbättring av prestanda finns i [Nätverksplanering och prestandajustering för Microsoft 365.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="bb836-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="bb836-114">Stöd Microsoft 365 nätverk som leverantör av nätverksutrustning</span><span class="sxs-lookup"><span data-stu-id="bb836-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="bb836-115">Om du är leverantör av nätverksutrustning ansluter du till [Office 365 Nätverkspartnerprogram](microsoft-365-networking-partner-program.md).</span><span class="sxs-lookup"><span data-stu-id="bb836-115">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="bb836-116">Registrera dig för programmet för att bygga Office 365 principer för nätverksanslutning i dina produkter och lösningar.</span><span class="sxs-lookup"><span data-stu-id="bb836-116">Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="bb836-117">Office 365-slutpunkter</span><span class="sxs-lookup"><span data-stu-id="bb836-117">Office 365 endpoints</span></span>

<span data-ttu-id="bb836-118">Slutpunkter är en uppsättning IP-måladresser, DNS-domännamn och URL:er för Office 365 trafik på Internet.</span><span class="sxs-lookup"><span data-stu-id="bb836-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="bb836-119">För att optimera prestanda Office 365 av molnbaserade tjänster behöver vissa slutpunkter särskild hantering av dina klientwebbläsare och enheter i ditt gränsnätverk.</span><span class="sxs-lookup"><span data-stu-id="bb836-119">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network.</span></span> <span data-ttu-id="bb836-120">Dessa enheter omfattar brandväggar, SSL-avbrott, inspektera och paketinspektionsenheter samt system för skydd mot dataförlust.</span><span class="sxs-lookup"><span data-stu-id="bb836-120">These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="bb836-121">Mer [information Office 365 hantera slutpunkter.](managing-office-365-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="bb836-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="bb836-122">Det finns för närvarande fem Office 365 moln.</span><span class="sxs-lookup"><span data-stu-id="bb836-122">There are currently five different Office 365 clouds.</span></span> <span data-ttu-id="bb836-123">Den här tabellen tar dig till listan med slutpunkter för var och en.</span><span class="sxs-lookup"><span data-stu-id="bb836-123">This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="bb836-124">Slutpunkter</span><span class="sxs-lookup"><span data-stu-id="bb836-124">Endpoints</span></span> | <span data-ttu-id="bb836-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bb836-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="bb836-126">Globala slutpunkter</span><span class="sxs-lookup"><span data-stu-id="bb836-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="bb836-127">Slutpunkterna för globala Office 365 prenumerationer, som omfattar USA och Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="bb836-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="bb836-128">Slutpunkter för Myndighetsskydd i USA</span><span class="sxs-lookup"><span data-stu-id="bb836-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="bb836-129">Slutpunkterna för United States Department of Defense-prenumerationer (DoD).</span><span class="sxs-lookup"><span data-stu-id="bb836-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="bb836-130">Slutpunkter för Myndighetsskydd i USA (GCC High)</span><span class="sxs-lookup"><span data-stu-id="bb836-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="bb836-131">Slutpunkterna för prenumerationer med Government Community Cloud Hög (GCC Hög).</span><span class="sxs-lookup"><span data-stu-id="bb836-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="bb836-132">Office 365 som drivs av 21Vianet – Slutpunkter</span><span class="sxs-lookup"><span data-stu-id="bb836-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="bb836-133">Slutpunkterna för Office 365 som drivs av 21Vianet, som är utformade för att tillgodose behoven Office 365 i Kina.</span><span class="sxs-lookup"><span data-stu-id="bb836-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="bb836-134">Slutpunkter för Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="bb836-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="bb836-135">Slutpunkterna för ett separat moln i Europa för de kunder i Tyskland, Europeiska unionen (EU) och EES (European Free Trade Association) som regleras mest.</span><span class="sxs-lookup"><span data-stu-id="bb836-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="bb836-136">Information om hur du automatiserar hur du hämtar den senaste listan med slutpunkter för Office 365-molnet finns [i Office 365 IP-adress och URL-webbtjänst.](microsoft-365-ip-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="bb836-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="bb836-137">Fler slutpunkter finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="bb836-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="bb836-138">Ytterligare slutpunkter som inte ingår i webbtjänsten</span><span class="sxs-lookup"><span data-stu-id="bb836-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="bb836-139">Nätverksbegäranden i Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="bb836-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="bb836-140">Ytterligare ämnen för Microsoft 365 nätverk</span><span class="sxs-lookup"><span data-stu-id="bb836-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="bb836-141">Läs följande artiklar för specialiserade ämnen Microsoft 365 nätverk:</span><span class="sxs-lookup"><span data-stu-id="bb836-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="bb836-142">Nätverk för innehållsleverans</span><span class="sxs-lookup"><span data-stu-id="bb836-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="bb836-143">IPv6-stöd i Office 365-tjänster</span><span class="sxs-lookup"><span data-stu-id="bb836-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="bb836-144">Stöd för NAT med Office 365</span><span class="sxs-lookup"><span data-stu-id="bb836-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="bb836-145">ExpressRoute för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb836-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="bb836-146">Läs följande artiklar för information om hur du använder ExpressRoute för Office 365 trafik:</span><span class="sxs-lookup"><span data-stu-id="bb836-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="bb836-147">Azure ExpressRoute för Office 365</span><span class="sxs-lookup"><span data-stu-id="bb836-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="bb836-148">Implementera ExpressRoute för Office 365</span><span class="sxs-lookup"><span data-stu-id="bb836-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="bb836-149">Nätverksplanering med ExpressRoute för Office 365</span><span class="sxs-lookup"><span data-stu-id="bb836-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="bb836-150">Dirigering med ExpressRoute för Office 365</span><span class="sxs-lookup"><span data-stu-id="bb836-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
