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
description: Läs mer om domäner genom att hitta svar på dina vanliga frågor.
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068109"
---
# <a name="domains-faq"></a><span data-ttu-id="59ae0-103">Vanliga frågor och svar om domäner</span><span class="sxs-lookup"><span data-stu-id="59ae0-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="59ae0-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="59ae0-104">The admin center is changing.</span></span> <span data-ttu-id="59ae0-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="59ae0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="59ae0-106">Den här artikeln innehåller svar på vanliga frågor om domäner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59ae0-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="59ae0-107">Om du inte hittar ett svar på din fråga här, kan du lämna en kommentar om det så lägger vi till det i listan.</span><span class="sxs-lookup"><span data-stu-id="59ae0-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="59ae0-108">I den här artikeln</span><span class="sxs-lookup"><span data-stu-id="59ae0-108">In this article</span></span>

- [<span data-ttu-id="59ae0-109">Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="59ae0-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="59ae0-110">Hur validerar jag SPF-poster för min domän?</span><span class="sxs-lookup"><span data-stu-id="59ae0-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="59ae0-111">Vad är ett domännamn?</span><span class="sxs-lookup"><span data-stu-id="59ae0-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="59ae0-112">Vad händer om min DNS-värd inte har stöd för vissa typer av poster?</span><span class="sxs-lookup"><span data-stu-id="59ae0-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="59ae0-113">Hur ställer jag in eller ändrar standarddomänen i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="59ae0-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="59ae0-114">Kan jag lägga till anpassade underdomäner eller flera domäner i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="59ae0-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="59ae0-115">Varför har jag en onmicrosoft.com-domän?</span><span class="sxs-lookup"><span data-stu-id="59ae0-115">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="59ae0-116">Varför har jag en "onmicrosoft.de"-domän?</span><span class="sxs-lookup"><span data-stu-id="59ae0-116">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="59ae0-117">Hur verifierar jag min ideella organisation eller utbildningsstatus?</span><span class="sxs-lookup"><span data-stu-id="59ae0-117">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="59ae0-118">Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="59ae0-118">What is MX priority?</span></span>

<span data-ttu-id="59ae0-119">E-post levereras till Exchange-servern med lägst företrädesnummer (högst prioritet). Därför ska den MX-post som du använder för e-postdirigering ha det lägsta företrädesnumret, vanligtvis 0, eller  *hög*  prioritet.</span><span class="sxs-lookup"><span data-stu-id="59ae0-119">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="59ae0-120">När du skapar en MX-post måste du ange ett företrädesnummer för de flesta DNS-värdar.</span><span class="sxs-lookup"><span data-stu-id="59ae0-120">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="59ae0-121">Vissa kallar rutan för  *företräde*  , andra för  *prioritet*  .</span><span class="sxs-lookup"><span data-stu-id="59ae0-121">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="59ae0-122">Vissa kräver ett nummer medan andra ber dig att välja mellan  *låg*  ,  *mellan*  eller  *hög*  .</span><span class="sxs-lookup"><span data-stu-id="59ae0-122">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="59ae0-123">Om du bara har en MX-post går det bra med vilket värde som helst för prioritet eller företräde.</span><span class="sxs-lookup"><span data-stu-id="59ae0-123">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="59ae0-124">Om du har fler än en ser du till att MX-posten för e-postdirigering har högre prioritet än den som används för att verifiera att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="59ae0-124">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="59ae0-125">Hur validerar jag SPF-poster för min domän?</span><span class="sxs-lookup"><span data-stu-id="59ae0-125">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="59ae0-126">Det är viktigt att du bara har eller skapar **en TXT-post för SPF**.</span><span class="sxs-lookup"><span data-stu-id="59ae0-126">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="59ae0-127">Om du redan har en SPF-post bör du lägga till de nya Microsoft 365-värdena i den i stället för att skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="59ae0-127">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="59ae0-128">När du har lagt till eller uppdaterat SPF-posten för Microsoft-e-post bör du kontrollera att syntaxen är korrekt med något av följande verktyg:</span><span class="sxs-lookup"><span data-stu-id="59ae0-128">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="59ae0-129">SPF Record Testing Tools</span><span class="sxs-lookup"><span data-stu-id="59ae0-129">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="59ae0-130">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="59ae0-130">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="59ae0-131">Dig web interface</span><span class="sxs-lookup"><span data-stu-id="59ae0-131">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="59ae0-132">Vad är ett domännamn?</span><span class="sxs-lookup"><span data-stu-id="59ae0-132">What is a domain name?</span></span>

<span data-ttu-id="59ae0-p103">En domän är ett unikt namn som visas efter **@** -tecknet i e-postadresser och efter **www.** i webbadresser. Det består vanligen av organisationens namn och ett vanligt Internetsuffix, till exempel  *företagsnamn.com*  eller  *universitetsnamn.edu*  .</span><span class="sxs-lookup"><span data-stu-id="59ae0-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="59ae0-136">Genom att använda en anpassad domän som "**rob \@ contoso.com**" med Microsoft 365 kan du skapa trovärdighet och erkännande för ditt varumärke.</span><span class="sxs-lookup"><span data-stu-id="59ae0-136">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="59ae0-137">Du kan [köpa en domän i Microsoft 365 och vi konfigurerar den automatiskt,](../get-help-with-domains/buy-a-domain-name.md)eller så kan du köpa eller ta med en som du redan äger från en domänregistratorer.</span><span class="sxs-lookup"><span data-stu-id="59ae0-137">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="59ae0-138">Vad händer om min DNS-värd inte har stöd för vissa typer av poster?</span><span class="sxs-lookup"><span data-stu-id="59ae0-138">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="59ae0-139">Om du hanterar dina egna DNS-poster och DNS-värden inte stöder alla DNS-poster som Microsoft 365 behöver fungerar inte vissa Microsoft 365-funktioner.</span><span class="sxs-lookup"><span data-stu-id="59ae0-139">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="59ae0-140">Vi rekommenderar att du för över din domän till en registrator som har stöd för alla DNS-poster som krävs.</span><span class="sxs-lookup"><span data-stu-id="59ae0-140">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="59ae0-141">Värdar som har stöd för alla DNS-poster som krävs:</span><span class="sxs-lookup"><span data-stu-id="59ae0-141">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="59ae0-142">Dynadot</span><span class="sxs-lookup"><span data-stu-id="59ae0-142">Dynadot</span></span>
    
- <span data-ttu-id="59ae0-143">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="59ae0-143">eNomCentral</span></span>
    
- <span data-ttu-id="59ae0-144">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="59ae0-144">Europe Registry</span></span>
    
- <span data-ttu-id="59ae0-145">Godaddy</span><span class="sxs-lookup"><span data-stu-id="59ae0-145">GoDaddy</span></span>
    
- <span data-ttu-id="59ae0-146">Hover</span><span class="sxs-lookup"><span data-stu-id="59ae0-146">Hover</span></span>
    
- <span data-ttu-id="59ae0-147">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="59ae0-147">MyHosting.com</span></span>
    
- <span data-ttu-id="59ae0-148">Name.com</span><span class="sxs-lookup"><span data-stu-id="59ae0-148">Name.com</span></span>
    
- <span data-ttu-id="59ae0-149">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="59ae0-149">Nearly Free Speech</span></span>
    
- <span data-ttu-id="59ae0-150">Nettica</span><span class="sxs-lookup"><span data-stu-id="59ae0-150">Nettica</span></span>
    
- <span data-ttu-id="59ae0-151">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="59ae0-151">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="59ae0-152">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="59ae0-152">Network Solutions</span></span>
    
- <span data-ttu-id="59ae0-153">Register.com</span><span class="sxs-lookup"><span data-stu-id="59ae0-153">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="59ae0-154">Hur ställer jag in eller ändrar standarddomänen i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="59ae0-154">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="59ae0-155">Du måste ha minst en anpassad domän som du har lagt till i Microsoft 365 innan du kan välja en standarddomän.</span><span class="sxs-lookup"><span data-stu-id="59ae0-155">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="59ae0-156">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="59ae0-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="59ae0-157">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="59ae0-157">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59ae0-158">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="59ae0-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="59ae0-159">På sidan **Domäner** väljer du den domän som du vill ange som standard för nya e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="59ae0-159">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="59ae0-160">Välj **Ange som standard**.</span><span class="sxs-lookup"><span data-stu-id="59ae0-160">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="59ae0-161">Du kan inte ändra namnet på din ursprungliga  *.onmicrosoft.com*  -domän.</span><span class="sxs-lookup"><span data-stu-id="59ae0-161">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="59ae0-162">Du kan inte ändra *.onmicrosoft.de* namnet på den ursprungliga .onmicrosoft.de-domänen.</span><span class="sxs-lookup"><span data-stu-id="59ae0-162">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="59ae0-163">Du kan inte ändra *.partner.onmschina.cn* namnet på den ursprungliga .partner.onmschina.cn-domänen.</span><span class="sxs-lookup"><span data-stu-id="59ae0-163">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="59ae0-164">Kan jag lägga till anpassade underdomäner eller flera domäner i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="59ae0-164">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="59ae0-165">Ja.</span><span class="sxs-lookup"><span data-stu-id="59ae0-165">Yes.</span></span> <span data-ttu-id="59ae0-166">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="59ae0-166">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="59ae0-167">Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="59ae0-167">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="59ae0-168">Ja!</span><span class="sxs-lookup"><span data-stu-id="59ae0-168">Yes!</span></span> <span data-ttu-id="59ae0-169">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="59ae0-169">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="59ae0-170">Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="59ae0-170">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="59ae0-171">Ja!</span><span class="sxs-lookup"><span data-stu-id="59ae0-171">Yes!</span></span> <span data-ttu-id="59ae0-172">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="59ae0-172">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="59ae0-173">Om du låter 21Vianet hantera dina DNS-inställningar med NS-poster kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="59ae0-173">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="59ae0-174">Vanligtvis kan du lägga till upp till 900 domäner i din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="59ae0-174">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="59ae0-175">Du kan till exempel lägga till domänerna contoso.com och contosomarketing.com, och sedan lägga till underdomänerna www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com och så vidare.</span><span class="sxs-lookup"><span data-stu-id="59ae0-175">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="59ae0-176">När du lägger till en underdomän verifieras den automatiskt baserat på den överordnade domänen som verifieras.</span><span class="sxs-lookup"><span data-stu-id="59ae0-176">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="59ae0-177">När du lägger till flera domäner i Microsoft 365 kan du vara värd för alla tjänster (som e-post) på någon av de domäner som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="59ae0-177">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="59ae0-178">*När du ändrar din e-post till Microsoft 365, genom att uppdatera en domäns MX-post, kommer alla e-postmeddelanden som skickas till den domänen att börja komma till Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="59ae0-178">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="59ae0-179">Om du har lagt till en contoso.com domän i en Microsoft 365-prenumeration kan du även lägga till underdomänen xyz.contoso.com i en annan Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="59ae0-179">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="59ae0-180">När du lägger till underdomänen uppmanas du att lägga till en TXT-post i DNS-värdleverantören.</span><span class="sxs-lookup"><span data-stu-id="59ae0-180">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="59ae0-181">Varför har jag en onmicrosoft.com-domän?</span><span class="sxs-lookup"><span data-stu-id="59ae0-181">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="59ae0-182">Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.com*, när du registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="59ae0-182">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="59ae0-183">Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="59ae0-183">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="59ae0-184">**Om du vill ha din e-post ser ut som *Alan \@ contoso.com:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller bara följa stegen i [Lägg till dina användare och domän till Microsoft 365](add-domain.md) om du äger den redan.</span><span class="sxs-lookup"><span data-stu-id="59ae0-184">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="59ae0-185">**Du kan inte byta namn på onmicrosoft-domänen efter registreringen.**</span><span class="sxs-lookup"><span data-stu-id="59ae0-185">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="59ae0-186">Om den initiala domänen du valde till exempel var fourthcoffee.onmicrosoft.com, kan du inte ändra den till fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="59ae0-186">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="59ae0-187">Om du vill använda en annan onmicrosoft.com domän måste du starta en ny prenumeration med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59ae0-187">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="59ae0-188">**Du kan inte byta namn på din gruppwebbplats-URL.**</span><span class="sxs-lookup"><span data-stu-id="59ae0-188">**You can't rename your team site URL.**</span></span> <span data-ttu-id="59ae0-189">Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.com domännamn.</span><span class="sxs-lookup"><span data-stu-id="59ae0-189">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="59ae0-190">På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="59ae0-190">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="59ae0-191">**Du kan inte ta bort domänen onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="59ae0-191">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="59ae0-192">Microsoft 365 måste behålla den eftersom den används bakom kulisserna för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="59ae0-192">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="59ae0-193">Men du behöver inte använda domänen när du har lagt till en egen domän.</span><span class="sxs-lookup"><span data-stu-id="59ae0-193">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="59ae0-p114">Du kan emellertid fortsätta använda den första onmicrosoft.com-domänen, även efter att du har lagt till din domän. Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.</span><span class="sxs-lookup"><span data-stu-id="59ae0-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="59ae0-196">Varför har jag en "onmicrosoft.de"-domän?</span><span class="sxs-lookup"><span data-stu-id="59ae0-196">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="59ae0-197">Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.de*, när du registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="59ae0-197">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="59ae0-198">Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="59ae0-198">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="59ae0-199">**Om du vill att din e-post ska se ut *alan@contoso.de:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara stegen i [Lägg till dina användare och domäner till Microsoft 365](add-domain.md) om du äger den redan.</span><span class="sxs-lookup"><span data-stu-id="59ae0-199">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="59ae0-200">**Du kan inte byta namn på onmicrosoft-domänen efter registreringen.**</span><span class="sxs-lookup"><span data-stu-id="59ae0-200">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="59ae0-201">Om den ursprungliga domänen du valde till exempel var fourthcoffee.onmicrosoft.de kan du inte ändra den till fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="59ae0-201">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="59ae0-202">Om du vill använda en annan onmicrosoft.de domän måste du starta en ny prenumeration med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59ae0-202">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="59ae0-203">**Du kan inte byta namn på din gruppwebbplats-URL.**</span><span class="sxs-lookup"><span data-stu-id="59ae0-203">**You can't rename your team site URL.**</span></span> <span data-ttu-id="59ae0-204">Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.de domännamn. På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="59ae0-204">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="59ae0-205">**Du kan inte ta bort domänen onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="59ae0-205">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="59ae0-206">Microsoft 365 måste behålla den eftersom den används bakom kulisserna för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="59ae0-206">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="59ae0-207">Men du behöver inte använda domänen när du har lagt till en egen domän.</span><span class="sxs-lookup"><span data-stu-id="59ae0-207">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="59ae0-208">Du kan fortsätta använda den ursprungliga onmicrosoft.de domänen även efter att du har lagt till domänen.</span><span class="sxs-lookup"><span data-stu-id="59ae0-208">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="59ae0-209">Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.</span><span class="sxs-lookup"><span data-stu-id="59ae0-209">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="59ae0-210">Hur verifierar jag min ideella organisation eller utbildningsstatus?</span><span class="sxs-lookup"><span data-stu-id="59ae0-210">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="59ae0-211">Välj **Installationsprogrammet** i [administrationscentret](https://docs.microsoft.com/microsoft-365/admin/admin-home) för att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="59ae0-211">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="59ae0-212">(Var noga med att logga in på Microsoft 365 först.)</span><span class="sxs-lookup"><span data-stu-id="59ae0-212">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="59ae0-213">Om du vill bli administratör för din skola väljer du alternativet **Bli administratör** i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59ae0-213">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="59ae0-214">Du uppmanas att lägga till en TXT DNS-post på DNS-värdwebbplatsen för din domän.</span><span class="sxs-lookup"><span data-stu-id="59ae0-214">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="59ae0-215">Varför?</span><span class="sxs-lookup"><span data-stu-id="59ae0-215">Why?</span></span> <span data-ttu-id="59ae0-216">Eftersom du genom att logga in hos DNS-värden och lägga till en post för domänen bevisar du för Microsoft 365 att du äger domännamnet.</span><span class="sxs-lookup"><span data-stu-id="59ae0-216">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="59ae0-217">När du har lagt till posten går du tillbaka till Microsoft 365-portalen och bekräftar att du har lagt till den, så att Microsoft 365 kan kontrollera.</span><span class="sxs-lookup"><span data-stu-id="59ae0-217">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="59ae0-218">Har du en ideell organisation och vill skaffa Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="59ae0-218">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="59ae0-219">[Kontrollera att din organisation kvalificerar sig](https://www.microsoft.com/en-us/nonprofits/eligibility) och sedan registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="59ae0-219">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="59ae0-220">Vill du veta mer om att bli admin för din skola?</span><span class="sxs-lookup"><span data-stu-id="59ae0-220">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="59ae0-221">[Lär dig allt om det](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="59ae0-221">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>