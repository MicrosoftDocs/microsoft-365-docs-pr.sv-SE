---
title: Skapa DNS-poster på Cloudflare för Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Cloudflare för Microsoft.
ms.openlocfilehash: 116132d096db61e7004315dcf159fc78dd790d43
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939325"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="6c840-103">Skapa DNS-poster på Cloudflare för Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c840-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="6c840-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="6c840-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6c840-105">Om Cloudflare är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="6c840-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6c840-106">När du har lagt till dessa poster på Cloudflare konfigureras domänen så att den fungerar med Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="6c840-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="6c840-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c840-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6c840-110">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="6c840-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="6c840-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="6c840-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c840-112">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="6c840-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="6c840-113">När du registrerade dig för Cloudflare lade du till en domän med hjälp av Cloudflares **konfigurationsprocess**.</span><span class="sxs-lookup"><span data-stu-id="6c840-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="6c840-114">Domänen som du lade till köptes från Cloudflare eller en separat domänregistrare.</span><span class="sxs-lookup"><span data-stu-id="6c840-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="6c840-115">Om du vill verifiera och skapa DNS-poster för din domän i Microsoft 365 måste du först ändra namnservrarna hos domänregistraren så att de använder Cloudflares namnservrar.</span><span class="sxs-lookup"><span data-stu-id="6c840-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="6c840-116">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="6c840-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="6c840-117">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="6c840-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="6c840-118">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="6c840-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="6c840-119">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="6c840-119">First nameserver</span></span>  <br/> |<span data-ttu-id="6c840-120">Använd namnservervärdet från Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="6c840-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="6c840-121">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="6c840-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="6c840-122">Använd namnservervärdet från Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="6c840-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="6c840-123">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="6c840-123">You should use at least two name server records.</span></span> <span data-ttu-id="6c840-124">Om det finns några andra namnservrar i listan bör du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="6c840-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="6c840-125">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="6c840-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c840-126">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="6c840-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6c840-127">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="6c840-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6c840-128">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="6c840-128">Add a TXT record for verification</span></span>
<span data-ttu-id="6c840-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6c840-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6c840-p105">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="6c840-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c840-p106">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="6c840-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6c840-134">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="6c840-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="6c840-135">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="6c840-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="6c840-136">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="6c840-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="6c840-137">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="6c840-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="6c840-138">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6c840-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="6c840-139">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6c840-139">**Type**</span></span>|<span data-ttu-id="6c840-140">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="6c840-140">**Name**</span></span>|<span data-ttu-id="6c840-141">**Automatic TTL (automatisk TTL)**</span><span class="sxs-lookup"><span data-stu-id="6c840-141">**Automatic TTL**</span></span>|<span data-ttu-id="6c840-142">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="6c840-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="6c840-143">TXT</span><span class="sxs-lookup"><span data-stu-id="6c840-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="6c840-144">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-144">30 minutes</span></span>  <br/> |<span data-ttu-id="6c840-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6c840-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6c840-146">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="6c840-146">**Note:** This is an example.</span></span> <span data-ttu-id="6c840-147">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="6c840-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="6c840-148">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="6c840-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="6c840-149">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6c840-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="6c840-150">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="6c840-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6c840-151">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och söker efter posten.</span><span class="sxs-lookup"><span data-stu-id="6c840-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="6c840-152">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="6c840-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6c840-153">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="6c840-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6c840-154">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="6c840-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6c840-155">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="6c840-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6c840-156">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="6c840-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6c840-p109">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c840-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6c840-160">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c840-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6c840-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6c840-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6c840-p110">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="6c840-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="6c840-164">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="6c840-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="6c840-165">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="6c840-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="6c840-166">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6c840-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="6c840-167">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6c840-167">**Type**</span></span>|<span data-ttu-id="6c840-168">**Namn**</span><span class="sxs-lookup"><span data-stu-id="6c840-168">**Name**</span></span>|<span data-ttu-id="6c840-169">**Mail server (postserver)**</span><span class="sxs-lookup"><span data-stu-id="6c840-169">**Mail server**</span></span>|<span data-ttu-id="6c840-170">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="6c840-170">**Priority**</span></span>|<span data-ttu-id="6c840-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6c840-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c840-172">MX</span><span class="sxs-lookup"><span data-stu-id="6c840-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="6c840-173">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6c840-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6c840-174">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft 365-konto.</span><span class="sxs-lookup"><span data-stu-id="6c840-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="6c840-175">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="6c840-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="6c840-176">1</span><span class="sxs-lookup"><span data-stu-id="6c840-176">1</span></span>  <br/> <span data-ttu-id="6c840-177">[Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="6c840-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="6c840-178">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="6c840-179">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6c840-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="6c840-180">Om det finns andra MX-poster som i avsnittet **MX Records** (MX-poster) ska du ta bort alla genom att välja ikonen **Delete (X)** (ta bort (X)).</span><span class="sxs-lookup"><span data-stu-id="6c840-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="6c840-181">Välj Ta bort i **bekräftelsedialogrutan** för att bekräfta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="6c840-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6c840-182">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c840-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6c840-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6c840-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="6c840-p112">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="6c840-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="6c840-186">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="6c840-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="6c840-187">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="6c840-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="6c840-188">Lägg till den första av de fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="6c840-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="6c840-189">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6c840-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="6c840-190">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6c840-190">**Type**</span></span>|<span data-ttu-id="6c840-191">**Namn**</span><span class="sxs-lookup"><span data-stu-id="6c840-191">**Name**</span></span>|<span data-ttu-id="6c840-192">**Mål**</span><span class="sxs-lookup"><span data-stu-id="6c840-192">**Target**</span></span>|<span data-ttu-id="6c840-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6c840-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c840-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c840-194">CNAME</span></span>  <br/> |<span data-ttu-id="6c840-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6c840-195">autodiscover</span></span>  <br/> |<span data-ttu-id="6c840-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6c840-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="6c840-197">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="6c840-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c840-198">CNAME</span></span>  <br/> |<span data-ttu-id="6c840-199">sip</span><span class="sxs-lookup"><span data-stu-id="6c840-199">sip</span></span>  <br/> |<span data-ttu-id="6c840-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6c840-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6c840-201">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="6c840-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c840-202">CNAME</span></span>  <br/> |<span data-ttu-id="6c840-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6c840-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6c840-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6c840-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6c840-205">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="6c840-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c840-206">CNAME</span></span>  <br/> |<span data-ttu-id="6c840-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6c840-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6c840-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6c840-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="6c840-209">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="6c840-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c840-210">CNAME</span></span>  <br/> |<span data-ttu-id="6c840-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6c840-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6c840-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6c840-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="6c840-213">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="6c840-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c840-214">CNAME</span></span>  <br/> |<span data-ttu-id="6c840-215">msoid</span><span class="sxs-lookup"><span data-stu-id="6c840-215">msoid</span></span>  <br/> |<span data-ttu-id="6c840-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="6c840-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="6c840-217">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="6c840-218">Välj **DNS Traffic-ikonen** (orange moln) för att kringgå Cloudflare-servrarna.</span><span class="sxs-lookup"><span data-stu-id="6c840-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="6c840-219">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6c840-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="6c840-220">Lägg till de andra fem CNAME-posterna var för sig.</span><span class="sxs-lookup"><span data-stu-id="6c840-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6c840-221">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="6c840-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6c840-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6c840-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c840-223">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="6c840-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6c840-224">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="6c840-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6c840-225">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c840-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="6c840-226">Lägg istället till de obligatoriska Microsoft 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="6c840-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="6c840-227">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="6c840-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="6c840-228">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="6c840-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="6c840-229">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="6c840-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="6c840-230">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="6c840-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="6c840-231">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6c840-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="6c840-232">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6c840-232">**Type**</span></span>|<span data-ttu-id="6c840-233">**Namn**</span><span class="sxs-lookup"><span data-stu-id="6c840-233">**Name**</span></span>|<span data-ttu-id="6c840-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6c840-234">**TTL**</span></span>|<span data-ttu-id="6c840-235">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="6c840-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c840-236">TXT</span><span class="sxs-lookup"><span data-stu-id="6c840-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="6c840-237">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-237">30 minutes</span></span>  <br/> |<span data-ttu-id="6c840-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6c840-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6c840-239">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="6c840-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="6c840-240">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6c840-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6c840-241">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c840-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6c840-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6c840-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c840-243">Tänk på att Cloudflare är ansvarigt för att göra den här funktionen tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6c840-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="6c840-244">Om du ser avvikelser mellan stegen nedan och det aktuella Cloudflare GUI (Grafiskt användargränssnitt), vänligen utnyttja [Cloudflare-communityn](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="6c840-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="6c840-245">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="6c840-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="6c840-246">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="6c840-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="6c840-247">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="6c840-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="6c840-248">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="6c840-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="6c840-249">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="6c840-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="6c840-250">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6c840-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="6c840-251">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="6c840-251">**Type**</span></span>|<span data-ttu-id="6c840-252">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="6c840-252">**Service**</span></span>|<span data-ttu-id="6c840-253">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="6c840-253">**Protocol**</span></span>|<span data-ttu-id="6c840-254">**Namn**</span><span class="sxs-lookup"><span data-stu-id="6c840-254">**Name**</span></span>|<span data-ttu-id="6c840-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6c840-255">**TTL**</span></span>|<span data-ttu-id="6c840-256">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="6c840-256">**Priority**</span></span>|<span data-ttu-id="6c840-257">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="6c840-257">**Weight**</span></span>|<span data-ttu-id="6c840-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="6c840-258">**Port**</span></span>|<span data-ttu-id="6c840-259">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="6c840-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c840-260">SRV</span><span class="sxs-lookup"><span data-stu-id="6c840-260">SRV</span></span>|<span data-ttu-id="6c840-261">_sip</span><span class="sxs-lookup"><span data-stu-id="6c840-261">_sip</span></span> |<span data-ttu-id="6c840-262">TLS</span><span class="sxs-lookup"><span data-stu-id="6c840-262">TLS</span></span> |<span data-ttu-id="6c840-263">Använd din *domain_name;* till exempel contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c840-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="6c840-264">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-264">30 minutes</span></span> | <span data-ttu-id="6c840-265">100</span><span class="sxs-lookup"><span data-stu-id="6c840-265">100</span></span>|<span data-ttu-id="6c840-266">1</span><span class="sxs-lookup"><span data-stu-id="6c840-266">1</span></span> |<span data-ttu-id="6c840-267">443</span><span class="sxs-lookup"><span data-stu-id="6c840-267">443</span></span> |<span data-ttu-id="6c840-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6c840-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="6c840-269">SRV</span><span class="sxs-lookup"><span data-stu-id="6c840-269">SRV</span></span>|<span data-ttu-id="6c840-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="6c840-270">_sipfederationtls</span></span> | <span data-ttu-id="6c840-271">TCP</span><span class="sxs-lookup"><span data-stu-id="6c840-271">TCP</span></span>|<span data-ttu-id="6c840-272">Använd din *domain_name;* till exempel contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c840-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="6c840-273">30 minuter</span><span class="sxs-lookup"><span data-stu-id="6c840-273">30 minutes</span></span> |<span data-ttu-id="6c840-274">100</span><span class="sxs-lookup"><span data-stu-id="6c840-274">100</span></span> |<span data-ttu-id="6c840-275">1</span><span class="sxs-lookup"><span data-stu-id="6c840-275">1</span></span> |<span data-ttu-id="6c840-276">5061</span><span class="sxs-lookup"><span data-stu-id="6c840-276">5061</span></span> | <span data-ttu-id="6c840-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6c840-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="6c840-278">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6c840-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="6c840-279">Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="6c840-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="6c840-p117">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c840-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
