---
title: URL-adresser och IP-adressintervall för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Sammanfattning: Office 365 kräver internetanslutning. Slutpunkterna nedan bör vara tillgängliga för kunder med Office 365-abonnemang, inklusive Government Community Cloud (GCC).'
hideEdit: true
ms.openlocfilehash: 386c92d0856b3faa88fb8a05f8ddff58a81e3c4f
ms.sourcegitcommit: a92b150da1e11d4a204c556ab98a4776727dbc22
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "49883342"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="69679-104">URL-adresser och IP-adressintervall för Office 365</span><span class="sxs-lookup"><span data-stu-id="69679-104">Office 365 URLs and IP address ranges</span></span>

<span data-ttu-id="69679-105">Office 365 kräver internetanslutning.</span><span class="sxs-lookup"><span data-stu-id="69679-105">Office 365 requires connectivity to the Internet.</span></span> <span data-ttu-id="69679-106">Slutpunkterna nedan bör vara tillgängliga för kunder med Office 365-abonnemang, inklusive Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="69679-106">The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
<span data-ttu-id="69679-107">*Office 365 Globalt (plus GCC)* | [Office 21 genom 365 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Tyskland](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="69679-107">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="69679-108">**Uppdaterades senast:** 2021-01-04 – ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Ändringsloggsprenumeration](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="69679-108">**Last updated:** 01/04/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span> <br/> |<span data-ttu-id="69679-109">**Ladda ned:** alla obligatoriska och valfria destinationer i en [JSON formaterad](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) lista.</span><span class="sxs-lookup"><span data-stu-id="69679-109">**Download:** all required and optional destinations in one [JSON formatted](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) list.</span></span>  <br/> | <span data-ttu-id="69679-110">**Använd:** våra proxy-[PAC-filer](managing-office-365-endpoints.md#pacfiles)</span><span class="sxs-lookup"><span data-stu-id="69679-110">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |

 <span data-ttu-id="69679-111">Börja med [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för hantering av nätverksanslutningar med dessa data.</span><span class="sxs-lookup"><span data-stu-id="69679-111">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data.</span></span> <span data-ttu-id="69679-112">Slutpunktsdata uppdateras i början av varje månad med nya IP-adresser och URL:er publicerade 30 dagar i förväg.</span><span class="sxs-lookup"><span data-stu-id="69679-112">Endpoints data is updated at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active.</span></span> <span data-ttu-id="69679-113">Det gör det möjligt för kunder som ännu inte har automatiserade uppdateringar att slutföra processerna innan nya anslutningar krävs.</span><span class="sxs-lookup"><span data-stu-id="69679-113">This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required.</span></span> <span data-ttu-id="69679-114">Slutpunkter kan också uppdateras under månaden om det behövs för att lösa stöd för eskalering, säkerhetstillbud och andra omedelbara driftskrav.</span><span class="sxs-lookup"><span data-stu-id="69679-114">Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements.</span></span> <span data-ttu-id="69679-115">De data som visas på den här sidan nedan skapas från de REST-baserade webbtjänsterna.</span><span class="sxs-lookup"><span data-stu-id="69679-115">The data shown on this page below is all generated from the REST-based web services.</span></span> <span data-ttu-id="69679-116">Om du använder ett skript eller en nätverksenhet för att komma åt dessa data ska du gå direkt till [Webbtjänst](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="69679-116">If you are using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.</span></span>

<span data-ttu-id="69679-117">I slutpunktsdata nedan visar krav för anslutning från en användares dator till Office 365.</span><span class="sxs-lookup"><span data-stu-id="69679-117">Endpoint data below lists requirements for connectivity from a user's machine to Office 365.</span></span> <span data-ttu-id="69679-118">Den innehåller inte nätverksanslutningar från Microsoft till ett kundnätverk, som ibland kallas hybrid-eller inkommande nätverksanslutningar.</span><span class="sxs-lookup"><span data-stu-id="69679-118">It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections.</span></span> <span data-ttu-id="69679-119">Mer information finns i [Ytterligare slutpunkter](additional-office365-ip-addresses-and-urls.md).</span><span class="sxs-lookup"><span data-stu-id="69679-119">See [Additional endpoints](additional-office365-ip-addresses-and-urls.md) for more information.</span></span>

<span data-ttu-id="69679-120">Slutpunkterna är grupperade i fyra tjänstområden.</span><span class="sxs-lookup"><span data-stu-id="69679-120">The endpoints are grouped into four service areas.</span></span> <span data-ttu-id="69679-121">De tre första tjänsterna kan väljas oberoende för anslutning.</span><span class="sxs-lookup"><span data-stu-id="69679-121">The first three service areas can be independently selected for connectivity.</span></span> <span data-ttu-id="69679-122">Det fjärde tjänstområdet är ett vanligt beroende (kallat Microsoft 365 Common och Office) och måste alltid ha nätverksanslutning.</span><span class="sxs-lookup"><span data-stu-id="69679-122">The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.</span></span>

<span data-ttu-id="69679-123">Data kolumnerna som visas är:</span><span class="sxs-lookup"><span data-stu-id="69679-123">Data columns shown are:</span></span>

- <span data-ttu-id="69679-124">**ID**: Raden för ID-numret, som även kallas för en slutpunktsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="69679-124">**ID**: The ID number of the row, also known as an endpoint set.</span></span> <span data-ttu-id="69679-125">Detta ID är samma som returneras av webbtjänsten för slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="69679-125">This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="69679-126">**Kategori**: Visar om slutpunktsuppsättningen kategoriseras som "Optimera", "Tillåt" eller "Standard".</span><span class="sxs-lookup"><span data-stu-id="69679-126">**Category**: Shows whether the endpoint set is categorized as "Optimize", "Allow", or "Default".</span></span> <span data-ttu-id="69679-127">Du kan läsa mer om de här kategorierna och anvisningarna för hur du hanterar dem i [Nya slutpunktskategorier för Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="69679-127">You can read about these categories and guidance for management of them at [New Office 365 endpoint categories](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="69679-128">I den här kolumnen visas även vilka slutpunktsuppsättningar som krävs för nätverksanslutningar.</span><span class="sxs-lookup"><span data-stu-id="69679-128">This column also lists which endpoint sets are required to have network connectivity.</span></span> <span data-ttu-id="69679-129">För slutpunktsuppsättningar som inte är nödvändiga för att ha nätverksanslutning tillhandahåller vi anteckningar i det här fältet för att ange vilka funktioner som skulle saknas om slutpunktsuppsättningen är blockerad.</span><span class="sxs-lookup"><span data-stu-id="69679-129">For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked.</span></span> <span data-ttu-id="69679-130">Om du undantar ett helt tjänstområde kräver inte slutpunktsuppsättningarna som anges som krav anslutning.</span><span class="sxs-lookup"><span data-stu-id="69679-130">If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="69679-131">**ER**: Det här är **Ja** om slutpunktsuppsättningen stöds över Azure ExpressRoute med Office 365-väg-prefix.</span><span class="sxs-lookup"><span data-stu-id="69679-131">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes.</span></span> <span data-ttu-id="69679-132">BGP-communityn som innehåller de väg-prefix som visas är justeras med tjänstområdet som visas.</span><span class="sxs-lookup"><span data-stu-id="69679-132">The BGP community that includes the route prefixes shown aligns with the service area listed.</span></span> <span data-ttu-id="69679-133">När ER är **Nej**, innebär det att ExpressRoute inte stöds för denna slutpunktsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="69679-133">When ER is **No**, this means that ExpressRoute is not supported for this endpoint set.</span></span> <span data-ttu-id="69679-134">Tänk dock på att det inte ska finnas några vägar som annonseras för en slutpunkt där ER är **Nej**.</span><span class="sxs-lookup"><span data-stu-id="69679-134">However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="69679-135">**Adresser**: listar FQDN-namn eller domännamn med jokertecken och IP-adressintervall för slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="69679-135">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set.</span></span> <span data-ttu-id="69679-136">Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.</span><span class="sxs-lookup"><span data-stu-id="69679-136">Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="69679-137">**Portar**: Listar de TCP-eller UDP-portar som kombineras med adresserna för att skapa nätverksslutpunkten.</span><span class="sxs-lookup"><span data-stu-id="69679-137">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint.</span></span> <span data-ttu-id="69679-138">Du märker kanske att det finns dubbletter i IP-adressintervall där olika portar finns med i listan.</span><span class="sxs-lookup"><span data-stu-id="69679-138">You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
><span data-ttu-id="69679-139">Rekommendationer om IP- och URL-adresser för Yammer finns i [Vi rekommenderar inte att du använder hårdkodade IP-adresser för Yammer](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) på Yammer-bloggen.</span><span class="sxs-lookup"><span data-stu-id="69679-139">For recommendations on Yammer IP addresses and URLs, see [Using hard-coded IP addresses for Yammer is not recommended](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) on the Yammer blog.</span></span>
>

## <a name="related-topics"></a><span data-ttu-id="69679-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="69679-140">Related Topics</span></span>

[<span data-ttu-id="69679-141">Hantera Office 365-slutpunkter</span><span class="sxs-lookup"><span data-stu-id="69679-141">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="69679-142">Allmänna Microsoft Stream-slutpunkter</span><span class="sxs-lookup"><span data-stu-id="69679-142">General Microsoft Stream endpoints</span></span>](https://docs.microsoft.com/stream/network-overview#general-microsoft-stream-endpoints)
  
[<span data-ttu-id="69679-143">Övervaka Microsoft 365 anslutning</span><span class="sxs-lookup"><span data-stu-id="69679-143">Monitor Microsoft 365 connectivity</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/monitor-connectivity)

[<span data-ttu-id="69679-144">Rot certifikatutfärdare (CA) och mellanliggande certifikatutfärdare i programsystemet från tredje part</span><span class="sxs-lookup"><span data-stu-id="69679-144">Root CA and the Intermediate CA bundle on the third-party application system</span></span>](../compliance/encryption-office-365-certificate-chains.md)
  
[<span data-ttu-id="69679-145">Klientanslutning</span><span class="sxs-lookup"><span data-stu-id="69679-145">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="69679-146">Nätverk för innehållsleverans</span><span class="sxs-lookup"><span data-stu-id="69679-146">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="69679-147">Microsoft Azure IP-intervall och servicetaggar – offentligt moln</span><span class="sxs-lookup"><span data-stu-id="69679-147">Microsoft Azure IP Ranges and Service Tags – Public Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=56519)

[<span data-ttu-id="69679-148">Microsoft Azure IP-intervall och servicetaggar – USA: s regeringsmoln</span><span class="sxs-lookup"><span data-stu-id="69679-148">Microsoft Azure IP Ranges and Service Tags – US Government Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57063)

[<span data-ttu-id="69679-149">Microsoft Azure IP-intervaller och servicetaggar – moln i Tyskland</span><span class="sxs-lookup"><span data-stu-id="69679-149">Microsoft Azure IP Ranges and Service Tags – Germany Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57064)

[<span data-ttu-id="69679-150">Microsoft Azure IP-intervall och servicetaggar – moln i Kina</span><span class="sxs-lookup"><span data-stu-id="69679-150">Microsoft Azure IP Ranges and Service Tags – China Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57062)
  
[<span data-ttu-id="69679-151">Microsoft Public IP-utrymme</span><span class="sxs-lookup"><span data-stu-id="69679-151">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)

[<span data-ttu-id="69679-152">Servicenamn och Transportprotokoll portnummerregister</span><span class="sxs-lookup"><span data-stu-id="69679-152">Service Name and Transport Protocol Port Number Registry</span></span>](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
