---
title: Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: Sammanfattning Konfigurera federerad autentisering med hög tillgänglighet för din Microsoft 365-prenumeration i Microsoft Azure.
ms.openlocfilehash: 3989ebb06b4ac5dfa1cded5e07c086c4778f94e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919158"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a><span data-ttu-id="bd53d-103">Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="bd53d-103">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>

<span data-ttu-id="bd53d-104">Den här artikeln innehåller länkar till stegvisa instruktioner för distribution av federerad autentisering med hög tillgänglighet för Microsoft Microsoft 365 i Azure-infrastrukturtjänster med dessa virtuella datorer:</span><span class="sxs-lookup"><span data-stu-id="bd53d-104">This article has links to the step-by-step instructions for deploying high availability federated authentication for Microsoft Microsoft 365 in Azure infrastructure services with these virtual machines:</span></span>
  
- <span data-ttu-id="bd53d-105">Två proxyservrar för webbprogram</span><span class="sxs-lookup"><span data-stu-id="bd53d-105">Two web application proxy servers</span></span>
    
- <span data-ttu-id="bd53d-106">Två AD FS-servrar (Active Directory Federation Services)</span><span class="sxs-lookup"><span data-stu-id="bd53d-106">Two Active Directory Federation Services (AD FS) servers</span></span>
    
- <span data-ttu-id="bd53d-107">Två replika domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="bd53d-107">Two replica domain controllers</span></span>
    
- <span data-ttu-id="bd53d-108">En katalogsynkroniseringsserver som kör Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="bd53d-108">One directory synchronization server running Azure AD Connect</span></span>
    
<span data-ttu-id="bd53d-109">Här är konfigurationen med platshållarnamn för varje server.</span><span class="sxs-lookup"><span data-stu-id="bd53d-109">Here is the configuration, with placeholder names for each server.</span></span>
  
<span data-ttu-id="bd53d-110">**En hög tillgänglighet federerad autentisering för Microsoft 365-infrastruktur i Azure**</span><span class="sxs-lookup"><span data-stu-id="bd53d-110">**A high availability federated authentication for Microsoft 365 infrastructure in Azure**</span></span>

