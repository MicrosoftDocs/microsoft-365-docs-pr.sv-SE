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
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049742"
---
# <a name="domains-faq"></a><span data-ttu-id="87b94-103">Vanliga frågor och svar om domäner</span><span class="sxs-lookup"><span data-stu-id="87b94-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="87b94-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="87b94-104">The admin center is changing.</span></span> <span data-ttu-id="87b94-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="87b94-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="87b94-106">Den här artikeln innehåller svar på vanliga frågor om domäner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87b94-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="87b94-107">Om du inte hittar ett svar på din fråga här, kan du lämna en kommentar om det så lägger vi till det i listan.</span><span class="sxs-lookup"><span data-stu-id="87b94-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="87b94-108">I den här artikeln</span><span class="sxs-lookup"><span data-stu-id="87b94-108">In this article</span></span>

<span data-ttu-id="87b94-109">[Vad är MX prioritet?](#what-is-mx-priority) 
 [Hur validerar jag SPF-poster för min domän?](#how-can-i-validate-spf-records-for-my-domain) 
 [Vad är ett domännamn?](#what-is-a-domain-name) 
 [Vad händer om min DNS-leverantör inte stöder vissa posttyper?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
 [Hur ställer jag in eller ändrar standarddomänen i Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
 [Kan jag lägga till anpassade underdomäner eller flera domäner i Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
 [Varför har jag en domän för "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain) 
 [Varför har jag en domän för "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain) 
 [Hur verifierar jag min ideella organisation eller utbildningsstatus?](#how-do-i-verify-my-nonprofit-or-education-status)</span><span class="sxs-lookup"><span data-stu-id="87b94-109">[What is MX priority?](#what-is-mx-priority)
[How can I validate SPF records for my domain?](#how-can-i-validate-spf-records-for-my-domain)
[What is a domain name?](#what-is-a-domain-name)
[What happens if my DNS provider doesn't support certain record types?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
[How do I set or change the default domain in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
[Can I add custom subdomains or multiple domains to Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
[Why do I have an "onmicrosoft.com" domain?](#why-do-i-have-an-onmicrosoftcom-domain)
[Why do I have an "onmicrosoft.de" domain?](#why-do-i-have-an-onmicrosoftde-domain)
[How do I verify my nonprofit or education status?](#how-do-i-verify-my-nonprofit-or-education-status)</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="87b94-110">Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="87b94-110">What is MX priority?</span></span>

<span data-ttu-id="87b94-111">E-post levereras till Exchange-servern med lägst företrädesnummer (högst prioritet). Därför ska den MX-post som du använder för e-postdirigering ha det lägsta företrädesnumret, vanligtvis 0, eller  *hög*  prioritet.</span><span class="sxs-lookup"><span data-stu-id="87b94-111">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="87b94-112">När du skapar en MX-post måste du ange ett företrädesnummer för de flesta DNS-värdar.</span><span class="sxs-lookup"><span data-stu-id="87b94-112">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="87b94-113">Vissa kallar rutan för  *företräde*  , andra för  *prioritet*  .</span><span class="sxs-lookup"><span data-stu-id="87b94-113">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="87b94-114">Vissa kräver ett nummer medan andra ber dig att välja mellan  *låg*  ,  *mellan*  eller  *hög*  .</span><span class="sxs-lookup"><span data-stu-id="87b94-114">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="87b94-115">Om du bara har en MX-post går det bra med vilket värde som helst för prioritet eller företräde.</span><span class="sxs-lookup"><span data-stu-id="87b94-115">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="87b94-116">Om du har fler än en ser du till att MX-posten för e-postdirigering har högre prioritet än den som används för att verifiera att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="87b94-116">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="87b94-117">Hur validerar jag SPF-poster för min domän?</span><span class="sxs-lookup"><span data-stu-id="87b94-117">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="87b94-118">Det är viktigt att du bara har eller skapar **en TXT-post för SPF**.</span><span class="sxs-lookup"><span data-stu-id="87b94-118">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="87b94-119">Om du redan har en SPF-post bör du lägga till de nya Microsoft 365-värdena i den i stället för att skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="87b94-119">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="87b94-120">När du har lagt till eller uppdaterat SPF-posten för Microsoft-e-post bör du kontrollera att syntaxen är korrekt med något av följande verktyg:</span><span class="sxs-lookup"><span data-stu-id="87b94-120">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="87b94-121">SPF Record Testing Tools</span><span class="sxs-lookup"><span data-stu-id="87b94-121">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="87b94-122">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="87b94-122">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="87b94-123">Dig web interface</span><span class="sxs-lookup"><span data-stu-id="87b94-123">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="87b94-124">Vad är ett domännamn?</span><span class="sxs-lookup"><span data-stu-id="87b94-124">What is a domain name?</span></span>

<span data-ttu-id="87b94-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span><span class="sxs-lookup"><span data-stu-id="87b94-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="87b94-126">in web addresses.</span><span class="sxs-lookup"><span data-stu-id="87b94-126">in web addresses.</span></span> <span data-ttu-id="87b94-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="87b94-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="87b94-128">Genom att använda en anpassad domän som "**rob \@ contoso.com**" med Microsoft 365 kan du skapa trovärdighet och erkännande för ditt varumärke.</span><span class="sxs-lookup"><span data-stu-id="87b94-128">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="87b94-129">Du kan [köpa en domän i Microsoft 365 och vi konfigurerar den automatiskt,](../get-help-with-domains/buy-a-domain-name.md)eller så kan du köpa eller ta med en som du redan äger från en domänregistratorer.</span><span class="sxs-lookup"><span data-stu-id="87b94-129">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="87b94-130">Vad händer om min DNS-värd inte har stöd för vissa typer av poster?</span><span class="sxs-lookup"><span data-stu-id="87b94-130">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="87b94-131">Om du hanterar dina egna DNS-poster och DNS-värden inte stöder alla DNS-poster som Microsoft 365 behöver fungerar inte vissa Microsoft 365-funktioner.</span><span class="sxs-lookup"><span data-stu-id="87b94-131">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="87b94-132">Vi rekommenderar att du för över din domän till en registrator som har stöd för alla DNS-poster som krävs.</span><span class="sxs-lookup"><span data-stu-id="87b94-132">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="87b94-133">Värdar som har stöd för alla DNS-poster som krävs:</span><span class="sxs-lookup"><span data-stu-id="87b94-133">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="87b94-134">Dynadot</span><span class="sxs-lookup"><span data-stu-id="87b94-134">Dynadot</span></span>
    
- <span data-ttu-id="87b94-135">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="87b94-135">eNomCentral</span></span>
    
- <span data-ttu-id="87b94-136">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="87b94-136">Europe Registry</span></span>
    
- <span data-ttu-id="87b94-137">Godaddy</span><span class="sxs-lookup"><span data-stu-id="87b94-137">GoDaddy</span></span>
    
- <span data-ttu-id="87b94-138">Hover</span><span class="sxs-lookup"><span data-stu-id="87b94-138">Hover</span></span>
    
- <span data-ttu-id="87b94-139">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="87b94-139">MyHosting.com</span></span>
    
- <span data-ttu-id="87b94-140">Name.com</span><span class="sxs-lookup"><span data-stu-id="87b94-140">Name.com</span></span>
    
- <span data-ttu-id="87b94-141">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="87b94-141">Nearly Free Speech</span></span>
    
- <span data-ttu-id="87b94-142">Nettica</span><span class="sxs-lookup"><span data-stu-id="87b94-142">Nettica</span></span>
    
- <span data-ttu-id="87b94-143">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="87b94-143">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="87b94-144">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="87b94-144">Network Solutions</span></span>
    
- <span data-ttu-id="87b94-145">Register.com</span><span class="sxs-lookup"><span data-stu-id="87b94-145">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="87b94-146">Hur ställer jag in eller ändrar standarddomänen i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="87b94-146">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="87b94-147">Du måste ha minst en anpassad domän som du har lagt till i Microsoft 365 innan du kan välja en standarddomän.</span><span class="sxs-lookup"><span data-stu-id="87b94-147">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="87b94-148">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="87b94-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="87b94-149">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="87b94-149">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="87b94-150">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="87b94-150">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="87b94-151">På sidan **Domäner** väljer du den domän som du vill ange som standard för nya e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="87b94-151">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="87b94-152">Välj **Ange som standard**.</span><span class="sxs-lookup"><span data-stu-id="87b94-152">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="87b94-153">Du kan inte ändra namnet på din ursprungliga  *.onmicrosoft.com*  -domän.</span><span class="sxs-lookup"><span data-stu-id="87b94-153">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="87b94-154">Du kan inte ändra *.onmicrosoft.de* namnet på den ursprungliga .onmicrosoft.de-domänen.</span><span class="sxs-lookup"><span data-stu-id="87b94-154">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="87b94-155">Du kan inte ändra *.partner.onmschina.cn* namnet på den ursprungliga .partner.onmschina.cn-domänen.</span><span class="sxs-lookup"><span data-stu-id="87b94-155">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="87b94-156">Kan jag lägga till anpassade underdomäner eller flera domäner i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="87b94-156">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="87b94-157">Ja.</span><span class="sxs-lookup"><span data-stu-id="87b94-157">Yes.</span></span> <span data-ttu-id="87b94-158">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="87b94-158">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="87b94-159">Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="87b94-159">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="87b94-160">Ja!</span><span class="sxs-lookup"><span data-stu-id="87b94-160">Yes!</span></span> <span data-ttu-id="87b94-161">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="87b94-161">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="87b94-162">Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="87b94-162">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="87b94-163">Ja!</span><span class="sxs-lookup"><span data-stu-id="87b94-163">Yes!</span></span> <span data-ttu-id="87b94-164">Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="87b94-164">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="87b94-165">Om du låter 21Vianet hantera dina DNS-inställningar med NS-poster kan du inte lägga till underdomäner.</span><span class="sxs-lookup"><span data-stu-id="87b94-165">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="87b94-166">Vanligtvis kan du lägga till upp till 900 domäner i din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="87b94-166">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="87b94-167">Du kan till exempel lägga till domänerna contoso.com och contosomarketing.com, och sedan lägga till underdomänerna www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com och så vidare.</span><span class="sxs-lookup"><span data-stu-id="87b94-167">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="87b94-168">När du lägger till en underdomän verifieras den automatiskt baserat på den överordnade domänen som verifieras.</span><span class="sxs-lookup"><span data-stu-id="87b94-168">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="87b94-169">När du lägger till flera domäner i Microsoft 365 kan du vara värd för alla tjänster (som e-post) på någon av de domäner som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="87b94-169">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="87b94-170">*När du ändrar din e-post till Microsoft 365, genom att uppdatera en domäns MX-post, kommer alla e-postmeddelanden som skickas till den domänen att börja komma till Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="87b94-170">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="87b94-171">Om du har lagt till en contoso.com domän i en Microsoft 365-prenumeration kan du även lägga till underdomänen xyz.contoso.com i en annan Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="87b94-171">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="87b94-172">När du lägger till underdomänen uppmanas du att lägga till en TXT-post i DNS-värdleverantören.</span><span class="sxs-lookup"><span data-stu-id="87b94-172">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="87b94-173">Varför har jag en onmicrosoft.com-domän?</span><span class="sxs-lookup"><span data-stu-id="87b94-173">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="87b94-174">Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.com*, när du registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="87b94-174">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="87b94-175">Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="87b94-175">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="87b94-176">**Om du vill ha din e-post ser ut som *Alan \@ contoso.com:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller bara följa stegen i [Lägg till dina användare och domän till Microsoft 365](add-domain.md) om du äger den redan.</span><span class="sxs-lookup"><span data-stu-id="87b94-176">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="87b94-177">**Du kan inte byta namn på onmicrosoft-domänen efter registreringen.**</span><span class="sxs-lookup"><span data-stu-id="87b94-177">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="87b94-178">Om den initiala domänen du valde till exempel var fourthcoffee.onmicrosoft.com, kan du inte ändra den till fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="87b94-178">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="87b94-179">Om du vill använda en annan onmicrosoft.com domän måste du starta en ny prenumeration med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87b94-179">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="87b94-180">**Du kan inte byta namn på din gruppwebbplats-URL.**</span><span class="sxs-lookup"><span data-stu-id="87b94-180">**You can't rename your team site URL.**</span></span> <span data-ttu-id="87b94-181">Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.com domännamn.</span><span class="sxs-lookup"><span data-stu-id="87b94-181">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="87b94-182">På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="87b94-182">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="87b94-183">**Du kan inte ta bort domänen onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="87b94-183">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="87b94-184">Microsoft 365 måste behålla den eftersom den används bakom kulisserna för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="87b94-184">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="87b94-185">Men du behöver inte använda domänen när du har lagt till en egen domän.</span><span class="sxs-lookup"><span data-stu-id="87b94-185">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="87b94-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="87b94-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="87b94-187">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="87b94-187">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="87b94-188">Varför har jag en "onmicrosoft.de"-domän?</span><span class="sxs-lookup"><span data-stu-id="87b94-188">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="87b94-189">Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.de*, när du registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="87b94-189">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="87b94-190">Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="87b94-190">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="87b94-191">**Om du vill att din e-post ska se ut *alan@contoso.de:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara stegen i [Lägg till dina användare och domäner till Microsoft 365](add-domain.md) om du äger den redan.</span><span class="sxs-lookup"><span data-stu-id="87b94-191">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="87b94-192">**Du kan inte byta namn på onmicrosoft-domänen efter registreringen.**</span><span class="sxs-lookup"><span data-stu-id="87b94-192">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="87b94-193">Om den ursprungliga domänen du valde till exempel var fourthcoffee.onmicrosoft.de kan du inte ändra den till fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="87b94-193">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="87b94-194">Om du vill använda en annan onmicrosoft.de domän måste du starta en ny prenumeration med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87b94-194">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="87b94-195">**Du kan inte byta namn på din gruppwebbplats-URL.**</span><span class="sxs-lookup"><span data-stu-id="87b94-195">**You can't rename your team site URL.**</span></span> <span data-ttu-id="87b94-196">Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.de domännamn. På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="87b94-196">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="87b94-197">**Du kan inte ta bort domänen onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="87b94-197">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="87b94-198">Microsoft 365 måste behålla den eftersom den används bakom kulisserna för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="87b94-198">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="87b94-199">Men du behöver inte använda domänen när du har lagt till en egen domän.</span><span class="sxs-lookup"><span data-stu-id="87b94-199">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="87b94-200">Du kan fortsätta använda den ursprungliga onmicrosoft.de domänen även efter att du har lagt till domänen.</span><span class="sxs-lookup"><span data-stu-id="87b94-200">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="87b94-201">Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.</span><span class="sxs-lookup"><span data-stu-id="87b94-201">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="87b94-202">Hur verifierar jag min ideella organisation eller utbildningsstatus?</span><span class="sxs-lookup"><span data-stu-id="87b94-202">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="87b94-203">Välj **Installationsprogrammet** i [administrationscentret](https://docs.microsoft.com/microsoft-365/admin/admin-home) för att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="87b94-203">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="87b94-204">(Var noga med att logga in på Microsoft 365 först.)</span><span class="sxs-lookup"><span data-stu-id="87b94-204">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="87b94-205">Om du vill bli administratör för din skola väljer du alternativet **Bli administratör** i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87b94-205">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="87b94-206">Du uppmanas att lägga till en TXT DNS-post på DNS-värdwebbplatsen för din domän.</span><span class="sxs-lookup"><span data-stu-id="87b94-206">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="87b94-207">Varför?</span><span class="sxs-lookup"><span data-stu-id="87b94-207">Why?</span></span> <span data-ttu-id="87b94-208">Eftersom du genom att logga in hos DNS-värden och lägga till en post för domänen bevisar du för Microsoft 365 att du äger domännamnet.</span><span class="sxs-lookup"><span data-stu-id="87b94-208">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="87b94-209">När du har lagt till posten går du tillbaka till Microsoft 365-portalen och bekräftar att du har lagt till den, så att Microsoft 365 kan kontrollera.</span><span class="sxs-lookup"><span data-stu-id="87b94-209">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="87b94-210">Har du en ideell organisation och vill skaffa Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="87b94-210">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="87b94-211">[Kontrollera att din organisation kvalificerar sig](https://www.microsoft.com/en-us/nonprofits/eligibility) och sedan registrerar dig för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="87b94-211">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="87b94-212">Vill du veta mer om att bli admin för din skola?</span><span class="sxs-lookup"><span data-stu-id="87b94-212">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="87b94-213">[Lär dig allt om det](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="87b94-213">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>