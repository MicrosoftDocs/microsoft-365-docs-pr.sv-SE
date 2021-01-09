---
title: Nätverks översikt för Microsoft 365
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
ms.openlocfilehash: 2962adf7bdca35d06672696471e0932fd1a7b09c
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787757"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="1ee36-103">Nätverks översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1ee36-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="1ee36-104">Microsoft 365 för företag innehåller samarbets-och produktivitets moln tjänster, Microsoft Intune och många identitets-och säkerhets tjänster i Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="1ee36-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="1ee36-105">Alla dessa molnbaserade tjänster kräver säkerhet, prestanda och tillförlitlighet för anslutningar från klientenheter via Internet eller dedikerade kretsar.</span><span class="sxs-lookup"><span data-stu-id="1ee36-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="1ee36-106">Om du vill ha de här tjänsterna och göra dem tillgängliga för kunder över hela världen har Microsoft utformat en nätverksinfrastruktur som betonar prestanda och integrering.</span><span class="sxs-lookup"><span data-stu-id="1ee36-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="1ee36-107">En viktig del av din Microsoft 365-registrering är att kontrol lera att nätverks-och Internet anslutningarna är konfigurerade för optimerad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="1ee36-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="1ee36-108">Att konfigurera det lokala nätverket för att få åtkomst till ett globalt distribuerat program som-som-as-service-moln är inte samma som ett traditionellt nätverk som är optimerat för trafik till lokala data Center och en central Internet anslutning.</span><span class="sxs-lookup"><span data-stu-id="1ee36-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="1ee36-109">Använd dessa artiklar för att förstå de viktigaste skillnaderna och för att ändra dina gräns enheter, klient datorer och lokala nätverk för att få bästa möjliga prestanda för dina lokala användare.</span><span class="sxs-lookup"><span data-stu-id="1ee36-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="1ee36-110">Planera</span><span class="sxs-lookup"><span data-stu-id="1ee36-110">Plan</span></span>

<span data-ttu-id="1ee36-111">Under planerings fasen av nätverks implementeringen:</span><span class="sxs-lookup"><span data-stu-id="1ee36-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="1ee36-112">Förstå hur Microsoft 365-nätverk fungerar</span><span class="sxs-lookup"><span data-stu-id="1ee36-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="1ee36-113">Bedöma din aktuella nätverks anslutning</span><span class="sxs-lookup"><span data-stu-id="1ee36-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="1ee36-114">Avgöra om ExpressRoute passar din organisation</span><span class="sxs-lookup"><span data-stu-id="1ee36-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="1ee36-115">Planera för nätverks enheter</span><span class="sxs-lookup"><span data-stu-id="1ee36-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="1ee36-116">Konfigurera nätverks inställningar för migrering</span><span class="sxs-lookup"><span data-stu-id="1ee36-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="1ee36-117">Distribuera</span><span class="sxs-lookup"><span data-stu-id="1ee36-117">Deploy</span></span>

<span data-ttu-id="1ee36-118">I distributions fasen av nätverks implementeringen:</span><span class="sxs-lookup"><span data-stu-id="1ee36-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="1ee36-119">Kontrol lera att ditt företags nätverk är optimerat för Microsoft 365-anslutning</span><span class="sxs-lookup"><span data-stu-id="1ee36-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="1ee36-120">Lägga till DNS-domäner för din organisation</span><span class="sxs-lookup"><span data-stu-id="1ee36-120">Add the DNS domains for your organization</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [<span data-ttu-id="1ee36-121">Optimera anslutningen till Microsoft 365-slutpunkter</span><span class="sxs-lookup"><span data-stu-id="1ee36-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="1ee36-122">Optimera anslutningen för fjärranställda</span><span class="sxs-lookup"><span data-stu-id="1ee36-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="1ee36-123">Om det behövs [konfigurerar du ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="1ee36-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="1ee36-124">Hantera</span><span class="sxs-lookup"><span data-stu-id="1ee36-124">Manage</span></span>

<span data-ttu-id="1ee36-125">I hanterings fasen av nätverks implementeringen:</span><span class="sxs-lookup"><span data-stu-id="1ee36-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="1ee36-126">Kontrol lera att dina nätverks enheter använder de senaste Office 365-slutpunkterna</span><span class="sxs-lookup"><span data-stu-id="1ee36-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="1ee36-127">Övervaka och justera nätverks prestanda</span><span class="sxs-lookup"><span data-stu-id="1ee36-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="1ee36-128">Övervaka dina ExpressRoute-anslutningar</span><span class="sxs-lookup"><span data-stu-id="1ee36-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="1ee36-129">Leverantörer av nätverks utrustning</span><span class="sxs-lookup"><span data-stu-id="1ee36-129">Network equipment vendors</span></span>

<span data-ttu-id="1ee36-130">Om du är nätverks utrustning kan du gå med i [Microsoft 365 Network partner-programmet](microsoft-365-networking-partner-program.md).</span><span class="sxs-lookup"><span data-stu-id="1ee36-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="1ee36-131">Registrera dig för att skapa Microsoft 365-nätverks anslutnings principer till produkterna och lösningarna.</span><span class="sxs-lookup"><span data-stu-id="1ee36-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="1ee36-132">Så här fungerade contoso för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1ee36-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="1ee36-133">Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [optimerade sina nätverksenheter och Internet-anslutningar](contoso-networking.md) för Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="1ee36-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="1ee36-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1ee36-135">Next step</span></span>

<span data-ttu-id="1ee36-136">Starta Nätverks planering med [Översikt över Microsoft 365-nätverksanslutningen](microsoft-365-networking-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1ee36-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>
