---
title: Steg 2. Tillhandahålla fjärråtkomst till lokala appar och tjänster
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Kontrollera att dina distansarbetare kan komma åt lokala resurser samtidigt som du optimerar åtkomst till Microsoft 365-molntjänster.
ms.openlocfilehash: fb91451b52c55f2cad1e0efefe19a044ce1cc37b
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003402"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="0592b-104">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="0592b-104">Step 2.</span></span> <span data-ttu-id="0592b-105">Tillhandahålla fjärråtkomst till lokala appar och tjänster</span><span class="sxs-lookup"><span data-stu-id="0592b-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="0592b-106">Användarna använda VPN-anslutningarna för fjärråtkomst för att komma åt lokala appar och servrar om din organisation använder en VPN-lösning för fjärråtkomst, oftast med VPN-servrar på kanten av ditt nätverk och VPN-klienter som är installerade på användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="0592b-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="0592b-107">Men du kan behöva optimera trafik för molnbaserade Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="0592b-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="0592b-108">Om dina användare inte använder en VPN-lösning kan du med hjälp av Azure Active Directory (Azure AD) Application Proxy och Azure Point-to-Site (P2S) VPN för att ge åtkomst, beroende på om alla dina appar är webbaserade.</span><span class="sxs-lookup"><span data-stu-id="0592b-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="0592b-109">Det finns tre primära konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="0592b-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="0592b-110">Du använder redan en VPN-lösning för fjärråtkomst.</span><span class="sxs-lookup"><span data-stu-id="0592b-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="0592b-111">Du använder inte en VPN-lösning för fjärråtkomst, men du har en hybrididentitet och du behöver endast fjärråtkomst till lokala webbaserade appar.</span><span class="sxs-lookup"><span data-stu-id="0592b-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="0592b-112">Du använder inte en VPN-lösning för fjärråtkomst och du behöver åtkomst till lokala appar, varav några inte är webbaserade.</span><span class="sxs-lookup"><span data-stu-id="0592b-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="0592b-113">Med fjärråtkomstanslutningar kan du även använda [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) för att ansluta dina användare till en lokal dator.</span><span class="sxs-lookup"><span data-stu-id="0592b-113">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="0592b-114">En distansarbetare kan använda Remote Desktop för att ansluta till datorn på deras kontor från deras Windows-, iOS- eller Android-enhet.</span><span class="sxs-lookup"><span data-stu-id="0592b-114">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="0592b-115">När de har fjärranslutit kan de använda den som om de satt framför den.</span><span class="sxs-lookup"><span data-stu-id="0592b-115">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="0592b-116">Optimera prestanda för VPN-klienter för fjärråtkomst till Microsoft 365-molntjänster</span><span class="sxs-lookup"><span data-stu-id="0592b-116">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="0592b-117">Om din distansarbetare använder en traditionell VPN-klient för att få fjärråtkomst till organisationens nätverk ska du kontrollera att VPN-klienten har stöd för delad tunnel.</span><span class="sxs-lookup"><span data-stu-id="0592b-117">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="0592b-118">Utan delad tunnel skickas all din fjärrtrafik över VPN-anslutningen, där den måste vidarebefordras till organisationens gränsenheter, bli processad och sedan skickas via Internet.</span><span class="sxs-lookup"><span data-stu-id="0592b-118">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Nätverkstrafik från VPN-klienter utan tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="0592b-120">Microsoft 365-trafik måste ta en indirekt väg via din organisation, som kan vara vidarebefordrad till en Microsoft Network startpunkt långt bort från VPN-klientens fysiska plats.</span><span class="sxs-lookup"><span data-stu-id="0592b-120">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="0592b-121">Denna indirekta väg lägger till en fördröjning för nätverkstrafiken och minskar prestandan.</span><span class="sxs-lookup"><span data-stu-id="0592b-121">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="0592b-122">Med delad tunnel kan du konfigurera VPN-klienten så att den exkluderar vissa typer av trafik som inte skickas via VPN-anslutningen till organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="0592b-122">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="0592b-123">Om du vill optimera åtkomst till Microsoft 365 molnresurser konfigurerar du VPN-klienter för uppdelad tunnel för att undanta trafik till **optimera** kategori Microsoft 365-slutpunkter över VPN-anslutningen.</span><span class="sxs-lookup"><span data-stu-id="0592b-123">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="0592b-124">Mer information finns i [Office 365-slutpunktskategorier](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="0592b-124">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="0592b-125">Se listan över optimera kategorislutpunkter [här](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="0592b-125">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![Nätverkstrafik från VPN-klienter med tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="0592b-127">Detta gör att VPN-klienten kan skicka och ta emot viktig trafik i Microsoft 365 molntjänster direkt via Internet och till närmaste startpunkt i Microsoft-nätverket.</span><span class="sxs-lookup"><span data-stu-id="0592b-127">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="0592b-128">Detaljerad information finn i [Optimera Office 365-anslutning för fjärranvändare med delad VPN-tunnel](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="0592b-128">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="0592b-129">Distribuera fjärråtkomst när alla dina appar är webbprogram och du har en hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="0592b-129">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="0592b-130">Om dina distansarbetare inte använder en traditionell VPN-klient och dina lokala användarkonton och -grupper är synkroniserade med Azure Active Directory kan du använda Azure Active Directory Application Proxy för att tillhandahålla säker fjärråtkomst för webbaserade program som finns på intranätservrar.</span><span class="sxs-lookup"><span data-stu-id="0592b-130">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="0592b-131">Webbaserade program är SharePoint-webbplatser, Outlook Web Access-servrar eller andra webbaserade affärsprogram.</span><span class="sxs-lookup"><span data-stu-id="0592b-131">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="0592b-132">Här är komponenterna i Azure Active Directory Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="0592b-132">Here are the components of Azure AD Application Proxy.</span></span>

