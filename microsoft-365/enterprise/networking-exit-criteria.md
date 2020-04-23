---
title: 'Fas 1: Avslutsvillkor för nätverksinfrastruktur'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Kontrollera att din konfiguration uppfyller Microsoft 365 Enterprise-villkoren för nätverksinfrastruktur.
ms.openlocfilehash: 6d9133fa6f3c993efe88ea53b412b9a272c1b98b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631495"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="c6817-103">Fas 1: Avslutsvillkor för nätverksinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="c6817-103">Phase 1: Networking infrastructure exit criteria</span></span>

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="c6817-105">Kontrollera att nätverksinfrastrukturen uppfyller följande krav och att du har övervägt de som är valfria.</span><span class="sxs-lookup"><span data-stu-id="c6817-105">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="c6817-106">Obligatoriskt: Ditt nätverk är redo för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6817-106">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="c6817-107">Dina kontor har tillräcklig internetbandbredd för Microsoft 365-trafik, t. ex. installationer och uppdateringar av Office 365, Microsoft Intune och Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c6817-107">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates.</span></span>
- <span data-ttu-id="c6817-108">Ditt nätverk är mappat till en [referensarkitektur för Microsoft 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span><span class="sxs-lookup"><span data-stu-id="c6817-108">Your overall network maps to an [Microsoft 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="c6817-109">Din nätverksändringar har övervakats och testats och uppfyller dina krav gällande trafikfördröjning.</span><span class="sxs-lookup"><span data-stu-id="c6817-109">Your network changes have been piloted and tested and meet with your traffic latency requirements.</span></span>

<span data-ttu-id="c6817-110">Vid behov kan [Steg 1](networking-provide-bandwidth-cloud-services.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="c6817-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="c6817-111">Obligatoriskt: De lokala kontoren har lokala internetanslutningar och namnmatchning</span><span class="sxs-lookup"><span data-stu-id="c6817-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="c6817-112">Du har konfigurerat varje lokalt kontor med internetåtkomst via en lokal internetleverantör vars DNS-servrar använder en lokal, publik IP-adress som identifierar deras plats på internet.</span><span class="sxs-lookup"><span data-stu-id="c6817-112">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet.</span></span> <span data-ttu-id="c6817-113">Detta säkerställer bästa möjliga prestanda för användare av Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="c6817-113">This ensures the best possible performance for users who access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="c6817-114">Om du inte använder en lokal internetleverantör för varje filial kan prestandan bli lidande då nätverkstrafiken måste korsa företagets stamnät, eller också hanteras dataförfrågningar av fjärrservrar.</span><span class="sxs-lookup"><span data-stu-id="c6817-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c6817-115">Så testar man</span><span class="sxs-lookup"><span data-stu-id="c6817-115">How to test</span></span>
<span data-ttu-id="c6817-116">Använd ett verktyg eller en webbplats från en enhet i det kontoret för att avgöra den publika IP-adress som proxyservern använder.</span><span class="sxs-lookup"><span data-stu-id="c6817-116">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using.</span></span> <span data-ttu-id="c6817-117">Använd till exempel webbplatsen [What Is My IP Address](https://www.whatismypublicip.com/).</span><span class="sxs-lookup"><span data-stu-id="c6817-117">For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page.</span></span> <span data-ttu-id="c6817-118">Den publika IP-adress som tilldelats dig av internetleverantören bör vara geografiskt lokal.</span><span class="sxs-lookup"><span data-stu-id="c6817-118">This public IP address assigned by your ISP should be geographically local.</span></span> <span data-ttu-id="c6817-119">Den ska inte vara från ett offentligt IP-adressintervall för ett centralt kontor eller en molnbaserad leverantör av nätverkssäkerhet.</span><span class="sxs-lookup"><span data-stu-id="c6817-119">It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="c6817-120">Vid behov kan [Steg 2](networking-dns-resolution-same-location.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="c6817-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a><span data-ttu-id="c6817-121">Valfritt: onödiga nätverkshairpins tas bort</span><span class="sxs-lookup"><span data-stu-id="c6817-121">Optional: Unnecessary network hairpins are removed</span></span>

<span data-ttu-id="c6817-122">Du har undersökt nätverkets hairpins och fastställt effekten på prestandan för alla dina kontor.</span><span class="sxs-lookup"><span data-stu-id="c6817-122">You examined your network hairpins and determined their impact on performance for all of your offices.</span></span> <span data-ttu-id="c6817-123">Du har tagit bort hårnålar i nätverket där det är möjligt eller arbetat med ditt nätverk från tredje part eller säkerhetsleverantören för att implementera optimal Microsoft 365-peering för deras nätverk.</span><span class="sxs-lookup"><span data-stu-id="c6817-123">You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="c6817-124">Vid behov kan [Steg 3](networking-avoid-network-hairpins.md) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="c6817-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="c6817-125">Valfritt: Du har konfigurerat förbikoppling av trafik på dina webbläsare och edge-enheter</span><span class="sxs-lookup"><span data-stu-id="c6817-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="c6817-126">De senaste PAC-filerna har distribuerats i dina lokala webbläsare så att trafik till Microsoft 365 DNS-domännamn förbigår proxyservrar.</span><span class="sxs-lookup"><span data-stu-id="c6817-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="c6817-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span><span class="sxs-lookup"><span data-stu-id="c6817-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="c6817-128">Så testar man</span><span class="sxs-lookup"><span data-stu-id="c6817-128">How to test</span></span>

<span data-ttu-id="c6817-129">Använd loggningsverktygen på nätverkets kringliggande enheter för att säkerställa att trafik till Microsoft 365-destinationer inte kontrolleras, dekrypteras eller på annat sätt förhindras.</span><span class="sxs-lookup"><span data-stu-id="c6817-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="c6817-130">Vid behov kan [Steg 4](networking-configure-proxies-firewalls.md) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="c6817-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-microsoft-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="c6817-131">Valfritt: Dina klienter och Microsoft 365-appar är konfigurerade för optimala prestanda</span><span class="sxs-lookup"><span data-stu-id="c6817-131">Optional: Your clients and Microsoft 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="c6817-132">Du har optimerat TCP-inställningarna (Transmission Control Protocol) på dina klientenheter och för Exchange Online, Skype för företag – Online, SharePoint Online och Microsoft Project Online-tjänster.</span><span class="sxs-lookup"><span data-stu-id="c6817-132">You have optimized the Transmission Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="c6817-133">Vid behov kan [Steg 5](networking-optimize-tcp-performance.md) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="c6817-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="c6817-134">Resultat och nästa steg</span><span class="sxs-lookup"><span data-stu-id="c6817-134">Results and next steps</span></span>

<span data-ttu-id="c6817-135">Dina intranätanvändare är nu redo att använda Microsoft 365-molntjänster via en effektiv nätverksväg till och på internet.</span><span class="sxs-lookup"><span data-stu-id="c6817-135">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="c6817-137">Om du följer stegen för slutpunkt till slutpunkt-distribution av Microsoft 365 Enterprise, är nästa fas [identitet](identity-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="c6817-137">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
