---
title: 'Steg 2: Konfigurera lokala internetanslutningar för varje kontor'
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
description: Förstå och konfigurera DNS-upplösningen för bättre prestanda.
ms.openlocfilehash: 8b4302c06e75c59a1b99eb60399c9df897ad17ea
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806024"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="29171-103">Steg 2: Konfigurera lokala internetanslutningar för varje kontor</span><span class="sxs-lookup"><span data-stu-id="29171-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="29171-104">*Det här steget är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="29171-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="29171-106">I steg 2 ser du till att alla dina kontor har lokala Internet-anslutningar och använder lokala DNS-servrar.</span><span class="sxs-lookup"><span data-stu-id="29171-106">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers.</span></span> <span data-ttu-id="29171-107">Båda dessa element är nödvändiga för att minska anslutningsfördröjningen och se till att lokala klientdatorer ansluter till närmaste molnbaserade Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="29171-107">Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="29171-108">I traditionella nätverk för stora organisationer sänds Internet-trafik via nätverksstamnätet till en central Internet-anslutning.</span><span class="sxs-lookup"><span data-stu-id="29171-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="29171-109">Det här fungerar inte bra för att optimera prestanda för en global distribuerad Saas-infrastruktur (programvara som tjänst), som omfattar Office 365- och Intune-produkter i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29171-109">This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Intune products in Microsoft 365.</span></span>

<span data-ttu-id="29171-110">Microsofts globala nätverk innehåller en *distribuerad Front Door Service*-infrastruktur, en nätverksgräns med hög tillgänglighet som är mycket skalbar med geografiskt distribuerade platser.</span><span class="sxs-lookup"><span data-stu-id="29171-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="29171-111">Den avslutar användarens anslutningar på en Front Door-server och dirigerar effektivt slutanvändarens trafik i Microsofts globala nätverk.</span><span class="sxs-lookup"><span data-stu-id="29171-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![Microsofts globala nätverk](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="29171-113">För bästa prestanda ska lokala klienter komma åt en plats som ligger geografiskt närmast, i stället för att trafiken skickas via ett nätverksstamnät och till den startpunkt (front door) som ligger närmast organisationens centrala Internet-anslutning.</span><span class="sxs-lookup"><span data-stu-id="29171-113">For the best performance, on-premises clients should access a front door location that is geographically closest to them, rather than sending the traffic over a network backbone and to the front door that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="29171-114">Här följer ett exempel.</span><span class="sxs-lookup"><span data-stu-id="29171-114">Here’s an example.</span></span>

![Exempel på användning av Microsofts globala nätverk](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="29171-116">När en användare på det lokala kontoret i Paris vill få åtkomst till en SharePoint Online-webbplats:</span><span class="sxs-lookup"><span data-stu-id="29171-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="29171-117">Den skickar en DNS-fråga för att matcha ett namn, t. ex. contoso.sharepoint.com.</span><span class="sxs-lookup"><span data-stu-id="29171-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="29171-118">Den DNS-server som tillhandahålls av Internet-leverantören vidarebefordrar den frågan till en Microsoft DNS-server.</span><span class="sxs-lookup"><span data-stu-id="29171-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="29171-119">Microsofts DNS-servrar matchar käll-IP-adressen för den vidarebefordrade DNS-frågan till den region i världen som tilldelats adressen.</span><span class="sxs-lookup"><span data-stu-id="29171-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="29171-120">Microsofts DNS-server svarar med IP-adressen för den närmaste Microsoft-nätverksanslutningen i Europa.</span><span class="sxs-lookup"><span data-stu-id="29171-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="29171-121">Internet-leverantörens DNS-server skickar IP-adressen till användaren.</span><span class="sxs-lookup"><span data-stu-id="29171-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="29171-122">Användaren upprättar en anslutning till SharePoint-servern via Europas startpunkt.</span><span class="sxs-lookup"><span data-stu-id="29171-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="29171-123">Om du vill dirigera en klientbegäran till en startpunkt som är närmast geografiskt använder Microsofts DNS-servrar DNS-frågorna som motsvarar klientens första anslutningsbegäran.</span><span class="sxs-lookup"><span data-stu-id="29171-123">To direct a client request to the geographically nearest front door, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request.</span></span> <span data-ttu-id="29171-124">För att få lägsta möjliga nätverksfördröjning ska:</span><span class="sxs-lookup"><span data-stu-id="29171-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="29171-125">Alla kontor i din organisation ha lokala Internet-anslutningar för att [optimera](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) kategorin för nätverkstrafik.</span><span class="sxs-lookup"><span data-stu-id="29171-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="29171-126">Varje lokal Internet-anslutning ska använda en regional lokal DNS-server för utgående Internet-trafik från den platsen.</span><span class="sxs-lookup"><span data-stu-id="29171-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="29171-127">Mer information finns i [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally) (Utgående lokala nätverksanslutningar).</span><span class="sxs-lookup"><span data-stu-id="29171-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="29171-128">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step2) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="29171-128">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="29171-129">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="29171-129">Next step</span></span>

|||
|:-------|:-----|
|![Steg 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="29171-131">Undvika nätverkshairpins</span><span class="sxs-lookup"><span data-stu-id="29171-131">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
