---
title: Distribuera federerad för hög tillgänglighet för Microsoft 365 i Azure
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
description: 'Sammanfattning: Konfigurera federerad för hög tillgänglighet för Microsoft 365-prenumerationen i Microsoft Azure.'
ms.openlocfilehash: abe01445b8963dcdc5693b45a680e273f5084446
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694685"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a><span data-ttu-id="7b89f-103">Distribuera federerad för hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="7b89f-103">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>

<span data-ttu-id="7b89f-104">Den här artikeln innehåller länkar till stegvisa instruktioner för hur du distribuerar federerad för extern tillgänglighet för Microsoft Microsoft 365 i Azure Infrastructure Services med de här virtuella datorerna:</span><span class="sxs-lookup"><span data-stu-id="7b89f-104">This article has links to the step-by-step instructions for deploying high availability federated authentication for Microsoft Microsoft 365 in Azure infrastructure services with these virtual machines:</span></span>
  
- <span data-ttu-id="7b89f-105">Två Webbprogramproxy</span><span class="sxs-lookup"><span data-stu-id="7b89f-105">Two web application proxy servers</span></span>
    
- <span data-ttu-id="7b89f-106">Två AD FS-servrar (Active Directory Federation Services)</span><span class="sxs-lookup"><span data-stu-id="7b89f-106">Two Active Directory Federation Services (AD FS) servers</span></span>
    
- <span data-ttu-id="7b89f-107">Två reservdomänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="7b89f-107">Two replica domain controllers</span></span>
    
- <span data-ttu-id="7b89f-108">En katalogpartition med Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="7b89f-108">One directory synchronization server running Azure AD Connect</span></span>
    
<span data-ttu-id="7b89f-109">Här är konfigurationen, med plats hållare för varje server.</span><span class="sxs-lookup"><span data-stu-id="7b89f-109">Here is the configuration, with placeholder names for each server.</span></span>
  
<span data-ttu-id="7b89f-110">**En federerad åtkomst med hög tillgänglighet för Microsoft 365-infrastrukturen i Azure**</span><span class="sxs-lookup"><span data-stu-id="7b89f-110">**A high availability federated authentication for Microsoft 365 infrastructure in Azure**</span></span>

