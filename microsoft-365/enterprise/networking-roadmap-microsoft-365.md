---
title: Nätverksöversikt för Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Översikten för implementering av Microsoft 365-nätverk.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923558"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="5409c-103">Nätverksöversikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5409c-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="5409c-104">Microsoft 365 för företag innehåller molntjänster för samarbete och produktivitet, Microsoft Intune och många identitets- och säkerhetstjänster i Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="5409c-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="5409c-105">Alla dessa molnbaserade tjänster kräver säkerhet, prestanda och tillförlitlighet för anslutningar från klientenheter via Internet eller dedikerade kretsar.</span><span class="sxs-lookup"><span data-stu-id="5409c-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="5409c-106">Om du vill ha de här tjänsterna och göra dem tillgängliga för kunder över hela världen har Microsoft utformat en nätverksinfrastruktur som betonar prestanda och integrering.</span><span class="sxs-lookup"><span data-stu-id="5409c-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="5409c-107">En viktig del av din Microsoft 365-registrering är att säkerställa att dina nätverks- och Internetanslutningar är konfigurerade för optimerad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="5409c-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="5409c-108">Att konfigurera ditt lokala nätverk för att få tillgång till ett globalt distribuerat SaaS-moln (programvara som en tjänst) skiljer sig från ett traditionellt nätverk som är optimerat för trafik till lokala datacenter och en central Internetanslutning.</span><span class="sxs-lookup"><span data-stu-id="5409c-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="5409c-109">Använd de här artiklarna för att förstå de viktigaste skillnaderna och för att ändra dina edge-enheter, klientdatorer och lokala nätverk för att få den bästa prestandan för dina lokala användare.</span><span class="sxs-lookup"><span data-stu-id="5409c-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="5409c-110">Planera</span><span class="sxs-lookup"><span data-stu-id="5409c-110">Plan</span></span>

<span data-ttu-id="5409c-111">I planeringsfasen av din nätverksimplementering:</span><span class="sxs-lookup"><span data-stu-id="5409c-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="5409c-112">Förstå hur Microsoft 365-nätverk fungerar</span><span class="sxs-lookup"><span data-stu-id="5409c-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="5409c-113">Utvärdera den nuvarande nätverksanslutningen</span><span class="sxs-lookup"><span data-stu-id="5409c-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="5409c-114">Avgöra om ExpressRoute är rätt för din organisation</span><span class="sxs-lookup"><span data-stu-id="5409c-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="5409c-115">Planera för nätverksenheter</span><span class="sxs-lookup"><span data-stu-id="5409c-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="5409c-116">Konfigurera nätverket för migrering</span><span class="sxs-lookup"><span data-stu-id="5409c-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="5409c-117">Distribuera</span><span class="sxs-lookup"><span data-stu-id="5409c-117">Deploy</span></span>

<span data-ttu-id="5409c-118">I distributionsfasen av din nätverksimplementering:</span><span class="sxs-lookup"><span data-stu-id="5409c-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="5409c-119">Se till att företagsnätverket är optimerat för Microsoft 365-anslutningar</span><span class="sxs-lookup"><span data-stu-id="5409c-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="5409c-120">Lägga till DNS-domänerna för din organisation</span><span class="sxs-lookup"><span data-stu-id="5409c-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="5409c-121">Optimera anslutningen till Microsoft 365-slutpunkter</span><span class="sxs-lookup"><span data-stu-id="5409c-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="5409c-122">Optimera anslutningen för fjärranslutna medarbetare</span><span class="sxs-lookup"><span data-stu-id="5409c-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="5409c-123">Om det behövs [konfigurerar du ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="5409c-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="5409c-124">Hantera</span><span class="sxs-lookup"><span data-stu-id="5409c-124">Manage</span></span>

<span data-ttu-id="5409c-125">I hanteringsfasen av din nätverksimplementering:</span><span class="sxs-lookup"><span data-stu-id="5409c-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="5409c-126">Kontrollera att dina nätverksenheter använder de senaste Office 365-slutpunkterna</span><span class="sxs-lookup"><span data-stu-id="5409c-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="5409c-127">Övervaka och justera nätverksprestanda</span><span class="sxs-lookup"><span data-stu-id="5409c-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="5409c-128">Övervaka ExpressRoute-anslutningar</span><span class="sxs-lookup"><span data-stu-id="5409c-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="5409c-129">Leverantörer av nätverksutrustning</span><span class="sxs-lookup"><span data-stu-id="5409c-129">Network equipment vendors</span></span>

<span data-ttu-id="5409c-130">Om du är leverantör av nätverksutrustning kan du gå med [i Microsoft 365 Networking Partner Program.](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="5409c-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="5409c-131">Registrera dig för programmet och skapa nätverksanslutningsprinciper för Microsoft 365 i dina produkter och lösningar.</span><span class="sxs-lookup"><span data-stu-id="5409c-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="5409c-132">Hur Contoso nätverkade för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5409c-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="5409c-133">Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [optimerade sina nätverksenheter och Internet-anslutningar](contoso-networking.md) för Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="5409c-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="5409c-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5409c-135">Next step</span></span>

<span data-ttu-id="5409c-136">Börja din nätverksplanering med [översikten över Microsoft 365-nätverksanslutningar.](microsoft-365-networking-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5409c-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>