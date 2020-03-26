---
title: 'Steg 3: undvika nätverkshairpins'
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
description: Förstå och ta bort hairpins för bättre prestanda.
ms.openlocfilehash: f9499fdb8e8c3f7b77e3349d6cc99f6dbf465870
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807630"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="5a165-103">Steg 3: undvika nätverkshairpins</span><span class="sxs-lookup"><span data-stu-id="5a165-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="5a165-104">*Det här steget är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5a165-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="5a165-106">En [nätverkshairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) uppstår när trafik som är kopplad till ett mål först dirigeras till en annan mellanliggande plats, t. ex. en lokal säkerhetsstack, molnåtkomstkoordinator eller en molnbaserad webbgateway.</span><span class="sxs-lookup"><span data-stu-id="5a165-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="5a165-107">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="5a165-107">Here is an example.</span></span>

![Exempel på en nätverkshairpin](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="5a165-109">En nätverkshairpin kan också orsakas av dålig routning på Internet på grund av nätverksleverantörer.</span><span class="sxs-lookup"><span data-stu-id="5a165-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="5a165-110">En hairpin lägger till en svarstid och kan eventuellt dirigera om trafik till en geografiskt avlägsen plats.</span><span class="sxs-lookup"><span data-stu-id="5a165-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="5a165-111">För att optimera prestanda för trafik till molnbaserade Microsoft 365-tjänster kontrollerar du om Internet-leverantören av den lokala Internet-anslutningen har någon direkt peeringrelation med Microsofts globala nätverk i närheten av platsen.</span><span class="sxs-lookup"><span data-stu-id="5a165-111">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location.</span></span> <span data-ttu-id="5a165-112">De här anslutningarna har inte hairpins.</span><span class="sxs-lookup"><span data-stu-id="5a165-112">These connections do not have hairpins.</span></span>

<span data-ttu-id="5a165-113">Om du använder molnbaserade nätverks- eller säkerhetstjänster för din Microsoft 365-trafik ska du se till att hairpinningeffekten utvärderas och att dess påverkan på prestanda förstås.</span><span class="sxs-lookup"><span data-stu-id="5a165-113">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood.</span></span> <span data-ttu-id="5a165-114">Undersök följande:</span><span class="sxs-lookup"><span data-stu-id="5a165-114">Examine the following:</span></span>

- <span data-ttu-id="5a165-115">Antal och platser för dina tjänstleverantörer som trafiken vidarebefordras i i förhållande till dina olika kontor och Microsofts globala nätverkspeeringpunkter</span><span class="sxs-lookup"><span data-stu-id="5a165-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="5a165-116">Kvaliteten på tjänstleverantörens nätverkspeeringrelation med din Internet-leverantör och Microsoft</span><span class="sxs-lookup"><span data-stu-id="5a165-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="5a165-117">Prestandaeffekten av backhaul i infrastrukturen för tjänstleverantören</span><span class="sxs-lookup"><span data-stu-id="5a165-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="5a165-118">När det är möjligt konfigurerar du dina gränsroutrar så att de skickar betrodd Microsoft 365-trafik direkt, i stället för via proxy eller tunnel via en moln- eller molnbaserad nätverkssäkerhetsleverantör från tredje part som behandlar din Internet-trafik.</span><span class="sxs-lookup"><span data-stu-id="5a165-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Exempel på att förbikoppla en nätverkshairpin](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="5a165-120">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step3) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="5a165-120">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5a165-121">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5a165-121">Next step</span></span>

|||
|:-------|:-----|
|![Steg 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="5a165-123">Konfigurera förbikoppling av trafik</span><span class="sxs-lookup"><span data-stu-id="5a165-123">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
