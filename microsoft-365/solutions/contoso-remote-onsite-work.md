---
title: Contosos COVID-19-svar och stöd för hybridarbete
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso Corporation besvarade COVID-19-installationen ochkompilerade deras programvaruinstallations- och uppdateringsinfrastruktur för hybridarbete.
ms.openlocfilehash: 2d28b0513221f6c14526baba69bf0f5986154805
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788385"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a><span data-ttu-id="8e005-103">Contosos COVID-19-svar och stöd för hybridarbete</span><span class="sxs-lookup"><span data-stu-id="8e005-103">Contoso's COVID-19 response and support for hybrid work</span></span>

<span data-ttu-id="8e005-104">Contoso hade alltid stöd för fjärranslutna medarbetare som hade åtkomst till lokala resurser via en central VPN-server i huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="8e005-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="8e005-105">Contoso hade utfärdat alla fjärranslutna medarbetare till en hanterad bärbar dator.</span><span class="sxs-lookup"><span data-stu-id="8e005-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="8e005-106">Lokala medarbetare hade en blandning av stationära och bärbara datorer.</span><span class="sxs-lookup"><span data-stu-id="8e005-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="8e005-107">Contosos svar till COVID-19</span><span class="sxs-lookup"><span data-stu-id="8e005-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="8e005-108">Med hjälp av COVID-19-personalen var plötsligt alla utom viktiga medarbetare fjärranslutna medarbetare.</span><span class="sxs-lookup"><span data-stu-id="8e005-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="8e005-109">Contoso har svarat genom att skifta arbetsstyrkan för att arbeta hemifrån och utföra sina primära aktiviteter via fjärråtkomst till lokala resurser och online med hjälp Microsoft 365 molntjänster.</span><span class="sxs-lookup"><span data-stu-id="8e005-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="8e005-110">Contoso hade fjärråtkomst till VPN-servrar i Paris huvudkontorskontor för att stödja 25 % av dess redan fjärranslutna arbetsstyrka, men flyttade snabbt för att öka dess fjärranslutna åtkomstkapacitet till 90 % av arbetsstyrkan.</span><span class="sxs-lookup"><span data-stu-id="8e005-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="8e005-111">Contoso distribuerade VPN-servrar för fjärråtkomst i varje satellitkontor så att fjärranslutna medarbetare skulle använda en regional stängningspunkt för åtkomst till Contoso-intranätet.</span><span class="sxs-lookup"><span data-stu-id="8e005-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="8e005-112">Contoso uppdaterade även konfigurationen av VPN-klienter som är installerade på bärbara datorer, surfplattor och smartphones för delade tunnlar så att trafiken för Optimera-uppsättningen av Office 365-slutpunkter kringgår VPN-anslutningen och skickas direkt via Internet.</span><span class="sxs-lookup"><span data-stu-id="8e005-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="8e005-113">Mer information finns i Optimera [Office 365 anslutningar för fjärranvändare med VPN-delade tunnlar.](../enterprise/microsoft-365-vpn-split-tunnel.md)</span><span class="sxs-lookup"><span data-stu-id="8e005-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="8e005-114">Här är den resulterande konfigurationen med VPN-enheter som installeras i paris huvudkontor och var och en av satellitkontoren.</span><span class="sxs-lookup"><span data-stu-id="8e005-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contosos VPN-infrastruktur](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="8e005-116">En fjärransluten anställd med den installerade VPN-klienten använder DNS för att hitta det regionala närmaste kontoret och ansluter till VPN-enheten som är installerad där.</span><span class="sxs-lookup"><span data-stu-id="8e005-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="8e005-117">Med delade tunnlar skickas trafik till Microsoft 365 och optimerar slutpunkter direkt till den region Microsoft 365 nätverksplatsen.</span><span class="sxs-lookup"><span data-stu-id="8e005-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="8e005-118">All annan trafik skickas via VPN-anslutningen till VPN-enheten.</span><span class="sxs-lookup"><span data-stu-id="8e005-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-hybrid-work"></a><span data-ttu-id="8e005-119">Contosos stöd för hybridarbete</span><span class="sxs-lookup"><span data-stu-id="8e005-119">Contoso’s support for hybrid work</span></span>

<span data-ttu-id="8e005-120">Efter att de initiala ändringarna gjorts för att stödja fjärranslutna medarbetare under regionala lockdowns gjorde Contoso infrastrukturändringar för att stödja hybridarbete där en anställd kan vara:</span><span class="sxs-lookup"><span data-stu-id="8e005-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support hybrid work in which a worker could be:</span></span>

- <span data-ttu-id="8e005-121">Alltid fjärrstyrd.</span><span class="sxs-lookup"><span data-stu-id="8e005-121">Always remote.</span></span>
- <span data-ttu-id="8e005-122">Alltid på plats.</span><span class="sxs-lookup"><span data-stu-id="8e005-122">Always onsite.</span></span>
- <span data-ttu-id="8e005-123">En kombination av olika platser och fjärranslutna platser.</span><span class="sxs-lookup"><span data-stu-id="8e005-123">A combination of onsite and remote.</span></span>

