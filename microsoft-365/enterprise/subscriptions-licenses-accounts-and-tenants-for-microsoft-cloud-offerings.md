---
title: Prenumerationer, licenser, konton och klienter för Microsofts molntjänster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/25/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: Förstå relationer mellan organisationer, prenumerationer, licenser, användarkonton och klientorganisationer i Microsofts molntjänster.
ms.openlocfilehash: c48e2ecc321f4b6e06ced13f029e344faf12650b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446037"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a><span data-ttu-id="20212-103">Prenumerationer, licenser, konton och klienter för Microsofts molntjänster</span><span class="sxs-lookup"><span data-stu-id="20212-103">Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings</span></span>

<span data-ttu-id="20212-104">Microsoft tillhandahåller en hierarki med organisationer, prenumerationer, licenser och användarkonton för konsekvent användning av identiteter och fakturering i molnerbjudanden:</span><span class="sxs-lookup"><span data-stu-id="20212-104">Microsoft provides a hierarchy of organizations, subscriptions, licenses, and user accounts for consistent use of identities and billing across its cloud offerings:</span></span>
  
- <span data-ttu-id="20212-105">Microsoft 365 och Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="20212-105">Microsoft 365 and Microsoft Office 365</span></span>
- <span data-ttu-id="20212-106">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="20212-106">Microsoft Azure</span></span>
- <span data-ttu-id="20212-107">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="20212-107">Microsoft Dynamics 365</span></span>

## <a name="elements-of-the-hierarchy"></a><span data-ttu-id="20212-108">Element i hierarkin</span><span class="sxs-lookup"><span data-stu-id="20212-108">Elements of the hierarchy</span></span>

<span data-ttu-id="20212-109">Här är elementen i hierarkin:</span><span class="sxs-lookup"><span data-stu-id="20212-109">Here are the elements of the hierarchy:</span></span>
  
### <a name="organization"></a><span data-ttu-id="20212-110">Organisation</span><span class="sxs-lookup"><span data-stu-id="20212-110">Organization</span></span>

<span data-ttu-id="20212-111">En organisation representerar en affärsenhet som använder Microsofts molntjänster, som vanligtvis identifieras av ett eller flera DNS-domännamn (Domain Name System), till exempel contoso.com.</span><span class="sxs-lookup"><span data-stu-id="20212-111">An organization represents a business entity that is using Microsoft cloud offerings, typically identified by one or more public Domain Name System (DNS) domain names, such as contoso.com.</span></span> <span data-ttu-id="20212-112">Organisationen är en behållare för-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="20212-112">The organization is a container for subscriptions.</span></span>
  
### <a name="subscriptions"></a><span data-ttu-id="20212-113">Prenumerationer</span><span class="sxs-lookup"><span data-stu-id="20212-113">Subscriptions</span></span>

<span data-ttu-id="20212-114">En prenumeration är ett avtal med Microsoft om att använda en eller flera Microsoft molnbaserade plattformar eller tjänster, för vilka avgifter ska periodiseras baserat på en licensavgift per användare eller för molnbaserad resursförbrukning.</span><span class="sxs-lookup"><span data-stu-id="20212-114">A subscription is an agreement with Microsoft to use one or more Microsoft cloud platforms or services, for which charges accrue based on either a per-user license fee or on cloud-based resource consumption.</span></span> 

- <span data-ttu-id="20212-115">Microsofts Software as a Service (SaaS)-baserad molntjänst (Microsoft 365 och Dynamics 365) debiterar licensavgifter per användare.</span><span class="sxs-lookup"><span data-stu-id="20212-115">Microsoft's Software as a Service (SaaS)-based cloud offerings (Microsoft 365 and Dynamics 365) charge per-user license fees.</span></span> 
- <span data-ttu-id="20212-116">Microsofts Platform as a Service (PaaS) och Infrastructure as a Service (IaaS) molnerbjudanden (Azure), debiterar baserat på förbrukning av molnresurser.</span><span class="sxs-lookup"><span data-stu-id="20212-116">Microsoft's Platform as a Service (PaaS) and Infrastructure as a Service (IaaS) cloud offerings (Azure) charge based on cloud resource consumption.</span></span>
 
<span data-ttu-id="20212-117">Du kan också använda en provprenumeration, men prenumerationen upphör att gälla efter en bestämd tid eller förbrukning.</span><span class="sxs-lookup"><span data-stu-id="20212-117">You can also use a trial subscription, but the subscription expires after a specific amount of time or consumption charges.</span></span> <span data-ttu-id="20212-118">Du kan omvandla en provprenumeration till en betalprenumeration.</span><span class="sxs-lookup"><span data-stu-id="20212-118">You can convert a trial subscription to a paid subscription.</span></span>
  
