---
title: Skapa DNS-poster på web.com för Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på web.com för Microsoft.
ms.openlocfilehash: 943070f3790f532a0cc686270e0ecdea08f802fd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656897"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="f7fad-103">Skapa DNS-poster på web.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="f7fad-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="f7fad-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="f7fad-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f7fad-105">Om web.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="f7fad-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f7fad-106">När du har lagt till dessa poster på web.com är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="f7fad-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="f7fad-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f7fad-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f7fad-110">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="f7fad-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f7fad-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="f7fad-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7fad-112">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="f7fad-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="f7fad-113">När du registrerade dig för web.com har du lagt till en domän med web.com **konfigurations** process.</span><span class="sxs-lookup"><span data-stu-id="f7fad-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="f7fad-114">Om du vill verifiera och skapa DNS-poster för din domän i Microsoft måste du först ändra namnservrar hos domän registratorn så att de använder Web. com-namnservrar.</span><span class="sxs-lookup"><span data-stu-id="f7fad-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="f7fad-115">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="f7fad-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="f7fad-116">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="f7fad-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f7fad-117">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="f7fad-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="f7fad-118">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="f7fad-118">First nameserver</span></span>  <br/> |<span data-ttu-id="f7fad-119">Använd det namnserver-värde som tillhandahålls av web.com.</span><span class="sxs-lookup"><span data-stu-id="f7fad-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="f7fad-120">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="f7fad-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="f7fad-121">Använd det namnserver-värde som tillhandahålls av web.com.</span><span class="sxs-lookup"><span data-stu-id="f7fad-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="f7fad-122">Du bör använda minst två namnserver poster.</span><span class="sxs-lookup"><span data-stu-id="f7fad-122">You should use at least two name server records.</span></span> <span data-ttu-id="f7fad-123">Om det finns andra namnservrar angivna ska du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="f7fad-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="f7fad-124">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="f7fad-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f7fad-125">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="f7fad-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f7fad-126">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="f7fad-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f7fad-127">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="f7fad-127">Add a TXT record for verification</span></span>
<span data-ttu-id="f7fad-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f7fad-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f7fad-p104">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="f7fad-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f7fad-p105">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="f7fad-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f7fad-133">Kom igång genom att gå till sidan Domains på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f7fad-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f7fad-134">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="f7fad-134">Log in first.</span></span>
  
2. <span data-ttu-id="f7fad-135">På sidan **konto hanteraren** väljer du **Mina domän namn**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f7fad-136">Under \* \* Hantera \* min domän \* \* \* väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="f7fad-137">Klicka på **Edit TXT Records** under **text (TXT-poster)** på sidan **Domain Names** och välj sedan värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f7fad-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="f7fad-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="f7fad-138">**Host**</span></span>|<span data-ttu-id="f7fad-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f7fad-139">**TTL**</span></span>|<span data-ttu-id="f7fad-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="f7fad-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="f7fad-141">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-141">3600</span></span>  <br/> |<span data-ttu-id="f7fad-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f7fad-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f7fad-143">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="f7fad-143">**Note:** This is an example.</span></span> <span data-ttu-id="f7fad-144">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="f7fad-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="f7fad-145">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="f7fad-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="f7fad-146">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="f7fad-147">Vänta några minuter innan du verifierar en ny TXT-post så att den post som du just skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="f7fad-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f7fad-148">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="f7fad-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="f7fad-149">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="f7fad-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f7fad-150">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="f7fad-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f7fad-151">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="f7fad-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f7fad-152">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f7fad-153">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f7fad-p108">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f7fad-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f7fad-157">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7fad-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f7fad-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f7fad-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f7fad-159">Kom igång genom att gå till sidan Domains på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f7fad-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f7fad-160">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="f7fad-160">Log in first.</span></span>
  
