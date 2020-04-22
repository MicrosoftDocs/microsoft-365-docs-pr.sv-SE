---
title: 'Steg 3: undvika nätverkshairpins'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och ta bort hairpins för bättre prestanda.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583431"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="e50ea-103">Steg 3: undvika nätverkshairpins</span><span class="sxs-lookup"><span data-stu-id="e50ea-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="e50ea-104">*Det här steget är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e50ea-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="e50ea-106">En [nätverkshairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) uppstår när trafik som är kopplad till ett mål först dirigeras till en annan mellanliggande plats, t. ex. en lokal säkerhetsstack, molnåtkomstkoordinator eller en molnbaserad webbgateway.</span><span class="sxs-lookup"><span data-stu-id="e50ea-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="e50ea-107">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="e50ea-107">Here is an example.</span></span>

![Exempel på en nätverkshairpin](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="e50ea-109">En nätverkshairpin kan också orsakas av dålig routning på Internet på grund av nätverksleverantörer.</span><span class="sxs-lookup"><span data-stu-id="e50ea-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="e50ea-110">En hairpin lägger till en svarstid och kan eventuellt dirigera om trafik till en geografiskt avlägsen plats.</span><span class="sxs-lookup"><span data-stu-id="e50ea-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="e50ea-111">För att optimera prestanda för trafik till molnbaserade Microsoft 365-tjänster kontrollerar du om Internet-leverantören av den lokala Internet-anslutningen har någon direkt peeringrelation med Microsofts globala nätverk i närheten av platsen.</span><span class="sxs-lookup"><span data-stu-id="e50ea-111">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location.</span></span> <span data-ttu-id="e50ea-112">De här anslutningarna har inte hairpins.</span><span class="sxs-lookup"><span data-stu-id="e50ea-112">These connections do not have hairpins.</span></span>

<span data-ttu-id="e50ea-113">Om du använder molnbaserade nätverks- eller säkerhetstjänster för din Microsoft 365-trafik ska du se till att hairpinningeffekten utvärderas och att dess påverkan på prestanda förstås.</span><span class="sxs-lookup"><span data-stu-id="e50ea-113">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood.</span></span> <span data-ttu-id="e50ea-114">Undersök följande:</span><span class="sxs-lookup"><span data-stu-id="e50ea-114">Examine the following:</span></span>

- <span data-ttu-id="e50ea-115">Antal och platser för dina tjänstleverantörer som trafiken vidarebefordras i i förhållande till dina olika kontor och Microsofts globala nätverkspeeringpunkter</span><span class="sxs-lookup"><span data-stu-id="e50ea-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="e50ea-116">Kvaliteten på tjänstleverantörens nätverkspeeringrelation med din Internet-leverantör och Microsoft</span><span class="sxs-lookup"><span data-stu-id="e50ea-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="e50ea-117">Prestandaeffekten av backhaul i infrastrukturen för tjänstleverantören</span><span class="sxs-lookup"><span data-stu-id="e50ea-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="e50ea-118">När det är möjligt konfigurerar du dina gränsroutrar så att de skickar betrodd Microsoft 365-trafik direkt, i stället för via proxy eller tunnel via en moln- eller molnbaserad nätverkssäkerhetsleverantör från tredje part som behandlar din Internet-trafik.</span><span class="sxs-lookup"><span data-stu-id="e50ea-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Exempel på att förbikoppla en nätverkshairpin](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="e50ea-120">Om du vill testa hur nära du befinner dig i en ingångspunkt för Microsoft globalt nätverk och hur nära din plats som organisationens nätverk ansluter till din Internetleverantör använder du [Office 365 Network Onboarding Tool](https://connectivity.office.com/).</span><span class="sxs-lookup"><span data-stu-id="e50ea-120">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="e50ea-121">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step3) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="e50ea-121">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e50ea-122">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e50ea-122">Next step</span></span>

|||
|:-------|:-----|
|![Steg 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="e50ea-124">Konfigurera förbikoppling av trafik</span><span class="sxs-lookup"><span data-stu-id="e50ea-124">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