![Den slutliga konfigurationen av microsoft 365-infrastrukturen för federerad autentisering med hög tillgänglighet i Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="bd53d-112">Alla virtuella maskiner finns i ett enda virtuellt Azure-nätverk (VNet).</span><span class="sxs-lookup"><span data-stu-id="bd53d-112">All of the virtual machines are in a single cross-premises Azure virtual network (VNet).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bd53d-113">Federerad autentisering av enskilda användare är inte beroende av några lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="bd53d-113">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="bd53d-114">Men om den tvärlokala anslutningen blir otillgänglig kommer domänkontrollanterna i det virtuella nätverket inte att få uppdateringar för användarkonton och grupper som gjorts i ad ds (Active Directory Domain Services) lokalt.</span><span class="sxs-lookup"><span data-stu-id="bd53d-114">However, if the cross-premises connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="bd53d-115">Du kan se till att det inte sker genom att konfigurera hög tillgänglighet för den lokala anslutningen.</span><span class="sxs-lookup"><span data-stu-id="bd53d-115">To ensure this does not happen, you can configure high availability for your cross-premises connection.</span></span> <span data-ttu-id="bd53d-116">Mer information finns i [Mycket tillgänglig, tvärlokal anslutning och VNet-till-VNet-anslutning](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="bd53d-116">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="bd53d-117">Varje par virtuella maskiner för en viss roll är i en egen undernät och tillgänglighetsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="bd53d-117">Each pair of virtual machines for a specific role is in its own subnet and availability set.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd53d-118">Eftersom det här VNet är anslutet till det lokala nätverket inkluderar den här konfigurationen inte jumpbox eller övervakning av virtuella maskiner på ett hanteringsundernät.</span><span class="sxs-lookup"><span data-stu-id="bd53d-118">Because this VNet is connected to the on-premises network, this configuration does not include jumpbox or monitoring virtual machines on a management subnet.</span></span> <span data-ttu-id="bd53d-119">Mer information finns i Köra [Windows VMs för en N-nivåarkitektur.](/azure/guidance/guidance-compute-n-tier-vm)</span><span class="sxs-lookup"><span data-stu-id="bd53d-119">For more information, see [Running Windows VMs for an N-tier architecture](/azure/guidance/guidance-compute-n-tier-vm).</span></span> 
  
<span data-ttu-id="bd53d-120">Resultatet av den här konfigurationen är att du har federerad autentisering för alla dina Microsoft 365-användare där de kan använda sina AD DS-autentiseringsuppgifter för att logga in i stället för sitt Microsoft 365-konto.</span><span class="sxs-lookup"><span data-stu-id="bd53d-120">The result of this configuration is that you will have federated authentication for all of your Microsoft 365 users, in which they can use their AD DS credentials to sign in rather than their Microsoft 365 account.</span></span> <span data-ttu-id="bd53d-121">Den externa autentiseringsinfrastrukturen använder en redundant uppsättning servrar som enklare distribueras i Azure-infrastrukturtjänster, i stället för i ditt lokala gränsnätverk.</span><span class="sxs-lookup"><span data-stu-id="bd53d-121">The federated authentication infrastructure uses a redundant set of servers that are more easily deployed in Azure infrastructure services, rather than in your on-premises edge network.</span></span>
  
## <a name="bill-of-materials"></a><span data-ttu-id="bd53d-122">Strukturlista</span><span class="sxs-lookup"><span data-stu-id="bd53d-122">Bill of materials</span></span>

<span data-ttu-id="bd53d-123">Den här baslinjekonfigurationen kräver följande uppsättning Azure-tjänster och -komponenter:</span><span class="sxs-lookup"><span data-stu-id="bd53d-123">This baseline configuration requires the following set of Azure services and components:</span></span>
  
- <span data-ttu-id="bd53d-124">Sju virtuella datorer</span><span class="sxs-lookup"><span data-stu-id="bd53d-124">Seven virtual machines</span></span>
    
- <span data-ttu-id="bd53d-125">Ett virtuellt korslokalt nätverk med fyra undernät</span><span class="sxs-lookup"><span data-stu-id="bd53d-125">One cross-premises virtual network with four subnets</span></span>
    
- <span data-ttu-id="bd53d-126">Fyra resursgrupper</span><span class="sxs-lookup"><span data-stu-id="bd53d-126">Four resource groups</span></span>
    
- <span data-ttu-id="bd53d-127">Tre tillgänglighetsuppsättningar</span><span class="sxs-lookup"><span data-stu-id="bd53d-127">Three availability sets</span></span>
    
- <span data-ttu-id="bd53d-128">En Azure-prenumeration</span><span class="sxs-lookup"><span data-stu-id="bd53d-128">One Azure subscription</span></span>
    
<span data-ttu-id="bd53d-129">Här är de virtuella maskinerna och deras standardstorlekar för den här konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="bd53d-129">Here are the virtual machines and their default sizes for this configuration.</span></span>
  
|<span data-ttu-id="bd53d-130">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="bd53d-130">**Item**</span></span>|<span data-ttu-id="bd53d-131">**Beskrivning av virtuell dator**</span><span class="sxs-lookup"><span data-stu-id="bd53d-131">**Virtual machine description**</span></span>|<span data-ttu-id="bd53d-132">**Azure-galleribild**</span><span class="sxs-lookup"><span data-stu-id="bd53d-132">**Azure gallery image**</span></span>|<span data-ttu-id="bd53d-133">**Standardstorlek**</span><span class="sxs-lookup"><span data-stu-id="bd53d-133">**Default size**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd53d-134">1.</span><span class="sxs-lookup"><span data-stu-id="bd53d-134">1.</span></span>  <br/> |<span data-ttu-id="bd53d-135">Första domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="bd53d-135">First domain controller</span></span>  <br/> |<span data-ttu-id="bd53d-136">Windows Server 2016-datacenter</span><span class="sxs-lookup"><span data-stu-id="bd53d-136">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="bd53d-137">D2</span><span class="sxs-lookup"><span data-stu-id="bd53d-137">D2</span></span>  <br/> |
|<span data-ttu-id="bd53d-138">2.</span><span class="sxs-lookup"><span data-stu-id="bd53d-138">2.</span></span>  <br/> |<span data-ttu-id="bd53d-139">Andra domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="bd53d-139">Second domain controller</span></span>  <br/> |<span data-ttu-id="bd53d-140">Windows Server 2016-datacenter</span><span class="sxs-lookup"><span data-stu-id="bd53d-140">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="bd53d-141">D2</span><span class="sxs-lookup"><span data-stu-id="bd53d-141">D2</span></span>  <br/> |
|<span data-ttu-id="bd53d-142">3.</span><span class="sxs-lookup"><span data-stu-id="bd53d-142">3.</span></span>  <br/> |<span data-ttu-id="bd53d-143">Azure AD Connect-server</span><span class="sxs-lookup"><span data-stu-id="bd53d-143">Azure AD Connect server</span></span>  <br/> |<span data-ttu-id="bd53d-144">Windows Server 2016-datacenter</span><span class="sxs-lookup"><span data-stu-id="bd53d-144">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="bd53d-145">D2</span><span class="sxs-lookup"><span data-stu-id="bd53d-145">D2</span></span>  <br/> |
|<span data-ttu-id="bd53d-146">4.</span><span class="sxs-lookup"><span data-stu-id="bd53d-146">4.</span></span>  <br/> |<span data-ttu-id="bd53d-147">First AD FS server</span><span class="sxs-lookup"><span data-stu-id="bd53d-147">First AD FS server</span></span>  <br/> |<span data-ttu-id="bd53d-148">Windows Server 2016-datacenter</span><span class="sxs-lookup"><span data-stu-id="bd53d-148">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="bd53d-149">D2</span><span class="sxs-lookup"><span data-stu-id="bd53d-149">D2</span></span>  <br/> |
|<span data-ttu-id="bd53d-150">5.</span><span class="sxs-lookup"><span data-stu-id="bd53d-150">5.</span></span>  <br/> |<span data-ttu-id="bd53d-151">Second AD FS server</span><span class="sxs-lookup"><span data-stu-id="bd53d-151">Second AD FS server</span></span>  <br/> |<span data-ttu-id="bd53d-152">Windows Server 2016-datacenter</span><span class="sxs-lookup"><span data-stu-id="bd53d-152">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="bd53d-153">D2</span><span class="sxs-lookup"><span data-stu-id="bd53d-153">D2</span></span>  <br/> |
|<span data-ttu-id="bd53d-154">6.</span><span class="sxs-lookup"><span data-stu-id="bd53d-154">6.</span></span>  <br/> |<span data-ttu-id="bd53d-155">First web application proxy server</span><span class="sxs-lookup"><span data-stu-id="bd53d-155">First web application proxy server</span></span>  <br/> |<span data-ttu-id="bd53d-156">Windows Server 2016-datacenter</span><span class="sxs-lookup"><span data-stu-id="bd53d-156">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="bd53d-157">D2</span><span class="sxs-lookup"><span data-stu-id="bd53d-157">D2</span></span>  <br/> |
|<span data-ttu-id="bd53d-158">7.</span><span class="sxs-lookup"><span data-stu-id="bd53d-158">7.</span></span>  <br/> |<span data-ttu-id="bd53d-159">Andra webbprogramproxyservern</span><span class="sxs-lookup"><span data-stu-id="bd53d-159">Second web application proxy server</span></span>  <br/> |<span data-ttu-id="bd53d-160">Windows Server 2016-datacenter</span><span class="sxs-lookup"><span data-stu-id="bd53d-160">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="bd53d-161">D2</span><span class="sxs-lookup"><span data-stu-id="bd53d-161">D2</span></span>  <br/> |
   
<span data-ttu-id="bd53d-162">Information om beräknade kostnader för den här konfigurationen finns i [Azure-priskalkylatorn](https://azure.microsoft.com/pricing/calculator/)</span><span class="sxs-lookup"><span data-stu-id="bd53d-162">To compute the estimated costs for this configuration, see the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/)</span></span>
  
## <a name="phases-of-deployment"></a><span data-ttu-id="bd53d-163">Faser i distributionen</span><span class="sxs-lookup"><span data-stu-id="bd53d-163">Phases of deployment</span></span>

<span data-ttu-id="bd53d-164">Du distribuerar arbetsbelastningen i följande faser:</span><span class="sxs-lookup"><span data-stu-id="bd53d-164">You deploy this workload in the following phases:</span></span>
  
- <span data-ttu-id="bd53d-165">[Fas 1: Konfigurera Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="bd53d-165">[Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> <span data-ttu-id="bd53d-166">Skapa resursgrupper, lagringskonton, tillgänglighetsuppsättningar och ett virtuellt nätverk på flera platser.</span><span class="sxs-lookup"><span data-stu-id="bd53d-166">Create resource groups, storage accounts, availability sets, and a cross-premises virtual network.</span></span>
    
- <span data-ttu-id="bd53d-167">[Fas 2: Konfigurera domänkontrollanter](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="bd53d-167">[Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="bd53d-168">Skapa och konfigurera replika AD DS-domänkontrollanter och katalogsynkroniseringsservern.</span><span class="sxs-lookup"><span data-stu-id="bd53d-168">Create and configure replica AD DS domain controllers and the directory synchronization server.</span></span>
    
- <span data-ttu-id="bd53d-169">[Fas 3: Konfigurera AD FS-servrar.](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)</span><span class="sxs-lookup"><span data-stu-id="bd53d-169">[Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="bd53d-170">Skapa och konfigurera de två AD FS-servrarna.</span><span class="sxs-lookup"><span data-stu-id="bd53d-170">Create and configure the two AD FS servers.</span></span>
    
- <span data-ttu-id="bd53d-171">[Fas 4: Konfigurera proxyprogram för webbprogram.](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)</span><span class="sxs-lookup"><span data-stu-id="bd53d-171">[Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="bd53d-172">Skapa och konfigurera de två proxyservrarna för webbprogram.</span><span class="sxs-lookup"><span data-stu-id="bd53d-172">Create and configure the two web application proxy servers.</span></span>
    
- <span data-ttu-id="bd53d-173">[Fas 5: Konfigurera federerad autentisering för Microsoft 365.](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)</span><span class="sxs-lookup"><span data-stu-id="bd53d-173">[Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="bd53d-174">Konfigurera federerad autentisering för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="bd53d-174">Configure federated authentication for your Microsoft 365 subscription.</span></span>
    
<span data-ttu-id="bd53d-175">I de här artiklarna finns en fördefinierad, fas för fas-guide för en fördefinierad arkitektur för att skapa en funktionell, federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure-infrastrukturtjänster.</span><span class="sxs-lookup"><span data-stu-id="bd53d-175">These articles provide a prescriptive, phase-by-phase guide for a predefined architecture to create a functional, high availability federated authentication for Microsoft 365 in Azure infrastructure services.</span></span> <span data-ttu-id="bd53d-176">Tänk på följande:</span><span class="sxs-lookup"><span data-stu-id="bd53d-176">Keep the following in mind:</span></span>
  
- <span data-ttu-id="bd53d-177">Om du är en erfaren AD FS-implementerare kan du anpassa instruktionerna i fas 3 och 4 och bygga den uppsättning servrar som bäst passar dina behov.</span><span class="sxs-lookup"><span data-stu-id="bd53d-177">If you are an experienced AD FS implementer, feel free to adapt the instructions in phases 3 and 4 and build the set of servers that best suits your needs.</span></span>
    
- <span data-ttu-id="bd53d-178">Om du redan har en befintlig Azure-hybridmolndistribution med ett befintligt virtuellt korslokalt nätverk kan du anpassa eller hoppa över instruktionerna i faserna 1 och 2 och placera AD FS- och webbprogramproxyservrarna på lämpliga undernät.</span><span class="sxs-lookup"><span data-stu-id="bd53d-178">If you already have an existing Azure hybrid cloud deployment with an existing cross-premises virtual network, feel free to adapt or skip the instructions in phases 1 and 2 and place the AD FS and web application proxy servers on the appropriate subnets.</span></span>
    
<span data-ttu-id="bd53d-179">Information om hur du skapar en utvecklings-/testmiljö eller ett koncepttest för den här konfigurationen finns i Federerad identitet för [utvecklings-/testmiljön för Microsoft 365.](federated-identity-for-your-microsoft-365-dev-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="bd53d-179">To build a dev/test environment or a proof-of-concept of this configuration, see [Federated identity for your Microsoft 365 dev/test environment](federated-identity-for-your-microsoft-365-dev-test-environment.md).</span></span>
  
## <a name="next-step"></a><span data-ttu-id="bd53d-180">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bd53d-180">Next step</span></span>

<span data-ttu-id="bd53d-181">Börja konfigurationen av den här arbetsbelastningen [med steg 1: Konfigurera Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="bd53d-181">Start the configuration of this workload with [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> 
