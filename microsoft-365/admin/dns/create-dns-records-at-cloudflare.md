---
title: Skapa DNS-poster för Office 365 hos Cloudfare
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Cloudflare för Office 365.
ms.openlocfilehash: efd7a4a41a0cc27c2a50da732d648c87c79c6ff7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810824"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a><span data-ttu-id="ab7b4-103">Skapa DNS-poster för Office 365 hos Cloudfare</span><span class="sxs-lookup"><span data-stu-id="ab7b4-103">Create DNS records at Cloudflare for Office 365</span></span>

 <span data-ttu-id="ab7b4-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ab7b4-105">Om Cloudflare är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ab7b4-106">När du har lagt till dessa poster i Cloudflare är domänen konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-106">After you add these records at Cloudflare, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ab7b4-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ab7b4-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="ab7b4-111">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="ab7b4-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="ab7b4-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7b4-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab7b4-113">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="ab7b4-114">När du registrerade dig för Cloudflare lade du till en domän med hjälp av Cloudflares **konfigurationsprocess**.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="ab7b4-p102">Den domän du lade till har köpts från en separat domänregistrator. Cloudflare erbjuder inte tjänster för domänregistrering. Om du vill verifiera och skapa DNS-poster för din domän i Office 365, måste du ändra namnservrarna hos domänregistratorn så att de använder Cloudflares namnservrar.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p102">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services. To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="ab7b4-117">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="ab7b4-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="ab7b4-118">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="ab7b4-119">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="ab7b4-120">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="ab7b4-120">First nameserver</span></span>  <br/> |<span data-ttu-id="ab7b4-121">Använd namnservervärdet från Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="ab7b4-122">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="ab7b4-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="ab7b4-123">Använd namnservervärdet från Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="ab7b4-124">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-124">You should use at least two name server records.</span></span> <span data-ttu-id="ab7b4-125">Om det finns några andra namnservrar i listan bör du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="ab7b4-126">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ab7b4-p104">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p104">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ab7b4-129">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="ab7b4-129">Add a TXT record for verification</span></span>
