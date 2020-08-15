---
title: Distribuera Microsoft 365-profilsynkronisering i Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Lär dig hur du distribuerar Azure AD Connect på en virtuell dator i Azure för att synkronisera konton mellan den lokala katalogen och Azure AD-klienten.
ms.openlocfilehash: 8db78d20ee4c2186918a0b3b433f8f0ae056816e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694681"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a><span data-ttu-id="f6856-103">Distribuera Microsoft 365-profilsynkronisering i Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="f6856-103">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>

<span data-ttu-id="f6856-104">Azure Active Directory (Azure AD) Connect (kallades tidigare verktyg för katalog, katalog eller DirSync.exe) är ett program som du installerar på en domänansluten Server för att synkronisera dina lokala Active Directory Domain Services-användare i din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="f6856-104">Azure Active Directory (Azure AD) Connect (formerly known as the Directory Synchronization tool, Directory Sync tool, or the DirSync.exe tool) is an application that you install on a domain-joined server to synchronize your on-premises Active Directory Domain Services (AD DS) users to the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="f6856-105">Microsoft 365 använder Azure AD för sin katalog tjänst.</span><span class="sxs-lookup"><span data-stu-id="f6856-105">Microsoft 365 uses Azure AD for its directory service.</span></span> <span data-ttu-id="f6856-106">Ditt Microsoft 365-abonnemang inkluderar en Azure AD-klient.</span><span class="sxs-lookup"><span data-stu-id="f6856-106">Your Microsoft 365 subscription includes an Azure AD tenant.</span></span> <span data-ttu-id="f6856-107">Denna klient organisation kan även användas för att hantera din företags identitet med andra moln arbets belastningar, inklusive andra SaaS-program och appar i Azure.</span><span class="sxs-lookup"><span data-stu-id="f6856-107">This tenant can also be used for management of your organization's identities with other cloud workloads, including other SaaS applications and apps in Azure.</span></span>

<span data-ttu-id="f6856-108">Du kan installera Azure AD Connect på en lokal server, men du kan även installera den på en virtuell dator i Azure av följande anledningar:</span><span class="sxs-lookup"><span data-stu-id="f6856-108">You can install Azure AD Connect on a on-premises server, but you can also install it on a virtual machine in Azure for these reasons:</span></span>
  
- <span data-ttu-id="f6856-109">Du kan etablera och konfigurera molnbaserade servrar snabbare, vilket gör tjänsterna tillgängliga för dina användare fortare.</span><span class="sxs-lookup"><span data-stu-id="f6856-109">You can provision and configure cloud-based servers faster, making the services available to your users sooner.</span></span>
- <span data-ttu-id="f6856-110">Azure erbjuder bättre tillgänglighet för webbplatsen med mindre ansträngning.</span><span class="sxs-lookup"><span data-stu-id="f6856-110">Azure offers better site availability with less effort.</span></span>
- <span data-ttu-id="f6856-111">Du kan minska antalet lokala servrar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f6856-111">You can reduce the number of on-premises servers in your organization.</span></span>

