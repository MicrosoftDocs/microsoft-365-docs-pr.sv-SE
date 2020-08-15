---
title: Konfigurera ditt nätverk för Microsoft 365
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
description: Hitta länkar till artiklar med information som hjälper dig att konfigurera ditt nätverk för Microsoft 365, inklusive en översikt över nätverks anslutningen och en lista med slut punkter.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694376"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="fe1c0-103">Konfigurera ditt nätverk för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="fe1c0-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fe1c0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fe1c0-105">En viktig del av din Microsoft 365-registrering är att kontrol lera att nätverks-och Internet anslutningarna är konfigurerade för optimerad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="fe1c0-106">Att konfigurera det lokala nätverket för att få åtkomst till ett globalt distribuerat program som-som-as-service-moln är inte samma som ett traditionellt nätverk som är optimerat för trafik till lokala data Center och en central Internet anslutning.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="fe1c0-107">Använd dessa artiklar för att förstå de viktigaste skillnaderna och för att ändra dina gräns enheter, klient datorer och lokala nätverk för att få bästa möjliga prestanda för dina lokala användare.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="fe1c0-108">Så fungerar Microsoft 365-nätverk</span><span class="sxs-lookup"><span data-stu-id="fe1c0-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="fe1c0-109">De här artiklarna visar en översikt över anslutnings barhet för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="fe1c0-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="fe1c0-110">Översikt över Microsoft 365-nätverk</span><span class="sxs-lookup"><span data-stu-id="fe1c0-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="fe1c0-111">Principer för nätverks åtkomst för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="fe1c0-112">Utvärderar Microsoft 365-nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="fe1c0-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="fe1c0-113">Råd om hur du förbättrar prestanda finns i [nätverks planering och prestanda justering för Microsoft 365](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="fe1c0-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="fe1c0-114">Hantera Microsoft 365-nätverk som nätverks utrustnings leverantör</span><span class="sxs-lookup"><span data-stu-id="fe1c0-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="fe1c0-115">Om du är nätverks utrustning kan du gå med i [Office 365 Network partner-programmet](microsoft-365-networking-partner-program.md).</span><span class="sxs-lookup"><span data-stu-id="fe1c0-115">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="fe1c0-116">Registrera programmet för att skapa principer för Office 365-nätverks anslutningar till dina produkter och lösningar.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-116">Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="fe1c0-117">Slut punkter för Office 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-117">Office 365 endpoints</span></span>

<span data-ttu-id="fe1c0-118">Slut punkter är den uppsättning mål-IP-adresser, DNS-domännamn och URL: er för Office 365-trafik på Internet.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="fe1c0-119">För att optimera prestanda i Office 365-molnbaserade tjänster behöver vissa slut punkter särskild hantering av dina klient webbläsare och enheter i ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-119">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network.</span></span> <span data-ttu-id="fe1c0-120">Dessa enheter inkluderar brand väggar, SSL-avbrotts-och inspektions enheter samt system för skydd mot data förlust.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-120">These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="fe1c0-121">Mer information finns i [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) .</span><span class="sxs-lookup"><span data-stu-id="fe1c0-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="fe1c0-122">Det finns fem olika Office 365-moln.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-122">There are currently five different Office 365 clouds.</span></span> <span data-ttu-id="fe1c0-123">I den här tabellen går du till listan med slut punkter för var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-123">This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="fe1c0-124">Slut punkter</span><span class="sxs-lookup"><span data-stu-id="fe1c0-124">Endpoints</span></span> | <span data-ttu-id="fe1c0-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fe1c0-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="fe1c0-126">Slut punkter för hela världen</span><span class="sxs-lookup"><span data-stu-id="fe1c0-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="fe1c0-127">Slut punkter för Office 365-prenumerationer, som omfattar Förenta staternas regerings community-moln (GCC).</span><span class="sxs-lookup"><span data-stu-id="fe1c0-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="fe1c0-128">Amerikanska myndigheters DoD slut punkter</span><span class="sxs-lookup"><span data-stu-id="fe1c0-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="fe1c0-129">Slut punkter för abonnemang med DoD för Förenta staternas försvar (departementet).</span><span class="sxs-lookup"><span data-stu-id="fe1c0-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="fe1c0-130">Amerikanska myndigheters GCC höga slut punkter</span><span class="sxs-lookup"><span data-stu-id="fe1c0-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="fe1c0-131">Slut punkterna för de samhälls omfattande community-molnen (GCC hög).</span><span class="sxs-lookup"><span data-stu-id="fe1c0-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="fe1c0-132">Office 365 som drivs av 21Vianet-slutpunkter</span><span class="sxs-lookup"><span data-stu-id="fe1c0-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="fe1c0-133">Slut punkter för Office 365 som drivs av 21Vianet, som är avsedda att möta behoven hos Office 365 i Kina.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="fe1c0-134">Office 365 Germany-slut punkter</span><span class="sxs-lookup"><span data-stu-id="fe1c0-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="fe1c0-135">Slut punkterna för ett separat moln i Europa för de mest reglerade kunderna i Tyskland, Europeiska unionen (EU) och Europeiska fri handels associationen (EFTA).</span><span class="sxs-lookup"><span data-stu-id="fe1c0-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="fe1c0-136">Information om hur du hämtar den senaste listan över slut punkter för Office 365-molnet finns i [office 365 IP Address and URL Web Service](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="fe1c0-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="fe1c0-137">Ytterligare slut punkter finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="fe1c0-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="fe1c0-138">Ytterligare slut punkter som inte ingår i webb tjänsten</span><span class="sxs-lookup"><span data-stu-id="fe1c0-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="fe1c0-139">Nätverks begär anden i Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="fe1c0-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="fe1c0-140">Ytterligare avsnitt för Microsoft 365-nätverk</span><span class="sxs-lookup"><span data-stu-id="fe1c0-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="fe1c0-141">De här artiklarna innehåller specialiserade ämnen i Microsoft 365-nätverk:</span><span class="sxs-lookup"><span data-stu-id="fe1c0-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="fe1c0-142">Nätverk för innehålls leverans</span><span class="sxs-lookup"><span data-stu-id="fe1c0-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="fe1c0-143">IPv6-stöd i Office 365-tjänster</span><span class="sxs-lookup"><span data-stu-id="fe1c0-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="fe1c0-144">Stöd för NAT med Office 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="fe1c0-145">ExpressRoute för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="fe1c0-146">Se de här artiklarna för att få information om hur du använder ExpressRoute för Office 365-trafik:</span><span class="sxs-lookup"><span data-stu-id="fe1c0-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="fe1c0-147">Azure ExpressRoute för Office 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="fe1c0-148">Implementera ExpressRoute för Office 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="fe1c0-149">Nätverks planering med ExpressRoute för Office 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="fe1c0-150">Routning med ExpressRoute för Office 365</span><span class="sxs-lookup"><span data-stu-id="fe1c0-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
