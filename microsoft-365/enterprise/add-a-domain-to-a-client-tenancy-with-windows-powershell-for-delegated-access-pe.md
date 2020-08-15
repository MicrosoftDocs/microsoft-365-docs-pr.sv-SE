---
title: Lägga till en domän till en klient innehav med Windows PowerShell för DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Sammanfattning: Använd PowerShell för Microsoft 365 för att lägga till ett alternativt domän namn i en befintlig kund klient organisation.'
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694897"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="0618a-103">Lägga till en domän i en klient innehav med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)</span><span class="sxs-lookup"><span data-stu-id="0618a-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="0618a-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0618a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0618a-105">Du kan skapa och koppla nya domäner till kundens innehav med PowerShell för Microsoft 365 snabbare än att använda administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0618a-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="0618a-106">DAP-partners (delegerade åtkomst behörigheter) för syndikering och moln lösnings leverantörer.</span><span class="sxs-lookup"><span data-stu-id="0618a-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="0618a-107">De är ofta nätverks-eller Telekom-leverantörer i andra företag.</span><span class="sxs-lookup"><span data-stu-id="0618a-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="0618a-108">De fördelar Microsoft 365-abonnemang till sina kunder.</span><span class="sxs-lookup"><span data-stu-id="0618a-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="0618a-109">När de säljer en Microsoft 365-prenumeration beviljas de automatiskt administration på uppdrag av (AOBO) behörigheter till kundens innehav så att de kan administrera och rapportera om kundens innehavare.</span><span class="sxs-lookup"><span data-stu-id="0618a-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0618a-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="0618a-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="0618a-111">Procedurerna i det här avsnittet kräver att du ansluter till [Microsoft 365 med PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0618a-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="0618a-112">Du behöver också dina autentiseringsuppgifter för partner klient organisation.</span><span class="sxs-lookup"><span data-stu-id="0618a-112">You also need your partner tenant administrator credentials.</span></span>
  
<span data-ttu-id="0618a-113">Du behöver också följande information:</span><span class="sxs-lookup"><span data-stu-id="0618a-113">You also need the following information:</span></span>
  
- <span data-ttu-id="0618a-114">Du behöver det fullständigt kvalificerade domän namnet (FQDN) som din kund önskar.</span><span class="sxs-lookup"><span data-stu-id="0618a-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>
    
- <span data-ttu-id="0618a-115">Du behöver kundens **TenantId**.</span><span class="sxs-lookup"><span data-stu-id="0618a-115">You need the customer's **TenantId**.</span></span>
    
