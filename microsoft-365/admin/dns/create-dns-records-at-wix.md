---
title: Skapa DNS-poster för Office 365 på Wix
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Wix för Office 365.
ms.openlocfilehash: 43d2f2417153dd0c848c33736733237b1681c02c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807540"
---
# <a name="create-dns-records-at-wix-for-office-365"></a><span data-ttu-id="eb857-103">Skapa DNS-poster för Office 365 på Wix</span><span class="sxs-lookup"><span data-stu-id="eb857-103">Create DNS records at Wix for Office 365</span></span>

 <span data-ttu-id="eb857-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="eb857-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="eb857-105">Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="eb857-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="eb857-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="eb857-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="eb857-107">[Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="eb857-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="eb857-108">[Lägga till en MX-post så att e-post för din domän kommer till Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="eb857-108">[Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span></span>
    
- <span data-ttu-id="eb857-109">[Lägg till de fem CNAME-poster som krävs för Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="eb857-109">[Add the five CNAME records that are required for Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span></span>
    
- <span data-ttu-id="eb857-110">[Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="eb857-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="eb857-111">[Lägga till de två SRV-posterna som krävs för Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="eb857-111">[Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span></span>
    
<span data-ttu-id="eb857-112">När du har lagt till dessa poster på Wix är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="eb857-112">After you add these records at Wix, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="eb857-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eb857-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="eb857-116">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="eb857-116">Add a TXT record for verification</span></span>
<span data-ttu-id="eb857-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="eb857-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="eb857-p102">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="eb857-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb857-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="eb857-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="eb857-122">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="eb857-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="eb857-123">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eb857-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eb857-124">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="eb857-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="eb857-125">Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="eb857-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="eb857-126">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="eb857-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="eb857-127">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="eb857-127">**Host Name**</span></span> <br/> |<span data-ttu-id="eb857-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="eb857-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="eb857-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eb857-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="eb857-130">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="eb857-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="eb857-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="eb857-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="eb857-132">**Anm.:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="eb857-132">**Note:** This is an example.</span></span> <span data-ttu-id="eb857-133">Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb857-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="eb857-134">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="eb857-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="eb857-135">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="eb857-136">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="eb857-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="eb857-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="eb857-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="eb857-138">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="eb857-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="eb857-139">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="eb857-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="eb857-140">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="eb857-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="eb857-141">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="eb857-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="eb857-142">Välj **Starta inställningar**på sidan **Inställningar** .</span><span class="sxs-lookup"><span data-stu-id="eb857-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="eb857-143">På sidan **Verifiera domän** väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="eb857-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="eb857-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eb857-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="eb857-147">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="eb857-147">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="eb857-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="eb857-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="eb857-149">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="eb857-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="eb857-150">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eb857-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eb857-151">På sidan **Mina domäner** i området **Postlådor** väljer du länken **Konfigurera MX-poster.**</span><span class="sxs-lookup"><span data-stu-id="eb857-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="eb857-152">Välj **Annat** i listrutan **E-postleverantör.**</span><span class="sxs-lookup"><span data-stu-id="eb857-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="eb857-153">Välj **+ Lägg till en annan**.</span><span class="sxs-lookup"><span data-stu-id="eb857-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="eb857-154">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="eb857-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="eb857-155">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="eb857-155">**Host Name**</span></span>|<span data-ttu-id="eb857-156">**Points to (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="eb857-156">**Points to**</span></span>|<span data-ttu-id="eb857-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="eb857-157">**Priority**</span></span>|<span data-ttu-id="eb857-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eb857-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb857-159">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="eb857-159">Automatically populated</span></span> <br/> | <span data-ttu-id="eb857-160">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eb857-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="eb857-161">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="eb857-161">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="eb857-162">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="eb857-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="eb857-163">0</span><span class="sxs-lookup"><span data-stu-id="eb857-163">0</span></span>  <br/> <span data-ttu-id="eb857-164">[Mer information om prioritet finns i ](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="eb857-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="eb857-165">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-165">1 Hour</span></span>|
   
6. <span data-ttu-id="eb857-166">Om det finns några andra MX-poster i listan tar du bort var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="eb857-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="eb857-167">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb857-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="eb857-168">Välj **OK**i bekräftelsedialogrutan .</span><span class="sxs-lookup"><span data-stu-id="eb857-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="eb857-169">Lägga till de fem CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="eb857-169">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="eb857-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="eb857-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="eb857-p109">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eb857-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="eb857-173">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="eb857-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="eb857-174">Välj **+ Lägg till en annan** i raden **CNAME (Alias)** på DNS-redigeraren för varje CNAME-post.</span><span class="sxs-lookup"><span data-stu-id="eb857-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="eb857-175">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="eb857-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="eb857-176">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="eb857-176">**Host Name**</span></span>|<span data-ttu-id="eb857-177">**Points to (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="eb857-177">**Points to**</span></span>|<span data-ttu-id="eb857-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eb857-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eb857-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eb857-179">autodiscover</span></span>  <br/> |<span data-ttu-id="eb857-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eb857-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="eb857-181">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="eb857-182">sip</span><span class="sxs-lookup"><span data-stu-id="eb857-182">sip</span></span>  <br/> |<span data-ttu-id="eb857-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb857-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="eb857-184">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="eb857-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eb857-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="eb857-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb857-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="eb857-187">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="eb857-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="eb857-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="eb857-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="eb857-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="eb857-190">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="eb857-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="eb857-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="eb857-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="eb857-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="eb857-193">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="eb857-194">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="eb857-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="eb857-195">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="eb857-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="eb857-196">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="eb857-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="eb857-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="eb857-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb857-198">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="eb857-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="eb857-199">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="eb857-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="eb857-200">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb857-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="eb857-201">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="eb857-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="eb857-202">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="eb857-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="eb857-203">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eb857-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eb857-204">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="eb857-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="eb857-205">Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="eb857-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="eb857-206">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="eb857-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="eb857-207">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="eb857-207">**Host Name**</span></span>|<span data-ttu-id="eb857-208">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="eb857-208">**TXT Value**</span></span>|<span data-ttu-id="eb857-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eb857-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eb857-210">[lämna det här blankt]</span><span class="sxs-lookup"><span data-stu-id="eb857-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="eb857-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="eb857-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="eb857-212">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="eb857-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="eb857-213">TXT</span><span class="sxs-lookup"><span data-stu-id="eb857-213">TXT</span></span>  <br/> | <span data-ttu-id="eb857-214">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-214">1 Hour</span></span> |
   
5. <span data-ttu-id="eb857-215">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="eb857-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="eb857-216">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="eb857-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="eb857-217">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="eb857-217">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="eb857-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="eb857-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="eb857-219">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="eb857-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="eb857-220">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eb857-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eb857-221">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="eb857-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="eb857-222">Välj **+ Lägg till en annan** i **SRV-raden** i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="eb857-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="eb857-223">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="eb857-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="eb857-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="eb857-224">**Service**</span></span>|<span data-ttu-id="eb857-225">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="eb857-225">**Protocol**</span></span>|<span data-ttu-id="eb857-226">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="eb857-226">**Name**</span></span>|<span data-ttu-id="eb857-227">**Weight**</span><span class="sxs-lookup"><span data-stu-id="eb857-227">**Weight**</span></span>|<span data-ttu-id="eb857-228">**Port**</span><span class="sxs-lookup"><span data-stu-id="eb857-228">**Port**</span></span>|<span data-ttu-id="eb857-229">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="eb857-229">**Target**</span></span>|<span data-ttu-id="eb857-230">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="eb857-230">**Priority**</span></span>|<span data-ttu-id="eb857-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eb857-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb857-232">sip</span><span class="sxs-lookup"><span data-stu-id="eb857-232">sip</span></span>  |<span data-ttu-id="eb857-233">tls</span><span class="sxs-lookup"><span data-stu-id="eb857-233">tls</span></span>  |<span data-ttu-id="eb857-234">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="eb857-234">Automatically populated</span></span> |<span data-ttu-id="eb857-235">1</span><span class="sxs-lookup"><span data-stu-id="eb857-235">1</span></span>  |<span data-ttu-id="eb857-236">443</span><span class="sxs-lookup"><span data-stu-id="eb857-236">443</span></span>   |<span data-ttu-id="eb857-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb857-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="eb857-238">100</span><span class="sxs-lookup"><span data-stu-id="eb857-238">100</span></span> |<span data-ttu-id="eb857-239">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-239">1 Hour</span></span> |
|<span data-ttu-id="eb857-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="eb857-240">sipfed</span></span>|<span data-ttu-id="eb857-241">tcp</span><span class="sxs-lookup"><span data-stu-id="eb857-241">tcp</span></span> |<span data-ttu-id="eb857-242">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="eb857-242">Automatically populated</span></span>|<span data-ttu-id="eb857-243">1</span><span class="sxs-lookup"><span data-stu-id="eb857-243">1</span></span> |<span data-ttu-id="eb857-244">5061</span><span class="sxs-lookup"><span data-stu-id="eb857-244">5061</span></span> |<span data-ttu-id="eb857-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb857-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="eb857-246">100</span><span class="sxs-lookup"><span data-stu-id="eb857-246">100</span></span> | <span data-ttu-id="eb857-247">1 timme</span><span class="sxs-lookup"><span data-stu-id="eb857-247">1 Hour</span></span> |
   
5. <span data-ttu-id="eb857-248">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="eb857-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="eb857-249">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="eb857-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="eb857-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eb857-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

