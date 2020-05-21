---
title: Vanliga frågor och svar om domäner
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Läs mer om domäner genom att hitta svar på dina frågor i vanliga frågor.
ms.custom: okr_smb
ms.openlocfilehash: 1af20ed0052a7bb4f98072a7142bf7e112b8305e
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327118"
---
# <a name="domains-faq"></a><span data-ttu-id="84b44-103">Vanliga frågor och svar om domäner</span><span class="sxs-lookup"><span data-stu-id="84b44-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="84b44-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="84b44-104">The admin center is changing.</span></span> <span data-ttu-id="84b44-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="84b44-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="84b44-106">Den här artikeln innehåller svar på vanliga frågor och svar om domäner i Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-106">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="84b44-107">Om du inte hittar ett svar på din fråga här, kan du lämna en kommentar om det så lägger vi till det i listan.</span><span class="sxs-lookup"><span data-stu-id="84b44-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="84b44-108">Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="84b44-108">What is MX priority?</span></span>

<span data-ttu-id="84b44-109">E-post levereras till Exchange-servern med lägst företrädesnummer (högst prioritet). Därför ska den MX-post som du använder för e-postdirigering ha det lägsta företrädesnumret, vanligtvis 0, eller  *hög*  prioritet.</span><span class="sxs-lookup"><span data-stu-id="84b44-109">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="84b44-110">När du skapar en MX-post måste du ange ett företrädesnummer för de flesta DNS-värdar.</span><span class="sxs-lookup"><span data-stu-id="84b44-110">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="84b44-111">Vissa kallar rutan för  *företräde*  , andra för  *prioritet*  .</span><span class="sxs-lookup"><span data-stu-id="84b44-111">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="84b44-112">Vissa kräver ett nummer medan andra ber dig att välja mellan  *låg*  ,  *mellan*  eller  *hög*  .</span><span class="sxs-lookup"><span data-stu-id="84b44-112">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="84b44-113">Om du bara har en MX-post går det bra med vilket värde som helst för prioritet eller företräde.</span><span class="sxs-lookup"><span data-stu-id="84b44-113">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="84b44-114">Om du har fler än en ser du till att MX-posten för e-postdirigering har högre prioritet än den som används för att verifiera att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="84b44-114">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="84b44-115">Hur validerar jag SPF-poster för min domän?</span><span class="sxs-lookup"><span data-stu-id="84b44-115">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="84b44-116">Det är viktigt att du har eller skapar **endast en TXT-post för SPF**.</span><span class="sxs-lookup"><span data-stu-id="84b44-116">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="84b44-117">Om du redan har en SPF-post ska du lägga till nya Office 365-värden till den istället för att skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="84b44-117">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="84b44-118">När du har lagt till eller uppdaterat SPF-posten för Microsoft-e-post bör du kontrollera att syntaxen är korrekt med något av följande verktyg:</span><span class="sxs-lookup"><span data-stu-id="84b44-118">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="84b44-119">SPF Record Testing Tools</span><span class="sxs-lookup"><span data-stu-id="84b44-119">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="84b44-120">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="84b44-120">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="84b44-121">Dig web interface</span><span class="sxs-lookup"><span data-stu-id="84b44-121">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="84b44-122">Hur hanteras mina DNS-poster i Office 365?</span><span class="sxs-lookup"><span data-stu-id="84b44-122">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="84b44-123">Det finns två alternativ för DNS-hantering med Office 365:</span><span class="sxs-lookup"><span data-stu-id="84b44-123">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="84b44-124">Du ändrar dina NS-poster (Nameserver) och sedan tar Microsoft hand om alla tjänstspecifika poster, till exempel konfigurera din MX-post för e-post.</span><span class="sxs-lookup"><span data-stu-id="84b44-124">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="84b44-125">**(Rekommenderas)**</span><span class="sxs-lookup"><span data-stu-id="84b44-125">**(Recommended)**</span></span>
    
