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
description: Använd installationsguiden för att lägga till din domän Microsoft 365 i Microsoft 365 genom att lägga till en DNS-post hos din DNS-värd.
ms.openlocfilehash: 152144737b0ff8cb8b0c27db2a4fc1051fb2a8a7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635684"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="a5d1e-103">Lägga till en domän i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5d1e-103">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="a5d1e-104">**[Läs frågor och svar om domäner](domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-104">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="a5d1e-105">*Om du vill lägga till, ändra eller ta bort **domäner måste** du vara **global administratör** för ett [företags- eller företagsplan.](https://products.office.com/business/office) Dessa ändringar påverkar hela *klientorganisationen, anpassade* administratörer *eller vanliga* användare kommer inte att kunna göra dessa ändringar.*</span><span class="sxs-lookup"><span data-stu-id="a5d1e-105">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 ## <a name="add-a-domain"></a><span data-ttu-id="a5d1e-106">Lägga till en domän</span><span class="sxs-lookup"><span data-stu-id="a5d1e-106">Add a domain</span></span>

<span data-ttu-id="a5d1e-107">Följ de här anvisningarna om du vill lägga till, konfigurera eller fortsätta att konfigurera en domän.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5d1e-108">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="a5d1e-109">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5d1e-110">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a5d1e-111">Gå till sidan **Inställningar**  >  **Domains.**</span><span class="sxs-lookup"><span data-stu-id="a5d1e-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="a5d1e-112">Välj **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="a5d1e-113">Ange namnet på den domän som du vill lägga till och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a5d1e-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="a5d1e-114">Välj hur du vill verifiera att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="a5d1e-115">Om din domänregistrator använder [Domain Anslut](#domain-connect-registrars-integrating-with-microsoft-365)konfigureras dina poster automatiskt av [Microsoft](../get-help-with-domains/domain-connect.md) genom att du loggar in på registratorn och bekräftar anslutningen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="a5d1e-116">Du kommer tillbaka till administrationscentret och Microsoft verifierar sedan automatiskt din domän.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="a5d1e-117">Du kan använda en TXT-post för att verifiera din domän.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="a5d1e-118">Välj det här alternativet **och välj** Nästa för att se anvisningar för hur du lägger till DNS-posten på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="a5d1e-119">Det kan ta upp till 30 minuter att verifiera detta när du har lagt till posten.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="a5d1e-120">Du kan lägga till en textfil på webbplatsen för din domän.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="a5d1e-121">Välj och ladda .txt filen från installationsguiden och ladda sedan upp filen till webbplatsens toppnivåmapp.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="a5d1e-122">Sökvägen till filen bör se ut ungefär så här: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="a5d1e-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="a5d1e-123">Vi bekräftar att du äger domänen genom att leta reda på filen på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="a5d1e-124">Välj hur du vill göra de DNS-ändringar som krävs för att Microsoft ska kunna använda din domän.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="a5d1e-125">Välj **Add the DNS records for me** om din registrator har stöd för Domain [Anslut](#domain-connect-registrars-integrating-with-microsoft-365), så kommer [Microsoft](../get-help-with-domains/domain-connect.md) att konfigurera dina poster automatiskt genom att du loggar in på din registrator och bekräftar anslutningen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="a5d1e-126">Välj **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="a5d1e-127">**Välj det här alternativet om du vet exakt vad du gör.**</span><span class="sxs-lookup"><span data-stu-id="a5d1e-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="a5d1e-128">Om du väljer att lägga  till *DNS-poster* själv väljer du Nästa. Då visas en sida med alla poster som du behöver lägga till på domänregistratorns webbplats för att konfigurera domänen.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="a5d1e-129">Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="a5d1e-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="a5d1e-130">Kontrollera listan med [värdspecifika instruktioner](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="a5d1e-131">Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="a5d1e-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="a5d1e-132">Om du vill vänta till senare avmarkerar du antingen alla tjänster och  klickar på **Fortsätt,** eller så väljer du Fler alternativ i föregående domänanslutningssteg och väljer Hoppa över det **här tills vidare.**</span><span class="sxs-lookup"><span data-stu-id="a5d1e-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="a5d1e-133">Välj **Slutför** – nu är du klar!</span><span class="sxs-lookup"><span data-stu-id="a5d1e-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="a5d1e-134">Lägga till eller redigera anpassade DNS-poster</span><span class="sxs-lookup"><span data-stu-id="a5d1e-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="a5d1e-135">Följ stegen nedan för att lägga till en anpassad post för en webbplats eller tredjepartstjänst.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="a5d1e-136">Logga in på Microsofts administrationscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="a5d1e-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a5d1e-137">Gå till sidan **Inställningar**   >  **Domains.**</span><span class="sxs-lookup"><span data-stu-id="a5d1e-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="a5d1e-138">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="a5d1e-139">Under **DNS-inställningar** väljer du **Anpassade poster**. välj sedan **Ny anpassad post**.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="a5d1e-140">Välj den typ av DNS-post du vill lägga till och ange informationen för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="a5d1e-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="a5d1e-142">Registratorer med Anslut</span><span class="sxs-lookup"><span data-stu-id="a5d1e-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="a5d1e-143">[Domän Anslut](https://www.domainconnect.org/) domänregistratorer låter dig lägga till din domän Microsoft 365 i en trestegsprocess som bara tar några minuter.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="a5d1e-144">I guiden bekräftar vi bara att du äger domänen och sedan konfigureras domänens poster automatiskt, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, till exempel Teams, fungerar med din domän.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5d1e-145">Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="a5d1e-146">Domän Anslut domänregistratorer som integrerar med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5d1e-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="a5d1e-147">1 &amp; 1 I ENTISKT</span><span class="sxs-lookup"><span data-stu-id="a5d1e-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="a5d1e-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="a5d1e-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="a5d1e-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="a5d1e-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="a5d1e-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="a5d1e-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="a5d1e-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="a5d1e-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="a5d1e-152">Hannsk</span><span class="sxs-lookup"><span data-stu-id="a5d1e-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="a5d1e-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="a5d1e-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="a5d1e-154">SecureServer eller WildWestDomains (GoDaddy-återförsäljare som använder SecureServer DNS-värd)</span><span class="sxs-lookup"><span data-stu-id="a5d1e-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="a5d1e-155">Exempel:</span><span class="sxs-lookup"><span data-stu-id="a5d1e-155">Examples:</span></span>
        - [<span data-ttu-id="a5d1e-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="a5d1e-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="a5d1e-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="a5d1e-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="a5d1e-158">Vad händer med min e-post och webbplats?</span><span class="sxs-lookup"><span data-stu-id="a5d1e-158">What happens to my email and website?</span></span>

<span data-ttu-id="a5d1e-159">När du är klar med konfigurationen uppdateras MX-posten för din domän så att den pekar på Microsoft 365 och all e-post för domänen börjar komma Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="a5d1e-160">Kontrollera att du har lagt till användare och ställt in postlådor i Microsoft 365 för alla som får e-post på din domän!</span><span class="sxs-lookup"><span data-stu-id="a5d1e-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="a5d1e-161">Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="a5d1e-162">Domänkonfigurationsstegen Anslut påverkar inte din webbplats.</span><span class="sxs-lookup"><span data-stu-id="a5d1e-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-content"></a><span data-ttu-id="a5d1e-163">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="a5d1e-163">Related content</span></span>

<span data-ttu-id="a5d1e-164">[Vanliga frågor och svar om domäner](domains-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a5d1e-164">[Domains FAQ](domains-faq.yml) (article)</span></span>\
[<span data-ttu-id="a5d1e-165">Vad är en domän?</span><span class="sxs-lookup"><span data-stu-id="a5d1e-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md) <span data-ttu-id="a5d1e-166">(artikel)</span><span class="sxs-lookup"><span data-stu-id="a5d1e-166">(article)</span></span>\
<span data-ttu-id="a5d1e-167">[Köp ett domännamn i Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a5d1e-167">[Buy a domain name in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (article)</span></span>\
<span data-ttu-id="a5d1e-168">[Konfigurera din domän](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a5d1e-168">[Set up your domain](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (article)</span></span>