<span data-ttu-id="ab7b4-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7b4-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ab7b4-p105">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p105">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab7b4-p106">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ab7b4-135">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="ab7b4-136">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="ab7b4-137">På **startsidan** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="ab7b4-138">Välj **DNS**på sidan **Översikt** för domänen.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="ab7b4-139">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="ab7b4-140">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-140">**Type**</span></span>|<span data-ttu-id="ab7b4-141">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-141">**Name**</span></span>|<span data-ttu-id="ab7b4-142">**Automatic TTL (automatisk TTL)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-142">**Automatic TTL**</span></span>|<span data-ttu-id="ab7b4-143">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="ab7b4-144">TXT</span><span class="sxs-lookup"><span data-stu-id="ab7b4-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="ab7b4-145">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-145">30 minutes</span></span>  <br/> |<span data-ttu-id="ab7b4-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ab7b4-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ab7b4-p108">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p108">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="ab7b4-150">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="ab7b4-151">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ab7b4-152">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-152">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ab7b4-153">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-153">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ab7b4-154">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="ab7b4-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ab7b4-155">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ab7b4-156">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ab7b4-157">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ab7b4-p109">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ab7b4-161">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="ab7b4-161">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ab7b4-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7b4-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ab7b4-p110">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="ab7b4-165">På **startsidan** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="ab7b4-166">Välj **DNS**på sidan **Översikt** för domänen.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="ab7b4-167">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="ab7b4-168">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-168">**Type**</span></span>|<span data-ttu-id="ab7b4-169">**Namn**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-169">**Name**</span></span>|<span data-ttu-id="ab7b4-170">**Mail server (postserver)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-170">**Mail server**</span></span>|<span data-ttu-id="ab7b4-171">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-171">**Priority**</span></span>|<span data-ttu-id="ab7b4-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ab7b4-173">MX</span><span class="sxs-lookup"><span data-stu-id="ab7b4-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="ab7b4-174">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ab7b4-175">**Obs:** Hämta din \* \<domännyckel\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-175">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="ab7b4-176">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="ab7b4-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="ab7b4-177">1</span><span class="sxs-lookup"><span data-stu-id="ab7b4-177">1</span></span>  <br/> <span data-ttu-id="ab7b4-178">[Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="ab7b4-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="ab7b4-179">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="ab7b4-180">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="ab7b4-181">Om det finns andra MX-poster som i avsnittet **MX Records** (MX-poster) ska du ta bort alla genom att välja ikonen **Delete (X)** (ta bort (X)).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="ab7b4-182">Välj **Ta bort** i bekräftelsedialogrutan för att bekräfta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ab7b4-183">Lägga till de sex CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="ab7b4-183">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ab7b4-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7b4-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ab7b4-p112">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="ab7b4-187">På **startsidan** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="ab7b4-188">Välj **DNS**på sidan **Översikt** för domänen.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="ab7b4-189">Lägg till den första av de fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="ab7b4-190">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="ab7b4-191">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-191">**Type**</span></span>|<span data-ttu-id="ab7b4-192">**Namn**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-192">**Name**</span></span>|<span data-ttu-id="ab7b4-193">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-193">**Target**</span></span>|<span data-ttu-id="ab7b4-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ab7b4-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab7b4-195">CNAME</span></span>  <br/> |<span data-ttu-id="ab7b4-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ab7b4-196">autodiscover</span></span>  <br/> |<span data-ttu-id="ab7b4-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="ab7b4-198">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="ab7b4-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab7b4-199">CNAME</span></span>  <br/> |<span data-ttu-id="ab7b4-200">sip</span><span class="sxs-lookup"><span data-stu-id="ab7b4-200">sip</span></span>  <br/> |<span data-ttu-id="ab7b4-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="ab7b4-202">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="ab7b4-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab7b4-203">CNAME</span></span>  <br/> |<span data-ttu-id="ab7b4-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ab7b4-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ab7b4-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="ab7b4-206">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="ab7b4-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab7b4-207">CNAME</span></span>  <br/> |<span data-ttu-id="ab7b4-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ab7b4-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ab7b4-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ab7b4-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="ab7b4-210">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="ab7b4-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab7b4-211">CNAME</span></span>  <br/> |<span data-ttu-id="ab7b4-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ab7b4-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ab7b4-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="ab7b4-214">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="ab7b4-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab7b4-215">CNAME</span></span>  <br/> |<span data-ttu-id="ab7b4-216">msoid</span><span class="sxs-lookup"><span data-stu-id="ab7b4-216">msoid</span></span>  <br/> |<span data-ttu-id="ab7b4-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="ab7b4-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="ab7b4-218">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="ab7b4-219">Välj **ikonen DNS Traffic** (orange moln) för att kringgå Cloudflare-servrarna.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="ab7b4-220">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="ab7b4-221">Lägg till de andra fem CNAME-posterna var för sig.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ab7b4-222">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="ab7b4-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ab7b4-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7b4-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab7b4-224">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ab7b4-225">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ab7b4-226">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ab7b4-227">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="ab7b4-228">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="ab7b4-229">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="ab7b4-230">På **startsidan** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="ab7b4-231">Välj **DNS**på sidan **Översikt** för domänen.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="ab7b4-232">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="ab7b4-233">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-233">**Type**</span></span>|<span data-ttu-id="ab7b4-234">**Namn**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-234">**Name**</span></span>|<span data-ttu-id="ab7b4-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-235">**TTL**</span></span>|<span data-ttu-id="ab7b4-236">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ab7b4-237">TXT</span><span class="sxs-lookup"><span data-stu-id="ab7b4-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="ab7b4-238">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-238">30 minutes</span></span>  <br/> |<span data-ttu-id="ab7b4-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ab7b4-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ab7b4-240">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="ab7b4-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="ab7b4-241">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ab7b4-242">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="ab7b4-242">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="ab7b4-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7b4-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab7b4-244">Tänk på att Cloudflare ansvarar för att göra den här funktionen tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="ab7b4-245">Om du ser avvikelser mellan stegen nedan och det aktuella Cloudflare GUI(Graphical User Interface) kan du utnyttja [Cloudflare-communityn](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-245">In case you see discrepancies between the steps below and the current Cloudflare GUI(Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="ab7b4-246">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="ab7b4-247">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="ab7b4-248">På **startsidan** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="ab7b4-249">Välj **DNS**på sidan **Översikt** för domänen.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="ab7b4-250">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="ab7b4-251">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="ab7b4-252">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-252">**Type**</span></span>|<span data-ttu-id="ab7b4-253">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-253">**Service**</span></span>|<span data-ttu-id="ab7b4-254">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-254">**Protocol**</span></span>|<span data-ttu-id="ab7b4-255">**Namn**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-255">**Name**</span></span>|<span data-ttu-id="ab7b4-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-256">**TTL**</span></span>|<span data-ttu-id="ab7b4-257">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-257">**Priority**</span></span>|<span data-ttu-id="ab7b4-258">**Weight**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-258">**Weight**</span></span>|<span data-ttu-id="ab7b4-259">**Port**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-259">**Port**</span></span>|<span data-ttu-id="ab7b4-260">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="ab7b4-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ab7b4-261">SRV</span><span class="sxs-lookup"><span data-stu-id="ab7b4-261">SRV</span></span>|<span data-ttu-id="ab7b4-262">_sip</span><span class="sxs-lookup"><span data-stu-id="ab7b4-262">_sip</span></span> |<span data-ttu-id="ab7b4-263">TLS</span><span class="sxs-lookup"><span data-stu-id="ab7b4-263">TLS</span></span> |<span data-ttu-id="ab7b4-264">Använd din *domain_name;* till exempel contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="ab7b4-265">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-265">30 minutes</span></span> | <span data-ttu-id="ab7b4-266">100</span><span class="sxs-lookup"><span data-stu-id="ab7b4-266">100</span></span>|<span data-ttu-id="ab7b4-267">1</span><span class="sxs-lookup"><span data-stu-id="ab7b4-267">1</span></span> |<span data-ttu-id="ab7b4-268">443</span><span class="sxs-lookup"><span data-stu-id="ab7b4-268">443</span></span> |<span data-ttu-id="ab7b4-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="ab7b4-270">SRV</span><span class="sxs-lookup"><span data-stu-id="ab7b4-270">SRV</span></span>|<span data-ttu-id="ab7b4-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ab7b4-271">_sipfederationtls</span></span> | <span data-ttu-id="ab7b4-272">TCP</span><span class="sxs-lookup"><span data-stu-id="ab7b4-272">TCP</span></span>|<span data-ttu-id="ab7b4-273">Använd din *domain_name;* till exempel contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="ab7b4-274">30 minuter</span><span class="sxs-lookup"><span data-stu-id="ab7b4-274">30 minutes</span></span> |<span data-ttu-id="ab7b4-275">100</span><span class="sxs-lookup"><span data-stu-id="ab7b4-275">100</span></span> |<span data-ttu-id="ab7b4-276">1</span><span class="sxs-lookup"><span data-stu-id="ab7b4-276">1</span></span> |<span data-ttu-id="ab7b4-277">5061</span><span class="sxs-lookup"><span data-stu-id="ab7b4-277">5061</span></span> | <span data-ttu-id="ab7b4-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ab7b4-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="ab7b4-279">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="ab7b4-280">Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="ab7b4-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="ab7b4-p117">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
