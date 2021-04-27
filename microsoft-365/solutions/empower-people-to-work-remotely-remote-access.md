---
title: Steg 2. Tillhandahålla fjärråtkomst till lokala appar och tjänster
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Kontrollera att dina distansarbetare kan komma åt lokala resurser samtidigt som du optimerar åtkomst till Microsoft 365-molntjänster.
ms.openlocfilehash: 9fea86bb9c564a37a519d2c7e0ef2e2fd0a59470
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029140"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="e7da0-104">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="e7da0-104">Step 2.</span></span> <span data-ttu-id="e7da0-105">Tillhandahålla fjärråtkomst till lokala appar och tjänster</span><span class="sxs-lookup"><span data-stu-id="e7da0-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="e7da0-106">Användarna använda VPN-anslutningarna för fjärråtkomst för att komma åt lokala appar och servrar om din organisation använder en VPN-lösning för fjärråtkomst, oftast med VPN-servrar på kanten av ditt nätverk och VPN-klienter som är installerade på användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="e7da0-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="e7da0-107">Men du kan behöva optimera trafik för molnbaserade Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="e7da0-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="e7da0-108">Om dina användare inte använder en VPN-lösning kan du med hjälp av Azure Active Directory (Azure AD) Application Proxy och Azure Point-to-Site (P2S) VPN för att ge åtkomst, beroende på om alla dina appar är webbaserade.</span><span class="sxs-lookup"><span data-stu-id="e7da0-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="e7da0-109">Här beskrivs de primära konfigurationerna för fjärråtkomst:</span><span class="sxs-lookup"><span data-stu-id="e7da0-109">Here are the primary configurations for remote access:</span></span>

- <span data-ttu-id="e7da0-110">Du använder redan en VPN-lösning för fjärråtkomst.</span><span class="sxs-lookup"><span data-stu-id="e7da0-110">You are already using a remote access VPN solution.</span></span>
- <span data-ttu-id="e7da0-111">Du använder inte en VPN-lösning för fjärråtkomst och du vill att dina distansarbetare ska använda sina egna datorer.</span><span class="sxs-lookup"><span data-stu-id="e7da0-111">You are not using a remote access VPN solution and you want your remote workers to use their personal computers.</span></span>
- <span data-ttu-id="e7da0-112">Du använder inte en VPN-lösning för fjärråtkomst, men du har en hybrididentitet och du behöver endast fjärråtkomst till lokala webbaserade appar.</span><span class="sxs-lookup"><span data-stu-id="e7da0-112">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
- <span data-ttu-id="e7da0-113">Du använder inte en VPN-lösning för fjärråtkomst och du behöver åtkomst till lokala appar, varav några inte är webbaserade.</span><span class="sxs-lookup"><span data-stu-id="e7da0-113">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="e7da0-114">Se det här flödesschemat för konfigurationsalternativen för fjärråtkomst som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e7da0-114">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Flödesdiagram över konfigurationen för fjärråtkomst](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="e7da0-116">Med fjärråtkomstanslutningar kan du även använda [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) för att ansluta dina användare till en lokal dator.</span><span class="sxs-lookup"><span data-stu-id="e7da0-116">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="e7da0-117">Distansarbetare kan till exempel använda Remote Desktop för att ansluta till sina datorer på kontoret från sina Windows-, iOS- eller Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="e7da0-117">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS, or Android device.</span></span> <span data-ttu-id="e7da0-118">När de har fjärranslutit kan de använda den som om de satt framför den.</span><span class="sxs-lookup"><span data-stu-id="e7da0-118">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="e7da0-119">Optimera prestanda för VPN-klienter för fjärråtkomst till Microsoft 365-molntjänster</span><span class="sxs-lookup"><span data-stu-id="e7da0-119">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="e7da0-120">Om din distansarbetare använder en traditionell VPN-klient för att få fjärråtkomst till organisationens nätverk ska du kontrollera att VPN-klienten har stöd för delad tunnel.</span><span class="sxs-lookup"><span data-stu-id="e7da0-120">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="e7da0-121">Utan delad tunnel skickas all din fjärrtrafik över VPN-anslutningen, där den måste vidarebefordras till organisationens gränsenheter, bli processad och sedan skickas via Internet.</span><span class="sxs-lookup"><span data-stu-id="e7da0-121">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Nätverkstrafik från VPN-klienter utan tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="e7da0-123">Microsoft 365-trafik måste ta en indirekt väg genom din organisation, som kan vidarebefordras till en Microsoft-nätverksingångspunkt långt ifrån VPN-klientens fysiska plats.</span><span class="sxs-lookup"><span data-stu-id="e7da0-123">Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="e7da0-124">Denna indirekta väg lägger till en fördröjning för nätverkstrafiken och minskar prestandan.</span><span class="sxs-lookup"><span data-stu-id="e7da0-124">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="e7da0-125">Med delad tunnel kan du konfigurera VPN-klienten så att den exkluderar vissa typer av trafik som inte skickas via VPN-anslutningen till organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="e7da0-125">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="e7da0-126">Om du vill optimera åtkomst till Microsoft 365 molnresurser konfigurerar du VPN-klienter för uppdelad tunnel för att undanta trafik till **optimera** kategori Microsoft 365-slutpunkter över VPN-anslutningen.</span><span class="sxs-lookup"><span data-stu-id="e7da0-126">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="e7da0-127">Mer information finns i [Office 365-slutpunktskategorier](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="e7da0-127">For more information, see [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="e7da0-128">Se listan över Optimera kategorislutpunkter [här](../enterprise/urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="e7da0-128">See [this list](../enterprise/urls-and-ip-address-ranges.md) of Optimize category endpoints.</span></span>

