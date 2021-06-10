---
title: Distribuera Microsoft 365 katalogsynkronisering i Microsoft Azure
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
description: Lär dig hur du distribuerar Azure AD Anslut på en virtuell dator i Azure för att synkronisera konton mellan din lokala katalog och Azure AD-klientorganisationen.
ms.openlocfilehash: 52c1bb2eb53cc4e6753d528e0d82822b2a0eebc5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919092"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a><span data-ttu-id="99445-103">Distribuera Microsoft 365 katalogsynkronisering i Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="99445-103">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>

<span data-ttu-id="99445-104">Azure Active Directory (Azure AD) Anslut (kallades tidigare för katalogsynkroniseringsverktyget, katalogsynkroniseringsverktyget eller DirSync.exe-verktyget) är ett program som du installerar på en domän ansluten server för att synkronisera dina lokala AD DS-användare (Active Directory Domain Services) till Azure AD-klientorganisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="99445-104">Azure Active Directory (Azure AD) Connect (formerly known as the Directory Synchronization tool, Directory Sync tool, or the DirSync.exe tool) is an application that you install on a domain-joined server to synchronize your on-premises Active Directory Domain Services (AD DS) users to the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="99445-105">Microsoft 365 använder Azure AD för sin katalogtjänst.</span><span class="sxs-lookup"><span data-stu-id="99445-105">Microsoft 365 uses Azure AD for its directory service.</span></span> <span data-ttu-id="99445-106">I Microsoft 365-prenumeration ingår en Azure AD-klient.</span><span class="sxs-lookup"><span data-stu-id="99445-106">Your Microsoft 365 subscription includes an Azure AD tenant.</span></span> <span data-ttu-id="99445-107">Den här klientorganisationen kan också användas för hantering av organisationens identiteter med andra molnarbetsbelastningar, inklusive andra SaaS-program och -appar i Azure.</span><span class="sxs-lookup"><span data-stu-id="99445-107">This tenant can also be used for management of your organization's identities with other cloud workloads, including other SaaS applications and apps in Azure.</span></span>

<span data-ttu-id="99445-108">Du kan installera Azure AD Anslut på en lokal server, men du kan också installera det på en virtuell dator i Azure av följande anledningar:</span><span class="sxs-lookup"><span data-stu-id="99445-108">You can install Azure AD Connect on a on-premises server, but you can also install it on a virtual machine in Azure for these reasons:</span></span>
  
- <span data-ttu-id="99445-109">Du kan tillhandahålla och konfigurera molnbaserade servrar snabbare, vilket gör tjänsterna tillgängliga för användarna snabbare.</span><span class="sxs-lookup"><span data-stu-id="99445-109">You can provision and configure cloud-based servers faster, making the services available to your users sooner.</span></span>
- <span data-ttu-id="99445-110">Azure erbjuder bättre webbplatstillgänglighet med mindre ansträngning.</span><span class="sxs-lookup"><span data-stu-id="99445-110">Azure offers better site availability with less effort.</span></span>
- <span data-ttu-id="99445-111">Du kan minska antalet lokala servrar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="99445-111">You can reduce the number of on-premises servers in your organization.</span></span>

<span data-ttu-id="99445-112">Den här lösningen kräver anslutning mellan ditt lokala nätverk och ditt virtuella Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="99445-112">This solution requires connectivity between your on-premises network and your Azure virtual network.</span></span> <span data-ttu-id="99445-113">Mer information finns i [Anslut ett lokalt nätverk till ett Microsoft Azure virtuellt nätverk.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)</span><span class="sxs-lookup"><span data-stu-id="99445-113">For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="99445-114">I den här artikeln beskrivs synkronisering av en enda domän i en enda skog.</span><span class="sxs-lookup"><span data-stu-id="99445-114">This article describes synchronization of a single domain in a single forest.</span></span> <span data-ttu-id="99445-115">Azure AD Anslut synkroniserar alla AD DS-domäner i Active Directory-skogen med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99445-115">Azure AD Connect synchronizes all AD DS domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="99445-116">Om du har flera Active Directory-skogar att synkronisera med Microsoft 365 finns mer information i Scenariot Katalogsynkronisering [med Sign-On med flera skogar.](/azure/active-directory/hybrid/whatis-hybrid-identity)</span><span class="sxs-lookup"><span data-stu-id="99445-116">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span> 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a><span data-ttu-id="99445-117">Översikt över distribution Microsoft 365 katalogsynkronisering i Azure</span><span class="sxs-lookup"><span data-stu-id="99445-117">Overview of deploying Microsoft 365 directory synchronization in Azure</span></span>

