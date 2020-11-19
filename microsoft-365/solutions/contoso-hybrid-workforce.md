---
title: Contosos COVID – 19 svar och support för en hybrid arbets styrka
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso Corporation svarade på COVID-19 Pandemic och har utvecklat sina program varu installationer och uppdatera infrastrukturen för en hybrid arbets styrka.
ms.openlocfilehash: a29ffee1413f60da30ad34aa62ca465ca16e0430
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357975"
---
# <a name="contosos-covid-19-response-and-support-for-a-hybrid-workforce"></a><span data-ttu-id="d0f22-103">Contosos COVID – 19 svar och support för en hybrid arbets styrka</span><span class="sxs-lookup"><span data-stu-id="d0f22-103">Contoso's COVID-19 response and support for a hybrid workforce</span></span>

<span data-ttu-id="d0f22-104">Contoso hade alltid stöd för sina fjärranställda, vilka kom åt lokala resurser via en central VPN-server i Paris huvud gruppen.</span><span class="sxs-lookup"><span data-stu-id="d0f22-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="d0f22-105">Contoso hade utfärdat alla fjärranslutna kollegor till en hanterad bärbar dator.</span><span class="sxs-lookup"><span data-stu-id="d0f22-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="d0f22-106">Lokala arbetare hade en blandning av Station ära och bärbara datorer.</span><span class="sxs-lookup"><span data-stu-id="d0f22-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="d0f22-107">Contosos svar till COVID-19</span><span class="sxs-lookup"><span data-stu-id="d0f22-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="d0f22-108">Med COVID-19-pandemics fast alla som är avgörande för arbets tagarna.</span><span class="sxs-lookup"><span data-stu-id="d0f22-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="d0f22-109">Contoso svarade genom att ändra dess arbets styrka för att arbeta hemifrån och genomföra dess primära aktiviteter via fjärråtkomst till lokala resurser och online med Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="d0f22-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="d0f22-110">Contoso hade VPN-servrar för fjärråtkomst på Paris huvud kontoret för att stödja 25% av dess redan fjärranställda, men snabbt flyttad för att skala upp den för att kunna hantera 90% av dess arbets styrka.</span><span class="sxs-lookup"><span data-stu-id="d0f22-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="d0f22-111">Contoso distribuerade VPN-servrar för fjärråtkomst på varje satellit kontor så att fjärranslutna användare kan använda en regionalt avstängnings punkt för åtkomst till Contosos intranät.</span><span class="sxs-lookup"><span data-stu-id="d0f22-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="d0f22-112">Contoso har också uppdaterat konfigurationen för VPN-klienter som är installerade på bärbara datorer, surfplattor och fasta telefoner för delade tunnlar så att trafik för optimering av Office 365-slutpunkter kringgår VPN-anslutningen och har skickats direkt via Internet.</span><span class="sxs-lookup"><span data-stu-id="d0f22-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="d0f22-113">Mer information finns i [optimera Office 365-anslutningar för fjärran vändare via VPN-delning](../enterprise/microsoft-365-vpn-split-tunnel.md).</span><span class="sxs-lookup"><span data-stu-id="d0f22-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="d0f22-114">Här är den resulterande konfigurationen med VPN-enheter som är installerade i Paris huvud gruppen och vart och ett av satellit kontoren.</span><span class="sxs-lookup"><span data-stu-id="d0f22-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contosos VPN-infrastruktur](../media/contoso-hybrid-workforce/contoso-vpn-infrastructure.png)

<span data-ttu-id="d0f22-116">En fjärran sluten anställd med den installerade VPN-klienten använder DNS för att hitta det regionala närmaste kontoret och ansluter till den VPN-enhet som är installerad där.</span><span class="sxs-lookup"><span data-stu-id="d0f22-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="d0f22-117">Med delade tunnlar kan trafik till Microsoft 365 optimera slut punkter direkt till den regionala närmast Microsoft 365-nätverks platsen.</span><span class="sxs-lookup"><span data-stu-id="d0f22-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="d0f22-118">All annan trafik skickas via VPN-anslutningen till VPN-enheten.</span><span class="sxs-lookup"><span data-stu-id="d0f22-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-a-dynamic-hybrid-workforce"></a><span data-ttu-id="d0f22-119">Organisationens support för en dynamisk hybrid arbets styrka</span><span class="sxs-lookup"><span data-stu-id="d0f22-119">Contoso’s support for a dynamic hybrid workforce</span></span>

<span data-ttu-id="d0f22-120">Efter det att de ursprungliga ändringarna har gjorts till stöd som var och en av de flesta fjärranställdaer under regionala låsningar, har contoso infrastruktur ändringar för att stödja en hybrid arbets styrka där en anställd kan vara:</span><span class="sxs-lookup"><span data-stu-id="d0f22-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support a hybrid workforce in which a worker could be:</span></span>

- <span data-ttu-id="d0f22-121">Alltid fjärr.</span><span class="sxs-lookup"><span data-stu-id="d0f22-121">Always remote.</span></span>
- <span data-ttu-id="d0f22-122">Alltid lokal.</span><span class="sxs-lookup"><span data-stu-id="d0f22-122">Always on-premises.</span></span>
- <span data-ttu-id="d0f22-123">En kombination av fjär och lokal.</span><span class="sxs-lookup"><span data-stu-id="d0f22-123">A combination of remote and on-premises.</span></span>