![Komponenter i Azure Active Directory Application Proxy](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="0592b-134">Mer information finns i den här [översikt över Azure Active Directory Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="0592b-134">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="0592b-135">Distribuera fjärråtkomst när alla appar inte är webbprogram</span><span class="sxs-lookup"><span data-stu-id="0592b-135">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="0592b-136">Om din distansarbetare inte använder en traditionell VPN-klient och några av dina appar inte är webbaserade kan du använda en Azure Point-to-Site (P2S) VPN.</span><span class="sxs-lookup"><span data-stu-id="0592b-136">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="0592b-137">En P2S VPN-anslutning skapar en säker anslutning från en distansarbetares enhet till organisationens nätverk via ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="0592b-137">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Komponenter i Azure P2S VPN](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="0592b-139">Mer information finns i denna [översikt över P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="0592b-139">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="0592b-140">Distribuera Windows Virtual Desktop för att tillhandahålla fjärråtkomst för distansarbetare som använder personliga enheter</span><span class="sxs-lookup"><span data-stu-id="0592b-140">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="0592b-141">Om du vill stödja distansarbetare som endast kan använda sina personliga och ohanterade enheter kan du använda Windows Virtual Desktop i Azure och skapa och allokera virtuella skrivbord för användarna att använda hemifrån.</span><span class="sxs-lookup"><span data-stu-id="0592b-141">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="0592b-142">Virtualiserade datorer kan agera precis som datorer som är anslutna till din organisations nätverk.</span><span class="sxs-lookup"><span data-stu-id="0592b-142">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="0592b-143">Mer information finns i [den här översikten över Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="0592b-143">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="0592b-144">Tekniska administrationsresurser för fjärråtkomst</span><span class="sxs-lookup"><span data-stu-id="0592b-144">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="0592b-145">Så här kan du snabbt optimera Office 365-trafik för fjärransluten personal och minska belastningen på infrastrukturen</span><span class="sxs-lookup"><span data-stu-id="0592b-145">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="0592b-146">Optimera Office 365-anslutningen för fjärranvändare med uppdelad VPN-tunnel</span><span class="sxs-lookup"><span data-stu-id="0592b-146">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="0592b-147">Resultat av steg 2</span><span class="sxs-lookup"><span data-stu-id="0592b-147">Results of Step 2</span></span>

<span data-ttu-id="0592b-148">Efter distribution av en lösning för fjärråtkomst för dina distansarbetare:</span><span class="sxs-lookup"><span data-stu-id="0592b-148">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="0592b-149">Konfigurationen för fjärråtkomst</span><span class="sxs-lookup"><span data-stu-id="0592b-149">Remote access configuration</span></span> | <span data-ttu-id="0592b-150">Resultat</span><span class="sxs-lookup"><span data-stu-id="0592b-150">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="0592b-151">En VPN-lösning för fjärråtkomst finns på plats</span><span class="sxs-lookup"><span data-stu-id="0592b-151">A remote access VPN solution is in place</span></span> | <span data-ttu-id="0592b-152">Du har konfigurerat VPN-klienten för fjärråtkomst för uppdelad tunnel och för optimeringskategori för Microsoft 365-slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="0592b-152">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="0592b-153">Ingen VPN-lösning för fjärråtkomst och du behöver endast fjärråtkomst till lokala webbaserade appar</span><span class="sxs-lookup"><span data-stu-id="0592b-153">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="0592b-154">Du har konfigurerat Azure Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="0592b-154">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="0592b-155">Ingen VPN-lösning för fjärråtkomst och du behöver åtkomst till lokala appar, vissa som inte är webbaserade</span><span class="sxs-lookup"><span data-stu-id="0592b-155">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="0592b-156">Du har konfigurerat Azure P2S VPN.</span><span class="sxs-lookup"><span data-stu-id="0592b-156">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="0592b-157">Distansarbetare använder sina personliga enheter från hemmet</span><span class="sxs-lookup"><span data-stu-id="0592b-157">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="0592b-158">Du har konfigurerat Windows Virtual Desktop.</span><span class="sxs-lookup"><span data-stu-id="0592b-158">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="0592b-159">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0592b-159">Next step</span></span>

<span data-ttu-id="0592b-160">Fortsätt med [Steg 3](empower-people-to-work-remotely-manage-endpoints.md) för att hantera enheter, datorer och andra slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="0592b-160">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
