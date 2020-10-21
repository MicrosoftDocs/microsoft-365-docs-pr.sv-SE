---
title: Vanliga frågor och svar om domäner
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Lär dig mer om domäner genom att hitta svar på vanliga frågor.
ms.openlocfilehash: b51b5fe56bbae56dd473dd831ec91e629d9233f3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644590"
---
# <a name="domains-faq"></a><span data-ttu-id="cc3d6-103">Vanliga frågor och svar om domäner</span><span class="sxs-lookup"><span data-stu-id="cc3d6-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cc3d6-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-104">The admin center is changing.</span></span> <span data-ttu-id="cc3d6-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="cc3d6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="cc3d6-106">Den här artikeln innehåller svar på vanliga frågor om domäner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="cc3d6-107">Om du inte hittar ett svar på din fråga här, kan du lämna en kommentar om det så lägger vi till det i listan.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="cc3d6-108">I den här artikeln</span><span class="sxs-lookup"><span data-stu-id="cc3d6-108">In this article</span></span>

- [<span data-ttu-id="cc3d6-109">Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="cc3d6-110">Hur validerar jag SPF-poster för min domän?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="cc3d6-111">Vad är ett domännamn?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="cc3d6-112">Vad händer om min DNS-värd inte har stöd för vissa typer av poster?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="cc3d6-113">Hur ställer jag in eller ändrar standard domänen i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="cc3d6-114">Kan jag lägga till egna under domäner eller flera domäner i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="cc3d6-115">Hur överför jag en domän från Microsoft 365 till en annan värd?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="cc3d6-116">Varför har jag en onmicrosoft.com-domän?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="cc3d6-117">Varför har jag en "onmicrosoft.de"-domän?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="cc3d6-118">Hur verifierar jag min status som inte vinst eller utbildning?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="cc3d6-119">Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-119">What is MX priority?</span></span>

<span data-ttu-id="cc3d6-120">E-post levereras till Exchange-servern med lägst företrädesnummer (högst prioritet). Därför ska den MX-post som du använder för e-postdirigering ha det lägsta företrädesnumret, vanligtvis 0, eller  *hög*  prioritet.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="cc3d6-121">När du skapar en MX-post måste du ange ett företrädesnummer för de flesta DNS-värdar.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="cc3d6-122">Vissa kallar rutan för  *företräde*  , andra för  *prioritet*  .</span><span class="sxs-lookup"><span data-stu-id="cc3d6-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="cc3d6-123">Vissa kräver ett nummer medan andra ber dig att välja mellan  *låg*  ,  *mellan*  eller  *hög*  .</span><span class="sxs-lookup"><span data-stu-id="cc3d6-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="cc3d6-124">Om du bara har en MX-post går det bra med vilket värde som helst för prioritet eller företräde.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="cc3d6-125">Om du har fler än en ser du till att MX-posten för e-postdirigering har högre prioritet än den som används för att verifiera att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="cc3d6-126">Hur validerar jag SPF-poster för min domän?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="cc3d6-127">Det är viktigt att du har eller  **bara skapar en TXT-post för SPF**.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="cc3d6-128">Om du redan har en SPF-post ska du lägga till de nya Microsoft 365-värdena i stället för att skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="cc3d6-129">När du har lagt till eller uppdaterat SPF-posten för Microsoft-e-post bör du kontrol lera att syntaxen stämmer med något av följande verktyg:</span><span class="sxs-lookup"><span data-stu-id="cc3d6-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="cc3d6-130">SPF Record Testing Tools</span><span class="sxs-lookup"><span data-stu-id="cc3d6-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="cc3d6-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="cc3d6-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="cc3d6-132">Dig web interface</span><span class="sxs-lookup"><span data-stu-id="cc3d6-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="cc3d6-133">Vad är ett domännamn?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-133">What is a domain name?</span></span>

<span data-ttu-id="cc3d6-p103">En domän är ett unikt namn som visas efter **@** -tecknet i e-postadresser och efter **www.** i webbadresser. Det består vanligen av organisationens namn och ett vanligt Internetsuffix, till exempel  *företagsnamn.com*  eller  *universitetsnamn.edu*  .</span><span class="sxs-lookup"><span data-stu-id="cc3d6-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="cc3d6-137">Om du använder en egen domän som "**anders \@ contoso.com**" med Microsoft 365 kan du skapa trovärdighet och igenkänning för varumärket.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="cc3d6-138">Du kan [köpa en domän i Microsoft 365 och ställa in den automatiskt](../get-help-with-domains/buy-a-domain-name.md), eller så kan du köpa eller ta med en du redan äger från en domän registrator.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="cc3d6-139">Vad händer om min DNS-värd inte har stöd för vissa typer av poster?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="cc3d6-140">Om du hanterar dina egna DNS-poster och din DNS-värd inte har stöd för alla DNS-poster som Microsoft 365 behöver kommer vissa funktioner i Microsoft 365 inte att fungera.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="cc3d6-141">Vi rekommenderar att du för över din domän till en registrator som har stöd för alla DNS-poster som krävs.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="cc3d6-142">Värdar som har stöd för alla DNS-poster som krävs:</span><span class="sxs-lookup"><span data-stu-id="cc3d6-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="cc3d6-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="cc3d6-143">Dynadot</span></span>
    
- <span data-ttu-id="cc3d6-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="cc3d6-144">eNomCentral</span></span>
    
- <span data-ttu-id="cc3d6-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="cc3d6-145">Europe Registry</span></span>
    
- <span data-ttu-id="cc3d6-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="cc3d6-146">GoDaddy</span></span>
    
- <span data-ttu-id="cc3d6-147">Hover</span><span class="sxs-lookup"><span data-stu-id="cc3d6-147">Hover</span></span>
    
- <span data-ttu-id="cc3d6-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="cc3d6-148">MyHosting.com</span></span>
    
- <span data-ttu-id="cc3d6-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="cc3d6-149">Name.com</span></span>
    
- <span data-ttu-id="cc3d6-150">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="cc3d6-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="cc3d6-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="cc3d6-151">Nettica</span></span>
    
- <span data-ttu-id="cc3d6-152">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="cc3d6-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="cc3d6-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="cc3d6-153">Network Solutions</span></span>
    
- <span data-ttu-id="cc3d6-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="cc3d6-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="cc3d6-155">Hur ställer jag in eller ändrar standard domänen i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="cc3d6-156">Du måste ha minst en egen domän som du har lagt till i Microsoft 365 innan du kan välja en standard domän.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cc3d6-157">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cc3d6-158">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cc3d6-159">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="cc3d6-160">På sidan **domäner** väljer du den domän som du vill ange som standard för nya e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="cc3d6-161">Välj **Ange som standard**.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="cc3d6-162">Du kan inte ändra namnet på din ursprungliga  *.onmicrosoft.com*  -domän.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cc3d6-163">Du kan inte ändra namnet på din initiala  *onmicrosoft.de*  -domän.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cc3d6-164">Du kan inte ändra namnet på din initiala  *partner.onmschina.cn*  -domän.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="cc3d6-165">Kan jag lägga till egna under domäner eller flera domäner i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="cc3d6-166">Ja.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-166">Yes.</span></span> <span data-ttu-id="cc3d6-167">Om du vill lägga till under domäner måste du hantera dina egna DNS-inställningar hos registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cc3d6-168">Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till under domäner.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cc3d6-169">Ja!</span><span class="sxs-lookup"><span data-stu-id="cc3d6-169">Yes!</span></span> <span data-ttu-id="cc3d6-170">Om du vill lägga till under domäner måste du hantera dina egna DNS-inställningar hos registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cc3d6-171">Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till under domäner.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cc3d6-172">Ja!</span><span class="sxs-lookup"><span data-stu-id="cc3d6-172">Yes!</span></span> <span data-ttu-id="cc3d6-173">Om du vill lägga till under domäner måste du hantera dina egna DNS-inställningar hos registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cc3d6-174">Om du låter 21Vianet hantera dina DNS-inställningar med NS-poster kan du inte lägga till under domäner.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="cc3d6-175">Vanligt vis kan du lägga till upp till 900-domäner i din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="cc3d6-176">Du kan till exempel lägga till domänerna contoso.com och contosomarketing.com, och sedan lägga till underdomänerna www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com och så vidare.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="cc3d6-177">När du lägger till en under domän verifieras den automatiskt baserat på den överordnade domänen som verifieras.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="cc3d6-178">När du lägger till flera domäner i Microsoft 365 kan du hantera alla tjänster (som e-post) på någon av de domäner som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="cc3d6-179">*När du ändrar din e-post till Microsoft 365 genom att uppdatera en domäns MX-post kommer ALL e-post som skickas till domänen att komma till Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="cc3d6-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="cc3d6-180">Om du har lagt till en contoso.com-domän i en Microsoft 365-prenumeration kan du också lägga till under domäns xyz.contoso.com till en annan Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="cc3d6-181">När du lägger till under domänen uppmanas du att lägga till en TXT-post i DNS-värden.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="cc3d6-182">Hur överför jag en domän från Microsoft 365 till en annan värd?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="cc3d6-183">Information om hur du överför en domän finns i [överföra en domän från Microsoft till en annan värd](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span><span class="sxs-lookup"><span data-stu-id="cc3d6-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="cc3d6-184">Pilot Microsoft 365 från min anpassade domän</span><span class="sxs-lookup"><span data-stu-id="cc3d6-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="cc3d6-185">Anvisningar för hur du piloterar Microsoft 365-e-postfunktioner från en anpassad domän till en Microsoft 365-postlåda finns i [pilot Microsoft 365 From My Custom Domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="cc3d6-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="cc3d6-186">Varför har jag en onmicrosoft.com-domän?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="cc3d6-187">Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.com*, när du registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="cc3d6-188">Det användar-ID som du skapar när du registrerar dig inkluderar domänen, till exempel *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="cc3d6-189">**Om du vill att e-postmeddelandet ska se ut som *Alan \@ contoso.com*:** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ instruktionerna i [lägga till användare och domän till Microsoft 365](add-domain.md) om du redan har den.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="cc3d6-190">**Du kan inte byta namn på onmicrosoft-domänen efter registreringen.**</span><span class="sxs-lookup"><span data-stu-id="cc3d6-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="cc3d6-191">Om den initiala domänen du valde till exempel var fourthcoffee.onmicrosoft.com, kan du inte ändra den till fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="cc3d6-192">Om du vill använda en annan onmicrosoft.com-domän måste du starta en ny prenumeration med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="cc3d6-193">**Du kan inte byta namn på din gruppwebbplats-URL.**</span><span class="sxs-lookup"><span data-stu-id="cc3d6-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="cc3d6-194">Din grupp webbplats URL baseras på ditt onmicrosoft.com-domän namn.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="cc3d6-195">Tyvärr kan du inte byta namn på grupp webbplatsen på grund av hur SharePoint Online-arkitekturen fungerar.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="cc3d6-196">**Du kan inte ta bort domänen onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="cc3d6-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="cc3d6-197">Microsoft 365 måste hålla det nära eftersom det används bakom dina abonnemangs scener.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="cc3d6-198">Men du behöver inte använda domänen när du har lagt till en egen domän.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="cc3d6-p114">Du kan emellertid fortsätta använda den första onmicrosoft.com-domänen, även efter att du har lagt till din domän. Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="cc3d6-201">Varför har jag en "onmicrosoft.de"-domän?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="cc3d6-202">Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.de*, när du registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="cc3d6-203">Det användar-ID som du skapar när du registrerar dig inkluderar domänen, till exempel *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="cc3d6-204">**Om du vill att ditt e-postmeddelande ska se ut som *Alan@contoso.de*:** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara anvisningarna i [lägga till användare och domän i Microsoft 365](add-domain.md) om du redan har den.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="cc3d6-205">**Du kan inte byta namn på onmicrosoft-domänen efter registreringen.**</span><span class="sxs-lookup"><span data-stu-id="cc3d6-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="cc3d6-206">Om den första domänen du väljer är fourthcoffee.onmicrosoft.de kan du till exempel inte ändra den till att vara fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="cc3d6-207">Om du vill använda en annan onmicrosoft.de-domän måste du starta en ny prenumeration med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="cc3d6-208">**Du kan inte byta namn på din gruppwebbplats-URL.**</span><span class="sxs-lookup"><span data-stu-id="cc3d6-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="cc3d6-209">Din grupp webbplats URL baseras på ditt onmicrosoft.de-domän namn. Tyvärr kan du inte byta namn på grupp webbplatsen på grund av hur SharePoint Online-arkitekturen fungerar.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="cc3d6-210">**Du kan inte ta bort domänen onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="cc3d6-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="cc3d6-211">Microsoft 365 måste hålla det nära eftersom det används bakom dina abonnemangs scener.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="cc3d6-212">Men du behöver inte använda domänen när du har lagt till en egen domän.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="cc3d6-213">Du kan fortsätta att använda den initiala onmicrosoft.de-domänen även efter att du har lagt till din domän.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="cc3d6-214">Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="cc3d6-215">Hur verifierar jag min status som inte vinst eller utbildning?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="cc3d6-216">Välj **Inställningar** i [administrations centret](https://docs.microsoft.com/microsoft-365/admin/admin-home) för att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="cc3d6-217">(Kontrol lera att du loggar in på Microsoft 365 först.)</span><span class="sxs-lookup"><span data-stu-id="cc3d6-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="cc3d6-218">Om du vill bli administratör för skolan markerar du alternativet  **bli administratör** i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="cc3d6-219">Du uppmanas att lägga till en TXT DNS-post på DNS-värd webbplatsen för din domän.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="cc3d6-220">Varför?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-220">Why?</span></span> <span data-ttu-id="cc3d6-221">På grund av att du loggar in på DNS-värden och lägger till en post för din domän bekräftar du att du har Microsoft 365 som du äger domän namnet.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="cc3d6-222">När du har lagt till posten går du tillbaka till Microsoft 365-portalen och bekräftar att du har lagt till den, så att Microsoft 365 kan kontrol lera det.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="cc3d6-223">Har du ingen vinst och vill skaffa Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="cc3d6-224">[Kontrol lera att din organisation uppfyller](https://www.microsoft.com/en-us/nonprofits/eligibility) och registrera dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cc3d6-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="cc3d6-225">Vill du veta mer om hur du blir administratör för skolan?</span><span class="sxs-lookup"><span data-stu-id="cc3d6-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="cc3d6-226">[Lär dig allt](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="cc3d6-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>