<span data-ttu-id="d0f22-124">Microsoft 365-funktioner för identitet, säkerhet och efterlevnad är avsedda för noll och fungerar oberoende av användarens och enhetens plats.</span><span class="sxs-lookup"><span data-stu-id="d0f22-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="d0f22-125">Mer information finns i avsnittet [noll](https://www.microsoft.com/security/business/zero-trust).</span><span class="sxs-lookup"><span data-stu-id="d0f22-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="d0f22-126">Men hanteringen av nya installationer och uppdateringar av program vara beror på enhetens plats eftersom program varan som installeras kan komma från en lokal eller Internet källa.</span><span class="sxs-lookup"><span data-stu-id="d0f22-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="d0f22-127">Contoso IT Architects utformade sina nya installationer och uppdaterar infrastrukturen baserat på enhetens plats i stället för i arbetaren.</span><span class="sxs-lookup"><span data-stu-id="d0f22-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="d0f22-128">De har utsett två typer av enheter: dedikerade lokala och roaming.</span><span class="sxs-lookup"><span data-stu-id="d0f22-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="d0f22-129">Dedikerad lokal</span><span class="sxs-lookup"><span data-stu-id="d0f22-129">Dedicated on-premises</span></span>

<span data-ttu-id="d0f22-130">En dedikerad lokal enhet är en stationär eller serverdator som aldrig lämnar Contosos intranät och inte har någon VPN-klient installerad.</span><span class="sxs-lookup"><span data-stu-id="d0f22-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="d0f22-131">Dessa lokala enheter fortsätter att använda Microsoft Endpoint Configuration Manager och dess distributions platser för installationer och uppdateringar av Windows 10, Microsoft 365-appar för företag och Edge browser.</span><span class="sxs-lookup"><span data-stu-id="d0f22-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="d0f22-132">Roaming</span><span class="sxs-lookup"><span data-stu-id="d0f22-132">Roaming</span></span>

<span data-ttu-id="d0f22-133">En central enhet kan lämna Contosos intranät och inkluderar bärbara datorer som utfärdas till många kontors kollegor och alla andra organisations ägda enheter, till exempel telefoner och surfplattor med contoso VPN-klient installerad.</span><span class="sxs-lookup"><span data-stu-id="d0f22-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="d0f22-134">Eftersom dessa enheter kan anslutas till Internet samtidigt använder de Intune eller andra molnbaserade tjänster för installation och uppdateringar av Windows 10, Microsoft 365-appar för företag och Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f22-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="d0f22-135">De använder inte befintliga lokala Configuration Manager-distributionslistor.</span><span class="sxs-lookup"><span data-stu-id="d0f22-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="d0f22-136">Det innebär att vissa installationer och uppdateringar för centrala enheter utförs via Internet medan de är lokala och anslutna till intranätet.</span><span class="sxs-lookup"><span data-stu-id="d0f22-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="d0f22-137">Men contoso IT Architects bestämde att det är enkelt att konfigurera, än att kunna optimera bandbredden på intranätet till Internet, särskilt när de flesta fjärranställda inte är anslutna till intranätet.</span><span class="sxs-lookup"><span data-stu-id="d0f22-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="d0f22-138">Här är den resulterande infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="d0f22-138">Here is the resulting infrastructure.</span></span>

![Organisationens installationer och uppdateringar](../media/contoso-hybrid-workforce/contoso-updates-infrastructure.png)

<span data-ttu-id="d0f22-140">Installations-och uppdaterings beteende fastställs genom att göra dator konton för enheter till medlemmar i en av dessa grupper:</span><span class="sxs-lookup"><span data-stu-id="d0f22-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="d0f22-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="d0f22-141">OnPremDevices</span></span>

  <span data-ttu-id="d0f22-142">Configuration Manager-klienten på enheten använder distributions platser för installationer och uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="d0f22-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="d0f22-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="d0f22-143">RoamingDevices</span></span>

  <span data-ttu-id="d0f22-144">Intune och andra inställningar på enheten anger hur Microsoft 365-nätverket används för installationer och uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="d0f22-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="d0f22-145">Ny registrerings process</span><span class="sxs-lookup"><span data-stu-id="d0f22-145">New onboarding process</span></span>

<span data-ttu-id="d0f22-146">För att en ny dedikerad lokal enhet ska utfärdas till en ny anställd eller för en ny server i ett Data Center, när en användare loggar in, kan Configuration Manager-klienten baserat på enhetens medlemskap i OnPremDevices-gruppen Ladda ned och installera de senaste uppdateringarna för Windows 10, Microsoft 365-appar för företag och Edge från lokala Configuration Manager-distributionslistor.</span><span class="sxs-lookup"><span data-stu-id="d0f22-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="d0f22-147">När det är klart är den dedikerade lokala enheten klar för användning och använder dessa distributions platser för pågående uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="d0f22-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="d0f22-148">För en ny fjär renhet som utfärdas till en ny anställd, när en arbets tagare loggar in, beror på dess medlemskap i gruppen RoamingDevices, kontaktar Intune-molnet och andra tjänster och laddar ned och installerar de senaste uppdateringarna för Windows 10, Microsoft 365-appar för företag och Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f22-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="d0f22-149">När det är klart är fjär renheten klar för användning och använder den installerade VPN-klienten för åtkomst till lokala resurser och Microsoft 365-nätverket för pågående uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="d0f22-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="d0f22-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d0f22-150">Next step</span></span>

<span data-ttu-id="d0f22-151">Ge [fjärranställda](empower-people-to-work-remotely.md) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d0f22-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>