2. <span data-ttu-id="f7fad-161">På sidan **konto hanteraren** väljer du **Mina domän namn**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f7fad-162">Under \* \* Hantera \* min domän \* \* \* väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="f7fad-163">Under **e-postservrar (MX-poster)** klickar du på **Edit MX Records** och väljer sedan värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f7fad-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="f7fad-164">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="f7fad-164">**Priority**</span></span>|<span data-ttu-id="f7fad-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f7fad-165">**TTL**</span></span>|<span data-ttu-id="f7fad-166">**Mail server (postserver)**</span><span class="sxs-lookup"><span data-stu-id="f7fad-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f7fad-167">9.1</span><span class="sxs-lookup"><span data-stu-id="f7fad-167">1</span></span>  <br/> <span data-ttu-id="f7fad-168">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="f7fad-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="f7fad-169">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-169">3600</span></span>  <br/> |<span data-ttu-id="f7fad-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f7fad-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f7fad-171">**Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="f7fad-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="f7fad-172">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="f7fad-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="f7fad-173">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="f7fad-174">Om det finns andra MX-poster i avsnittet **MX Records** markerar du kryss rutan bredvid posten under **ta bort** och väljer **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="f7fad-175">På bekräftelse sidan väljer du **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f7fad-176">Lägga till de sex CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="f7fad-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="f7fad-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f7fad-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f7fad-178">Kom igång genom att gå till sidan Domains på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f7fad-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f7fad-179">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f7fad-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="f7fad-180">På sidan **konto hanteraren** väljer du **Mina domän namn**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f7fad-181">Under \* \* Hantera \* min domän \* \* \* väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="f7fad-182">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="f7fad-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="f7fad-183">Under **Host aliases (CNAME-poster)** klickar du på **Redigera CNAME-poster** och väljer sedan värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f7fad-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="f7fad-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f7fad-184">**Alias**</span></span>|<span data-ttu-id="f7fad-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f7fad-185">**TTL**</span></span>|<span data-ttu-id="f7fad-186">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="f7fad-186">**Refers to Host Name**</span></span>|<span data-ttu-id="f7fad-187">**Annan värd**</span><span class="sxs-lookup"><span data-stu-id="f7fad-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f7fad-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f7fad-188">autodiscover</span></span>  <br/> |<span data-ttu-id="f7fad-189">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-189">3600</span></span>  <br/> |<span data-ttu-id="f7fad-190">@ (inget)</span><span class="sxs-lookup"><span data-stu-id="f7fad-190">@ (none)</span></span>  <br/> |<span data-ttu-id="f7fad-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f7fad-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f7fad-192">sip</span><span class="sxs-lookup"><span data-stu-id="f7fad-192">sip</span></span>  <br/> |<span data-ttu-id="f7fad-193">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-193">3600</span></span>  <br/> |<span data-ttu-id="f7fad-194">@ (inget)</span><span class="sxs-lookup"><span data-stu-id="f7fad-194">@ (none)</span></span>  <br/> |<span data-ttu-id="f7fad-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f7fad-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f7fad-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f7fad-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f7fad-197">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-197">3600</span></span>  <br/> |<span data-ttu-id="f7fad-198">@ (inget)</span><span class="sxs-lookup"><span data-stu-id="f7fad-198">@ (none)</span></span>  <br/> | <span data-ttu-id="f7fad-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f7fad-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f7fad-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f7fad-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f7fad-201">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-201">3600</span></span>  <br/> |<span data-ttu-id="f7fad-202">@ (inget)</span><span class="sxs-lookup"><span data-stu-id="f7fad-202">@ (none)</span></span>  <br/> |<span data-ttu-id="f7fad-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f7fad-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="f7fad-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f7fad-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f7fad-205">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-205">3600</span></span>  <br/> |<span data-ttu-id="f7fad-206">@ (inget)</span><span class="sxs-lookup"><span data-stu-id="f7fad-206">@ (none)</span></span>  <br/> |<span data-ttu-id="f7fad-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f7fad-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="f7fad-208">msoid</span><span class="sxs-lookup"><span data-stu-id="f7fad-208">msoid</span></span>  <br/> |<span data-ttu-id="f7fad-209">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-209">3600</span></span>  <br/> |<span data-ttu-id="f7fad-210">@ (inget)</span><span class="sxs-lookup"><span data-stu-id="f7fad-210">@ (none)</span></span>  <br/> |<span data-ttu-id="f7fad-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="f7fad-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="f7fad-212">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="f7fad-213">Lägg till de andra fem CNAME-posterna var för sig.</span><span class="sxs-lookup"><span data-stu-id="f7fad-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f7fad-214">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="f7fad-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f7fad-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f7fad-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7fad-216">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="f7fad-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f7fad-217">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="f7fad-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f7fad-218">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7fad-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f7fad-219">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="f7fad-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="f7fad-220">Kom igång genom att gå till sidan Domains på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f7fad-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f7fad-221">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="f7fad-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="f7fad-222">På sidan **konto hanteraren** väljer du **Mina domän namn**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f7fad-223">Under \* \* Hantera \* min domän \* \* \* väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="f7fad-224">Klicka på **Edit TXT Records** under **text (TXT-poster)** på sidan **Domain Names** och välj sedan värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f7fad-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="f7fad-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="f7fad-225">**Host**</span></span>|<span data-ttu-id="f7fad-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f7fad-226">**TTL**</span></span>|<span data-ttu-id="f7fad-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="f7fad-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f7fad-228">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-228">3600</span></span>  <br/> |<span data-ttu-id="f7fad-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f7fad-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f7fad-230">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="f7fad-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="f7fad-231">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-231">Select **Continue**.</span></span>

