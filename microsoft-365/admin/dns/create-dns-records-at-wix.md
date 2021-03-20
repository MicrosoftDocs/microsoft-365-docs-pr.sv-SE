---
title: Skapa DNS-poster på Wix för Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster hos Wix för Microsoft.
ms.openlocfilehash: 3ec2ea0dc24e1872ba22e591fae96b39a9a0deee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916112"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="16980-103">Skapa DNS-poster på Wix för Microsoft</span><span class="sxs-lookup"><span data-stu-id="16980-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="16980-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="16980-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="16980-105">Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="16980-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="16980-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="16980-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="16980-107">[Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="16980-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="16980-108">[Lägg till en MX-post så att e-post för din domän kommer till Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="16980-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="16980-109">[Lägg till de fem CNAME-posterna som krävs för Microsoft.](#add-the-five-cname-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="16980-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="16980-110">[Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="16980-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="16980-111">[Lägg till de två SRV-posterna som krävs för Microsoft.](#add-the-two-srv-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="16980-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="16980-112">När du har lagt till dessa poster på Wix är domänen konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="16980-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="16980-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16980-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="16980-116">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="16980-116">Add a TXT record for verification</span></span>
<span data-ttu-id="16980-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="16980-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="16980-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="16980-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16980-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="16980-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="16980-122">WIX stöder inte DNS-poster för underdomäner.</span><span class="sxs-lookup"><span data-stu-id="16980-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="16980-123">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="16980-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="16980-124">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16980-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="16980-125">Välj **knappen Edit** DNS (redigera **DNS) i** området Advanced **(avancerat) på sidan My** Domains (mina domäner).</span><span class="sxs-lookup"><span data-stu-id="16980-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="16980-126">Välj **+ Add another (lägg** till ytterligare en) på raden TXT **(Text)** i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="16980-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="16980-127">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="16980-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="16980-128">Host Name</span><span class="sxs-lookup"><span data-stu-id="16980-128">Host Name</span></span> <br/> | <span data-ttu-id="16980-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="16980-129">TXT Value</span></span> <br/> | <span data-ttu-id="16980-130">TTL</span><span class="sxs-lookup"><span data-stu-id="16980-130">TTL</span></span> <br/> |
   |<span data-ttu-id="16980-131">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="16980-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="16980-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="16980-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="16980-133">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="16980-133">**Note:** This is an example.</span></span> <span data-ttu-id="16980-134">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="16980-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="16980-135">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="16980-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="16980-136">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="16980-137">Välj knappen Save DNS (spara **DNS)** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="16980-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="16980-138">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="16980-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="16980-139">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="16980-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="16980-140">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="16980-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="16980-141">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="16980-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="16980-142">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="16980-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="16980-143">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="16980-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="16980-144">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="16980-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="16980-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16980-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="16980-148">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16980-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="16980-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="16980-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="16980-150">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="16980-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="16980-151">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16980-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="16980-152">På sidan **My Domains,** i området **Mailboxes,** väljer du **länken Configure your MX records.**</span><span class="sxs-lookup"><span data-stu-id="16980-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="16980-153">Välj **Annat** i **listrutan Din** e-postleverantör.</span><span class="sxs-lookup"><span data-stu-id="16980-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="16980-154">Välj **+ Add another (lägg till ytterligare en).**</span><span class="sxs-lookup"><span data-stu-id="16980-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="16980-155">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="16980-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="16980-156">Host Name</span><span class="sxs-lookup"><span data-stu-id="16980-156">Host Name</span></span> | <span data-ttu-id="16980-157">Pekar på</span><span class="sxs-lookup"><span data-stu-id="16980-157">Points to</span></span> | <span data-ttu-id="16980-158">Prioritet</span><span class="sxs-lookup"><span data-stu-id="16980-158">Priority</span></span> | <span data-ttu-id="16980-159">TTL</span><span class="sxs-lookup"><span data-stu-id="16980-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="16980-160">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="16980-160">Automatically populated</span></span> <br/> | <span data-ttu-id="16980-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="16980-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="16980-162">**Obs!** Skaffa ditt  *\<domain-key\>*  Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="16980-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="16980-163">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="16980-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="16980-164">0</span><span class="sxs-lookup"><span data-stu-id="16980-164">0</span></span>  <br/> <span data-ttu-id="16980-165">Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="16980-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> | <span data-ttu-id="16980-166">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-166">1 Hour</span></span>|
   
6. <span data-ttu-id="16980-167">Om det finns andra MX-poster tar du bort dem.</span><span class="sxs-lookup"><span data-stu-id="16980-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="16980-168">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="16980-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="16980-169">Välj OK i **bekräftelsedialogrutan.**</span><span class="sxs-lookup"><span data-stu-id="16980-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="16980-170">Lägg till de fem CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="16980-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="16980-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="16980-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="16980-p109">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16980-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="16980-174">Välj **knappen Edit** DNS (redigera **DNS) i** området Advanced **(avancerat) på sidan My** Domains (mina domäner).</span><span class="sxs-lookup"><span data-stu-id="16980-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="16980-175">Välj **+ Add another (lägg** till ytterligare **en) på raden CNAME (Aliases)** i DNS-redigeraren för varje CNAME-post.</span><span class="sxs-lookup"><span data-stu-id="16980-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="16980-176">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="16980-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="16980-177">Host Name</span><span class="sxs-lookup"><span data-stu-id="16980-177">Host Name</span></span> | <span data-ttu-id="16980-178">Pekar på</span><span class="sxs-lookup"><span data-stu-id="16980-178">Points to</span></span> | <span data-ttu-id="16980-179">TTL</span><span class="sxs-lookup"><span data-stu-id="16980-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="16980-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="16980-180">autodiscover</span></span>  <br/> |<span data-ttu-id="16980-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="16980-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="16980-182">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="16980-183">sip</span><span class="sxs-lookup"><span data-stu-id="16980-183">sip</span></span>  <br/> |<span data-ttu-id="16980-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16980-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="16980-185">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="16980-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="16980-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="16980-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16980-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="16980-188">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="16980-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="16980-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="16980-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="16980-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="16980-191">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="16980-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="16980-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="16980-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="16980-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="16980-194">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="16980-195">Välj knappen Save DNS (spara **DNS)** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="16980-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="16980-196">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="16980-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="16980-197">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="16980-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="16980-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="16980-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="16980-199">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="16980-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="16980-200">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="16980-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="16980-201">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16980-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="16980-202">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="16980-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="16980-203">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="16980-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="16980-204">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16980-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="16980-205">Välj **knappen Edit** DNS (redigera **DNS) i** området Advanced **(avancerat) på sidan My** Domains (mina domäner).</span><span class="sxs-lookup"><span data-stu-id="16980-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="16980-206">Välj **+ Add another (lägg** till ytterligare en) på raden TXT **(Text)** i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="16980-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="16980-207">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="16980-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="16980-208">Host Name</span><span class="sxs-lookup"><span data-stu-id="16980-208">Host Name</span></span> | <span data-ttu-id="16980-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="16980-209">TXT Value</span></span> | <span data-ttu-id="16980-210">TTL</span><span class="sxs-lookup"><span data-stu-id="16980-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="16980-211">[lämna det här blankt]</span><span class="sxs-lookup"><span data-stu-id="16980-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="16980-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="16980-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="16980-213">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="16980-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="16980-214">TXT</span><span class="sxs-lookup"><span data-stu-id="16980-214">TXT</span></span>  <br/> | <span data-ttu-id="16980-215">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-215">1 Hour</span></span> |
   
5. <span data-ttu-id="16980-216">Välj knappen Save DNS (spara **DNS)** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="16980-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="16980-217">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="16980-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="16980-218">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="16980-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="16980-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="16980-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="16980-220">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="16980-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="16980-221">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16980-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="16980-222">Välj **knappen Edit** DNS (redigera **DNS) i** området Advanced **(avancerat) på sidan My** Domains (mina domäner).</span><span class="sxs-lookup"><span data-stu-id="16980-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="16980-223">Välj **+ Add another (lägg** till ytterligare **en) på raden SRV** i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="16980-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="16980-224">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="16980-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="16980-225">Tjänst</span><span class="sxs-lookup"><span data-stu-id="16980-225">Service</span></span> | <span data-ttu-id="16980-226">Protokoll</span><span class="sxs-lookup"><span data-stu-id="16980-226">Protocol</span></span> | <span data-ttu-id="16980-227">Namn</span><span class="sxs-lookup"><span data-stu-id="16980-227">Name</span></span> | <span data-ttu-id="16980-228">Vikt</span><span class="sxs-lookup"><span data-stu-id="16980-228">Weight</span></span> | <span data-ttu-id="16980-229">Port</span><span class="sxs-lookup"><span data-stu-id="16980-229">Port</span></span> | <span data-ttu-id="16980-230">Mål</span><span class="sxs-lookup"><span data-stu-id="16980-230">Target</span></span> | <span data-ttu-id="16980-231">Prioritet</span><span class="sxs-lookup"><span data-stu-id="16980-231">Priority</span></span> | <span data-ttu-id="16980-232">TTL</span><span class="sxs-lookup"><span data-stu-id="16980-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="16980-233">sip</span><span class="sxs-lookup"><span data-stu-id="16980-233">sip</span></span>  |<span data-ttu-id="16980-234">tls</span><span class="sxs-lookup"><span data-stu-id="16980-234">tls</span></span>  |<span data-ttu-id="16980-235">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="16980-235">Automatically populated</span></span> |<span data-ttu-id="16980-236">1</span><span class="sxs-lookup"><span data-stu-id="16980-236">1</span></span>  |<span data-ttu-id="16980-237">443</span><span class="sxs-lookup"><span data-stu-id="16980-237">443</span></span>   |<span data-ttu-id="16980-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16980-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="16980-239">100</span><span class="sxs-lookup"><span data-stu-id="16980-239">100</span></span> |<span data-ttu-id="16980-240">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-240">1 Hour</span></span> |
   |<span data-ttu-id="16980-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="16980-241">sipfed</span></span>|<span data-ttu-id="16980-242">tcp</span><span class="sxs-lookup"><span data-stu-id="16980-242">tcp</span></span> |<span data-ttu-id="16980-243">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="16980-243">Automatically populated</span></span>|<span data-ttu-id="16980-244">1</span><span class="sxs-lookup"><span data-stu-id="16980-244">1</span></span> |<span data-ttu-id="16980-245">5061</span><span class="sxs-lookup"><span data-stu-id="16980-245">5061</span></span> |<span data-ttu-id="16980-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16980-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="16980-247">100</span><span class="sxs-lookup"><span data-stu-id="16980-247">100</span></span> | <span data-ttu-id="16980-248">1 timme</span><span class="sxs-lookup"><span data-stu-id="16980-248">1 Hour</span></span> |
   
5. <span data-ttu-id="16980-249">Välj knappen Save DNS (spara **DNS)** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="16980-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="16980-250">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="16980-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="16980-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16980-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
