---
title: Lägga till en domän i Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Lägg till din domän i Office 365 i Microsoft 365-administrationscentret genom att lägga till en DNS-post hos din DNS-värd. Installationsguiden går igenom processen.
ms.openlocfilehash: bab4da6e4a8191d91ccdd38dd54f62f4d790c3b8
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140781"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="0048f-104">Lägga till en domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="0048f-104">Add a domain to Office 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0048f-105">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="0048f-105">The admin center is changing.</span></span> <span data-ttu-id="0048f-106">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="0048f-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="0048f-107">**[Läs frågor och svar om domäner](domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="0048f-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="0048f-108">*Om du vill lägga till, ändra eller ta bort domäner **måste** du vara **global administratör för** ett företag eller en [företagsplan.](https://products.office.com/business/office) Dessa ändringar påverkar hela klienten, *anpassade administratörer* eller *vanliga användare* kan inte göra dessa ändringar.*</span><span class="sxs-lookup"><span data-stu-id="0048f-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="0048f-109">Följ dessa steg för att lägga till, konfigurera eller fortsätta konfigurera en domän.</span><span class="sxs-lookup"><span data-stu-id="0048f-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0048f-110">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0048f-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="0048f-111">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="0048f-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0048f-112">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="0048f-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="0048f-113">Gå till sidan > **Installationsdomäner.** **Setup**</span><span class="sxs-lookup"><span data-stu-id="0048f-113">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="0048f-114">Välj **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="0048f-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="0048f-115">Ange namnet på den domän som du vill lägga till och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0048f-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="0048f-116">Välj hur du vill verifiera att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="0048f-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="0048f-117">Om din domän är registrerad på&amp;GoDaddy eller 1 1 väljer du **Logga in** > **nästa** så[konfigurerar](../get-help-with-domains/domain-connect.md)Microsoft dina poster automatiskt .</span><span class="sxs-lookup"><span data-stu-id="0048f-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft[will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="0048f-118">Du kan välja att ett e-postmeddelande ska skickas till den registrerade kontakten för domänen med en verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="0048f-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="0048f-119">Om du inte känner igen eller har tillgång till e-postmeddelandet kan du använda det tredje alternativet.</span><span class="sxs-lookup"><span data-stu-id="0048f-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="0048f-120">Du kan använda en TXT-post för att verifiera din domän.</span><span class="sxs-lookup"><span data-stu-id="0048f-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="0048f-121">Välj det här och välj **Nästa** om du vill se instruktioner för hur du lägger till den här DNS-posten på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="0048f-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="0048f-122">Det kan ta upp till 30 minuter att verifiera när du har lagt till posten.</span><span class="sxs-lookup"><span data-stu-id="0048f-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="0048f-123">Välj hur du vill göra de DNS-ändringar som krävs för att Office ska kunna använda domänen.</span><span class="sxs-lookup"><span data-stu-id="0048f-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="0048f-124">Välj **Lägg till DNS-posterna åt mig** om du vill att Dns ska konfigureras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0048f-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="0048f-125">Välj **Jag lägger till DNS-posterna själv** om du bara vill koppla specifika Office 365-tjänster till din domän eller om du vill hoppa över detta för tillfället och göra detta senare.</span><span class="sxs-lookup"><span data-stu-id="0048f-125">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="0048f-126">**Välj det här alternativet om du vet exakt vad du gör.**</span><span class="sxs-lookup"><span data-stu-id="0048f-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="0048f-127">Om du själv väljer att lägga till *DNS-poster* väljer du **Nästa** och du ser en sida med alla poster som du behöver lägga till på registrarernas webbplats för att konfigurera domänen.</span><span class="sxs-lookup"><span data-stu-id="0048f-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="0048f-128">Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="0048f-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="0048f-129">Kontrollera listan med [värdspecifika instruktioner](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver.</span><span class="sxs-lookup"><span data-stu-id="0048f-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="0048f-130">Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="0048f-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="0048f-131">Om du vill vänta till senare bläddrar du längst ned och väljer **Hoppa över det här steget**.</span><span class="sxs-lookup"><span data-stu-id="0048f-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="0048f-132">Välj **Slutför** - du är klar!</span><span class="sxs-lookup"><span data-stu-id="0048f-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="0048f-133">Lägga till eller redigera anpassade DNS-poster</span><span class="sxs-lookup"><span data-stu-id="0048f-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="0048f-134">Följ stegen nedan för att lägga till en anpassad post för en webbplats eller tjänst från tredje part.</span><span class="sxs-lookup"><span data-stu-id="0048f-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="0048f-135">Logga in på Microsofts <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>administrationscenter på .</span><span class="sxs-lookup"><span data-stu-id="0048f-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0048f-136">Gå till sidan **Inställningar**  > **domäner.**</span><span class="sxs-lookup"><span data-stu-id="0048f-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="0048f-137">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="0048f-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="0048f-138">Under **DNS-inställningar**väljer du **Anpassade poster.** välj sedan **Ny anpassad post**.</span><span class="sxs-lookup"><span data-stu-id="0048f-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="0048f-139">Välj den typ av DNS-post som du vill lägga till och skriv informationen för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="0048f-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="0048f-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0048f-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="0048f-141">Registratorer med Domain Connect</span><span class="sxs-lookup"><span data-stu-id="0048f-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="0048f-142">[Med Domain](https://www.domainconnect.org/) Connect-aktiverade registratorer kan du lägga till din domän i Microsoft 365 i en trestegsprocess som tar minuter.</span><span class="sxs-lookup"><span data-stu-id="0048f-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="0048f-143">I guiden bekräftar vi bara att du äger domänen och sedan automatiskt konfigurerar domänens poster, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, som Teams, fungerar med din domän.</span><span class="sxs-lookup"><span data-stu-id="0048f-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0048f-144">Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="0048f-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="0048f-145">Domain Connect-registratorer som integreras med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0048f-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="0048f-146">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="0048f-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="0048f-147">123Reg (På andra)</span><span class="sxs-lookup"><span data-stu-id="0048f-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="0048f-148">Godaddy</span><span class="sxs-lookup"><span data-stu-id="0048f-148">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="0048f-149">Wordpress</span><span class="sxs-lookup"><span data-stu-id="0048f-149">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="0048f-150">Plesk</span><span class="sxs-lookup"><span data-stu-id="0048f-150">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="0048f-151">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="0048f-151">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="0048f-152">SecureServer eller WildWestDomains (GoDaddy-återförsäljare med SecureServer DNS hosting)</span><span class="sxs-lookup"><span data-stu-id="0048f-152">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="0048f-153">MadDog domäner</span><span class="sxs-lookup"><span data-stu-id="0048f-153">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="0048f-154">BilligaNamn</span><span class="sxs-lookup"><span data-stu-id="0048f-154">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="0048f-155">Vad händer med min e-post och webbplats?</span><span class="sxs-lookup"><span data-stu-id="0048f-155">What happens to my email and website?</span></span>

<span data-ttu-id="0048f-156">När du är klar med installationen uppdateras MX-posten för din domän så att den pekar på Microsoft 365 och all e-post för din domän börjar komma till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0048f-156">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="0048f-157">Kontrollera att du har lagt till användare och konfigurerat postlådor i Office 365 för alla som får e-post i din domän.</span><span class="sxs-lookup"><span data-stu-id="0048f-157">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="0048f-158">Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är.</span><span class="sxs-lookup"><span data-stu-id="0048f-158">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="0048f-159">Installationsstegen För Domain Connect påverkar inte din webbplats.</span><span class="sxs-lookup"><span data-stu-id="0048f-159">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0048f-160">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="0048f-160">Related articles</span></span>

[<span data-ttu-id="0048f-161">Vanliga frågor och svar om domäner</span><span class="sxs-lookup"><span data-stu-id="0048f-161">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="0048f-162">Vad är en domän?</span><span class="sxs-lookup"><span data-stu-id="0048f-162">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="0048f-163">Köpa ett domännamn i Office 365</span><span class="sxs-lookup"><span data-stu-id="0048f-163">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="0048f-164">Konfigurera din domän (tjänstspecifika instruktioner)</span><span class="sxs-lookup"><span data-stu-id="0048f-164">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="0048f-165">Få hjälp med domäner</span><span class="sxs-lookup"><span data-stu-id="0048f-165">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