2. <span data-ttu-id="84b44-126">Du lägger själv till DNS-poster för e-post och andra Office 365-tjänster hos din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="84b44-126">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="84b44-127">**(Endast experter)**</span><span class="sxs-lookup"><span data-stu-id="84b44-127">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="84b44-128">Office 365 skapar och är värd för DNS-posterna</span><span class="sxs-lookup"><span data-stu-id="84b44-128">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="84b44-129">**Fördelar**</span><span class="sxs-lookup"><span data-stu-id="84b44-129">**Advantages**</span></span> 
- <span data-ttu-id="84b44-130">Du behöver inte oroa dig för att göra misstag i de värden du anger för DNS-posterna för Office 365-tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="84b44-130">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="84b44-131">Du får fler valmöjligheter när det gäller domänregistrator och DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="84b44-131">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="84b44-132">Du kan använda valfri leverantör som låter dig ändra namnserverposterna, även om leverantören inte hanterar alla nödvändiga posttyper.</span><span class="sxs-lookup"><span data-stu-id="84b44-132">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="84b44-133">När Office 365 lägger till nya DNS-poster behöver du inte göra uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="84b44-133">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="84b44-134">Nackdelar</span><span class="sxs-lookup"><span data-stu-id="84b44-134">Disadvantages</span></span> 
- <span data-ttu-id="84b44-135">Du kan inte ändra dina DNS-poster för e-post utanför Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-135">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="84b44-136">Om du redan använder en offentlig webbplats med din domän som adress, till exempel www.fourthcoffee.com, måste du dirigera om besökare till den adressen från Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-136">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="84b44-137">För att kunna konfigurera en omdirigering behöver du en statisk IP-adress, och det är inte alltid lätt att få tag i för offentliga webbplatser.</span><span class="sxs-lookup"><span data-stu-id="84b44-137">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="84b44-138">- Om din nuvarande domänregistratorer inte tillåter dig att ändra domänens namnserverposter måste du byta till en annan registrator för att använda det här DNS-hanteringsalternativet.</span><span class="sxs-lookup"><span data-stu-id="84b44-138">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="84b44-139">Du hanterar DNS-posterna själv</span><span class="sxs-lookup"><span data-stu-id="84b44-139">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="84b44-140">Fördelar</span><span class="sxs-lookup"><span data-stu-id="84b44-140">Advantages</span></span>
- <span data-ttu-id="84b44-141">Du styr DNS-posterna för Office 365-tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="84b44-141">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="84b44-142">Om du har en offentlig webbplats med din domän som adress, exempelvis www.fourthcoffee.com, behöver du inte tänka på att dirigera om för att folk fortfarande ska kunna använda webbplatsen när du har konfigurerat domänen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-142">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="84b44-143">Du har möjlighet att ha e-post någon annanstans, t.ex. med en lokal Exchange-server.    </span><span class="sxs-lookup"><span data-stu-id="84b44-143">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="84b44-144">Nackdelar</span><span class="sxs-lookup"><span data-stu-id="84b44-144">Disadvantages</span></span>
<span data-ttu-id="84b44-145">Du måste konfigurera DNS-posterna för Office 365-tjänsterna själv (om du inte har en GoDaddy-domän).</span><span class="sxs-lookup"><span data-stu-id="84b44-145">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="84b44-146">Om din nuvarande DNS-värd inte stöder alla nödvändiga posttyper för Microsoft 365 är vissa funktioner inte tillgängliga och du kan behöva byta till en annan DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="84b44-146">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="84b44-147">När Office 365 ändrar krav för DNS-poster eller lägger till nya tjänster måste du själv göra uppdateringar hos din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="84b44-147">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="84b44-148">Vad är ett domännamn?</span><span class="sxs-lookup"><span data-stu-id="84b44-148">What is a domain name?</span></span>


