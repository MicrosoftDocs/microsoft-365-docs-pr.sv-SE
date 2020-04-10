---
title: Skapa DNS-poster för Office 365 på Wix
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Wix för Office 365.
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211068"
---
# <a name="create-dns-records-at-wix-for-office-365"></a><span data-ttu-id="9309c-103">Skapa DNS-poster för Office 365 på Wix</span><span class="sxs-lookup"><span data-stu-id="9309c-103">Create DNS records at Wix for Office 365</span></span>

 <span data-ttu-id="9309c-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="9309c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9309c-105">Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="9309c-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9309c-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="9309c-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="9309c-107">[Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="9309c-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="9309c-108">[Lägga till en MX-post så att e-post för din domän kommer till Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="9309c-108">[Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span></span>
    
- <span data-ttu-id="9309c-109">[Lägg till de fem CNAME-poster som krävs för Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="9309c-109">[Add the five CNAME records that are required for Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span></span>
    
- <span data-ttu-id="9309c-110">[Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="9309c-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="9309c-111">[Lägga till de två SRV-posterna som krävs för Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="9309c-111">[Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span></span>
    
<span data-ttu-id="9309c-112">När du har lagt till dessa poster på Wix är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="9309c-112">After you add these records at Wix, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9309c-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9309c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9309c-116">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="9309c-116">Add a TXT record for verification</span></span>
<span data-ttu-id="9309c-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="9309c-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="9309c-p102">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="9309c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9309c-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="9309c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9309c-122">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="9309c-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="9309c-123">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9309c-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9309c-124">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="9309c-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="9309c-125">Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="9309c-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="9309c-126">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9309c-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9309c-127">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="9309c-127">**Host Name**</span></span> <br/> |<span data-ttu-id="9309c-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="9309c-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="9309c-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9309c-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="9309c-130">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="9309c-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="9309c-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9309c-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9309c-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="9309c-132">**Note:** This is an example.</span></span> <span data-ttu-id="9309c-133">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="9309c-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="9309c-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="9309c-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="9309c-135">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="9309c-136">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="9309c-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="9309c-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="9309c-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9309c-138">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="9309c-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9309c-139">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="9309c-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9309c-140">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="9309c-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9309c-141">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="9309c-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="9309c-142">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="9309c-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="9309c-143">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="9309c-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9309c-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9309c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="9309c-147">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="9309c-147">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="9309c-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="9309c-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="9309c-149">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="9309c-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="9309c-150">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9309c-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9309c-151">På sidan **Mina domäner** i området **Postlådor** väljer du länken **Konfigurera MX-poster.**</span><span class="sxs-lookup"><span data-stu-id="9309c-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="9309c-152">Välj **Annat** i listrutan **E-postleverantör.**</span><span class="sxs-lookup"><span data-stu-id="9309c-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="9309c-153">Välj **+ Lägg till en annan**.</span><span class="sxs-lookup"><span data-stu-id="9309c-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="9309c-154">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="9309c-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="9309c-155">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="9309c-155">**Host Name**</span></span>|<span data-ttu-id="9309c-156">**Points to (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="9309c-156">**Points to**</span></span>|<span data-ttu-id="9309c-157">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="9309c-157">**Priority**</span></span>|<span data-ttu-id="9309c-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9309c-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9309c-159">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="9309c-159">Automatically populated</span></span> <br/> | <span data-ttu-id="9309c-160">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9309c-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9309c-161">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="9309c-161">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="9309c-162">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="9309c-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="9309c-163">0</span><span class="sxs-lookup"><span data-stu-id="9309c-163">0</span></span>  <br/> <span data-ttu-id="9309c-164">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span><span class="sxs-lookup"><span data-stu-id="9309c-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="9309c-165">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-165">1 Hour</span></span>|
   
6. <span data-ttu-id="9309c-166">Om det finns några andra MX-poster i listan tar du bort var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="9309c-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="9309c-167">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9309c-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="9309c-168">Välj **OK**i bekräftelsedialogrutan .</span><span class="sxs-lookup"><span data-stu-id="9309c-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="9309c-169">Lägga till de fem CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="9309c-169">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="9309c-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="9309c-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="9309c-p109">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9309c-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9309c-173">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="9309c-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="9309c-174">Välj **+ Lägg till en annan** i raden **CNAME (Alias)** på DNS-redigeraren för varje CNAME-post.</span><span class="sxs-lookup"><span data-stu-id="9309c-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="9309c-175">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="9309c-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="9309c-176">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="9309c-176">**Host Name**</span></span>|<span data-ttu-id="9309c-177">**Pekar på**</span><span class="sxs-lookup"><span data-stu-id="9309c-177">**Points to**</span></span>|<span data-ttu-id="9309c-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9309c-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9309c-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9309c-179">autodiscover</span></span>  <br/> |<span data-ttu-id="9309c-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9309c-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="9309c-181">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="9309c-182">sip</span><span class="sxs-lookup"><span data-stu-id="9309c-182">sip</span></span>  <br/> |<span data-ttu-id="9309c-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9309c-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9309c-184">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="9309c-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9309c-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9309c-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9309c-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="9309c-187">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="9309c-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9309c-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9309c-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9309c-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="9309c-190">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="9309c-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9309c-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9309c-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9309c-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="9309c-193">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="9309c-194">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="9309c-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="9309c-195">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="9309c-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9309c-196">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="9309c-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9309c-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="9309c-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9309c-198">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="9309c-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9309c-199">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="9309c-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9309c-200">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="9309c-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="9309c-201">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="9309c-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="9309c-202">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="9309c-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="9309c-203">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9309c-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9309c-204">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="9309c-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="9309c-205">Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="9309c-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="9309c-206">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="9309c-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="9309c-207">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="9309c-207">**Host Name**</span></span>|<span data-ttu-id="9309c-208">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="9309c-208">**TXT Value**</span></span>|<span data-ttu-id="9309c-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9309c-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9309c-210">[lämna det här blankt]</span><span class="sxs-lookup"><span data-stu-id="9309c-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="9309c-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9309c-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9309c-212">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="9309c-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="9309c-213">TXT</span><span class="sxs-lookup"><span data-stu-id="9309c-213">TXT</span></span>  <br/> | <span data-ttu-id="9309c-214">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-214">1 Hour</span></span> |
   
5. <span data-ttu-id="9309c-215">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="9309c-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="9309c-216">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="9309c-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="9309c-217">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="9309c-217">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="9309c-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="9309c-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="9309c-219">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="9309c-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="9309c-220">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9309c-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9309c-221">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="9309c-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="9309c-222">Välj **+ Lägg till en annan** i **SRV-raden** i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="9309c-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="9309c-223">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="9309c-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="9309c-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="9309c-224">**Service**</span></span>|<span data-ttu-id="9309c-225">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="9309c-225">**Protocol**</span></span>|<span data-ttu-id="9309c-226">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="9309c-226">**Name**</span></span>|<span data-ttu-id="9309c-227">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="9309c-227">**Weight**</span></span>|<span data-ttu-id="9309c-228">**Port**</span><span class="sxs-lookup"><span data-stu-id="9309c-228">**Port**</span></span>|<span data-ttu-id="9309c-229">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="9309c-229">**Target**</span></span>|<span data-ttu-id="9309c-230">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="9309c-230">**Priority**</span></span>|<span data-ttu-id="9309c-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9309c-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9309c-232">sip</span><span class="sxs-lookup"><span data-stu-id="9309c-232">sip</span></span>  |<span data-ttu-id="9309c-233">tls</span><span class="sxs-lookup"><span data-stu-id="9309c-233">tls</span></span>  |<span data-ttu-id="9309c-234">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="9309c-234">Automatically populated</span></span> |<span data-ttu-id="9309c-235">1</span><span class="sxs-lookup"><span data-stu-id="9309c-235">1</span></span>  |<span data-ttu-id="9309c-236">443</span><span class="sxs-lookup"><span data-stu-id="9309c-236">443</span></span>   |<span data-ttu-id="9309c-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9309c-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="9309c-238">100</span><span class="sxs-lookup"><span data-stu-id="9309c-238">100</span></span> |<span data-ttu-id="9309c-239">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-239">1 Hour</span></span> |
|<span data-ttu-id="9309c-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="9309c-240">sipfed</span></span>|<span data-ttu-id="9309c-241">tcp</span><span class="sxs-lookup"><span data-stu-id="9309c-241">tcp</span></span> |<span data-ttu-id="9309c-242">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="9309c-242">Automatically populated</span></span>|<span data-ttu-id="9309c-243">1</span><span class="sxs-lookup"><span data-stu-id="9309c-243">1</span></span> |<span data-ttu-id="9309c-244">5061</span><span class="sxs-lookup"><span data-stu-id="9309c-244">5061</span></span> |<span data-ttu-id="9309c-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9309c-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="9309c-246">100</span><span class="sxs-lookup"><span data-stu-id="9309c-246">100</span></span> | <span data-ttu-id="9309c-247">1 timme</span><span class="sxs-lookup"><span data-stu-id="9309c-247">1 Hour</span></span> |
   
5. <span data-ttu-id="9309c-248">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="9309c-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="9309c-249">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="9309c-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="9309c-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9309c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

