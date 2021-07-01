---
title: Lägga till en domän i en klientens innehavare med Windows PowerShell för DAP-partner
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
description: Sammanfattning Använd PowerShell för Microsoft 365 lägga till ett alternativt domännamn i en befintlig kundklientorganisation.
ms.openlocfilehash: 3bcdb40e2c72e5aac8103b0b55ff6fccfe6a9fcc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229089"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="db2ad-103">Lägga till en domän i ett klientföretag med Windows PowerShell för DAP-partners (Delegerad åtkomstbehörighet)</span><span class="sxs-lookup"><span data-stu-id="db2ad-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="db2ad-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="db2ad-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="db2ad-105">Du kan skapa och koppla nya domäner till kundens innehavare med PowerShell för Microsoft 365 snabbare än med Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db2ad-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>

<span data-ttu-id="db2ad-106">DAP-partner (Delegerad åtkomstbehörighet) är syndicerings- och molnlösningsleverantörer (CSP).</span><span class="sxs-lookup"><span data-stu-id="db2ad-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="db2ad-107">De är ofta nätverks- eller telekommunikationsleverantörer till andra företag.</span><span class="sxs-lookup"><span data-stu-id="db2ad-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="db2ad-108">De paketar Microsoft 365 prenumerationer till sina tjänsteerbjudanden till sina kunder.</span><span class="sxs-lookup"><span data-stu-id="db2ad-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="db2ad-109">När de säljer en Microsoft 365-prenumeration tilldelas de automatiskt behörigheten Administrera för (AOBO) för kundens företag så att de kan administrera och rapportera om kundrelationerna.</span><span class="sxs-lookup"><span data-stu-id="db2ad-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db2ad-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="db2ad-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="db2ad-111">Procedurerna i det här avsnittet kräver att du ansluter [till Anslut och Microsoft 365 med PowerShell.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="db2ad-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="db2ad-112">Du behöver också autentiseringsuppgifterna för partnerklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="db2ad-112">You also need your partner tenant administrator credentials.</span></span>

<span data-ttu-id="db2ad-113">Du behöver också följande information:</span><span class="sxs-lookup"><span data-stu-id="db2ad-113">You also need the following information:</span></span>

- <span data-ttu-id="db2ad-114">Du behöver det fullständigt kvalificerade domännamnet (FQDN) som kunden vill ha.</span><span class="sxs-lookup"><span data-stu-id="db2ad-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>

- <span data-ttu-id="db2ad-115">Du behöver kundens **Klientorganisations-ID.**</span><span class="sxs-lookup"><span data-stu-id="db2ad-115">You need the customer's **TenantId**.</span></span>

- <span data-ttu-id="db2ad-116">FQDN måste vara registrerat med en DNS-registrator (Internet Domain Name Service), till exempel GoDaddy.</span><span class="sxs-lookup"><span data-stu-id="db2ad-116">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy.</span></span> <span data-ttu-id="db2ad-117">Mer information om hur du registrerar ett domännamn offentligt finns i [Så här köper du ett domännamn.](../admin/get-help-with-domains/buy-a-domain-name.md)</span><span class="sxs-lookup"><span data-stu-id="db2ad-117">For more information on how to publically register a domain name, see [How to buy a domain name](../admin/get-help-with-domains/buy-a-domain-name.md).</span></span>

- <span data-ttu-id="db2ad-118">Du behöver veta hur du lägger till en TXT-post i den registrerade DNS-zonen för din DNS-registrator.</span><span class="sxs-lookup"><span data-stu-id="db2ad-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="db2ad-119">Mer information om hur du lägger till en TXT-post finns i Lägga [till DNS-poster för att ansluta din domän.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="db2ad-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="db2ad-120">Om de procedurerna inte fungerar för dig måste du hitta procedurerna för din DNS-registrator.</span><span class="sxs-lookup"><span data-stu-id="db2ad-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>

## <a name="create-domains"></a><span data-ttu-id="db2ad-121">Skapa domäner</span><span class="sxs-lookup"><span data-stu-id="db2ad-121">Create domains</span></span>

 <span data-ttu-id="db2ad-122">Kunderna kommer antagligen att be dig skapa fler domäner att associera med deras innehavare eftersom de inte vill att standarddomänen .onmicrosoft.com ska vara den primära som representerar deras företagsidentiteter i <domain> världen.</span><span class="sxs-lookup"><span data-stu-id="db2ad-122">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world.</span></span> <span data-ttu-id="db2ad-123">I den här proceduren får du hjälp med att skapa en ny domän som är kopplad till kundens innehavare.</span><span class="sxs-lookup"><span data-stu-id="db2ad-123">This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>