- <span data-ttu-id="0618a-116">FQDN måste vara registrerat hos en DNS-registrator för Internet, till exempel GoDaddy.</span><span class="sxs-lookup"><span data-stu-id="0618a-116">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy.</span></span> <span data-ttu-id="0618a-117">Mer information om hur du registrerar ett domän namn offentligt finns i [så här köper du ett domän namn](https://go.microsoft.com/fwlink/p/?LinkId=532541).</span><span class="sxs-lookup"><span data-stu-id="0618a-117">For more information on how to publically register a domain name, see [How to buy a domain name](https://go.microsoft.com/fwlink/p/?LinkId=532541).</span></span>
    
- <span data-ttu-id="0618a-118">Du måste veta hur du lägger till en TXT-post i den registrerade DNS-zonen för din DNS-registrator.</span><span class="sxs-lookup"><span data-stu-id="0618a-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="0618a-119">Mer information om hur du lägger till en TXT-post finns i [lägga till DNS-poster för att ansluta din domän](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span><span class="sxs-lookup"><span data-stu-id="0618a-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="0618a-120">Om dessa procedurer inte fungerar för dig måste du hitta procedurerna för din DNS-registrator.</span><span class="sxs-lookup"><span data-stu-id="0618a-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>
    
## <a name="create-domains"></a><span data-ttu-id="0618a-121">Skapa domäner</span><span class="sxs-lookup"><span data-stu-id="0618a-121">Create domains</span></span>

 <span data-ttu-id="0618a-122">Kunderna uppmanas antagligen att skapa ytterligare domäner för att kopplas till deras innehavande, eftersom de inte vill använda standard <domain> domänen. onmicrosoft.com domain som representerar deras företags identitet för världen.</span><span class="sxs-lookup"><span data-stu-id="0618a-122">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world.</span></span> <span data-ttu-id="0618a-123">Med den här proceduren får du hjälp med att skapa en ny domän som är kopplad till kundens innehav.</span><span class="sxs-lookup"><span data-stu-id="0618a-123">This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0618a-124">För att utföra vissa av dessa åtgärder måste partner administratörs kontot som du loggar in med vara inställt på **fullständig administration** för gruppen **tilldela administrativ åtkomst till företag som du** har 365 stöd för.</span><span class="sxs-lookup"><span data-stu-id="0618a-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0618a-125">Mer information om hur du hanterar roller för partner administratörer finns i [partners: tillhandahålla delegerad administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span><span class="sxs-lookup"><span data-stu-id="0618a-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span> 
  
### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="0618a-126">Skapa domänen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0618a-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="0618a-127">Det här kommandot skapar domänen i Azure Active Directory men associerar den inte med den offentligt registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="0618a-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="0618a-128">Det kommer när du bevisa att du äger den offentligt registrerade domänen till Microsoft Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="0618a-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
><span data-ttu-id="0618a-129">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="0618a-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="0618a-130">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0618a-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="0618a-131">Hämta data för DNS TXT-verifierings posten</span><span class="sxs-lookup"><span data-stu-id="0618a-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="0618a-132">Microsoft 365 kommer att skapa specifika data som du måste placera i DNS TXT-verifieringen.</span><span class="sxs-lookup"><span data-stu-id="0618a-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="0618a-133">Kör det här kommandot för att hämta data.</span><span class="sxs-lookup"><span data-stu-id="0618a-133">To get the data, run this command.</span></span>
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="0618a-134">Då får du utdata som:</span><span class="sxs-lookup"><span data-stu-id="0618a-134">This will give you output like:</span></span>
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> <span data-ttu-id="0618a-135">Du behöver den här texten för att skapa TXT-posten i den offentligt registrerade DNS-zonen.</span><span class="sxs-lookup"><span data-stu-id="0618a-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="0618a-136">Glöm inte att kopiera och spara den.</span><span class="sxs-lookup"><span data-stu-id="0618a-136">Be sure to copy and save it.</span></span> 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="0618a-137">Lägga till en TXT-post i den offentligt registrerade DNS-zonen</span><span class="sxs-lookup"><span data-stu-id="0618a-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="0618a-138">Innan Microsoft 365 kommer att börja acceptera trafik som dirigeras till det offentligt registrerade domän namnet måste du bevisa att du äger och har administratörs behörighet för domänen.</span><span class="sxs-lookup"><span data-stu-id="0618a-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="0618a-139">Du bekräftar att du äger domänen genom att skapa en TXT-post i domänen.</span><span class="sxs-lookup"><span data-stu-id="0618a-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="0618a-140">En TXT-post gör ingenting i din domän och kan tas bort när din domän är uppkopplad.</span><span class="sxs-lookup"><span data-stu-id="0618a-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="0618a-141">Skapa TXT-posterna genom att följa anvisningarna i [lägga till DNS-poster för att ansluta din domän](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span><span class="sxs-lookup"><span data-stu-id="0618a-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="0618a-142">Om dessa procedurer inte fungerar för dig måste du hitta procedurerna för din DNS-registrator.</span><span class="sxs-lookup"><span data-stu-id="0618a-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>
  
<span data-ttu-id="0618a-143">Bekräfta att TXT-posten har skapats via nslookup.</span><span class="sxs-lookup"><span data-stu-id="0618a-143">Confirm the successful creation of the TXT record via nslookup.</span></span> <span data-ttu-id="0618a-144">Följ den här syntaxen.</span><span class="sxs-lookup"><span data-stu-id="0618a-144">Follow this syntax.</span></span>
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="0618a-145">Då får du utdata som:</span><span class="sxs-lookup"><span data-stu-id="0618a-145">This will give you output like:</span></span>
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="0618a-146">Verifiera domän ägarskap i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0618a-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="0618a-147">I det här förra steget validerar du till Microsoft 365 som du äger den offentligt registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="0618a-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="0618a-148">Efter det här steget börjar Microsoft 365 att acceptera trafik som dirigeras till det nya domän namnet.</span><span class="sxs-lookup"><span data-stu-id="0618a-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="0618a-149">Kör det här kommandot för att slutföra skapandet av domäner och registrering.</span><span class="sxs-lookup"><span data-stu-id="0618a-149">To complete the domain creation and registration process, run this command.</span></span> 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="0618a-150">Det här kommandot returnerar ingen utskrift, så du kan kontrol lera att det fungerade genom att köra det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="0618a-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="0618a-151">Det här kommer att returnera ungefär så här</span><span class="sxs-lookup"><span data-stu-id="0618a-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a><span data-ttu-id="0618a-152">Se även</span><span class="sxs-lookup"><span data-stu-id="0618a-152">See also</span></span>

#### 

[<span data-ttu-id="0618a-153">Hjälp för partners</span><span class="sxs-lookup"><span data-stu-id="0618a-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)