<span data-ttu-id="20212-119">Organisationer kan ha flera prenumerationer för Microsofts molntjänster.</span><span class="sxs-lookup"><span data-stu-id="20212-119">Organizations can have multiple subscriptions for Microsoft's cloud offerings.</span></span> <span data-ttu-id="20212-120">Bild 1 visar en organisation med flera Microsoft 365-prenumerationer, en Dynamics 365-prenumeration och flera Azure-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="20212-120">Figure 1 shows a single organization that has multiple Microsoft 365 subscriptions, a Dynamics 365 subscription, and multiple Azure subscriptions.</span></span>

<span data-ttu-id="20212-121">**Bild 1: Exempel på flera prenumerationer för en organisation**</span><span class="sxs-lookup"><span data-stu-id="20212-121">**Figure 1: Example of multiple subscriptions for an organization**</span></span>

![Ett exempel, organisationer med flera prenumerationer för Microsofts molntjänster.](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a><span data-ttu-id="20212-123">Licenser</span><span class="sxs-lookup"><span data-stu-id="20212-123">Licenses</span></span>

<span data-ttu-id="20212-124">För Microsofts SaaS molnerbjudanden kan en licens tillåta ett speciellt användarkonto att använda tjänsterna i molnerbjudandet.</span><span class="sxs-lookup"><span data-stu-id="20212-124">For Microsoft's SaaS cloud offerings, a license allows a specific user account to use the services of the cloud offering.</span></span> <span data-ttu-id="20212-125">Som en del av din prenumeration debiteras du en fast månatlig avgift.</span><span class="sxs-lookup"><span data-stu-id="20212-125">You are charged a fixed monthly fee as part of your subscription.</span></span> <span data-ttu-id="20212-126">Administratörer tilldelar licenser till enskilda användarkonton i prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="20212-126">Administrators assign licenses to individual user accounts in the subscription.</span></span> <span data-ttu-id="20212-127">I exemplet i Bild 2 har Contoso Corporation en Microsoft 365 E5-prenumeration med 100-licenser som gör att du kan använda upp till 100 enskilda användarkonton för att använda Microsoft 365 E5-funktioner och tjänster.</span><span class="sxs-lookup"><span data-stu-id="20212-127">For the example in Figure 2, the Contoso Corporation has a Microsoft 365 E5 subscription with 100 licenses, which allows to up to 100 individual user accounts to use Microsoft 365 E5 features and services.</span></span>
  
<span data-ttu-id="20212-128">**Bild 2: Licenser i SaaS-baserade prenumerationer för en organisation**</span><span class="sxs-lookup"><span data-stu-id="20212-128">**Figure 2: Licenses within the SaaS-based subscriptions for an organization**</span></span>

![Ett exempel på flera licenser i en prenumeration för Microsofts SaaS-baserade molnerbjudanden.](../media/Subscriptions/Subscriptions-Fig2.png)
  
<span data-ttu-id="20212-130">För Azure PaaS-baserade molntjänster finns det programvarulicenser som är inbyggda i serviceprissättning.</span><span class="sxs-lookup"><span data-stu-id="20212-130">For Azure PaaS-based cloud services, software licenses are built into the service pricing.</span></span>
  
<span data-ttu-id="20212-131">För Azure IaaS-baserade virtuella datorer kan kanske fler licenser för att använda programvaran eller programmet som är installerat på en virtuell datorbild krävas.</span><span class="sxs-lookup"><span data-stu-id="20212-131">For Azure IaaS-based virtual machines, additional licenses to use the software or application installed on a virtual machine image might be required.</span></span> <span data-ttu-id="20212-132">För vissa virtuella datorbilder finns licensierade versioner av programvaran och kostnaden ingår i per minut kostnaden för servern.</span><span class="sxs-lookup"><span data-stu-id="20212-132">Some virtual machine images have licensed versions of software installed and the cost is included in the per-minute rate for the server.</span></span> <span data-ttu-id="20212-133">Exempel är de virtuella datorbilderna för SQL Server 2014 och SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="20212-133">Examples are the virtual machine images for SQL Server 2014 and SQL Server 2016.</span></span> 
  
<span data-ttu-id="20212-134">För vissa virtuella datorbilder finns provversioner av installerade program och behöver ytterligare programvarulicenser för användning utanför provperioden.</span><span class="sxs-lookup"><span data-stu-id="20212-134">Some virtual machine images have trial versions of applications installed and need additional software application licenses for use beyond the trial period.</span></span> <span data-ttu-id="20212-135">SharePoint Server 2016-utvärderingsversionen av virtuell datorbild innehåller till exempel en förinstallerad utvärderingsversion av SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="20212-135">For example, the SharePoint Server 2016 Trial virtual machine image includes a trial version of SharePoint Server 2016 pre-installed.</span></span> <span data-ttu-id="20212-136">Om du vill fortsätta att använda SharePoint Server 2016 efter utgångsdatumet för utvärderingsversionen måste du köpa en SharePoint Server 2016 licens och kundlicenser från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20212-136">To continue using SharePoint Server 2016 after the trial expiration date, you must purchase a SharePoint Server 2016 license and client licenses from Microsoft.</span></span> <span data-ttu-id="20212-137">Dessa avgifter är åtskilda från Azure-prenumerationen och kostnaden per minut för att köra den virtuella datorn gäller fortfarande.</span><span class="sxs-lookup"><span data-stu-id="20212-137">These charges are separate from the Azure subscription and the per-minute rate to run the virtual machine still applies.</span></span>
  
### <a name="user-accounts"></a><span data-ttu-id="20212-138">Användarkonton</span><span class="sxs-lookup"><span data-stu-id="20212-138">User accounts</span></span>

<span data-ttu-id="20212-139">Användarkonton för alla Microsofts molnerbjudanden lagras i Azure Active Directory (Azure AD)-klientorganisationen som innehåller användarkonton och grupper.</span><span class="sxs-lookup"><span data-stu-id="20212-139">User accounts for all of Microsoft's cloud offerings are stored in an Azure Active Directory (Azure AD) tenant, which contains user accounts and groups.</span></span> <span data-ttu-id="20212-140">En Azure AD-klientorganisation kan synkroniseras med dina befintliga Active Directory Domain Services (AD DS)-konton med Azure AD Connect, en Windows serverbaserad tjänst.</span><span class="sxs-lookup"><span data-stu-id="20212-140">An Azure AD tenant can be synchronized with your existing Active Directory Domain Services (AD DS) accounts using Azure AD Connect, a Windows server-based service.</span></span> <span data-ttu-id="20212-141">Detta kallas för katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="20212-141">This is known as directory synchronization.</span></span>
  
<span data-ttu-id="20212-142">I Bild 3 visas ett exempel på flera prenumerationer för en organisation med hjälp av en vanlig Azure AD-klientorganisation som innehåller organisationens konton.</span><span class="sxs-lookup"><span data-stu-id="20212-142">Figure 3 shows an example of multiple subscriptions of an organization using a common Azure AD tenant that contains the organization's accounts.</span></span>
  
<span data-ttu-id="20212-143">**Bild 3: flera prenumerationer för en organisation som använder samma Azure AD-klientorganisation**</span><span class="sxs-lookup"><span data-stu-id="20212-143">**Figure 3: Multiple subscriptions of an organization that use the same Azure AD tenant**</span></span>

![Ett exempel på organisation med flera prenumerationer som använder samma Azure AD-klientorganisation.](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a><span data-ttu-id="20212-145">Klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="20212-145">Tenants</span></span>

<span data-ttu-id="20212-146">För SaaS molnerbjudanden är klientorganisationen den regionala plats där servrarna som tillhandahåller molntjänster finns.</span><span class="sxs-lookup"><span data-stu-id="20212-146">For SaaS cloud offerings, the tenant is the regional location that houses the servers providing cloud services.</span></span> <span data-ttu-id="20212-147">Contoso Corporation valde t. ex. en europeisk region som värd för Microsoft 365-, EMS- och Dynamics 365-klientorganisationer för de 15 000 arbetarna på deras huvudkontor i Paris.</span><span class="sxs-lookup"><span data-stu-id="20212-147">For example, the Contoso Corporation chose the European region to host its Microsoft 365, EMS, and Dynamics 365 tenants for the 15,000 workers in their Paris headquarters.</span></span>
  
<span data-ttu-id="20212-148">Azure PaaS tjänster och virtuella datorbaserade arbetsbelastningar som finns i Azure IaaS kan ha en klientorganisationskonto i vilket Azure-datacenter som helst över hela världen.</span><span class="sxs-lookup"><span data-stu-id="20212-148">Azure PaaS services and virtual machine-based workloads hosted in Azure IaaS can have tenancy in any Azure datacenter across the world.</span></span> <span data-ttu-id="20212-149">Du anger vilket Azure-datacenter, platsen, när du skapar Azure PaaS-appen eller-tjänsten eller elementet för en IaaS-arbetsbelastning.</span><span class="sxs-lookup"><span data-stu-id="20212-149">You specify the Azure datacenter, known as the location, when you create the Azure PaaS app or service or element of an IaaS workload.</span></span>
  
<span data-ttu-id="20212-150">En Azure AD-klientorganisation är en särskild instans av Azure AD som innehåller konton och grupper.</span><span class="sxs-lookup"><span data-stu-id="20212-150">An Azure AD tenant is a specific instance of Azure AD containing accounts and groups.</span></span> <span data-ttu-id="20212-151">Betal-eller utvärderingsprenumerationer av Microsoft 365 eller Dynamics 365 innehåller en kostnadsfri Azure AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="20212-151">Paid or trial subscriptions of Microsoft 365 or Dynamics 365 include a free Azure AD tenant.</span></span> <span data-ttu-id="20212-152">Azure AD-innehavaren inkluderar inte andra Azure-tjänster och är inte samma sak som en Azure-utvärderingsversion eller betald prenumeration.</span><span class="sxs-lookup"><span data-stu-id="20212-152">This Azure AD tenant does not include other Azure services and is not the same as an Azure trial or paid subscription.</span></span>
  
### <a name="summary-of-the-hierarchy"></a><span data-ttu-id="20212-153">Sammanfattning av hierarkin</span><span class="sxs-lookup"><span data-stu-id="20212-153">Summary of the hierarchy</span></span>

<span data-ttu-id="20212-154">Här är en snabb sammanfattning:</span><span class="sxs-lookup"><span data-stu-id="20212-154">Here is a quick recap:</span></span>
  
- <span data-ttu-id="20212-155">En organisation kan ha flera prenumerationer</span><span class="sxs-lookup"><span data-stu-id="20212-155">An organization can have multiple subscriptions</span></span>
    
  - <span data-ttu-id="20212-156">En prenumeration kan ha flera licenser</span><span class="sxs-lookup"><span data-stu-id="20212-156">A subscription can have multiple licenses</span></span>
    
  - <span data-ttu-id="20212-157">Licenser kan tilldelas till enskilda användarkonton</span><span class="sxs-lookup"><span data-stu-id="20212-157">Licenses can be assigned to individual user accounts</span></span>
    
  - <span data-ttu-id="20212-158">Användarkonton lagras i en Azure AD-klientorganisation</span><span class="sxs-lookup"><span data-stu-id="20212-158">User accounts are stored in an Azure AD tenant</span></span>
    
<span data-ttu-id="20212-159">Här är ett exempel på relationen mellan organisationer, prenumerationer, licenser och användarkonton:</span><span class="sxs-lookup"><span data-stu-id="20212-159">Here is an example of the relationship of organizations, subscriptions, licenses, and user accounts:</span></span>
  
- <span data-ttu-id="20212-160">En organisation som identifieras genom dess offentliga domännamn.</span><span class="sxs-lookup"><span data-stu-id="20212-160">An organization identified by its public domain name.</span></span>
    
  - <span data-ttu-id="20212-161">En Microsoft 365 E3-prenumeration med användarlicenser.</span><span class="sxs-lookup"><span data-stu-id="20212-161">A Microsoft 365 E3 subscription with user licenses.</span></span>
    
    <span data-ttu-id="20212-162">En Microsoft 365 E5-prenumeration med användarlicenser.</span><span class="sxs-lookup"><span data-stu-id="20212-162">A Microsoft 365 E5 subscription with user licenses.</span></span>
    
    <span data-ttu-id="20212-163">En Dynamics 365 E5-prenumeration med användarlicenser.</span><span class="sxs-lookup"><span data-stu-id="20212-163">A Dynamics 365 subscription with user licenses.</span></span>
    
    <span data-ttu-id="20212-164">Flera Azure-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="20212-164">Multiple Azure subscriptions.</span></span>
    
  - <span data-ttu-id="20212-165">Organisationens användarkonton i en vanlig Azure AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="20212-165">The organization's user accounts in a common Azure AD tenant.</span></span>
    
<span data-ttu-id="20212-166">Med flera prenumerationer på Microsoft Cloud får du en Azure AD-klientorganisation som agerar som gemensam identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="20212-166">Multiple Microsoft cloud offering subscriptions can use the same Azure AD tenant that acts as a common identity provider.</span></span> <span data-ttu-id="20212-167">En central Azure AD-klientorganisation som innehåller de synkroniserade kontona i din lokala AD DS tillhandahåller molnbaserad Identity as a Service (IDaaS) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="20212-167">A central Azure AD tenant that contains the synchronized accounts of your on-premises AD DS provides cloud-based Identity as a Service (IDaaS) for your organization.</span></span> 
  
<span data-ttu-id="20212-168">**Bild 4: Synkroniserade lokala konton och IDaaS för en organisation**</span><span class="sxs-lookup"><span data-stu-id="20212-168">**Figure 4: Synchronized on-premises accounts and IDaaS for an organization**</span></span>

![Identity as a Service (IaaS) IDaaS för din organisation.](../media/Subscriptions/Subscriptions-Fig4.png)
  
<span data-ttu-id="20212-170">Bild 4 visar hur en vanlig Azure AD-klientorganisation används i Microsofts SaaS-molntjänster, Azure PaaS-appar samt virtuella datorer i Azure IaaS som använder Azure AD Domain Services.</span><span class="sxs-lookup"><span data-stu-id="20212-170">Figure 4 shows how a common Azure AD tenant is used by Microsoft's SaaS cloud offerings, Azure PaaS apps, and virtual machines in Azure IaaS that use Azure AD Domain Services.</span></span> <span data-ttu-id="20212-171">Med Azure AD Connect synkroniseras den lokala AD DS-skogen med Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="20212-171">Azure AD Connect synchronizes the on-premises AD DS forest with the Azure AD tenant.</span></span>
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a><span data-ttu-id="20212-172">Kombinera prenumerationer för flera Microsoft molnerbjudanden</span><span class="sxs-lookup"><span data-stu-id="20212-172">Combining subscriptions for multiple Microsoft cloud offerings</span></span>

<span data-ttu-id="20212-173">I följande tabell beskrivs hur du kan kombinera flera Microsoft molnerbjudanden baserat på att redan har en prenumeration för en typ av molnerbjudande (etiketterna som går ner i den första kolumnen) och lägger till en prenumeration för ett annat molnerbjudande (går över kolumnerna).</span><span class="sxs-lookup"><span data-stu-id="20212-173">The following table describes how you can combine multiple Microsoft cloud offerings based on already having a subscription for one type of cloud offering (the labels going down the first column) and adding a subscription for a different cloud offering (going across the columns).</span></span>
  
||<span data-ttu-id="20212-174">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="20212-174">**Microsoft 365**</span></span>|<span data-ttu-id="20212-175">**Azure**</span><span class="sxs-lookup"><span data-stu-id="20212-175">**Azure**</span></span>|<span data-ttu-id="20212-176">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="20212-176">**Dynamics 365**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="20212-177">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="20212-177">**Microsoft 365**</span></span> <br/> |<span data-ttu-id="20212-178">SAKNAS</span><span class="sxs-lookup"><span data-stu-id="20212-178">NA</span></span>  <br/> |<span data-ttu-id="20212-179">Du lägger till en Azure-prenumeration i din organisation från Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="20212-179">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="20212-180">Du lägger till en Dynamics 365-prenumeration i din organisation från administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20212-180">You add a Dynamics 365 subscription to your organization from the Microsoft 365 admin center.</span></span>  <br/> |
|<span data-ttu-id="20212-181">**Azure**</span><span class="sxs-lookup"><span data-stu-id="20212-181">**Azure**</span></span> <br/> |<span data-ttu-id="20212-182">Du lägger till en Microsoft 365-prenumeration i organisationen.</span><span class="sxs-lookup"><span data-stu-id="20212-182">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="20212-183">SAKNAS</span><span class="sxs-lookup"><span data-stu-id="20212-183">NA</span></span>  <br/> |<span data-ttu-id="20212-184">Du lägger till en Dynamics 365-prenumeration i organisationen.</span><span class="sxs-lookup"><span data-stu-id="20212-184">You add a Dynamics 365 subscription to your organization.</span></span>  <br/> |
|<span data-ttu-id="20212-185">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="20212-185">**Dynamics 365**</span></span> <br/> |<span data-ttu-id="20212-186">Du lägger till en Microsoft 365-prenumeration i organisationen.</span><span class="sxs-lookup"><span data-stu-id="20212-186">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="20212-187">Du lägger till en Azure-prenumeration i din organisation från Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="20212-187">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="20212-188">SAKNAS</span><span class="sxs-lookup"><span data-stu-id="20212-188">NA</span></span>  <br/> |
   
<span data-ttu-id="20212-189">Ett enkelt sätt att lägga till prenumerationer i organisationen för Microsoft SaaS-baserade tjänster är via administrationscenter:</span><span class="sxs-lookup"><span data-stu-id="20212-189">An easy way to add subscriptions to your organization for Microsoft SaaS-based services is through the admin center:</span></span>
  
1. <span data-ttu-id="20212-190">Logga in på administrationscenter för Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="20212-190">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with your global administrator account.</span></span>
    
2. <span data-ttu-id="20212-191">Från vänster navigeringsfält i **Administrationscentrets** startsida klickar du på **Fakturering**, och sedan **Köptjänster**.</span><span class="sxs-lookup"><span data-stu-id="20212-191">From the left navigation of the **Admin center** home page, click **Billing**, and then **Purchase services**.</span></span>
    
3. <span data-ttu-id="20212-192">På sidan **Köptjänster** kan du köpa dina nya prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="20212-192">On the **Purchase services** page, purchase your new subscriptions.</span></span>
    
<span data-ttu-id="20212-193">Administrationscenter tilldelar organisationen och Azure AD-klientorganisationen för din Microsoft 365-prenumeration till de nya prenumerationerna för SaaS-baserade molnerbjudanden.</span><span class="sxs-lookup"><span data-stu-id="20212-193">The admin center assigns the organization and Azure AD tenant of your Microsoft 365 subscription to the new subscriptions for SaaS-based cloud offerings.</span></span>
  
<span data-ttu-id="20212-194">Så här lägger du till en Azure-prenumeration med samma organisation och Azure AD-klientorganisationen som Microsoft 365-prenumeration:</span><span class="sxs-lookup"><span data-stu-id="20212-194">To add an Azure subscription with the same organization and Azure AD tenant as your Microsoft 365 subscription:</span></span>
  
1. <span data-ttu-id="20212-195">Logga in på Azure-portalen ([https://portal.azure.com](https://portal.azure.com)) med ditt globala administratörskonto för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20212-195">Sign in to the Azure portal ([https://portal.azure.com](https://portal.azure.com)) with your Microsoft 365 global administrator account.</span></span>
    
2. <span data-ttu-id="20212-196">I vänster navigeringsfält, klicka på **Prenumerationer** och klicka sedanpå **Lägga till**.</span><span class="sxs-lookup"><span data-stu-id="20212-196">In the left navigation, click **Subscriptions**, and then click **Add**.</span></span>
    
3. <span data-ttu-id="20212-197">Välj ett erbjudande och slutför betalningsinformation och avtal genom att gå till sidan **Lägg till prenumerations**.</span><span class="sxs-lookup"><span data-stu-id="20212-197">On the **Add subscription** page, select an offer and complete the payment information and agreement.</span></span>
    
<span data-ttu-id="20212-198">Om du har köpt Azure-och Microsoft 365-prenumerationer separat och vill få åtkomst till Microsoft 365 Azure AD-klientorganisationen från din Azure-prenumeration läser du anvisningarna i [Lägga till en befintlig Azure-prenumeration i Azure Active Directory-klientorganisationen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span><span class="sxs-lookup"><span data-stu-id="20212-198">If you purchased Azure and Microsoft 365 subscriptions separately and want to access the Microsoft 365 Azure AD tenant from your Azure subscription, see the instructions in [Add an existing Azure subscription to your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="20212-199">Se även</span><span class="sxs-lookup"><span data-stu-id="20212-199">See also</span></span>

[<span data-ttu-id="20212-200">Illustrationer för Microsoft moln för företagsarkitektur</span><span class="sxs-lookup"><span data-stu-id="20212-200">Microsoft cloud for enterprise architects illustrations</span></span>](../solutions/cloud-architecture-models.md)
  
[<span data-ttu-id="20212-201">Arkitekturmodeller för SharePoint, Exchange, Skype för företag och Lync</span><span class="sxs-lookup"><span data-stu-id="20212-201">Architectural models for SharePoint, Exchange, Skype for Business, and Lync</span></span>](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[<span data-ttu-id="20212-202">Hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="20212-202">Hybrid solutions</span></span>](hybrid-solutions.md)

## <a name="next-step"></a><span data-ttu-id="20212-203">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="20212-203">Next step</span></span>

[<span data-ttu-id="20212-204">Utvärdera Microsoft 365 nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="20212-204">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