<span data-ttu-id="84b44-p106">En domän är ett unikt namn som visas efter **@** -tecknet i e-postadresser och efter **www.** i webbadresser. Det består vanligen av organisationens namn och ett vanligt Internetsuffix, till exempel  *företagsnamn.com*  eller  *universitetsnamn.edu*  .</span><span class="sxs-lookup"><span data-stu-id="84b44-p106">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="84b44-152">Genom att använda en anpassad domän som "**rob \@ contoso.com**" med Office 365 kan du skapa trovärdighet och erkännande för ditt varumärke.</span><span class="sxs-lookup"><span data-stu-id="84b44-152">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="84b44-153">Du kan [köpa en domän i Office 365](../get-help-with-domains/buy-a-domain-name.md), som vi konfigurerar automatiskt, eller så kan du köpa eller ta med en du redan äger från en domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="84b44-153">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="84b44-154">Kan jag överföra en domän som jag har köpt från Microsoft till en annan leverantör?</span><span class="sxs-lookup"><span data-stu-id="84b44-154">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="84b44-155">Ja, men du kan inte överföra en Office 365-domän till en annan registrator förrän 60 dagar efter att du köpte den med Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-155">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="84b44-156">Observera att en *Whois-fråga* visar en Office 365-köpt domänregistrare som Wild West Domains LLC.</span><span class="sxs-lookup"><span data-stu-id="84b44-156">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="84b44-157">Endast Office 365 bör dock kontaktas angående din köpta Office 365-domän.</span><span class="sxs-lookup"><span data-stu-id="84b44-157">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="84b44-158">Följ anvisningarna nedan för att hämta koden på Office 365, och gå sedan till den andra domänregistratorns webbplats för att överföra domännamnet till den registratorn.</span><span class="sxs-lookup"><span data-stu-id="84b44-158">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84b44-159">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-159">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84b44-160">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-160">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84b44-161">Gå till sidan **Inställningars** licenser i > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="84b44-161">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="84b44-162">På sidan **Domäner** väljer du den Office 365-domän som du vill överföra till en annan domänregistratorer och väljer sedan **Domain Transfer**  >  **Domänöverföring aktivera domänöverföring**.</span><span class="sxs-lookup"><span data-stu-id="84b44-162">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="84b44-163">Följ anvisningarna för att förbereda överföringen av domänen.</span><span class="sxs-lookup"><span data-stu-id="84b44-163">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="84b44-164">När du fått koden går du till webbplatsen för domänregistratorn som du vill hantera domännamnet hos framöver och följer dennes anvisningar för att överföra en domän (sök efter hjälp på domänregistratorns webbplats).</span><span class="sxs-lookup"><span data-stu-id="84b44-164">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="84b44-165">Om du behöver se koden igen väljer du **Visa auktoriseringskod för domänöverföring**på sidan **Domäninställningar** i Office 365 .</span><span class="sxs-lookup"><span data-stu-id="84b44-165">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="84b44-166">När överföringen är klar förnyar du domänen hos den nya domänregistraren.</span><span class="sxs-lookup"><span data-stu-id="84b44-166">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="84b44-167">Slutför processen genom att gå tillbaka till sidan Domäner för **administrationscenter** och välja **Slutför domänöverföring**.</span><span class="sxs-lookup"><span data-stu-id="84b44-167">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="84b44-168">*Observera att köpta Office 365-domäner inte är berättigade till namnserverändringar eller överföring av domänen mellan Office 365-klienter.  Om något av dessa krävs måste domänregistreringen överföras till en annan registrator.*</span><span class="sxs-lookup"><span data-stu-id="84b44-168">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="84b44-169">Hur ändrar jag hur mina DNS-poster hanteras i Office 365?</span><span class="sxs-lookup"><span data-stu-id="84b44-169">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="84b44-170">Ändra DNS-hanteringen till en DNS-värd utanför Office 365</span><span class="sxs-lookup"><span data-stu-id="84b44-170">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="84b44-171">Logga in på domänregistratorn för din domän.</span><span class="sxs-lookup"><span data-stu-id="84b44-171">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="84b44-p108">Leta reda på var du uppdaterar namnserverposterna på registratorns webbplats och uppdatera namnservrarna så att de pekar på domänens DNS-värd. (DNS-värden är ofta domänregistratorn.)</span><span class="sxs-lookup"><span data-stu-id="84b44-p108">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host. (The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="84b44-174">Följ en länk för att gå till installationsguiden för domäner:</span><span class="sxs-lookup"><span data-stu-id="84b44-174">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="84b44-175">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="84b44-176">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-176">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="84b44-177">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-177">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="84b44-178">På sidan **Domäner** väljer du den domän du byter och väljer **DNS-hantering**.</span><span class="sxs-lookup"><span data-stu-id="84b44-178">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="84b44-179">I guiden Konfigurera domäner väljer du Jag ska **hantera mina egna DNS-poster**på sidan **Konfigurera onlinetjänster** och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="84b44-179">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="84b44-180">Lägg till de DNS-poster som guiden föreslår på sidan **Uppdatera DNS-inställningar** på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="84b44-180">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="84b44-181">När du har lagt till posterna kommer du tillbaka till Office 365 och väljer **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="84b44-181">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="84b44-182">Ändra DNS-hanteringen till Office 365</span><span class="sxs-lookup"><span data-stu-id="84b44-182">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84b44-183">Gå till sidan **Inställningar** domäner i \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret..</a></span><span class="sxs-lookup"><span data-stu-id="84b44-183">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84b44-184">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-184">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84b44-185">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-185">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="84b44-186">På sidan **Domäner** väljer du den domän du byter och väljer **DNS-hantering**.</span><span class="sxs-lookup"><span data-stu-id="84b44-186">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="84b44-187">I guiden Konfigurera domäner väljer du Konfigurera mina onlinetjänster åt mig på sidan **Konfigurera onlinetjänster.** \*\* (Rekommenderas)\*\* och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="84b44-187">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="84b44-188">Om du inte har verifierat domänen ännu, följer du stegen nedan för att göra det först.</span><span class="sxs-lookup"><span data-stu-id="84b44-188">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="84b44-p109">På sidan **Uppdatera DNS-inställningar** visar vi namnservrarna för Office 365. Gå till domänregistratorn för domänen och uppdatera namnservrarna till Office 365-namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="84b44-p109">On the **Update DNS settings** page, we list the nameservers for Office 365. Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="84b44-191">När du har uppdaterat namnservrarna bör du **vänta i minst en timme**.</span><span class="sxs-lookup"><span data-stu-id="84b44-191">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="84b44-192">Välj sedan **Verifiera**i guiden i Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-192">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="84b44-193">Vad händer om min DNS-värd inte har stöd för vissa typer av poster?</span><span class="sxs-lookup"><span data-stu-id="84b44-193">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="84b44-p111">Om du hanterar dina egna DNS-poster och din DNS-värd inte har stöd för alla DNS-poster som Office 365 kräver kommer vissa funktioner i Office 365 inte att fungera. Vi rekommenderar att du för över din domän till en registrator som har stöd för alla DNS-poster som krävs.</span><span class="sxs-lookup"><span data-stu-id="84b44-p111">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work. We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="84b44-196">Värdar som har stöd för alla DNS-poster som krävs:</span><span class="sxs-lookup"><span data-stu-id="84b44-196">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="84b44-197">Dynadot</span><span class="sxs-lookup"><span data-stu-id="84b44-197">Dynadot</span></span>
    
- <span data-ttu-id="84b44-198">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="84b44-198">eNomCentral</span></span>
    
- <span data-ttu-id="84b44-199">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="84b44-199">Europe Registry</span></span>
    
- <span data-ttu-id="84b44-200">Godaddy</span><span class="sxs-lookup"><span data-stu-id="84b44-200">GoDaddy</span></span>
    
- <span data-ttu-id="84b44-201">Hover</span><span class="sxs-lookup"><span data-stu-id="84b44-201">Hover</span></span>
    
- <span data-ttu-id="84b44-202">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="84b44-202">MyHosting.com</span></span>
    
- <span data-ttu-id="84b44-203">Name.com</span><span class="sxs-lookup"><span data-stu-id="84b44-203">Name.com</span></span>
    
- <span data-ttu-id="84b44-204">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="84b44-204">Nearly Free Speech</span></span>
    
- <span data-ttu-id="84b44-205">Nettica</span><span class="sxs-lookup"><span data-stu-id="84b44-205">Nettica</span></span>
    
- <span data-ttu-id="84b44-206">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="84b44-206">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="84b44-207">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="84b44-207">Network Solutions</span></span>
    
- <span data-ttu-id="84b44-208">Register.com</span><span class="sxs-lookup"><span data-stu-id="84b44-208">Register.com</span></span>
    
 <span data-ttu-id="84b44-209">**Om SRV-poster inte stöds** är följande funktioner i Office 365 inte tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="84b44-209">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="84b44-210">Integration av Skype för företag - Online-funktioner för snabbmeddelanden och närvaro med Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="84b44-210">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="84b44-211">Extern kommunikation (federering) med Skype för företag - Online-användare i andra organisationer.</span><span class="sxs-lookup"><span data-stu-id="84b44-211">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="84b44-212">Public Internet Connectivity (PIC) med Skype för företag - Online-användare som loggat in med ett Microsoft-konto (hette tidigare Windows Live ID).</span><span class="sxs-lookup"><span data-stu-id="84b44-212">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="84b44-213">**Om flera CNAME-poster inte stöds** måste du välja mellan följande funktioner för Skype för företag – Online:</span><span class="sxs-lookup"><span data-stu-id="84b44-213">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="84b44-214">E-postklienter och mobila klienter kan använda Autodiscover för att automatiskt hitta Exchange Online-tjänsten så att användarna kan logga in utan att behöva ange ett servernamn.</span><span class="sxs-lookup"><span data-stu-id="84b44-214">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="84b44-215">Skype för företag - Online-skrivbordsklienter kan använda Autodiscover för att automatiskt hitta Skype för företag - Online-tjänsten så att användarna kan logga in utan att behöva ange ett servernamn.</span><span class="sxs-lookup"><span data-stu-id="84b44-215">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="84b44-216">Skype för företag - Online-klienter på mobila enheter kan använda Autodiscover för att automatiskt hitta Skype för företag - Online-tjänsten så att användarna kan logga in utan att behöva ange ett servernamn.</span><span class="sxs-lookup"><span data-stu-id="84b44-216">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>

- <span data-ttu-id="84b44-217">Microsoft Teams federation med Skype för företag, antingen lokalt eller online.</span><span class="sxs-lookup"><span data-stu-id="84b44-217">Microsoft Teams federation with Skype for Business, either on-premises or online.</span></span> <span data-ttu-id="84b44-218">Mer information finns i [Förbereda organisationens nätverk för Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="84b44-218">For more information, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>
    
 <span data-ttu-id="84b44-p113">**Om det inte finns stöd för SPF/TXT-poster** kan andra använda din domän för att skicka skräppost eller annan skadlig e-post. SPF-poster identifierar servrarna som är godkända för att skicka e-post från din domän.</span><span class="sxs-lookup"><span data-stu-id="84b44-p113">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email. SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="84b44-221">Hur anger eller ändrar jag standarddomänen i Office 365?</span><span class="sxs-lookup"><span data-stu-id="84b44-221">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="84b44-222">Du måste ha minst en egen domän som du har lagt till i Office 365 innan du kan välja en standarddomän.</span><span class="sxs-lookup"><span data-stu-id="84b44-222">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84b44-223">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-223">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84b44-224">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-224">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84b44-225">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84b44-225">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="84b44-226">På sidan **Domäner** väljer du den domän som du vill ange som standard för nya e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="84b44-226">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="84b44-227">Välj **Ange som standard**.</span><span class="sxs-lookup"><span data-stu-id="84b44-227">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="84b44-228">Du kan inte ändra namnet på din ursprungliga  *.onmicrosoft.com*  -domän.</span><span class="sxs-lookup"><span data-stu-id="84b44-228">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="84b44-229">Du kan inte ändra *.onmicrosoft.de* namnet på den ursprungliga .onmicrosoft.de-domänen.</span><span class="sxs-lookup"><span data-stu-id="84b44-229">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="84b44-230">Du kan inte ändra *.partner.onmschina.cn* namnet på den ursprungliga .partner.onmschina.cn-domänen.</span><span class="sxs-lookup"><span data-stu-id="84b44-230">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="84b44-231">Kan jag lägga till egna underdomäner eller flera domäner i Office 365?</span><span class="sxs-lookup"><span data-stu-id="84b44-231">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="84b44-232">Ja!</span><span class="sxs-lookup"><span data-stu-id="84b44-232">Yes!</span></span> <span data-ttu-id="84b44-233">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="84b44-233">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="84b44-234">Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="84b44-234">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="84b44-235">Ja!</span><span class="sxs-lookup"><span data-stu-id="84b44-235">Yes!</span></span> <span data-ttu-id="84b44-236">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="84b44-236">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="84b44-237">Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="84b44-237">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="84b44-238">Ja!</span><span class="sxs-lookup"><span data-stu-id="84b44-238">Yes!</span></span> <span data-ttu-id="84b44-239">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="84b44-239">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="84b44-240">Om du låter 21Vianet hantera dina DNS-inställningar med NS-poster kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="84b44-240">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="84b44-241">Vanligtvis kan du lägga till upp till 900 domäner i en Office 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="84b44-241">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="84b44-242">Du kan till exempel lägga till domänerna contoso.com och contosomarketing.com, och sedan lägga till underdomänerna www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com och så vidare.</span><span class="sxs-lookup"><span data-stu-id="84b44-242">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="84b44-243">När du lägger till en underdomän verifieras den automatiskt baserat på den överordnade domänen som verifieras.</span><span class="sxs-lookup"><span data-stu-id="84b44-243">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="84b44-p117">När du lägger till flera domäner i Office 365 kan du välja att ha valfri tjänst (t.ex. e-post) på valfri domän du har lagt till.  *När du ändrar din e-post till Office 365 genom att uppdatera en domäns MX-post levereras ALL e-post som skickas till den domänen till Office 365.*</span><span class="sxs-lookup"><span data-stu-id="84b44-p117">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.  *When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="84b44-246">Om du redan har lagt till en contoso.com domän i en Office 365-klientorganisation kan du också lägga till underdomänen xyz.contoso.com till en annan Office 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="84b44-246">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="84b44-247">När du lägger till underdomänen uppmanas du att lägga till en TXT-post i DNS-värdleverantören.</span><span class="sxs-lookup"><span data-stu-id="84b44-247">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="84b44-248">Varför har jag en onmicrosoft.com-domän?</span><span class="sxs-lookup"><span data-stu-id="84b44-248">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="84b44-249">Office 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.com*när du registrerar dig med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="84b44-249">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="84b44-250">Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="84b44-250">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="84b44-251">**Om du vill att din e-post ska se ut som *alan \@ contoso.com:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara stegen i [Lägg till dina användare och domäner i Office 365](add-domain.md) om du äger den redan.</span><span class="sxs-lookup"><span data-stu-id="84b44-251">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="84b44-p120">**Du kan inte byta namn på onmicrosoft-domänen efter registreringen.** Om den initiala domänen du valde till exempel var fourthcoffee.onmicrosoft.com, kan du inte ändra den till fabrikam.onmicrosoft.com. Om du vill använda en annan onmicrosoft.com-domän måste du påbörja en ny prenumeration med Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-p120">**You can't rename the onmicrosoft domain after sign-up.** For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com. To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="84b44-255">**Du kan inte byta namn på din gruppwebbplats-URL.**</span><span class="sxs-lookup"><span data-stu-id="84b44-255">**You can't rename your team site URL.**</span></span> <span data-ttu-id="84b44-256">Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.com domännamn.</span><span class="sxs-lookup"><span data-stu-id="84b44-256">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="84b44-257">På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="84b44-257">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="84b44-p122">**Du kan inte ta bort domänen onmicrosoft.** Office 365 måste behålla den eftersom den används i bakgrunden för din prenumeration. Men du behöver inte använda domänen när du har lagt till en egen domän.</span><span class="sxs-lookup"><span data-stu-id="84b44-p122">**You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="84b44-p123">Du kan emellertid fortsätta använda den första onmicrosoft.com-domänen, även efter att du har lagt till din domän. Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.</span><span class="sxs-lookup"><span data-stu-id="84b44-p123">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="84b44-263">Varför har jag en "onmicrosoft.de"-domän?</span><span class="sxs-lookup"><span data-stu-id="84b44-263">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="84b44-264">Office 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.de*, när du registrerar dig med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="84b44-264">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="84b44-265">Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="84b44-265">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="84b44-266">**Om du vill att din e-post ska se ut *alan@contoso.de:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara stegen i [Lägg till användare och domän i Office 365](add-domain.md) om du redan äger den.</span><span class="sxs-lookup"><span data-stu-id="84b44-266">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="84b44-267">**Du kan inte byta namn på onmicrosoft-domänen efter registreringen.**</span><span class="sxs-lookup"><span data-stu-id="84b44-267">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="84b44-268">Om den ursprungliga domänen du valde till exempel var fourthcoffee.onmicrosoft.de kan du inte ändra den till fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="84b44-268">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="84b44-269">Om du vill använda en annan onmicrosoft.de domän måste du starta en ny prenumeration med Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-269">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="84b44-270">**Du kan inte byta namn på din gruppwebbplats-URL.**</span><span class="sxs-lookup"><span data-stu-id="84b44-270">**You can't rename your team site URL.**</span></span> <span data-ttu-id="84b44-271">Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.de domännamn. På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="84b44-271">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="84b44-p127">**Du kan inte ta bort domänen onmicrosoft.** Office 365 måste behålla den eftersom den används i bakgrunden för din prenumeration. Men du behöver inte använda domänen när du har lagt till en egen domän.</span><span class="sxs-lookup"><span data-stu-id="84b44-p127">**You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="84b44-275">Du kan fortsätta använda den ursprungliga onmicrosoft.de domänen även efter att du har lagt till domänen.</span><span class="sxs-lookup"><span data-stu-id="84b44-275">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="84b44-276">Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.</span><span class="sxs-lookup"><span data-stu-id="84b44-276">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="84b44-277">Hur verifierar jag min ideella organisation eller utbildningsstatus?</span><span class="sxs-lookup"><span data-stu-id="84b44-277">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="84b44-278">Välj **Installationsprogrammet** i [administrationscentret](https://docs.microsoft.com/microsoft-365/admin/admin-home) för att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="84b44-278">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="84b44-279">(Var noga med att logga in på Office 365 först.)</span><span class="sxs-lookup"><span data-stu-id="84b44-279">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="84b44-280">Om du vill bli administratör för din skola väljer du alternativet **Bli administratör** i Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-280">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="84b44-281">Du uppmanas att lägga till en TXT DNS-post på DNS-värdwebbplatsen för din domän.</span><span class="sxs-lookup"><span data-stu-id="84b44-281">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="84b44-282">Varför?</span><span class="sxs-lookup"><span data-stu-id="84b44-282">Why?</span></span> <span data-ttu-id="84b44-283">Eftersom du genom att logga in på DNS-värden och lägga till en post för domänen bevisar du för Office 365 att du äger domännamnet.</span><span class="sxs-lookup"><span data-stu-id="84b44-283">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="84b44-284">När du har lagt till posten går du tillbaka till Office 365-portalen och bekräftar att du har lagt till den, så att Office 365 kan kontrollera.</span><span class="sxs-lookup"><span data-stu-id="84b44-284">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="84b44-285">Har du en ideell organisation och vill skaffa Office 365?</span><span class="sxs-lookup"><span data-stu-id="84b44-285">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="84b44-286">[Kontrollera att din organisation kvalificerar sig](https://www.microsoft.com/en-us/nonprofits/eligibility) och sedan registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="84b44-286">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="84b44-287">Vill du veta mer om att bli admin för din skola?</span><span class="sxs-lookup"><span data-stu-id="84b44-287">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="84b44-288">[Lär dig allt om det](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="84b44-288">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="84b44-289">Kan jag testa Office 365 med bara några få e-postadresser från min anpassade domän?</span><span class="sxs-lookup"><span data-stu-id="84b44-289">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="84b44-290">Du kan, men det finns begränsningar:</span><span class="sxs-lookup"><span data-stu-id="84b44-290">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="84b44-291">Din nuvarande e-postleverantör måste tillhandahålla vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="84b44-291">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="84b44-292">Du måste hantera dina Office 365-relaterade DNS-poster hos din DNS-värd i stället för att office 365 ska hantera dessa poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="84b44-292">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="84b44-293">Mer information om vad det innebär finns i Lägga till din domän i Office 365 när du vill hantera dina egna DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="84b44-293">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="84b44-294">Vissa Office 365-funktioner är inte tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="84b44-294">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="84b44-295">Användare kan inte se ledig/upptagen-information för de användare som finns på den andra e-postleverantören.</span><span class="sxs-lookup"><span data-stu-id="84b44-295">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="84b44-296">Administratörer kan inte administrera allas konton från ett ställe.</span><span class="sxs-lookup"><span data-stu-id="84b44-296">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="84b44-297">Användare kanske inte kan använda skräppostfiltrering i Office 365</span><span class="sxs-lookup"><span data-stu-id="84b44-297">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="84b44-298">Konfigurera en Office 365-pilot</span><span class="sxs-lookup"><span data-stu-id="84b44-298">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="84b44-299">Logga in på administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="84b44-299">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="84b44-300">Logga in på Office 365 med ditt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="84b44-300">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="84b44-301">Gå till **Inställningar** \> **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="84b44-301">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="84b44-302">Kontrollera att du äger den domän du vill använda</span><span class="sxs-lookup"><span data-stu-id="84b44-302">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="84b44-303">På sidan **Domäner** väljer du **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="84b44-303">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="84b44-304">Skriv domänen i det här exemplet cohowinery.com på panelen och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="84b44-304">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="84b44-305">Följ steg-för-steg-anvisningarna på sidan **Verifiera** domän.</span><span class="sxs-lookup"><span data-stu-id="84b44-305">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="84b44-306">Välj din DNS-värd i listrutan och följ instruktionerna för att visa att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="84b44-306">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="84b44-307">Välj **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="84b44-307">Select **Verify**.</span></span> <span data-ttu-id="84b44-308">Det tar mellan några minuter och 72 timmar innan DNS-ändringarna börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="84b44-308">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="84b44-309">När verifieringen lyckas blir du ombedd att ändra dina DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="84b44-309">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="84b44-310">Markera domänen som delad i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="84b44-310">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="84b44-311">Gå till **Administrationscentret** för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="84b44-311">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="84b44-312">Välj **Godkända domäner**i avsnittet **E-postflöde** .</span><span class="sxs-lookup"><span data-stu-id="84b44-312">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="84b44-313">Dubbelklicka på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="84b44-313">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="84b44-314">Välj **Internt relä**i fönstret som öppnas .</span><span class="sxs-lookup"><span data-stu-id="84b44-314">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="84b44-315">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="84b44-315">Select **Save**.</span></span> <span data-ttu-id="84b44-316">Den här inställningen kan kräva några minuter för att börja gälla.</span><span class="sxs-lookup"><span data-stu-id="84b44-316">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="84b44-317">Du kan också häva blockeringen av den befintliga e-postservern</span><span class="sxs-lookup"><span data-stu-id="84b44-317">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="84b44-318">Office 365 använder Exchange Online Protection (EOP) för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="84b44-318">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="84b44-319">Om EOP upptäcker en stor mängd skräppost som vidarebefordras av din nuvarande e-postserver kan det blockera den, vilket skulle förhindra att vidarebefordran fungerar.</span><span class="sxs-lookup"><span data-stu-id="84b44-319">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="84b44-320">Om du är säker på det skräppostskydd som din andra e-postleverantör använder kan du vitlista deras server i Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-320">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="84b44-321">Detta gör det dock också möjligt för skräppost som kommer via den ursprungliga servern att komma fram till Office 365-postlådorna, och du kan inte utvärdera hur väl Office 365 förhindrar skräppost.</span><span class="sxs-lookup"><span data-stu-id="84b44-321">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="84b44-322">Gå till Administrationscenter för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="84b44-322">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="84b44-323">I EAC väljer du **Skydd**och väljer sedan **Anslutningsfilter**.</span><span class="sxs-lookup"><span data-stu-id="84b44-323">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="84b44-324">I **listan TILLÅT IP**väljer du **+** och lägger till IP-adressen för e-postservern som du kan få från din nuvarande e-postleverantör.</span><span class="sxs-lookup"><span data-stu-id="84b44-324">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="84b44-325">Skapa användarkonton och ange den primära (svars)adressen</span><span class="sxs-lookup"><span data-stu-id="84b44-325">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="84b44-326">Gå till administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-326">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="84b44-327">I det vänstra **navigeringsfältet** väljer du Aktiva \> **användare .**</span><span class="sxs-lookup"><span data-stu-id="84b44-327">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="84b44-328">Skapa användarkontona.</span><span class="sxs-lookup"><span data-stu-id="84b44-328">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="84b44-329">För varje konto väljer du **+ (Ny)** och fyller i den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="84b44-329">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="84b44-330">Om du vill att användarens e-post ska vara på samma sätt som för närvarande bör fältet **Användarnamn** vara exakt samma som användarens befintliga e-postadress.</span><span class="sxs-lookup"><span data-stu-id="84b44-330">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="84b44-331">Bredvid Användarnamn väljer du ditt eget domännamn i listrutan.</span><span class="sxs-lookup"><span data-stu-id="84b44-331">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="84b44-332">Välj **Skapa** \> **stäng**.</span><span class="sxs-lookup"><span data-stu-id="84b44-332">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="84b44-333">Uppdatera DNS-poster hos din DNS-värd</span><span class="sxs-lookup"><span data-stu-id="84b44-333">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="84b44-334">Logga in på dns-värdleverantörens webbplats och följ [skapa DNS-poster på valfri DNS-värd för Office 365-steg](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="84b44-334">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="84b44-335">**Gör följande undantag:**</span><span class="sxs-lookup"><span data-stu-id="84b44-335">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="84b44-336">Skapa inte en ny MX-post eller ändra din befintliga MX-post.</span><span class="sxs-lookup"><span data-stu-id="84b44-336">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="84b44-337">Om du redan har en SPF-post (Sender Policy Framework) för din tidigare e-postleverantör, i stället för att skapa en ny SPF-post (TXT) för Exchange Online, lägger du bara till "include:spf.protection.outlook.com" i den aktuella TXT-posten.</span><span class="sxs-lookup"><span data-stu-id="84b44-337">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="84b44-338">Till exempel "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="84b44-338">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="84b44-339">Om du inte har en SPF-post ännu ändrar du den som rekommenderas av Office 365 för att inkludera domänen för din nuvarande e-postleverantör, plus spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="84b44-339">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="84b44-340">Detta godkänner utgående meddelanden från båda e-postsystemen.</span><span class="sxs-lookup"><span data-stu-id="84b44-340">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="84b44-341">Konfigurera vidarebefordran av e-post hos din nuvarande leverantör</span><span class="sxs-lookup"><span data-stu-id="84b44-341">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="84b44-342">Konfigurera vidarebefordran för användarnas e-postkonton på din nuvarande e-postleverantör till din onmicrosoft.com domän:</span><span class="sxs-lookup"><span data-stu-id="84b44-342">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="84b44-343">Användare A:s postlåda ska vidarebefordras till usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="84b44-343">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="84b44-344">Användare B:s postlåda ska vidarebefordras till userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="84b44-344">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="84b44-345">När du slutför det här steget:</span><span class="sxs-lookup"><span data-stu-id="84b44-345">When you complete this step:</span></span>
        
    5. <span data-ttu-id="84b44-346">All e-post som skickas till usera@yourcompany.com och userb@yourcompany.com är tillgänglig i Office 365.</span><span class="sxs-lookup"><span data-stu-id="84b44-346">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="84b44-347">Kommentarer:</span><span class="sxs-lookup"><span data-stu-id="84b44-347">Notes:</span></span>
        
        - <span data-ttu-id="84b44-348">Kontakta din nuvarande e-postleverantör för de exakta stegen för att konfigurera vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="84b44-348">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="84b44-349">Du behöver inte behålla en kopia av meddelanden hos den aktuella e-postleverantören.</span><span class="sxs-lookup"><span data-stu-id="84b44-349">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="84b44-350">De flesta leverantörer vidarebefordrar e-post och lämnar avsändarens svarsadress intakt, så att svaren går till den ursprungliga avsändaren.</span><span class="sxs-lookup"><span data-stu-id="84b44-350">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="84b44-351">Testa e-postflöde</span><span class="sxs-lookup"><span data-stu-id="84b44-351">Test mail flow</span></span>
    
    1. <span data-ttu-id="84b44-352">Logga in i Outlook Web App med autentiseringsuppgifter för användare A.</span><span class="sxs-lookup"><span data-stu-id="84b44-352">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="84b44-353">Utför följande tester:</span><span class="sxs-lookup"><span data-stu-id="84b44-353">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="84b44-354">Testa lokal Microsoft-e-post.</span><span class="sxs-lookup"><span data-stu-id="84b44-354">Test local Microsoft email.</span></span> <span data-ttu-id="84b44-355">Skicka till exempel ett e-postmeddelande till användare B. Detta e-postmeddelande bör levereras omedelbart.</span><span class="sxs-lookup"><span data-stu-id="84b44-355">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="84b44-356">I det här fallet dirigeras meddelandet inte till användare B-postlådan på den ursprungliga servern eftersom Office 365 ser postlådan som lokal.</span><span class="sxs-lookup"><span data-stu-id="84b44-356">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="84b44-357">Testa e-post till någon som är på det andra e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="84b44-357">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="84b44-358">Skicka till exempel ett e-postmeddelande till användare C. Det här e-postmeddelandet ska levereras till användare C:s postlåda på den ursprungliga e-postservern.</span><span class="sxs-lookup"><span data-stu-id="84b44-358">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="84b44-359">Från ett externt konto eller från en medarbetares e-postkonto i det andra e-postsystemet kontrollerar du att vidarebefordran är korrekt konfigurerad i det andra e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="84b44-359">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="84b44-360">Från användare C:s ursprungliga serverkonto eller ett Hotmail-konto skickar du till exempel ett e-postmeddelande till användare A och verifierar att den anländer till Office 365-postlådan för användare A.</span><span class="sxs-lookup"><span data-stu-id="84b44-360">For example, from User C's original server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="84b44-361">Flytta postlådeinnehåll</span><span class="sxs-lookup"><span data-stu-id="84b44-361">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="84b44-362">Eftersom det bara finns två användare att flytta, och eftersom användare A och användare B båda använder Outlook redan, kan e-postmeddelandet flyttas genom att öppna den gamla . PST-fil i den nya Outlook-profilen och kopiera meddelanden, kalenderobjekt, kontakter, etc. som visas i Importera Outlook-objekt från en Outlook-datafil (.pst).</span><span class="sxs-lookup"><span data-stu-id="84b44-362">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="84b44-363">När de har organiserats på rätt platser i Office 365-postlådan kan alla objekt nås från vilken enhet som helst, var som helst.</span><span class="sxs-lookup"><span data-stu-id="84b44-363">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="84b44-364">När fler postlådor är inblandade, eller om de anställda inte redan använder Outlook, kan du använda de migreringsverktyg som är tillgängliga i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="84b44-364">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="84b44-365">Kom igång genom att gå till administrationscentret för Exchange och följa anvisningarna i Migrera e-post från en IMAP-server till Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="84b44-365">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