<span data-ttu-id="e7da0-129">Här är det resulterande trafikflödet, där den mesta trafiken till Microsoft 365-molnappar kringgår VPN-anslutningen.</span><span class="sxs-lookup"><span data-stu-id="e7da0-129">Here is the resulting traffic flow, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![Nätverkstrafik från VPN-klienter med tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="e7da0-131">Detta gör att VPN-klienten kan skicka och ta emot viktig trafik i Microsoft 365 molntjänster direkt via Internet och till närmaste startpunkt i Microsoft-nätverket.</span><span class="sxs-lookup"><span data-stu-id="e7da0-131">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="e7da0-132">Detaljerad information finn i [Optimera Office 365-anslutning för fjärranvändare med delad VPN-tunnel](../enterprise/microsoft-365-vpn-split-tunnel.md).</span><span class="sxs-lookup"><span data-stu-id="e7da0-132">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="e7da0-133">Distribuera fjärråtkomst när alla dina appar är webbprogram och du har en hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="e7da0-133">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="e7da0-134">Om dina distansarbetare inte använder en traditionell VPN-klient och dina lokala användarkonton och -grupper är synkroniserade med Azure AD, kan du använda Azure AD Application Proxy för att tillhandahålla säker fjärråtkomst för webbaserade program som finns på lokala servrar.</span><span class="sxs-lookup"><span data-stu-id="e7da0-134">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on on-premises servers.</span></span> <span data-ttu-id="e7da0-135">Webbaserade program är SharePoint Server-webbplatser, Outlook Web Access-servrar eller andra webbaserade affärsprogram.</span><span class="sxs-lookup"><span data-stu-id="e7da0-135">Web-based applications include SharePoint Server sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="e7da0-136">Här är komponenterna i Azure Active Directory Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="e7da0-136">Here are the components of Azure AD Application Proxy.</span></span>

![Komponenter i Azure Active Directory Application Proxy](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="e7da0-138">Mer information finns i den här [översikt över Azure Active Directory Application Proxy](/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="e7da0-138">For more information, see this [overview of Azure AD Application Proxy](/azure/active-directory/manage-apps/application-proxy).</span></span>

>[!Note]
><span data-ttu-id="e7da0-139">Azure Active Directory Application Proxy ingår inte i en Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e7da0-139">Azure AD Application Proxy is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="e7da0-140">Du måste betala för användning med en separat Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e7da0-140">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="e7da0-141">Distribuera fjärråtkomst när alla appar inte är webbprogram</span><span class="sxs-lookup"><span data-stu-id="e7da0-141">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="e7da0-142">Om dina distansarbetare inte använder en traditionell VPN-klient och några av dina appar inte är webbaserade kan du använda en Azure Point-to-Site (P2S) VPN.</span><span class="sxs-lookup"><span data-stu-id="e7da0-142">If your remote workers are not using a traditional VPN client and you have apps that are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="e7da0-143">En P2S VPN-anslutning skapar en säker anslutning från en distansarbetares enhet till organisationens nätverk via ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="e7da0-143">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Komponenter i Azure P2S VPN](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="e7da0-145">Mer information finns i denna [översikt över P2S VPN](/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="e7da0-145">For more information, see this [overview of P2S VPN](/azure/vpn-gateway/point-to-site-about).</span></span>

>[!Note]
><span data-ttu-id="e7da0-146">Azure P2S VPN ingår inte i en Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e7da0-146">Azure P2S VPN is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="e7da0-147">Du måste betala för användning med en separat Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e7da0-147">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="e7da0-148">Distribuera Windows Virtual Desktop för att tillhandahålla fjärråtkomst för distansarbetare som använder personliga enheter</span><span class="sxs-lookup"><span data-stu-id="e7da0-148">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="e7da0-149">Om du vill stödja distansarbetare som endast kan använda sina personliga och ohanterade enheter kan du använda Windows Virtual Desktop i Azure och skapa och allokera virtuella skrivbord för användarna att använda hemifrån.</span><span class="sxs-lookup"><span data-stu-id="e7da0-149">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span> <span data-ttu-id="e7da0-150">Virtualiserade datorer kan agera precis som datorer som är anslutna till din organisations nätverk.</span><span class="sxs-lookup"><span data-stu-id="e7da0-150">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

![Komponenter i Azure Windows Virtual Desktop](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

<span data-ttu-id="e7da0-152">Mer information finns i [den här översikten över Windows Virtual Desktop](/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="e7da0-152">For more information, see this [overview of Windows Virtual Desktop](/azure/virtual-desktop/overview).</span></span> 

>[!Note]
><span data-ttu-id="e7da0-153">Windows Virtual Desktop ingår inte i en Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e7da0-153">Windows Virtual Desktop is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="e7da0-154">Du måste betala för användning med en separat Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e7da0-154">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a><span data-ttu-id="e7da0-155">Skydda dina anslutningar för fjärrskrivbordstjänster med gateway för fjärrskrivbordstjänster</span><span class="sxs-lookup"><span data-stu-id="e7da0-155">Protect your Remote Desktop Services connections with the Remote Desktop Services Gateway</span></span>

<span data-ttu-id="e7da0-156">Om du använder fjärrskrivbordstjänster (RDS) för att låta dina medarbetare ansluta till Windows-datorer i det lokala nätverket bör du använda en Microsoft Fjärrskrivbordtjänster-gateway i Edge-nätverket.</span><span class="sxs-lookup"><span data-stu-id="e7da0-156">If you are using Remote Desktop Services (RDS) to allow employees to connect into Windows-based computers on your on-premises network, you should use a Microsoft Remote Desktop Services gateway in your edge network.</span></span> <span data-ttu-id="e7da0-157">Gateway använder TLS (Transport Layer Security) för att kryptera trafik och förhindrar att den lokala datorn som är värd för RDS exponeras direkt för Internet.</span><span class="sxs-lookup"><span data-stu-id="e7da0-157">The gateway uses Transport Layer Security (TLS) to encrypt traffic and prevents the on-premises computer hosting RDS from being directly exposed to the Internet.</span></span>

![Anslutningar för fjärrskrivbordstjänster med gateway för fjärrskrivbordstjänster](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

<span data-ttu-id="e7da0-159">Mer information finns i [den här artikeln](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/).</span><span class="sxs-lookup"><span data-stu-id="e7da0-159">See [this article](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) for more information.</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="e7da0-160">Tekniska administrationsresurser för fjärråtkomst</span><span class="sxs-lookup"><span data-stu-id="e7da0-160">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="e7da0-161">Så här kan du snabbt optimera Office 365-trafik för fjärransluten personal och minska belastningen på infrastrukturen</span><span class="sxs-lookup"><span data-stu-id="e7da0-161">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="e7da0-162">Optimera Office 365-anslutningen för fjärranvändare med uppdelad VPN-tunnel</span><span class="sxs-lookup"><span data-stu-id="e7da0-162">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="results-of-step-2"></a><span data-ttu-id="e7da0-163">Resultat av steg 2</span><span class="sxs-lookup"><span data-stu-id="e7da0-163">Results of Step 2</span></span>

<span data-ttu-id="e7da0-164">Efter distribution av en lösning för fjärråtkomst för dina distansarbetare:</span><span class="sxs-lookup"><span data-stu-id="e7da0-164">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="e7da0-165">Konfigurationen för fjärråtkomst</span><span class="sxs-lookup"><span data-stu-id="e7da0-165">Remote access configuration</span></span> | <span data-ttu-id="e7da0-166">Resultat</span><span class="sxs-lookup"><span data-stu-id="e7da0-166">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="e7da0-167">En VPN-lösning för fjärråtkomst finns på plats</span><span class="sxs-lookup"><span data-stu-id="e7da0-167">A remote access VPN solution is in place</span></span> | <span data-ttu-id="e7da0-168">Du har konfigurerat VPN-klienten för fjärråtkomst för uppdelad tunnel och för optimeringskategori för Microsoft 365-slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="e7da0-168">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="e7da0-169">Ingen VPN-lösning för fjärråtkomst och du behöver endast fjärråtkomst till lokala webbaserade appar</span><span class="sxs-lookup"><span data-stu-id="e7da0-169">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="e7da0-170">Du har konfigurerat Azure Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="e7da0-170">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="e7da0-171">Ingen VPN-lösning för fjärråtkomst och du behöver åtkomst till lokala appar, vissa som inte är webbaserade</span><span class="sxs-lookup"><span data-stu-id="e7da0-171">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="e7da0-172">Du har konfigurerat Azure P2S VPN.</span><span class="sxs-lookup"><span data-stu-id="e7da0-172">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="e7da0-173">Distansarbetare använder sina personliga enheter från hemmet</span><span class="sxs-lookup"><span data-stu-id="e7da0-173">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="e7da0-174">Du har konfigurerat Windows Virtual Desktop.</span><span class="sxs-lookup"><span data-stu-id="e7da0-174">You have configured Windows Virtual Desktop.</span></span> |
| <span data-ttu-id="e7da0-175">Distansmedarbetare använder RDS-anslutningar i lokala system</span><span class="sxs-lookup"><span data-stu-id="e7da0-175">Remote workers are using RDS connections to on-premises systems</span></span> | <span data-ttu-id="e7da0-176">Du har distribuerat en gateway för fjärrskrivbordstjänster i Edge-nätverket.</span><span class="sxs-lookup"><span data-stu-id="e7da0-176">You have deployed a Remote Desktop Services gateway in your edge network.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="e7da0-177">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e7da0-177">Next step</span></span>

<span data-ttu-id="e7da0-178">[![Steg 3: Distribuera säkerhets- och efterlevnadstjänster med Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="e7da0-178">[![Step 3: Deploy Microsoft 365 security and compliance services](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span></span>

<span data-ttu-id="e7da0-179">Fortsätt med [Steg 3](empower-people-to-work-remotely-security-compliance.md) om du vill distribuera Microsoft 365 säkerhets och efterlevnadstjänster för att skydda appar, data och enheter.</span><span class="sxs-lookup"><span data-stu-id="e7da0-179">Continue with [Step 3](empower-people-to-work-remotely-security-compliance.md) to deploy Microsoft 365 security and compliance services to protect your apps, data, and devices.</span></span>