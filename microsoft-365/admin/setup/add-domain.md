---
title: Lägga till en domän i Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Lägga till din domän i Microsoft 365 i Microsoft 365 Admin Center genom att lägga till en DNS-post hos din DNS-värd. Installations guiden hjälper dig genom processen.
ms.openlocfilehash: 3e7463bd4cf6b7836a9770421e0b8ce597524a67
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658057"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="0c6c1-104">Lägga till en domän i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c6c1-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0c6c1-105">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-105">The admin center is changing.</span></span> <span data-ttu-id="0c6c1-106">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="0c6c1-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="0c6c1-107">**[Läs frågor och svar om domäner](domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-107">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="0c6c1-108">*För att lägga till, ändra eller ta bort domäner **måste** du vara **Global administratör** för [företags-eller företags abonnemang](https://products.office.com/business/office). Dessa ändringar påverkar hela klient organisationen, *anpassade administratörer* eller *vanliga användare* kommer inte att kunna göra dessa ändringar.*</span><span class="sxs-lookup"><span data-stu-id="0c6c1-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="0c6c1-109">Följ de här anvisningarna för att lägga till, konfigurera eller fortsätta konfigurera en domän.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0c6c1-110">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="0c6c1-111">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0c6c1-112">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="0c6c1-113">Gå till sidan **Inställningar**-  >  **domäner** .</span><span class="sxs-lookup"><span data-stu-id="0c6c1-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="0c6c1-114">Välj **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="0c6c1-115">Ange namnet på den domän som du vill lägga till och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="0c6c1-116">Välj hur du vill verifiera att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="0c6c1-117">Om domän registratorn använder [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365)konfigurerar Microsoft [posterna automatiskt](../get-help-with-domains/domain-connect.md) genom att logga in på din registrator och bekräfta anslutningen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="0c6c1-118">Du kommer att återföras till administrations centret och Microsoft verifierar sedan automatiskt din domän.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="0c6c1-119">Du kan använda en TXT-post för att verifiera din domän.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="0c6c1-120">Välj det här alternativet och välj **Nästa** för att Visa anvisningar för hur du lägger till den här DNS-posten på din registrators webbplats.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="0c6c1-121">Det kan ta upp till 30 minuter innan du har lagt till posten.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="0c6c1-122">Du kan lägga till en textfil till din domäns webbplats.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="0c6c1-123">Välj och ladda ner txt-filen från installations guiden och ladda upp filen till webbplatsen på den översta nivån.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="0c6c1-124">Sökvägen till filen bör se ut ungefär så här: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="0c6c1-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="0c6c1-125">Vi bekräftar att du äger domänen genom att hitta filen på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="0c6c1-126">Välj hur du vill göra DNS-ändringarna obligatoriska för Microsoft att använda din domän.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="0c6c1-127">Välj **Lägg till DNS-posterna åt mig** om din registrator har stöd för [domän anslutning](#domain-connect-registrars-integrating-with-microsoft-365)och Microsoft registrerar [dina poster automatiskt](../get-help-with-domains/domain-connect.md) genom att logga in på din registrator och bekräfta anslutningen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="0c6c1-128">Välj **jag lägger till DNS-posterna själv** om du bara vill bifoga specifika Microsoft 365-tjänster till din domän eller om du vill hoppa över detta för tillfället och gör det senare.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="0c6c1-129">**Välj det här alternativet om du vet exakt vad du gör.**</span><span class="sxs-lookup"><span data-stu-id="0c6c1-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="0c6c1-130">Om du väljer att *lägga till DNS-poster själv*  väljer du **Nästa** så visas en sida med alla de poster du behöver lägga till på webbplatsen för registratorer för att konfigurera din domän.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="0c6c1-131">Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="0c6c1-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="0c6c1-132">Kontrollera listan med [värdspecifika instruktioner](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="0c6c1-133">Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="0c6c1-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="0c6c1-134">Om du vill vänta senare, avmarkerar du alla tjänster och klickar på **Fortsätt**, eller i föregående steg i domän anslutningen väljer du **fler alternativ** och väljer **hoppa över detta**.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="0c6c1-135">Välj **finish** – nu är du klar!</span><span class="sxs-lookup"><span data-stu-id="0c6c1-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="0c6c1-136">Lägga till eller redigera anpassade DNS-poster</span><span class="sxs-lookup"><span data-stu-id="0c6c1-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="0c6c1-137">Följ stegen nedan om du vill lägga till en anpassad post för en webbplats eller tredje parts tjänst.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="0c6c1-138">Logga in på administrations centret för Microsoft på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="0c6c1-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0c6c1-139">Gå till sidan **Inställningar**-   >  **domäner** .</span><span class="sxs-lookup"><span data-stu-id="0c6c1-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="0c6c1-140">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="0c6c1-141">Välj **anpassade poster** under **DNS-inställningar**. Välj sedan **ny anpassad post**.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="0c6c1-142">Välj den typ av DNS-post du vill lägga till och ange informationen för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="0c6c1-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="0c6c1-144">Registratorer med domän anslutning</span><span class="sxs-lookup"><span data-stu-id="0c6c1-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="0c6c1-145">Med [domän Connect-reservdomänkontrollanter](https://www.domainconnect.org/) kan du lägga till din domän i Microsoft 365 i en tre stegs process som tar minuter.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="0c6c1-146">I guiden bekräftar vi bara att du äger domänen och registrerar sedan automatiskt domänens poster, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, till exempel Teams, fungerar med din domän.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c6c1-147">Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="0c6c1-148">Domän anslutnings registratorer som integreras med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c6c1-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="0c6c1-149">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="0c6c1-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="0c6c1-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="0c6c1-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="0c6c1-151">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="0c6c1-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="0c6c1-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="0c6c1-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="0c6c1-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="0c6c1-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="0c6c1-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="0c6c1-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="0c6c1-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="0c6c1-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="0c6c1-156">SecureServer eller WildWestDomains (GoDaddy åter försäljare med SecureServer DNS-värd)</span><span class="sxs-lookup"><span data-stu-id="0c6c1-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="0c6c1-157">Exempel:</span><span class="sxs-lookup"><span data-stu-id="0c6c1-157">Examples:</span></span>
        - [<span data-ttu-id="0c6c1-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="0c6c1-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="0c6c1-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="0c6c1-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="0c6c1-160">Vad händer med min e-post och webbplats?</span><span class="sxs-lookup"><span data-stu-id="0c6c1-160">What happens to my email and website?</span></span>

<span data-ttu-id="0c6c1-161">När du har slutfört installationen uppdateras MX-posten för domänen så att den pekar på Microsoft 365 och alla e-postmeddelanden för domänen kommer att komma till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="0c6c1-162">Kontrol lera att du har lagt till användare och konfigurerat post lådor i Microsoft 365 för alla som får e-post på din domän!</span><span class="sxs-lookup"><span data-stu-id="0c6c1-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="0c6c1-163">Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="0c6c1-164">Anvisningarna för att konfigurera domänen påverkar inte din webbplats.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0c6c1-165">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="0c6c1-165">Related articles</span></span>

[<span data-ttu-id="0c6c1-166">Vanliga frågor och svar om domäner</span><span class="sxs-lookup"><span data-stu-id="0c6c1-166">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="0c6c1-167">Vad är en domän?</span><span class="sxs-lookup"><span data-stu-id="0c6c1-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="0c6c1-168">Köpa ett domännamn i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c6c1-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="0c6c1-169">Konfigurera din domän (tjänstspecifika instruktioner)</span><span class="sxs-lookup"><span data-stu-id="0c6c1-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