<span data-ttu-id="8e005-124">Microsoft 365 funktioner för identitet, säkerhet och efterlevnad är utformade för Zero Trust och att fungera oavsett var användaren och deras enhet finns.</span><span class="sxs-lookup"><span data-stu-id="8e005-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="8e005-125">Mer information finns i [Noll förtroende](https://www.microsoft.com/security/business/zero-trust).</span><span class="sxs-lookup"><span data-stu-id="8e005-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="8e005-126">Hantering av nya installationer och uppdateringar av programvara beror emellertid på enhetens plats, eftersom programvaran som ska installeras kan komma från en lokal eller en Internetkälla.</span><span class="sxs-lookup"><span data-stu-id="8e005-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="8e005-127">Contoso IT-arkitekter utformade sin nya installation och uppdaterar infrastruktur baserat på enhetens plats, istället för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="8e005-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="8e005-128">De har angett två typer av enheter: dedikerad lokal roaming och roaming.</span><span class="sxs-lookup"><span data-stu-id="8e005-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="8e005-129">Dedikerad lokalt</span><span class="sxs-lookup"><span data-stu-id="8e005-129">Dedicated on-premises</span></span>

<span data-ttu-id="8e005-130">En dedikerad lokal enhet är en stationär eller serverdator som aldrig lämnar Contoso-intranätet och inte har en VPN-klient installerad.</span><span class="sxs-lookup"><span data-stu-id="8e005-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="8e005-131">De här lokala enheterna fortsätter att använda Microsoft Endpoint Configuration Manager och dess distributionspunkter för installationer och uppdateringar av Windows 10, Microsoft 365-appar för företag och Edge.</span><span class="sxs-lookup"><span data-stu-id="8e005-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="8e005-132">Roaming</span><span class="sxs-lookup"><span data-stu-id="8e005-132">Roaming</span></span>

<span data-ttu-id="8e005-133">En roamingenhet kan lämna Contosos intranät och omfattar bärbara datorer som har utfärdats till många kontorsanställda och alla fjärranslutna medarbetare och andra organisationer ägda enheter, till exempel smartphones och surfplattor med Contoso VPN-klienten installerad.</span><span class="sxs-lookup"><span data-stu-id="8e005-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="8e005-134">Eftersom dessa enheter kan vara anslutna till Internet när som helst använder de Intune eller andra molnbaserade tjänster för installationer och uppdateringar av Windows 10, Microsoft 365-appar för företag och Edge.</span><span class="sxs-lookup"><span data-stu-id="8e005-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="8e005-135">De använder inte de befintliga distributionspunkterna i Konfigurationshanteraren lokalt.</span><span class="sxs-lookup"><span data-stu-id="8e005-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="8e005-136">Det innebär att vissa installationer och uppdateringar för roaming-enheter görs via Internet medan de är lokala och anslutna till intranätet.</span><span class="sxs-lookup"><span data-stu-id="8e005-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="8e005-137">Men Contoso IT-arkitekter valde att det är viktigare att göra konfigurationen enklare än optimering av bandbredden på internet på intranätet, särskilt när de flesta fjärranslutna medarbetare sällan är anslutna till intranätet.</span><span class="sxs-lookup"><span data-stu-id="8e005-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="8e005-138">Här är den resulterande infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="8e005-138">Here is the resulting infrastructure.</span></span>

![Infrastruktur för installationer och uppdateringar av Contosos](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="8e005-140">Installations- och uppdateringsbeteendet bestäms genom att datorkonton för enheter blir medlemmar i någon av följande grupper:</span><span class="sxs-lookup"><span data-stu-id="8e005-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="8e005-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="8e005-141">OnPremDevices</span></span>

  <span data-ttu-id="8e005-142">Konfigurationshanterarens klient på enheten använder distributionspunkter för installationer och uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8e005-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="8e005-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="8e005-143">RoamingDevices</span></span>

  <span data-ttu-id="8e005-144">Intune och andra inställningar på enheten anger hur nätverket Microsoft 365 för installationer och uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8e005-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="8e005-145">Ny registreringsprocess</span><span class="sxs-lookup"><span data-stu-id="8e005-145">New onboarding process</span></span>

<span data-ttu-id="8e005-146">För en ny dedikerad lokal enhet som utfärdats till en ny anställd eller för en ny server i ett datacenter laddar Configuration Manager-klienten, baserat på enhetens medlemskap i gruppen Lokala enheter, ned och installerar de senaste uppdateringarna för Windows 10, Microsoft 365-appar för företag och Edge från lokala konfigurationshanterarens distributionspunkter.</span><span class="sxs-lookup"><span data-stu-id="8e005-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="8e005-147">När det är klart är den dedikerade lokala enheten klar för användning och använder distributionspunkterna för pågående uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8e005-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="8e005-148">När en anställd loggar in på en ny fjärransluten enhet, baserat på medlemskap i gruppen RoamingDevices, kontaktar du intune-molntjänsten och andra tjänster och laddar ned och installerar de senaste uppdateringarna för Windows 10, Microsoft 365-appar för företag och Edge.</span><span class="sxs-lookup"><span data-stu-id="8e005-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="8e005-149">När det är klart är fjärrenheten redo att användas och använder den installerade VPN-klienten för åtkomst till lokala resurser och Microsoft 365 för pågående uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8e005-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="8e005-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8e005-150">Next step</span></span>

<span data-ttu-id="8e005-151">[Konfigurera infrastrukturen för hybridarbete](empower-people-to-work-remotely.md) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8e005-151">[Set up your infrastructure for hybrid work](empower-people-to-work-remotely.md) in your organization.</span></span>
