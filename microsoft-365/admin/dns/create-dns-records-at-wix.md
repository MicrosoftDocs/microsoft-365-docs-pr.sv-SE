---
title: Skapa DNS-poster på WIX för Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på WIX för Microsoft.
ms.openlocfilehash: fcc0f8e8187e22dde68149e0f2a80073312bff7f
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814450"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="c9bf1-103">Skapa DNS-poster på WIX för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9bf1-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="c9bf1-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c9bf1-105">Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="c9bf1-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="c9bf1-107">[Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="c9bf1-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="c9bf1-108">[Lägg till en MX-post så att e-post för din domän kommer till Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="c9bf1-109">[Lägg till de fem CNAME-poster som krävs för Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="c9bf1-110">[Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="c9bf1-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="c9bf1-111">[Lägg till de två SRV-poster som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="c9bf1-112">När du har lagt till dessa poster på WIX är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c9bf1-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c9bf1-116">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="c9bf1-116">Add a TXT record for verification</span></span>
<span data-ttu-id="c9bf1-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bf1-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="c9bf1-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9bf1-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="c9bf1-122">WIX stöder inte DNS-poster för under domäner.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="c9bf1-123">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c9bf1-124">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9bf1-125">På sidan **My Domains** , i området **Avancerat** , väljer du knappen **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="c9bf1-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c9bf1-126">Välj **+ Lägg till en annan** på raden **txt (text)** i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c9bf1-127">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="c9bf1-128">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="c9bf1-128">Host Name</span></span> <br/> | <span data-ttu-id="c9bf1-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="c9bf1-129">TXT Value</span></span> <br/> | <span data-ttu-id="c9bf1-130">TTL</span><span class="sxs-lookup"><span data-stu-id="c9bf1-130">TTL</span></span> <br/> |
   |<span data-ttu-id="c9bf1-131">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="c9bf1-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="c9bf1-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c9bf1-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c9bf1-133">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-133">**Note:** This is an example.</span></span> <span data-ttu-id="c9bf1-134">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="c9bf1-135">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="c9bf1-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="c9bf1-136">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="c9bf1-137">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c9bf1-138">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c9bf1-139">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c9bf1-140">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c9bf1-141">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c9bf1-142">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="c9bf1-143">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="c9bf1-144">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c9bf1-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c9bf1-148">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c9bf1-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bf1-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="c9bf1-150">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c9bf1-151">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9bf1-152">Välj länken **Konfigurera dina MX-poster** i området **post lådor** på sidan **My Domains** .</span><span class="sxs-lookup"><span data-stu-id="c9bf1-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="c9bf1-153">Välj **annan** från List rutan **din e-postleverantör** .</span><span class="sxs-lookup"><span data-stu-id="c9bf1-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="c9bf1-154">Välj **+ Lägg till ett annat**.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="c9bf1-155">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="c9bf1-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c9bf1-156">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="c9bf1-156">Host Name</span></span> | <span data-ttu-id="c9bf1-157">Pekar på</span><span class="sxs-lookup"><span data-stu-id="c9bf1-157">Points to</span></span> | <span data-ttu-id="c9bf1-158">Ordningen</span><span class="sxs-lookup"><span data-stu-id="c9bf1-158">Priority</span></span> | <span data-ttu-id="c9bf1-159">TTL</span><span class="sxs-lookup"><span data-stu-id="c9bf1-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="c9bf1-160">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="c9bf1-160">Automatically populated</span></span> <br/> | <span data-ttu-id="c9bf1-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c9bf1-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c9bf1-162">**Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="c9bf1-163">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="c9bf1-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="c9bf1-164">siffrorna</span><span class="sxs-lookup"><span data-stu-id="c9bf1-164">0</span></span>  <br/> <span data-ttu-id="c9bf1-165">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="c9bf1-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="c9bf1-166">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-166">1 Hour</span></span>|
   
6. <span data-ttu-id="c9bf1-167">Om det finns andra MX-poster i listan tar du bort dem.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="c9bf1-168">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="c9bf1-169">Välj **OK**i bekräftelse dialog rutan.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c9bf1-170">Lägga till de fem CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9bf1-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c9bf1-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bf1-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="c9bf1-p109">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c9bf1-174">På sidan **My Domains** , i området **Avancerat** , väljer du knappen **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="c9bf1-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c9bf1-175">Välj **+ Lägg till en annan** på raden **CNAME (aliases)** i DNS-redigeraren för varje CNAME-post.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="c9bf1-176">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="c9bf1-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c9bf1-177">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="c9bf1-177">Host Name</span></span> | <span data-ttu-id="c9bf1-178">Pekar på</span><span class="sxs-lookup"><span data-stu-id="c9bf1-178">Points to</span></span> | <span data-ttu-id="c9bf1-179">TTL</span><span class="sxs-lookup"><span data-stu-id="c9bf1-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="c9bf1-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c9bf1-180">autodiscover</span></span>  <br/> |<span data-ttu-id="c9bf1-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c9bf1-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="c9bf1-182">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="c9bf1-183">sip</span><span class="sxs-lookup"><span data-stu-id="c9bf1-183">sip</span></span>  <br/> |<span data-ttu-id="c9bf1-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9bf1-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c9bf1-185">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="c9bf1-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c9bf1-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c9bf1-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9bf1-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="c9bf1-188">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="c9bf1-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c9bf1-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c9bf1-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c9bf1-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="c9bf1-191">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="c9bf1-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c9bf1-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c9bf1-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9bf1-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="c9bf1-194">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="c9bf1-195">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c9bf1-196">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c9bf1-197">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="c9bf1-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c9bf1-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bf1-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9bf1-199">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c9bf1-200">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c9bf1-201">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c9bf1-202">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="c9bf1-203">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c9bf1-204">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9bf1-205">På sidan **My Domains** , i området **Avancerat** , väljer du knappen **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="c9bf1-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c9bf1-206">Välj **+ Lägg till en annan** på raden **txt (text)** i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c9bf1-207">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="c9bf1-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c9bf1-208">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="c9bf1-208">Host Name</span></span> | <span data-ttu-id="c9bf1-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="c9bf1-209">TXT Value</span></span> | <span data-ttu-id="c9bf1-210">TTL</span><span class="sxs-lookup"><span data-stu-id="c9bf1-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="c9bf1-211">[lämna det här blankt]</span><span class="sxs-lookup"><span data-stu-id="c9bf1-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="c9bf1-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c9bf1-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c9bf1-213">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="c9bf1-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="c9bf1-214">TXT</span><span class="sxs-lookup"><span data-stu-id="c9bf1-214">TXT</span></span>  <br/> | <span data-ttu-id="c9bf1-215">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-215">1 Hour</span></span> |
   
5. <span data-ttu-id="c9bf1-216">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c9bf1-217">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c9bf1-218">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9bf1-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c9bf1-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bf1-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="c9bf1-220">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c9bf1-221">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c9bf1-222">På sidan **My Domains** , i området **Avancerat** , väljer du knappen **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="c9bf1-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c9bf1-223">Välj **+ Lägg till ytterligare** i **SRV** -raden i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c9bf1-224">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="c9bf1-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c9bf1-225">Tjänst</span><span class="sxs-lookup"><span data-stu-id="c9bf1-225">Service</span></span> | <span data-ttu-id="c9bf1-226">Protokoll</span><span class="sxs-lookup"><span data-stu-id="c9bf1-226">Protocol</span></span> | <span data-ttu-id="c9bf1-227">Namn</span><span class="sxs-lookup"><span data-stu-id="c9bf1-227">Name</span></span> | <span data-ttu-id="c9bf1-228">Väga</span><span class="sxs-lookup"><span data-stu-id="c9bf1-228">Weight</span></span> | <span data-ttu-id="c9bf1-229">Port</span><span class="sxs-lookup"><span data-stu-id="c9bf1-229">Port</span></span> | <span data-ttu-id="c9bf1-230">Mål</span><span class="sxs-lookup"><span data-stu-id="c9bf1-230">Target</span></span> | <span data-ttu-id="c9bf1-231">Ordningen</span><span class="sxs-lookup"><span data-stu-id="c9bf1-231">Priority</span></span> | <span data-ttu-id="c9bf1-232">TTL</span><span class="sxs-lookup"><span data-stu-id="c9bf1-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="c9bf1-233">sip</span><span class="sxs-lookup"><span data-stu-id="c9bf1-233">sip</span></span>  |<span data-ttu-id="c9bf1-234">tls</span><span class="sxs-lookup"><span data-stu-id="c9bf1-234">tls</span></span>  |<span data-ttu-id="c9bf1-235">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="c9bf1-235">Automatically populated</span></span> |<span data-ttu-id="c9bf1-236">9.1</span><span class="sxs-lookup"><span data-stu-id="c9bf1-236">1</span></span>  |<span data-ttu-id="c9bf1-237">443</span><span class="sxs-lookup"><span data-stu-id="c9bf1-237">443</span></span>   |<span data-ttu-id="c9bf1-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9bf1-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="c9bf1-239">100</span><span class="sxs-lookup"><span data-stu-id="c9bf1-239">100</span></span> |<span data-ttu-id="c9bf1-240">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-240">1 Hour</span></span> |
   |<span data-ttu-id="c9bf1-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="c9bf1-241">sipfed</span></span>|<span data-ttu-id="c9bf1-242">tcp</span><span class="sxs-lookup"><span data-stu-id="c9bf1-242">tcp</span></span> |<span data-ttu-id="c9bf1-243">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="c9bf1-243">Automatically populated</span></span>|<span data-ttu-id="c9bf1-244">9.1</span><span class="sxs-lookup"><span data-stu-id="c9bf1-244">1</span></span> |<span data-ttu-id="c9bf1-245">5061</span><span class="sxs-lookup"><span data-stu-id="c9bf1-245">5061</span></span> |<span data-ttu-id="c9bf1-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9bf1-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="c9bf1-247">100</span><span class="sxs-lookup"><span data-stu-id="c9bf1-247">100</span></span> | <span data-ttu-id="c9bf1-248">1 timme</span><span class="sxs-lookup"><span data-stu-id="c9bf1-248">1 Hour</span></span> |
   
5. <span data-ttu-id="c9bf1-249">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c9bf1-250">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="c9bf1-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c9bf1-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c9bf1-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