6. <span data-ttu-id="f7fad-232">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f7fad-233">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="f7fad-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="f7fad-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f7fad-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7fad-235">Kom ihåg att web.com är ansvarigt för att göra denna funktion tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f7fad-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="f7fad-236">Om du inte ser avvikelser mellan stegen nedan och det aktuella web.com GUI (grafiskt användar gränssnitt) bör du använda [Web.com community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="f7fad-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="f7fad-237">Kom igång genom att gå till sidan Domains på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f7fad-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f7fad-238">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="f7fad-238">Log in first.</span></span>
      
2. <span data-ttu-id="f7fad-239">På sidan **konto hanteraren** väljer du **Mina domän namn**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f7fad-240">Under \* \* Hantera \* min domän \* \* \* väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="f7fad-241">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="f7fad-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="f7fad-242">Under **tjänst (SRV-poster)** klickar du på **Redigera SRV-poster** och väljer sedan värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f7fad-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="f7fad-243">**Service**</span><span class="sxs-lookup"><span data-stu-id="f7fad-243">**Service**</span></span>|<span data-ttu-id="f7fad-244">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="f7fad-244">**Protocol**</span></span>|<span data-ttu-id="f7fad-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f7fad-245">**TTL**</span></span>|<span data-ttu-id="f7fad-246">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="f7fad-246">**Priority**</span></span>|<span data-ttu-id="f7fad-247">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="f7fad-247">**Weight**</span></span>|<span data-ttu-id="f7fad-248">**Port**</span><span class="sxs-lookup"><span data-stu-id="f7fad-248">**Port**</span></span>|<span data-ttu-id="f7fad-249">**Target**</span><span class="sxs-lookup"><span data-stu-id="f7fad-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f7fad-250">_sip</span><span class="sxs-lookup"><span data-stu-id="f7fad-250">_sip</span></span> |<span data-ttu-id="f7fad-251">_tls</span><span class="sxs-lookup"><span data-stu-id="f7fad-251">_tls</span></span> |<span data-ttu-id="f7fad-252">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-252">3600</span></span> | <span data-ttu-id="f7fad-253">100</span><span class="sxs-lookup"><span data-stu-id="f7fad-253">100</span></span>|<span data-ttu-id="f7fad-254">9.1</span><span class="sxs-lookup"><span data-stu-id="f7fad-254">1</span></span> |<span data-ttu-id="f7fad-255">443</span><span class="sxs-lookup"><span data-stu-id="f7fad-255">443</span></span> |<span data-ttu-id="f7fad-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f7fad-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="f7fad-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f7fad-257">_sipfederationtls</span></span> |<span data-ttu-id="f7fad-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="f7fad-258">_tcp</span></span> |<span data-ttu-id="f7fad-259">3600</span><span class="sxs-lookup"><span data-stu-id="f7fad-259">3600</span></span> |<span data-ttu-id="f7fad-260">100</span><span class="sxs-lookup"><span data-stu-id="f7fad-260">100</span></span> |<span data-ttu-id="f7fad-261">9.1</span><span class="sxs-lookup"><span data-stu-id="f7fad-261">1</span></span> |<span data-ttu-id="f7fad-262">5061</span><span class="sxs-lookup"><span data-stu-id="f7fad-262">5061</span></span> | <span data-ttu-id="f7fad-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f7fad-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="f7fad-264">Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="f7fad-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="f7fad-265">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-265">Select **Continue**.</span></span>

7. <span data-ttu-id="f7fad-266">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="f7fad-p116">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f7fad-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