<span data-ttu-id="f6856-112">Denna lösning kräver anslutning mellan det lokala nätverket och det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="f6856-112">This solution requires connectivity between your on-premises network and your Azure virtual network.</span></span> <span data-ttu-id="f6856-113">Mer information finns i [ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="f6856-113">For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f6856-114">I den här artikeln beskrivs synkronisering av en enda domän i en enda skog.</span><span class="sxs-lookup"><span data-stu-id="f6856-114">This article describes synchronization of a single domain in a single forest.</span></span> <span data-ttu-id="f6856-115">Azure AD Connect synkroniserar alla AD DS-domäner i din Active Directory-skog med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6856-115">Azure AD Connect synchronizes all AD DS domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="f6856-116">Om du har flera Active Directory-skogar att synkronisera med Microsoft 365 kan du läsa mer i [katalog för flera skogar med enkel inloggning](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span><span class="sxs-lookup"><span data-stu-id="f6856-116">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span></span> 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a><span data-ttu-id="f6856-117">Översikt över distribution av synkronisering av Microsoft 365-katalog i Azure</span><span class="sxs-lookup"><span data-stu-id="f6856-117">Overview of deploying Microsoft 365 directory synchronization in Azure</span></span>

<span data-ttu-id="f6856-118">Följande diagram visar hur Azure AD Connect körs på en virtuell dator i Azure (den katalogpartition som synkroniserar en lokal AD DS-skog till en Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="f6856-118">The following diagram shows Azure AD Connect running on a virtual machine in Azure (the directory sync server) that synchronizes an on-premises AD DS forest to a Microsoft 365 subscription.</span></span>
  
![Azure AD Connect-verktyg på en virtuell dator i Azure-synkronisering av lokala konton till Azure AD-klient organisationen för en Microsoft 365-prenumeration med trafikflöde](../media/CP-DirSyncOverview.png)
  
<span data-ttu-id="f6856-120">I diagrammet finns det två nätverk anslutna via plats-till-plats-ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="f6856-120">In the diagram, there are two networks connected by a site-to-site VPN or ExpressRoute connection.</span></span> <span data-ttu-id="f6856-121">Det finns ett lokalt nätverk där AD DS-domänkontrollanter finns och det finns ett Azure Virtual Network med en katalogpartition som är en virtuell dator med [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span><span class="sxs-lookup"><span data-stu-id="f6856-121">There is an on-premises network where AD DS domain controllers are located, and there is an Azure virtual network with a directory sync server, which is a virtual machine running [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span> <span data-ttu-id="f6856-122">Det finns två huvudsakliga trafik flöden som kommer från katalogen Sync-servern:</span><span class="sxs-lookup"><span data-stu-id="f6856-122">There are two main traffic flows originating from the directory sync server:</span></span>
  
-  <span data-ttu-id="f6856-123">Azure AD Connect frågar en domänkontrollant i det lokala nätverket för att ändra konto och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="f6856-123">Azure AD Connect queries a domain controller on the on-premises network for changes to accounts and passwords.</span></span>
-  <span data-ttu-id="f6856-124">Azure AD Connect skickar ändringarna till konton och lösen ord till Azure AD-instansen av ditt Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="f6856-124">Azure AD Connect sends the changes to accounts and passwords to the Azure AD instance of your Microsoft 365 subscription.</span></span> <span data-ttu-id="f6856-125">Eftersom den här servern finns i en längre del av ditt lokala nätverk, skickas dessa ändringar via det lokala nätverkets proxyserver.</span><span class="sxs-lookup"><span data-stu-id="f6856-125">Because the directory sync server is in an extended portion of your on-premises network, these changes are sent through the on-premises network's proxy server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f6856-126">Den här lösningen beskriver synkronisering av en enda Active Directory-domän i en enda Active Directory-skog.</span><span class="sxs-lookup"><span data-stu-id="f6856-126">This solution describes synchronization of a single Active Directory domain, in a single Active Directory forest.</span></span> <span data-ttu-id="f6856-127">Azure AD Connect synkroniserar alla Active Directory-domäner i din Active Directory-skog med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6856-127">Azure AD Connect synchronizes all Active Directory domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="f6856-128">Om du har flera Active Directory-skogar att synkronisera med Microsoft 365 kan du läsa mer i [katalog för flera skogar med enkel inloggning](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span><span class="sxs-lookup"><span data-stu-id="f6856-128">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span></span> 
  
<span data-ttu-id="f6856-129">Det finns två huvudsakliga steg när du distribuerar den här lösningen:</span><span class="sxs-lookup"><span data-stu-id="f6856-129">There are two major steps when you deploy this solution:</span></span>
  
1. <span data-ttu-id="f6856-130">Skapa ett Azure Virtual Network och etablera en VPN-anslutning för ett lokalt nätverk.</span><span class="sxs-lookup"><span data-stu-id="f6856-130">Create an Azure virtual network and establish a site-to-site VPN connection to your on-premises network.</span></span> <span data-ttu-id="f6856-131">Mer information finns i [ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="f6856-131">For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
    
2. <span data-ttu-id="f6856-132">Installera [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) på en domänansluten virtuell dator i Azure och synkronisera sedan den lokala AD DS till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6856-132">Install [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) on a domain-joined virtual machine in Azure, and then synchronize the on-premises AD DS to Microsoft 365.</span></span> <span data-ttu-id="f6856-133">Detta gäller:</span><span class="sxs-lookup"><span data-stu-id="f6856-133">This involves:</span></span>
    
    <span data-ttu-id="f6856-134">Skapa en virtuell Azure-dator för att köra Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="f6856-134">Creating an Azure Virtual Machine to run Azure AD Connect.</span></span>
    
    <span data-ttu-id="f6856-135">Installerar och konfigurerar [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span><span class="sxs-lookup"><span data-stu-id="f6856-135">Installing and configuring [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span>
    
    <span data-ttu-id="f6856-136">Konfiguration av Azure AD Connect kräver autentiseringsuppgifterna (användar namn och lösen ord) för ett Azure AD-administratörskonto och ett AD DS-konto för företags administratör.</span><span class="sxs-lookup"><span data-stu-id="f6856-136">Configuring Azure AD Connect requires the credentials (user name and password) of an Azure AD administrator account and a AD DS enterprise administrator account.</span></span> <span data-ttu-id="f6856-137">Azure AD Connect körs omedelbart och fort löp ande för att synkronisera den lokala AD DS-skogen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6856-137">Azure AD Connect runs immediately and on an ongoing basis to synchronize the on-premises AD DS forest to Microsoft 365.</span></span>
    
<span data-ttu-id="f6856-138">Innan du distribuerar den här lösningen i produktion kan du använda instruktionerna i [den simulerade företags bas konfigurationen](simulated-ent-base-configuration-microsoft-365-enterprise.md) för att konfigurera denna konfiguration som ett koncept bevis, för demonstrationer eller för experiment.</span><span class="sxs-lookup"><span data-stu-id="f6856-138">Before you deploy this solution in production, you can use the instructions in [The simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to set this configuration up as a proof of concept, for demonstrations, or for experimentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f6856-139">När Azure AD Connect-konfigurationen är klar sparas inte autentiseringsuppgifterna för AD DS-företagsprojekt för företag.</span><span class="sxs-lookup"><span data-stu-id="f6856-139">When Azure AD Connect configuration completes, it does not save the AD DS enterprise administrator account credentials.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f6856-140">Den här lösningen beskriver synkronisering av en enda AD DS-skog till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6856-140">This solution describes synchronizing a single AD DS forest to Microsoft 365.</span></span> <span data-ttu-id="f6856-141">Den topologi som diskuteras i den här artikeln är bara ett sätt att implementera den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="f6856-141">The topology discussed in this article represents only one way to implement this solution.</span></span> <span data-ttu-id="f6856-142">Din organisations topologi kan variera beroende på dina unika nätverks krav och säkerhets aspekter.</span><span class="sxs-lookup"><span data-stu-id="f6856-142">Your organization's topology might differ based on your unique network requirements and security considerations.</span></span> 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a><span data-ttu-id="f6856-143">Planera för en katalog synkroniseringsklient för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="f6856-143">Plan for hosting a directory sync server for Microsoft 365 in Azure</span></span>
<span data-ttu-id="f6856-144"><a name="PlanningVirtual"> </a></span><span class="sxs-lookup"><span data-stu-id="f6856-144"><a name="PlanningVirtual"> </a></span></span>

### <a name="prerequisites"></a><span data-ttu-id="f6856-145">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f6856-145">Prerequisites</span></span>

<span data-ttu-id="f6856-146">Innan du börjar bör du kontrol lera följande förutsättningar för den här lösningen:</span><span class="sxs-lookup"><span data-stu-id="f6856-146">Before you begin, review the following prerequisites for this solution:</span></span>
  
- <span data-ttu-id="f6856-147">Granska det relaterade planerings innehållet i [planera ditt Azure Virtual Network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span><span class="sxs-lookup"><span data-stu-id="f6856-147">Review the related planning content in [Plan your Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span></span>
    
- <span data-ttu-id="f6856-148">Se till att du uppfyller alla [förutsättningar](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) för konfigurering av Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="f6856-148">Ensure that you meet all [Prerequisites](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) for configuring the Azure virtual network.</span></span>
    
- <span data-ttu-id="f6856-149">Ha en Microsoft 365-prenumeration som innehåller Active Directory-integrering.</span><span class="sxs-lookup"><span data-stu-id="f6856-149">Have a Microsoft 365 subscription that includes the Active Directory integration feature.</span></span> <span data-ttu-id="f6856-150">Om du vill veta mer om Microsoft 365-prenumerationer går du till [prenumerations sidan för microsoft 365](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span><span class="sxs-lookup"><span data-stu-id="f6856-150">For information about Microsoft 365 subscriptions, go to the [Microsoft 365 subscription page](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span></span>
    
- <span data-ttu-id="f6856-151">Etablera en virtuell Azure-dator som kör Azure AD Connect för att synkronisera din lokala AD DS-skog med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6856-151">Provision one Azure Virtual Machine that runs Azure AD Connect to synchronize your on-premises AD DS forest with Microsoft 365.</span></span>
    
    <span data-ttu-id="f6856-152">Du måste ha autentiseringsuppgifterna (namn och lösen ord) för ett AD DS Enterprise-administratörskonto och ett Azure AD-administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="f6856-152">You must have the credentials (names and passwords) for a AD DS enterprise administrator account and an Azure AD Administrator account.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="f6856-153">Utvecklings antagande för lösnings arkitektur</span><span class="sxs-lookup"><span data-stu-id="f6856-153">Solution architecture design assumptions</span></span>

<span data-ttu-id="f6856-154">I följande lista beskrivs design alternativen för den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="f6856-154">The following list describes the design choices made for this solution.</span></span>
  
- <span data-ttu-id="f6856-155">Den här lösningen använder ett enda virtuellt Azure-nätverk med en VPN-anslutning för plats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="f6856-155">This solution uses a single Azure virtual network with a site-to-site VPN connection.</span></span> <span data-ttu-id="f6856-156">Det virtuella Azure-nätverket har ett enskilt undernät som har en server, den katalogpartition som kör Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="f6856-156">The Azure virtual network hosts a single subnet that has one server, the directory sync server that is running Azure AD Connect.</span></span> 
    
- <span data-ttu-id="f6856-157">I det lokala nätverket finns det en domänkontrollant och DNS-servrar.</span><span class="sxs-lookup"><span data-stu-id="f6856-157">On the on-premises network, a domain controller and DNS servers exist.</span></span>
    
- <span data-ttu-id="f6856-158">Azure AD Connect utför synkronisering av lösen ord i stället för enkel inloggning.</span><span class="sxs-lookup"><span data-stu-id="f6856-158">Azure AD Connect performs password hash synchronization instead of single sign-on.</span></span> <span data-ttu-id="f6856-159">Du behöver inte distribuera en AD FS-infrastruktur (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="f6856-159">You do not have to deploy an Active Directory Federation Services (AD FS) infrastructure.</span></span> <span data-ttu-id="f6856-160">Mer information om hur du synkroniserar och använder ett lösen ord finns i [välja rätt autentiseringsmetod för din Azure Active Directory-hybrid Identity-lösning](https://aka.ms/auth-options).</span><span class="sxs-lookup"><span data-stu-id="f6856-160">To learn more about password hash synchronization and single sign-on options, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://aka.ms/auth-options).</span></span>
    
<span data-ttu-id="f6856-161">Det finns fler design alternativ som du kanske bör tänka på när du distribuerar lösningen i din miljö.</span><span class="sxs-lookup"><span data-stu-id="f6856-161">There are additional design choices that you might consider when you deploy this solution in your environment.</span></span> <span data-ttu-id="f6856-162">Bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="f6856-162">These include the following:</span></span>
  
- <span data-ttu-id="f6856-163">Om det finns befintliga DNS-servrar i ett befintligt Azure-nätverk bestämmer du om du vill att din katalog synkroniseringsklient ska använda dem för namn matchning i stället för DNS-servrar i det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="f6856-163">If there are existing DNS servers in an existing Azure virtual network, determine whether you want your directory sync server to use them for name resolution instead of DNS servers on the on-premises network.</span></span>
    
- <span data-ttu-id="f6856-164">Om det finns domänkontrollanter i ett befintligt Azure-nätverk kan du bestämma om du vill konfigurera Active Directory-platser och tjänster.</span><span class="sxs-lookup"><span data-stu-id="f6856-164">If there are domain controllers in an existing Azure virtual network, determine whether configuring Active Directory Sites and Services may be a better option for you.</span></span> <span data-ttu-id="f6856-165">Med den här servern kan du söka efter domänkontrollanter i det lokala Azure-nätverket efter ändringar i konton och lösen ord i stället för domänkontrollanter på lokalt nätverk.</span><span class="sxs-lookup"><span data-stu-id="f6856-165">The directory sync server can query the domain controllers in the Azure virtual network for changes in accounts and passwords instead of domain controllers on the on-premises network.</span></span>
    
## <a name="deployment-roadmap"></a><span data-ttu-id="f6856-166">Distributions översikt</span><span class="sxs-lookup"><span data-stu-id="f6856-166">Deployment roadmap</span></span>

<span data-ttu-id="f6856-167">Distributionen av Azure AD Connect på en virtuell dator i Azure består av tre faser:</span><span class="sxs-lookup"><span data-stu-id="f6856-167">Deploying Azure AD Connect on a virtual machine in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="f6856-168">Fas 1: skapa och konfigurera Azure Virtual Network</span><span class="sxs-lookup"><span data-stu-id="f6856-168">Phase 1: Create and configure the Azure virtual network</span></span>
    
- <span data-ttu-id="f6856-169">Fas 2: skapa och konfigurera den virtuella Azure-datorn</span><span class="sxs-lookup"><span data-stu-id="f6856-169">Phase 2: Create and configure the Azure virtual machine</span></span>
    
- <span data-ttu-id="f6856-170">Fas 3: installera och konfigurera Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="f6856-170">Phase 3: Install and configure Azure AD Connect</span></span>
    
<span data-ttu-id="f6856-171">Efter distributionen måste du också tilldela platser och licenser för de nya användar kontona i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6856-171">After deployment, you must also assign locations and licenses for the new user accounts in Microsoft 365.</span></span>


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a><span data-ttu-id="f6856-172">Fas 1: skapa och konfigurera Azure Virtual Network</span><span class="sxs-lookup"><span data-stu-id="f6856-172">Phase 1: Create and configure the Azure virtual network</span></span>

<span data-ttu-id="f6856-173">För att skapa och konfigurera Azure Virtual Network kompletterar du [fas 1: förbereda ditt lokala nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) och [fas 2: skapa det lokala virtuella nätverket i Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) i distributions översikten för [Anslut ett lokalt nätverk till ett Microsoft Azure-](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)nätverk.</span><span class="sxs-lookup"><span data-stu-id="f6856-173">To create and configure the Azure virtual network, complete [Phase 1: Prepare your on-premises network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) and [Phase 2: Create the cross-premises virtual network in Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) in the deployment roadmap of [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
<span data-ttu-id="f6856-174">Det här är din resulterande konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6856-174">This is your resulting configuration.</span></span>
  
![Fas 1 av katalogen Sync Server för Microsoft 365 som finns i Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
<span data-ttu-id="f6856-176">Den här bilden visar ett lokalt nätverk som är kopplat till ett virtuellt Azure-nätverk via plats-till-plats-VPN eller ExpressRoute anslutning.</span><span class="sxs-lookup"><span data-stu-id="f6856-176">This figure shows an on-premises network connected to an Azure virtual network through a site-to-site VPN or ExpressRoute connection.</span></span>
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a><span data-ttu-id="f6856-177">Fas 2: skapa och konfigurera den virtuella Azure-datorn</span><span class="sxs-lookup"><span data-stu-id="f6856-177">Phase 2: Create and configure the Azure virtual machine</span></span>

<span data-ttu-id="f6856-178">Skapa den virtuella datorn i Azure genom att använda instruktionerna [skapa din första Windows-dator i Azure-portalen](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span><span class="sxs-lookup"><span data-stu-id="f6856-178">Create the virtual machine in Azure using the instructions [Create your first Windows virtual machine in the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span></span> <span data-ttu-id="f6856-179">Använd följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f6856-179">Use the following settings:</span></span>
  
- <span data-ttu-id="f6856-180">I fönstret **grunderna** väljer du samma prenumeration, plats och resurs grupp som ditt virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="f6856-180">On the **Basics** pane, select the same subscription, location, and resource group as your virtual network.</span></span> <span data-ttu-id="f6856-181">Spela in användar namn och lösen ord på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="f6856-181">Record the user name and password in a secure location.</span></span> <span data-ttu-id="f6856-182">Du behöver dessa senare för att ansluta till den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="f6856-182">You will need these later to connect to the virtual machine.</span></span>
    
- <span data-ttu-id="f6856-183">Välj standard storleken för **a2** i fönstret **Välj en storlek** .</span><span class="sxs-lookup"><span data-stu-id="f6856-183">On the **Choose a size** pane, choose the **A2 Standard** size.</span></span>
    
- <span data-ttu-id="f6856-184">Välj **standard** lagrings typ i avsnittet **lagring** i fönstret **Inställningar** .</span><span class="sxs-lookup"><span data-stu-id="f6856-184">On the **Settings** pane, in the **Storage** section, select the **Standard** storage type.</span></span> <span data-ttu-id="f6856-185">I avsnittet **nätverk** väljer du namnet på det virtuella nätverket och under nätet där katalogens synkroniseringstjänst (inte GatewaySubnet) finns.</span><span class="sxs-lookup"><span data-stu-id="f6856-185">In the **Network** section, select the name of your virtual network and the subnet for hosting the directory sync server (not the GatewaySubnet).</span></span> <span data-ttu-id="f6856-186">Lämna övriga inställningar till standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="f6856-186">Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="f6856-187">Kontrol lera att din katalog synkroniseringsklient använder DNS korrekt genom att kontrol lera den interna DNS-servern för att se till att en adress (A)-post har lagts till för den virtuella datorn med dess IP-adress.</span><span class="sxs-lookup"><span data-stu-id="f6856-187">Verify that your directory sync server is using DNS correctly by checking your internal DNS to make sure that an Address (A) record was added for the virtual machine with its IP address.</span></span> 
  
<span data-ttu-id="f6856-188">Följ instruktionerna i [ansluta till den virtuella datorn och logga in](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) för att ansluta till katalogen med en fjärr skrivbords anslutning.</span><span class="sxs-lookup"><span data-stu-id="f6856-188">Use the instructions in [Connect to the virtual machine and sign on](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to the directory sync server with a Remote Desktop Connection.</span></span> <span data-ttu-id="f6856-189">När du har loggat in ansluter du den virtuella datorn till den lokala AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="f6856-189">After signing in, join the virtual machine to the on-premises AD DS domain.</span></span>
  
<span data-ttu-id="f6856-190">För att Azure AD Connect ska få till gång till Internet resurser måste du konfigurera katalogpartitionen så att den använder det lokala nätverkets proxyserver.</span><span class="sxs-lookup"><span data-stu-id="f6856-190">For Azure AD Connect to gain access to Internet resources, you must configure the directory sync server to use the on-premises network's proxy server.</span></span> <span data-ttu-id="f6856-191">Kontakta nätverks administratören för att få ytterligare konfigurations steg.</span><span class="sxs-lookup"><span data-stu-id="f6856-191">You should contact your network administrator for any additional configuration steps to perform.</span></span>
  
<span data-ttu-id="f6856-192">Det här är din resulterande konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6856-192">This is your resulting configuration.</span></span>
  
![Fas 2 i katalogen med katalog servern för Microsoft 365 som finns i Azure](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
<span data-ttu-id="f6856-194">Den här bilden visar den virtuella katalogpartitionen för katalogpartition i det korslänkade Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="f6856-194">This figure shows the directory sync server virtual machine in the cross-premises Azure virtual network.</span></span>
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a><span data-ttu-id="f6856-195">Fas 3: installera och konfigurera Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="f6856-195">Phase 3: Install and configure Azure AD Connect</span></span>

<span data-ttu-id="f6856-196">Gör följande:</span><span class="sxs-lookup"><span data-stu-id="f6856-196">Complete the following procedure:</span></span>
  
1. <span data-ttu-id="f6856-197">Anslut till katalogen med en fjärr skrivbords server med ett AD DS-domännamn med lokala administratörs behörigheter.</span><span class="sxs-lookup"><span data-stu-id="f6856-197">Connect to the directory sync server using a Remote Desktop Connection with an AD DS domain account that has local administrator privileges.</span></span> <span data-ttu-id="f6856-198">Se [ansluta till den virtuella datorn och logga in](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="f6856-198">See [Connect to the virtual machine and sign on](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
    
2. <span data-ttu-id="f6856-199">Från katalogen för synkroniseringstjänst öppnar du [Microsoft 365-artikeln Konfigurera katalog synkronisering](set-up-directory-synchronization.md) och följer instruktionerna för profilsynkronisering med Lösenordssynkronisering med lösen ord.</span><span class="sxs-lookup"><span data-stu-id="f6856-199">From the directory sync server, open the [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) article and follow the directions for directory synchronization with password hash synchronization.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f6856-200">Installations programmet skapar **AAD_xxxxxxxxxxxx** kontot i organisationsenheten lokala användare.</span><span class="sxs-lookup"><span data-stu-id="f6856-200">Setup creates the **AAD_xxxxxxxxxxxx** account in the Local Users organizational unit (OU).</span></span> <span data-ttu-id="f6856-201">Det går inte att flytta eller ta bort det här kontot eller synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="f6856-201">Do not move or remove this account or synchronization will fail.</span></span>
  
<span data-ttu-id="f6856-202">Det här är din resulterande konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6856-202">This is your resulting configuration.</span></span>
  
![Fas 3 i katalogen för synkroniseringstjänst för Microsoft 365 som finns i Azure](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
<span data-ttu-id="f6856-204">I den här bilden visas den synkroniserade katalog servern med Azure AD Connect i det korslänkade Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="f6856-204">This figure shows the directory sync server with Azure AD Connect in the cross-premises Azure virtual network.</span></span>
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a><span data-ttu-id="f6856-205">Tilldela platser och licenser till användare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6856-205">Assign locations and licenses to users in Microsoft 365</span></span>

<span data-ttu-id="f6856-206">Azure AD Connect lägger till konton i din Microsoft 365-prenumeration från den lokala AD DS, men för att användare ska kunna logga in på Microsoft 365 och använda dess tjänster måste kontona vara konfigurerade med en plats och licenser.</span><span class="sxs-lookup"><span data-stu-id="f6856-206">Azure AD Connect adds accounts to your Microsoft 365 subscription from the on-premises AD DS, but in order for users to sign in to Microsoft 365 and use its services, the accounts must be configured with a location and licenses.</span></span> <span data-ttu-id="f6856-207">Följ de här anvisningarna för att lägga till platsen och aktivera licenser för lämpliga användar konton:</span><span class="sxs-lookup"><span data-stu-id="f6856-207">Use these steps to add the location and activate licenses for the appropriate user accounts:</span></span>
  
1. <span data-ttu-id="f6856-208">Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com)och klicka sedan på **admin**.</span><span class="sxs-lookup"><span data-stu-id="f6856-208">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com), and then click **Admin**.</span></span>
    
2. <span data-ttu-id="f6856-209">Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f6856-209">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="f6856-210">Markera kryss rutan bredvid den användare du vill aktivera i listan med användar konton.</span><span class="sxs-lookup"><span data-stu-id="f6856-210">In the list of user accounts, select the check box next to the user you want to activate.</span></span>
    
4. <span data-ttu-id="f6856-211">Klicka på **redigera** för **produkt licenser**på sidan för användaren.</span><span class="sxs-lookup"><span data-stu-id="f6856-211">On the page for the user, click **Edit** for **Product licenses**.</span></span>
    
5. <span data-ttu-id="f6856-212">På sidan **produkt licenser** väljer du en plats för användaren för **plats**och aktiverar sedan lämpliga licenser för användaren.</span><span class="sxs-lookup"><span data-stu-id="f6856-212">On the **Product licenses** page, select a location for the user for **Location**, and then enable the appropriate licenses for the user.</span></span>
    
6. <span data-ttu-id="f6856-213">När du är klar klickar du på **Spara**och sedan på **Stäng** två gånger.</span><span class="sxs-lookup"><span data-stu-id="f6856-213">When complete, click **Save**, and then click **Close** twice.</span></span>
    
7. <span data-ttu-id="f6856-214">Gå tillbaka till steg 3 för ytterligare användare.</span><span class="sxs-lookup"><span data-stu-id="f6856-214">Go back to step 3 for additional users.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f6856-215">Se även</span><span class="sxs-lookup"><span data-stu-id="f6856-215">See also</span></span>

[<span data-ttu-id="f6856-216">Microsoft 365-center för lösningar och arkitektur</span><span class="sxs-lookup"><span data-stu-id="f6856-216">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)
  
[<span data-ttu-id="f6856-217">Ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk</span><span class="sxs-lookup"><span data-stu-id="f6856-217">Connect an on-premises network to a Microsoft Azure virtual network</span></span>](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[<span data-ttu-id="f6856-218">Ladda ner Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="f6856-218">Download Azure AD Connect</span></span>](https://www.microsoft.com/download/details.aspx?id=47594)
  
[<span data-ttu-id="f6856-219">Konfigurera profilsynkronisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6856-219">Set up directory synchronization for Microsoft 365</span></span>](set-up-directory-synchronization.md)
  