> [!NOTE]
> <span data-ttu-id="db2ad-124">För att några av de här åtgärderna ska kunna utföras måste partneradministratörskontot som du loggar in med vara inställt på Fullständig **administration** för inställningen Tilldela administrativ åtkomst till företag som du stöder i informationen om administratörskontot i Administrationscenter för Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="db2ad-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="db2ad-125">Mer information om hur du hanterar partneradministratörsroller finns i [Partner: Erbjuda delegerad administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span><span class="sxs-lookup"><span data-stu-id="db2ad-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span>

### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="db2ad-126">Skapa domänen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="db2ad-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="db2ad-127">Det här kommandot skapar domänen i Azure Active Directory men associerar den inte med den offentligt registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="db2ad-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="db2ad-128">När du bevisar att du äger den offentligt registrerade domänen för Microsoft Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="db2ad-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> <span data-ttu-id="db2ad-129">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="db2ad-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="db2ad-130">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db2ad-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="db2ad-131">Hämta data för verifieringsposten för DNS TXT</span><span class="sxs-lookup"><span data-stu-id="db2ad-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="db2ad-132">Microsoft 365 genererar de specifika data som du behöver placera i DNS TXT-verifieringsposten.</span><span class="sxs-lookup"><span data-stu-id="db2ad-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="db2ad-133">Kör det här kommandot för att hämta data.</span><span class="sxs-lookup"><span data-stu-id="db2ad-133">To get the data, run this command.</span></span>

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="db2ad-134">Det ger dig följande utdata:</span><span class="sxs-lookup"><span data-stu-id="db2ad-134">This will give you output like:</span></span>

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> <span data-ttu-id="db2ad-135">Du behöver den här texten för att skapa TXT-posten i den offentligt registrerade DNS-zonen.</span><span class="sxs-lookup"><span data-stu-id="db2ad-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="db2ad-136">Se till att kopiera och spara den.</span><span class="sxs-lookup"><span data-stu-id="db2ad-136">Be sure to copy and save it.</span></span>

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="db2ad-137">Lägga till en TXT-post i den offentligt registrerade DNS-zonen</span><span class="sxs-lookup"><span data-stu-id="db2ad-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="db2ad-138">Innan Microsoft 365 börjar ta emot trafik som dirigeras till det offentligt registrerade domännamnet måste du bevisa att du äger och har administratörsbehörighet till domänen.</span><span class="sxs-lookup"><span data-stu-id="db2ad-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="db2ad-139">Du bevisa att du äger domänen genom att skapa en TXT-post i domänen.</span><span class="sxs-lookup"><span data-stu-id="db2ad-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="db2ad-140">En TXT-post gör inget i din domän och den kan tas bort när du har upprättat ägarskap för domänen.</span><span class="sxs-lookup"><span data-stu-id="db2ad-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="db2ad-141">Om du vill skapa TXT-posterna följer du procedurerna [för att lägga till DNS-poster för att ansluta din domän.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="db2ad-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="db2ad-142">Om de procedurerna inte fungerar för dig måste du hitta procedurerna för din DNS-registrator.</span><span class="sxs-lookup"><span data-stu-id="db2ad-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>

<span data-ttu-id="db2ad-143">Bekräfta att TXT-posten har skapats via nslookup.</span><span class="sxs-lookup"><span data-stu-id="db2ad-143">Confirm the successful creation of the TXT record via nslookup.</span></span> <span data-ttu-id="db2ad-144">Följ denna syntax.</span><span class="sxs-lookup"><span data-stu-id="db2ad-144">Follow this syntax.</span></span>

```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="db2ad-145">Det ger dig följande utdata:</span><span class="sxs-lookup"><span data-stu-id="db2ad-145">This will give you output like:</span></span>

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="db2ad-146">Verifiera domänägarskap i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db2ad-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="db2ad-147">I det sista steget verifierar du Microsoft 365 att du äger den offentligt registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="db2ad-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="db2ad-148">Efter det här steget Microsoft 365 trafik till det nya domännamnet.</span><span class="sxs-lookup"><span data-stu-id="db2ad-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="db2ad-149">Kör det här kommandot för att slutföra processen för att skapa och registrera en domän.</span><span class="sxs-lookup"><span data-stu-id="db2ad-149">To complete the domain creation and registration process, run this command.</span></span>

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="db2ad-150">Det här kommandot returnerar inte några utdata, så kör det här kommandot för att bekräfta att det fungerade.</span><span class="sxs-lookup"><span data-stu-id="db2ad-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="db2ad-151">Detta returnerar något i den här</span><span class="sxs-lookup"><span data-stu-id="db2ad-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```


## <a name="see-also"></a><span data-ttu-id="db2ad-152">Se även</span><span class="sxs-lookup"><span data-stu-id="db2ad-152">See also</span></span>

####

[<span data-ttu-id="db2ad-153">Hjälp för partners</span><span class="sxs-lookup"><span data-stu-id="db2ad-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)