![Den sista konfigurationen av infrastrukturen för extern tillgänglighet i Microsoft 365 i Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="7b89f-112">Alla virtuella datorer är i ett enda interlokalt Azure-virtuellt nätverk (VNet).</span><span class="sxs-lookup"><span data-stu-id="7b89f-112">All of the virtual machines are in a single cross-premises Azure virtual network (VNet).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7b89f-113">Federerad inloggningsautentisering för enskilda användare förlitar sig inte på lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="7b89f-113">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="7b89f-114">Men om den lokala anslutningen blir otillgänglig kommer domän kontrol Lanterna i VNet inte att få uppdateringar för användar konton och grupper som görs i den lokala Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7b89f-114">However, if the cross-premises connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="7b89f-115">För att säkerställa att detta inte sker kan du konfigurera hög tillgänglighet för din korslänkade förbindelse.</span><span class="sxs-lookup"><span data-stu-id="7b89f-115">To ensure this does not happen, you can configure high availability for your cross-premises connection.</span></span> <span data-ttu-id="7b89f-116">Mer information finns i [lättillgängliga kors lokala och VNET-till-VNet-anslutningar](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="7b89f-116">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="7b89f-117">Varje par med virtuella datorer för en viss roll är i dess eget undernät och tillgänglighets uppsättning.</span><span class="sxs-lookup"><span data-stu-id="7b89f-117">Each pair of virtual machines for a specific role is in its own subnet and availability set.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b89f-118">Eftersom den här VNet är ansluten till det lokala nätverket inkluderar den här konfigurationen inte hopp eller övervaka virtuella datorer i ett hanterings nät.</span><span class="sxs-lookup"><span data-stu-id="7b89f-118">Because this VNet is connected to the on-premises network, this configuration does not include jumpbox or monitoring virtual machines on a management subnet.</span></span> <span data-ttu-id="7b89f-119">Mer information finns i [köra Windows-VMS för en arkitektur med bara en nivå](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm).</span><span class="sxs-lookup"><span data-stu-id="7b89f-119">For more information, see [Running Windows VMs for an N-tier architecture](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm).</span></span> 
  
<span data-ttu-id="7b89f-120">Resultatet av denna konfiguration är att du har federerad autentisering för alla dina Microsoft 365-användare, där de kan använda sina AD DS-autentiseringsuppgifter för att logga in i stället för sitt Microsoft 365-konto.</span><span class="sxs-lookup"><span data-stu-id="7b89f-120">The result of this configuration is that you will have federated authentication for all of your Microsoft 365 users, in which they can use their AD DS credentials to sign in rather than their Microsoft 365 account.</span></span> <span data-ttu-id="7b89f-121">Infrastrukturen för federerad gästautentisering använder en redundant uppsättning servrar som är enklare att distribuera i Azure Infrastructure-tjänster, i stället för i ditt lokala Edge-nätverk.</span><span class="sxs-lookup"><span data-stu-id="7b89f-121">The federated authentication infrastructure uses a redundant set of servers that are more easily deployed in Azure infrastructure services, rather than in your on-premises edge network.</span></span>
  
## <a name="bill-of-materials"></a><span data-ttu-id="7b89f-122">Struktur lista</span><span class="sxs-lookup"><span data-stu-id="7b89f-122">Bill of materials</span></span>

<span data-ttu-id="7b89f-123">Denna bas linje konfiguration kräver följande uppsättning Azure-tjänster och-komponenter:</span><span class="sxs-lookup"><span data-stu-id="7b89f-123">This baseline configuration requires the following set of Azure services and components:</span></span>
  
- <span data-ttu-id="7b89f-124">Sju virtuella datorer</span><span class="sxs-lookup"><span data-stu-id="7b89f-124">Seven virtual machines</span></span>
    
- <span data-ttu-id="7b89f-125">Ett lokalt virtuellt nätverk med fyra undernät</span><span class="sxs-lookup"><span data-stu-id="7b89f-125">One cross-premises virtual network with four subnets</span></span>
    
- <span data-ttu-id="7b89f-126">Fyra resurs grupper</span><span class="sxs-lookup"><span data-stu-id="7b89f-126">Four resource groups</span></span>
    
- <span data-ttu-id="7b89f-127">Tre tillgänglighets uppsättningar</span><span class="sxs-lookup"><span data-stu-id="7b89f-127">Three availability sets</span></span>
    
- <span data-ttu-id="7b89f-128">Ett Azure-abonnemang</span><span class="sxs-lookup"><span data-stu-id="7b89f-128">One Azure subscription</span></span>
    
<span data-ttu-id="7b89f-129">Här är de virtuella datorerna och deras standard storlekar för denna konfiguration.</span><span class="sxs-lookup"><span data-stu-id="7b89f-129">Here are the virtual machines and their default sizes for this configuration.</span></span>
  
|<span data-ttu-id="7b89f-130">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="7b89f-130">**Item**</span></span>|<span data-ttu-id="7b89f-131">**Beskrivning av virtuell dator**</span><span class="sxs-lookup"><span data-stu-id="7b89f-131">**Virtual machine description**</span></span>|<span data-ttu-id="7b89f-132">**Bild av Azure-Galleri**</span><span class="sxs-lookup"><span data-stu-id="7b89f-132">**Azure gallery image**</span></span>|<span data-ttu-id="7b89f-133">**Standard storlek**</span><span class="sxs-lookup"><span data-stu-id="7b89f-133">**Default size**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b89f-134">1.</span><span class="sxs-lookup"><span data-stu-id="7b89f-134">1.</span></span>  <br/> |<span data-ttu-id="7b89f-135">Första domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="7b89f-135">First domain controller</span></span>  <br/> |<span data-ttu-id="7b89f-136">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="7b89f-136">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="7b89f-137">D2</span><span class="sxs-lookup"><span data-stu-id="7b89f-137">D2</span></span>  <br/> |
|<span data-ttu-id="7b89f-138">2.</span><span class="sxs-lookup"><span data-stu-id="7b89f-138">2.</span></span>  <br/> |<span data-ttu-id="7b89f-139">Andra domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="7b89f-139">Second domain controller</span></span>  <br/> |<span data-ttu-id="7b89f-140">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="7b89f-140">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="7b89f-141">D2</span><span class="sxs-lookup"><span data-stu-id="7b89f-141">D2</span></span>  <br/> |
|<span data-ttu-id="7b89f-142">3.</span><span class="sxs-lookup"><span data-stu-id="7b89f-142">3.</span></span>  <br/> |<span data-ttu-id="7b89f-143">Azure AD Connect-Server</span><span class="sxs-lookup"><span data-stu-id="7b89f-143">Azure AD Connect server</span></span>  <br/> |<span data-ttu-id="7b89f-144">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="7b89f-144">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="7b89f-145">D2</span><span class="sxs-lookup"><span data-stu-id="7b89f-145">D2</span></span>  <br/> |
|<span data-ttu-id="7b89f-146">4.</span><span class="sxs-lookup"><span data-stu-id="7b89f-146">4.</span></span>  <br/> |<span data-ttu-id="7b89f-147">Första AD FS server</span><span class="sxs-lookup"><span data-stu-id="7b89f-147">First AD FS server</span></span>  <br/> |<span data-ttu-id="7b89f-148">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="7b89f-148">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="7b89f-149">D2</span><span class="sxs-lookup"><span data-stu-id="7b89f-149">D2</span></span>  <br/> |
|<span data-ttu-id="7b89f-150">5.</span><span class="sxs-lookup"><span data-stu-id="7b89f-150">5.</span></span>  <br/> |<span data-ttu-id="7b89f-151">Andra AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="7b89f-151">Second AD FS server</span></span>  <br/> |<span data-ttu-id="7b89f-152">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="7b89f-152">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="7b89f-153">D2</span><span class="sxs-lookup"><span data-stu-id="7b89f-153">D2</span></span>  <br/> |
|<span data-ttu-id="7b89f-154">18.6.</span><span class="sxs-lookup"><span data-stu-id="7b89f-154">6.</span></span>  <br/> |<span data-ttu-id="7b89f-155">Första Webbprogramproxy</span><span class="sxs-lookup"><span data-stu-id="7b89f-155">First web application proxy server</span></span>  <br/> |<span data-ttu-id="7b89f-156">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="7b89f-156">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="7b89f-157">D2</span><span class="sxs-lookup"><span data-stu-id="7b89f-157">D2</span></span>  <br/> |
|<span data-ttu-id="7b89f-158">borttagning.</span><span class="sxs-lookup"><span data-stu-id="7b89f-158">7.</span></span>  <br/> |<span data-ttu-id="7b89f-159">Andra Webbprogramproxy</span><span class="sxs-lookup"><span data-stu-id="7b89f-159">Second web application proxy server</span></span>  <br/> |<span data-ttu-id="7b89f-160">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="7b89f-160">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="7b89f-161">D2</span><span class="sxs-lookup"><span data-stu-id="7b89f-161">D2</span></span>  <br/> |
   
<span data-ttu-id="7b89f-162">Information om hur du beräknar uppskattade kostnader för denna konfiguration finns i [Azure pris kalkylatorn](https://azure.microsoft.com/pricing/calculator/)</span><span class="sxs-lookup"><span data-stu-id="7b89f-162">To compute the estimated costs for this configuration, see the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/)</span></span>
  
## <a name="phases-of-deployment"></a><span data-ttu-id="7b89f-163">Faser i distributionen</span><span class="sxs-lookup"><span data-stu-id="7b89f-163">Phases of deployment</span></span>

<span data-ttu-id="7b89f-164">Du distribuerar denna arbets belastning i följande faser:</span><span class="sxs-lookup"><span data-stu-id="7b89f-164">You deploy this workload in the following phases:</span></span>
  
- <span data-ttu-id="7b89f-165">[Fas 1: Konfigurera Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="7b89f-165">[Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> <span data-ttu-id="7b89f-166">Skapa resurs grupper, lagrings konton, tillgänglighets uppsättningar och ett lokalt virtuellt nätverk.</span><span class="sxs-lookup"><span data-stu-id="7b89f-166">Create resource groups, storage accounts, availability sets, and a cross-premises virtual network.</span></span>
    
- <span data-ttu-id="7b89f-167">[Fas 2: Konfigurera domänkontrollanter](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="7b89f-167">[Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="7b89f-168">Skapa och konfigurera repliker för AD DS och server för katalogpartition.</span><span class="sxs-lookup"><span data-stu-id="7b89f-168">Create and configure replica AD DS domain controllers and the directory synchronization server.</span></span>
    
- <span data-ttu-id="7b89f-169">[Fas 3: Konfigurera AD FS-servrar](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span><span class="sxs-lookup"><span data-stu-id="7b89f-169">[Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="7b89f-170">Skapa och konfigurera de två AD FS-servrarna.</span><span class="sxs-lookup"><span data-stu-id="7b89f-170">Create and configure the two AD FS servers.</span></span>
    
- <span data-ttu-id="7b89f-171">[Fas 4: Konfigurera Webbprogramproxy](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span><span class="sxs-lookup"><span data-stu-id="7b89f-171">[Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="7b89f-172">Skapa och konfigurera de två webbprogramproxy.</span><span class="sxs-lookup"><span data-stu-id="7b89f-172">Create and configure the two web application proxy servers.</span></span>
    
- <span data-ttu-id="7b89f-173">[Fas 5: Konfigurera federerad auktorisering för Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span><span class="sxs-lookup"><span data-stu-id="7b89f-173">[Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="7b89f-174">Konfigurera federerad auktorisering för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="7b89f-174">Configure federated authentication for your Microsoft 365 subscription.</span></span>
    
<span data-ttu-id="7b89f-175">De här artiklarna innehåller en rikt linje för förhands instruktioner för en fördefinierad arkitektur för att skapa en funktionell, federerad inloggningsautentisering med hög tillgänglighet för Microsoft 365 i Azure Infrastructure Services.</span><span class="sxs-lookup"><span data-stu-id="7b89f-175">These articles provide a prescriptive, phase-by-phase guide for a predefined architecture to create a functional, high availability federated authentication for Microsoft 365 in Azure infrastructure services.</span></span> <span data-ttu-id="7b89f-176">Tänk på följande:</span><span class="sxs-lookup"><span data-stu-id="7b89f-176">Keep the following in mind:</span></span>
  
- <span data-ttu-id="7b89f-177">Om du är en erfaren AD FS-implementerare kan du anpassa instruktionerna i steg 3 och 4 och bygga den uppsättning servrar som bäst passar dina behov.</span><span class="sxs-lookup"><span data-stu-id="7b89f-177">If you are an experienced AD FS implementer, feel free to adapt the instructions in phases 3 and 4 and build the set of servers that best suits your needs.</span></span>
    
- <span data-ttu-id="7b89f-178">Om du redan har en befintlig Azure Hybrid Cloud-distribution med ett befintligt lokalt virtuellt nätverk, kan du helt enkelt anpassa eller hoppa över instruktionerna i steg 1 och 2 och placera AD FS-och Webbprogramproxy på de olika under näten.</span><span class="sxs-lookup"><span data-stu-id="7b89f-178">If you already have an existing Azure hybrid cloud deployment with an existing cross-premises virtual network, feel free to adapt or skip the instructions in phases 1 and 2 and place the AD FS and web application proxy servers on the appropriate subnets.</span></span>
    
<span data-ttu-id="7b89f-179">För att skapa en utvecklings-eller test miljö eller en proof-of-Concept av denna konfiguration, se [federerad identitet för din Microsoft 365-miljö](federated-identity-for-your-microsoft-365-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7b89f-179">To build a dev/test environment or a proof-of-concept of this configuration, see [Federated identity for your Microsoft 365 dev/test environment](federated-identity-for-your-microsoft-365-dev-test-environment.md).</span></span>
  
## <a name="next-step"></a><span data-ttu-id="7b89f-180">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7b89f-180">Next step</span></span>

<span data-ttu-id="7b89f-181">Starta konfigureringen av denna arbets belastning med [fas 1: Konfigurera Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="7b89f-181">Start the configuration of this workload with [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> 
  