<span data-ttu-id="99445-118">Följande diagram visar Azure AD Anslut som körs på en virtuell dator i Azure (katalogsynkroniseringsservern) som synkroniserar en lokal AD DS-skog med en Microsoft 365 prenumeration.</span><span class="sxs-lookup"><span data-stu-id="99445-118">The following diagram shows Azure AD Connect running on a virtual machine in Azure (the directory sync server) that synchronizes an on-premises AD DS forest to a Microsoft 365 subscription.</span></span>
  
![Azure AD Anslut-verktyg på en virtuell dator i Azure-synkronisering av lokala konton till Azure AD-klientorganisationen i en Microsoft 365-prenumeration med trafikflöde](../media/CP-DirSyncOverview.png)
  
<span data-ttu-id="99445-120">I diagrammet finns det två nätverk anslutna med VPN-anslutning mellan webbplatser eller ExpressRoute-anslutning.</span><span class="sxs-lookup"><span data-stu-id="99445-120">In the diagram, there are two networks connected by a site-to-site VPN or ExpressRoute connection.</span></span> <span data-ttu-id="99445-121">Det finns ett lokalt nätverk där AD DS-domänkontrollanter finns och det finns ett virtuellt Azure-nätverk med en katalogsynkroniseringsserver, som är en virtuell dator som kör [Azure AD Anslut.](https://www.microsoft.com/download/details.aspx?id=47594)</span><span class="sxs-lookup"><span data-stu-id="99445-121">There is an on-premises network where AD DS domain controllers are located, and there is an Azure virtual network with a directory sync server, which is a virtual machine running [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span> <span data-ttu-id="99445-122">Det finns två huvudsakliga trafikflöden som kommer från katalogsynkroniseringsservern:</span><span class="sxs-lookup"><span data-stu-id="99445-122">There are two main traffic flows originating from the directory sync server:</span></span>
  
-  <span data-ttu-id="99445-123">Azure AD Anslut frågar en domänkontrollant på det lokala nätverket om ändringar av konton och lösenord.</span><span class="sxs-lookup"><span data-stu-id="99445-123">Azure AD Connect queries a domain controller on the on-premises network for changes to accounts and passwords.</span></span>
-  <span data-ttu-id="99445-124">Azure AD Anslut skickar ändringarna till konton och lösenord till Azure AD-instansen av din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="99445-124">Azure AD Connect sends the changes to accounts and passwords to the Azure AD instance of your Microsoft 365 subscription.</span></span> <span data-ttu-id="99445-125">Eftersom katalogsynkroniseringsservern ligger i en utökad del av det lokala nätverket skickas ändringarna via det lokala nätverkets proxyserver.</span><span class="sxs-lookup"><span data-stu-id="99445-125">Because the directory sync server is in an extended portion of your on-premises network, these changes are sent through the on-premises network's proxy server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="99445-126">I den här lösningen beskrivs synkronisering av en enda Active Directory-domän i en enda Active Directory-skog.</span><span class="sxs-lookup"><span data-stu-id="99445-126">This solution describes synchronization of a single Active Directory domain, in a single Active Directory forest.</span></span> <span data-ttu-id="99445-127">Azure AD Anslut synkroniserar alla Active Directory-domäner i Active Directory-skogen med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99445-127">Azure AD Connect synchronizes all Active Directory domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="99445-128">Om du har flera Active Directory-skogar att synkronisera med Microsoft 365 finns mer information i Scenariot Katalogsynkronisering [med Sign-On med flera skogar.](/azure/active-directory/hybrid/whatis-hybrid-identity)</span><span class="sxs-lookup"><span data-stu-id="99445-128">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span> 
  
<span data-ttu-id="99445-129">Det finns två huvudsteg när du distribuerar den här lösningen:</span><span class="sxs-lookup"><span data-stu-id="99445-129">There are two major steps when you deploy this solution:</span></span>
  
1. <span data-ttu-id="99445-130">Skapa ett virtuellt Azure-nätverk och upprätta en VPN-anslutning mellan webbplatser till ditt lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="99445-130">Create an Azure virtual network and establish a site-to-site VPN connection to your on-premises network.</span></span> <span data-ttu-id="99445-131">Mer information finns i [Anslut ett lokalt nätverk till ett Microsoft Azure virtuellt nätverk.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)</span><span class="sxs-lookup"><span data-stu-id="99445-131">For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
    
2. <span data-ttu-id="99445-132">Installera [Azure AD Anslut](https://www.microsoft.com/download/details.aspx?id=47594) på en domän ansluten virtuell dator i Azure och synkronisera sedan den lokala AD DS till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99445-132">Install [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) on a domain-joined virtual machine in Azure, and then synchronize the on-premises AD DS to Microsoft 365.</span></span> <span data-ttu-id="99445-133">Detta omfattar:</span><span class="sxs-lookup"><span data-stu-id="99445-133">This involves:</span></span>
    
    <span data-ttu-id="99445-134">Skapa en virtuell Azure-dator för att köra Azure AD Anslut.</span><span class="sxs-lookup"><span data-stu-id="99445-134">Creating an Azure Virtual Machine to run Azure AD Connect.</span></span>
    
    <span data-ttu-id="99445-135">Installera och konfigurera [Azure AD-Anslut](https://www.microsoft.com/download/details.aspx?id=47594).</span><span class="sxs-lookup"><span data-stu-id="99445-135">Installing and configuring [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span>
    
    <span data-ttu-id="99445-136">För konfiguration av Azure AD Anslut måste du ha autentiseringsuppgifter (användarnamn och lösenord) för ett Azure AD-administratörskonto och ett AD DS-företagsadministratörskonto.</span><span class="sxs-lookup"><span data-stu-id="99445-136">Configuring Azure AD Connect requires the credentials (user name and password) of an Azure AD administrator account and a AD DS enterprise administrator account.</span></span> <span data-ttu-id="99445-137">Azure AD Anslut körs direkt och kontinuerligt för att synkronisera den lokala AD DS-skogen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99445-137">Azure AD Connect runs immediately and on an ongoing basis to synchronize the on-premises AD DS forest to Microsoft 365.</span></span>
    
<span data-ttu-id="99445-138">Innan du distribuerar den här lösningen i [](simulated-ent-base-configuration-microsoft-365-enterprise.md) produktionen kan du använda instruktionerna i Den simulerade företagskonfigurationen för att konfigurera den här konfigurationen som ett konceptbevis, för demonstrationer eller för experiment.</span><span class="sxs-lookup"><span data-stu-id="99445-138">Before you deploy this solution in production, you can use the instructions in [The simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to set this configuration up as a proof of concept, for demonstrations, or for experimentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="99445-139">När Azure AD Anslut-konfigurationen har slutförts sparas inte autentiseringsuppgifterna för ad ds-företagsadministratörens konto.</span><span class="sxs-lookup"><span data-stu-id="99445-139">When Azure AD Connect configuration completes, it does not save the AD DS enterprise administrator account credentials.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="99445-140">I den här lösningen beskrivs synkronisering av en enda AD DS-skog till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99445-140">This solution describes synchronizing a single AD DS forest to Microsoft 365.</span></span> <span data-ttu-id="99445-141">Topologin som beskrivs i den här artikeln representerar bara ett sätt att implementera den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="99445-141">The topology discussed in this article represents only one way to implement this solution.</span></span> <span data-ttu-id="99445-142">Organisationens topologi kan skilja sig åt beroende på dina unika nätverkskrav och säkerhetsöverväganden.</span><span class="sxs-lookup"><span data-stu-id="99445-142">Your organization's topology might differ based on your unique network requirements and security considerations.</span></span> 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a><span data-ttu-id="99445-143">Planera värd för en katalogsynkroniseringsserver för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="99445-143">Plan for hosting a directory sync server for Microsoft 365 in Azure</span></span>
<span data-ttu-id="99445-144"><a name="PlanningVirtual"> </a></span><span class="sxs-lookup"><span data-stu-id="99445-144"><a name="PlanningVirtual"> </a></span></span>

### <a name="prerequisites"></a><span data-ttu-id="99445-145">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="99445-145">Prerequisites</span></span>

<span data-ttu-id="99445-146">Innan du börjar granskar du följande krav för den här lösningen:</span><span class="sxs-lookup"><span data-stu-id="99445-146">Before you begin, review the following prerequisites for this solution:</span></span>
  
- <span data-ttu-id="99445-147">Granska relaterat planeringsinnehåll i [Planera ditt virtuella Azure-nätverk.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network)</span><span class="sxs-lookup"><span data-stu-id="99445-147">Review the related planning content in [Plan your Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span></span>
    
- <span data-ttu-id="99445-148">Se till att du uppfyller [alla krav för](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) att konfigurera det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="99445-148">Ensure that you meet all [Prerequisites](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) for configuring the Azure virtual network.</span></span>
    
- <span data-ttu-id="99445-149">Ha en Microsoft 365-prenumeration som innehåller Active Directory-integreringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="99445-149">Have a Microsoft 365 subscription that includes the Active Directory integration feature.</span></span> <span data-ttu-id="99445-150">Mer information om Microsoft 365 prenumerationer finns på sidan [Microsoft 365 prenumeration.](https://products.office.com/compare-all-microsoft-office-products?tab=2)</span><span class="sxs-lookup"><span data-stu-id="99445-150">For information about Microsoft 365 subscriptions, go to the [Microsoft 365 subscription page](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span></span>
    
- <span data-ttu-id="99445-151">Tillhandahålla en Virtuell Azure-dator som kör Azure AD Anslut för att synkronisera din lokala AD DS-skog med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99445-151">Provision one Azure Virtual Machine that runs Azure AD Connect to synchronize your on-premises AD DS forest with Microsoft 365.</span></span>
    
    <span data-ttu-id="99445-152">Du måste ha autentiseringsuppgifterna (namn och lösenord) för ett AD DS-företagsadministratörskonto och ett Azure AD-administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="99445-152">You must have the credentials (names and passwords) for a AD DS enterprise administrator account and an Azure AD Administrator account.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="99445-153">Antaganden om design av lösningsarkitektur</span><span class="sxs-lookup"><span data-stu-id="99445-153">Solution architecture design assumptions</span></span>

<span data-ttu-id="99445-154">I följande lista beskrivs de designval som gjorts för den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="99445-154">The following list describes the design choices made for this solution.</span></span>
  
- <span data-ttu-id="99445-155">Den här lösningen använder ett enda virtuellt Azure-nätverk med en VPN-anslutning mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="99445-155">This solution uses a single Azure virtual network with a site-to-site VPN connection.</span></span> <span data-ttu-id="99445-156">Det virtuella Azure-nätverket är värd för ett enda undernät som har en server, den katalogsynkroniseringsserver som kör Azure AD Anslut.</span><span class="sxs-lookup"><span data-stu-id="99445-156">The Azure virtual network hosts a single subnet that has one server, the directory sync server that is running Azure AD Connect.</span></span> 
    
- <span data-ttu-id="99445-157">I det lokala nätverket finns en domänkontrollant och DNS-servrar.</span><span class="sxs-lookup"><span data-stu-id="99445-157">On the on-premises network, a domain controller and DNS servers exist.</span></span>
    
- <span data-ttu-id="99445-158">Azure AD Anslut att utföra synkronisering av lösenordshashar i stället för enkel inloggning.</span><span class="sxs-lookup"><span data-stu-id="99445-158">Azure AD Connect performs password hash synchronization instead of single sign-on.</span></span> <span data-ttu-id="99445-159">Du behöver inte distribuera en AD FS-infrastruktur (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="99445-159">You do not have to deploy an Active Directory Federation Services (AD FS) infrastructure.</span></span> <span data-ttu-id="99445-160">Mer information om synkronisering av lösenordshashar och alternativ för enkel inloggning finns i Välja rätt autentiseringsmetod för din [Azure Active Directory hybrididentitetslösning.](/azure/active-directory/hybrid/choose-ad-authn)</span><span class="sxs-lookup"><span data-stu-id="99445-160">To learn more about password hash synchronization and single sign-on options, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](/azure/active-directory/hybrid/choose-ad-authn).</span></span>
    
<span data-ttu-id="99445-161">Det finns ytterligare designalternativ som du kan tänka på när du distribuerar den här lösningen i din miljö.</span><span class="sxs-lookup"><span data-stu-id="99445-161">There are additional design choices that you might consider when you deploy this solution in your environment.</span></span> <span data-ttu-id="99445-162">Det kan till exempel vara:</span><span class="sxs-lookup"><span data-stu-id="99445-162">These include the following:</span></span>
  
- <span data-ttu-id="99445-163">Om det finns befintliga DNS-servrar i ett befintligt virtuellt Azure-nätverk ska du avgöra om du vill att katalogsynkroniseringsservern ska använda dem för namnmatchning i stället för DNS-servrar i det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="99445-163">If there are existing DNS servers in an existing Azure virtual network, determine whether you want your directory sync server to use them for name resolution instead of DNS servers on the on-premises network.</span></span>
    
- <span data-ttu-id="99445-164">Om det finns domänkontrollanter i ett befintligt virtuellt Azure-nätverk avgör du om konfigurering av Active Directory -webbplatser och -tjänster kan vara ett bättre alternativ för dig.</span><span class="sxs-lookup"><span data-stu-id="99445-164">If there are domain controllers in an existing Azure virtual network, determine whether configuring Active Directory Sites and Services may be a better option for you.</span></span> <span data-ttu-id="99445-165">Katalogsynkroniseringsservern kan fråga domänkontrollanterna i det virtuella Azure-nätverket efter ändringar i konton och lösenord i stället för domänkontrollanter på det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="99445-165">The directory sync server can query the domain controllers in the Azure virtual network for changes in accounts and passwords instead of domain controllers on the on-premises network.</span></span>
    
## <a name="deployment-roadmap"></a><span data-ttu-id="99445-166">Distributionsöversikt</span><span class="sxs-lookup"><span data-stu-id="99445-166">Deployment roadmap</span></span>

<span data-ttu-id="99445-167">Distribution av Azure AD Anslut på en virtuell dator i Azure består av tre faser:</span><span class="sxs-lookup"><span data-stu-id="99445-167">Deploying Azure AD Connect on a virtual machine in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="99445-168">Fas 1: Skapa och konfigurera det virtuella Azure-nätverket</span><span class="sxs-lookup"><span data-stu-id="99445-168">Phase 1: Create and configure the Azure virtual network</span></span>
    
- <span data-ttu-id="99445-169">Fas 2: Skapa och konfigurera den virtuella Azure-datorn</span><span class="sxs-lookup"><span data-stu-id="99445-169">Phase 2: Create and configure the Azure virtual machine</span></span>
    
- <span data-ttu-id="99445-170">Fas 3: Installera och konfigurera Azure AD-Anslut</span><span class="sxs-lookup"><span data-stu-id="99445-170">Phase 3: Install and configure Azure AD Connect</span></span>
    
<span data-ttu-id="99445-171">Efter distributionen måste du också tilldela platser och licenser för de nya användarkontona i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99445-171">After deployment, you must also assign locations and licenses for the new user accounts in Microsoft 365.</span></span>


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a><span data-ttu-id="99445-172">Fas 1: Skapa och konfigurera det virtuella Azure-nätverket</span><span class="sxs-lookup"><span data-stu-id="99445-172">Phase 1: Create and configure the Azure virtual network</span></span>

<span data-ttu-id="99445-173">Slutför fas 1 för att skapa och konfigurera det virtuella [Azure-nätverket:](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) Förbered ditt lokala nätverk och fas [2:](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) Skapa det virtuella korslokala nätverket i Azure i översikten över distributionen av Anslut ett lokalt nätverk till ett [virtuellt](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)Microsoft Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="99445-173">To create and configure the Azure virtual network, complete [Phase 1: Prepare your on-premises network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) and [Phase 2: Create the cross-premises virtual network in Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) in the deployment roadmap of [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
<span data-ttu-id="99445-174">Det här är den resulterande konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="99445-174">This is your resulting configuration.</span></span>
  
![Fas 1 av katalogsynkroniseringsservern för Microsoft 365 finns i Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
<span data-ttu-id="99445-176">På den här bilden visas ett lokalt nätverk som är anslutet till ett virtuellt Azure-nätverk via en VPN-anslutning mellan webbplatser eller ExpressRoute-anslutning.</span><span class="sxs-lookup"><span data-stu-id="99445-176">This figure shows an on-premises network connected to an Azure virtual network through a site-to-site VPN or ExpressRoute connection.</span></span>
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a><span data-ttu-id="99445-177">Fas 2: Skapa och konfigurera den virtuella Azure-datorn</span><span class="sxs-lookup"><span data-stu-id="99445-177">Phase 2: Create and configure the Azure virtual machine</span></span>

<span data-ttu-id="99445-178">Skapa den virtuella datorn i Azure med hjälp av [anvisningarna Skapa din Windows virtuella datorn i Azure-portalen](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span><span class="sxs-lookup"><span data-stu-id="99445-178">Create the virtual machine in Azure using the instructions [Create your first Windows virtual machine in the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span></span> <span data-ttu-id="99445-179">Använd följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="99445-179">Use the following settings:</span></span>
  
- <span data-ttu-id="99445-180">I fönstret **Grunder** väljer du samma prenumeration, plats och resursgrupp som ditt virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="99445-180">On the **Basics** pane, select the same subscription, location, and resource group as your virtual network.</span></span> <span data-ttu-id="99445-181">Registrera användarnamnet och lösenordet på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="99445-181">Record the user name and password in a secure location.</span></span> <span data-ttu-id="99445-182">Du behöver dem senare för att ansluta till den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="99445-182">You will need these later to connect to the virtual machine.</span></span>
    
- <span data-ttu-id="99445-183">I fönstret **Välj en storlek** väljer du **A2 Standardstorlek.**</span><span class="sxs-lookup"><span data-stu-id="99445-183">On the **Choose a size** pane, choose the **A2 Standard** size.</span></span>
    
- <span data-ttu-id="99445-184">Välj **Inställningar** standardlagringstyp i **Storage** i **fönstret** Inställningar.</span><span class="sxs-lookup"><span data-stu-id="99445-184">On the **Settings** pane, in the **Storage** section, select the **Standard** storage type.</span></span> <span data-ttu-id="99445-185">I avsnittet **Nätverk** väljer du namnet på det virtuella nätverket och undernätet för värd för katalogsynkroniseringsservern (inte GatewaySubnet).</span><span class="sxs-lookup"><span data-stu-id="99445-185">In the **Network** section, select the name of your virtual network and the subnet for hosting the directory sync server (not the GatewaySubnet).</span></span> <span data-ttu-id="99445-186">Lämna alla andra inställningar för standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="99445-186">Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="99445-187">Kontrollera att din katalogsynkroniseringsserver använder DNS korrekt genom att kontrollera din interna DNS för att se till att en adresspost (A) har lagts till för den virtuella datorn med dess IP-adress.</span><span class="sxs-lookup"><span data-stu-id="99445-187">Verify that your directory sync server is using DNS correctly by checking your internal DNS to make sure that an Address (A) record was added for the virtual machine with its IP address.</span></span> 
  
<span data-ttu-id="99445-188">Följ anvisningarna i Anslut den virtuella datorn och logga [in](/azure/virtual-machines/windows/connect-logon) för att ansluta till katalogsynkroniseringsservern med en Fjärrskrivbordsanslutning.</span><span class="sxs-lookup"><span data-stu-id="99445-188">Use the instructions in [Connect to the virtual machine and sign on](/azure/virtual-machines/windows/connect-logon) to connect to the directory sync server with a Remote Desktop Connection.</span></span> <span data-ttu-id="99445-189">När du har loggat in ansluter du den virtuella datorn till den lokala AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="99445-189">After signing in, join the virtual machine to the on-premises AD DS domain.</span></span>
  
<span data-ttu-id="99445-190">För att Azure AD Anslut få åtkomst till Internetresurser måste du konfigurera katalogsynkroniseringsservern så att den använder det lokala nätverkets proxyserver.</span><span class="sxs-lookup"><span data-stu-id="99445-190">For Azure AD Connect to gain access to Internet resources, you must configure the directory sync server to use the on-premises network's proxy server.</span></span> <span data-ttu-id="99445-191">Kontakta nätverksadministratören för ytterligare konfigurationssteg.</span><span class="sxs-lookup"><span data-stu-id="99445-191">You should contact your network administrator for any additional configuration steps to perform.</span></span>
  
<span data-ttu-id="99445-192">Det här är den resulterande konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="99445-192">This is your resulting configuration.</span></span>
  
![Fas 2 av katalogsynkroniseringsservern för Microsoft 365 azure-server](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
<span data-ttu-id="99445-194">I den här bilden visas den virtuella katalogsynkroniseringsservern i det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="99445-194">This figure shows the directory sync server virtual machine in the cross-premises Azure virtual network.</span></span>
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a><span data-ttu-id="99445-195">Fas 3: Installera och konfigurera Azure AD-Anslut</span><span class="sxs-lookup"><span data-stu-id="99445-195">Phase 3: Install and configure Azure AD Connect</span></span>

<span data-ttu-id="99445-196">Slutför följande procedur:</span><span class="sxs-lookup"><span data-stu-id="99445-196">Complete the following procedure:</span></span>
  
1. <span data-ttu-id="99445-197">Anslut till katalogsynkroniseringsservern med en Anslutning till fjärrskrivbord med ett AD DS-domänkonto med lokal administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="99445-197">Connect to the directory sync server using a Remote Desktop Connection with an AD DS domain account that has local administrator privileges.</span></span> <span data-ttu-id="99445-198">Se [Anslut till den virtuella datorn och logga in på](/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="99445-198">See [Connect to the virtual machine and sign on](/azure/virtual-machines/windows/connect-logon).</span></span>
    
2. <span data-ttu-id="99445-199">Från katalogsynkroniseringsservern öppnar du artikeln Konfigurera katalogsynkronisering för [Microsoft 365](set-up-directory-synchronization.md) och följer anvisningarna för katalogsynkronisering med synkronisering av lösenordshashar.</span><span class="sxs-lookup"><span data-stu-id="99445-199">From the directory sync server, open the [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) article and follow the directions for directory synchronization with password hash synchronization.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="99445-200">Vid installationen **AAD_xxxxxxxxxxxx** kontot i organisationsenheten Lokala användare (OU).</span><span class="sxs-lookup"><span data-stu-id="99445-200">Setup creates the **AAD_xxxxxxxxxxxx** account in the Local Users organizational unit (OU).</span></span> <span data-ttu-id="99445-201">Flytta inte eller ta inte bort det här kontot, annars misslyckas synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="99445-201">Do not move or remove this account or synchronization will fail.</span></span>
  
<span data-ttu-id="99445-202">Det här är den resulterande konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="99445-202">This is your resulting configuration.</span></span>
  
![Fas 3 av katalogsynkroniseringsservern för Microsoft 365 finns i Azure](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
<span data-ttu-id="99445-204">I den här bilden visas katalogsynkroniseringsservern med Azure AD Anslut i det virtuella Azure-nätverket på plats.</span><span class="sxs-lookup"><span data-stu-id="99445-204">This figure shows the directory sync server with Azure AD Connect in the cross-premises Azure virtual network.</span></span>
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a><span data-ttu-id="99445-205">Tilldela platser och licenser till användare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="99445-205">Assign locations and licenses to users in Microsoft 365</span></span>

<span data-ttu-id="99445-206">Azure AD Anslut lägger till konton i Microsoft 365-prenumerationen från den lokala AD DS-tjänsten, men för att användarna ska kunna logga in på Microsoft 365 och använda tjänsterna måste kontona konfigureras med en plats och licenser.</span><span class="sxs-lookup"><span data-stu-id="99445-206">Azure AD Connect adds accounts to your Microsoft 365 subscription from the on-premises AD DS, but in order for users to sign in to Microsoft 365 and use its services, the accounts must be configured with a location and licenses.</span></span> <span data-ttu-id="99445-207">Gör så här för att lägga till platsen och aktivera licenser för lämpliga användarkonton:</span><span class="sxs-lookup"><span data-stu-id="99445-207">Use these steps to add the location and activate licenses for the appropriate user accounts:</span></span>
  
1. <span data-ttu-id="99445-208">Logga in på [Microsoft 365 och](https://admin.microsoft.com)klicka sedan på **Admin.**</span><span class="sxs-lookup"><span data-stu-id="99445-208">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com), and then click **Admin**.</span></span>
    
2. <span data-ttu-id="99445-209">Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="99445-209">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="99445-210">Markera kryssrutan bredvid den användare du vill aktivera i listan med användarkonton.</span><span class="sxs-lookup"><span data-stu-id="99445-210">In the list of user accounts, select the check box next to the user you want to activate.</span></span>
    
4. <span data-ttu-id="99445-211">På sidan för användaren klickar du på **Redigera för** **produktlicenser.**</span><span class="sxs-lookup"><span data-stu-id="99445-211">On the page for the user, click **Edit** for **Product licenses**.</span></span>
    
5. <span data-ttu-id="99445-212">På sidan **Produktlicenser** väljer du en plats för användaren **för Plats** och aktiverar sedan lämpliga licenser för användaren.</span><span class="sxs-lookup"><span data-stu-id="99445-212">On the **Product licenses** page, select a location for the user for **Location**, and then enable the appropriate licenses for the user.</span></span>
    
6. <span data-ttu-id="99445-213">När det är klart klickar **du på** Spara och sedan på **Stäng två** gånger.</span><span class="sxs-lookup"><span data-stu-id="99445-213">When complete, click **Save**, and then click **Close** twice.</span></span>
    
7. <span data-ttu-id="99445-214">Gå tillbaka till steg 3 för ytterligare användare.</span><span class="sxs-lookup"><span data-stu-id="99445-214">Go back to step 3 for additional users.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="99445-215">Se även</span><span class="sxs-lookup"><span data-stu-id="99445-215">See also</span></span>

[<span data-ttu-id="99445-216">Microsoft 365-lösning och arkitekturcenter</span><span class="sxs-lookup"><span data-stu-id="99445-216">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)
  
[<span data-ttu-id="99445-217">Anslut ett lokalt nätverk till ett virtuellt Microsoft Azure nätverk</span><span class="sxs-lookup"><span data-stu-id="99445-217">Connect an on-premises network to a Microsoft Azure virtual network</span></span>](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[<span data-ttu-id="99445-218">Ladda ned Azure AD-Anslut</span><span class="sxs-lookup"><span data-stu-id="99445-218">Download Azure AD Connect</span></span>](https://www.microsoft.com/download/details.aspx?id=47594)
  
[<span data-ttu-id="99445-219">Konfigurera katalogsynkronisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="99445-219">Set up directory synchronization for Microsoft 365</span></span>](set-up-directory-synchronization.md)
