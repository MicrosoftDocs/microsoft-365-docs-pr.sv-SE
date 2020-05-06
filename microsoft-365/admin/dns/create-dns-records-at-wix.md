---
title: Skapa DNS-poster på Wix för Microsoft
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Wix för Microsoft.
ms.openlocfilehash: 6f88cc65ae19f747a9fc3740ea1578f30d18b5e2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048861"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="a2880-103">Skapa DNS-poster på Wix för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2880-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="a2880-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="a2880-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a2880-105">Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="a2880-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a2880-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="a2880-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="a2880-107">[Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="a2880-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="a2880-108">[Lägg till en MX-post så att e-post för din domän kommer till Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="a2880-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="a2880-109">[Lägg till de fem CNAME-poster som krävs för Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="a2880-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="a2880-110">[Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="a2880-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="a2880-111">[Lägg till de två SRV-poster som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="a2880-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="a2880-112">När du har lagt till dessa poster på Wix konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="a2880-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a2880-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a2880-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a2880-116">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="a2880-116">Add a TXT record for verification</span></span>
<span data-ttu-id="a2880-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="a2880-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="a2880-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="a2880-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2880-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="a2880-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a2880-122">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a2880-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a2880-123">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a2880-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a2880-124">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="a2880-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="a2880-125">Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="a2880-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="a2880-126">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a2880-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a2880-127">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="a2880-127">**Host Name**</span></span> <br/> |<span data-ttu-id="a2880-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="a2880-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="a2880-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a2880-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="a2880-130">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="a2880-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="a2880-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a2880-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a2880-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="a2880-132">**Note:** This is an example.</span></span> <span data-ttu-id="a2880-133">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="a2880-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="a2880-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="a2880-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="a2880-135">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="a2880-136">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="a2880-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="a2880-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="a2880-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a2880-138">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="a2880-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a2880-139">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="a2880-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a2880-140">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="a2880-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a2880-141">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="a2880-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="a2880-142">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="a2880-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="a2880-143">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="a2880-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a2880-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a2880-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a2880-147">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2880-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a2880-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="a2880-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="a2880-149">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a2880-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a2880-150">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a2880-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a2880-151">På sidan **Mina domäner** i området **Postlådor** väljer du länken **Konfigurera MX-poster.**</span><span class="sxs-lookup"><span data-stu-id="a2880-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="a2880-152">Välj **Annat** i listrutan **E-postleverantör.**</span><span class="sxs-lookup"><span data-stu-id="a2880-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="a2880-153">Välj **+ Lägg till en annan**.</span><span class="sxs-lookup"><span data-stu-id="a2880-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="a2880-154">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a2880-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="a2880-155">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="a2880-155">**Host Name**</span></span>|<span data-ttu-id="a2880-156">**Points to (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="a2880-156">**Points to**</span></span>|<span data-ttu-id="a2880-157">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="a2880-157">**Priority**</span></span>|<span data-ttu-id="a2880-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a2880-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a2880-159">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="a2880-159">Automatically populated</span></span> <br/> | <span data-ttu-id="a2880-160">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a2880-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a2880-161">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="a2880-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="a2880-162">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="a2880-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="a2880-163">0</span><span class="sxs-lookup"><span data-stu-id="a2880-163">0</span></span>  <br/> <span data-ttu-id="a2880-164">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="a2880-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="a2880-165">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-165">1 Hour</span></span>|
   
6. <span data-ttu-id="a2880-166">Om det finns några andra MX-poster i listan tar du bort var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="a2880-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="a2880-167">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2880-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="a2880-168">Välj **OK**i bekräftelsedialogrutan .</span><span class="sxs-lookup"><span data-stu-id="a2880-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a2880-169">Lägga till de fem CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2880-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a2880-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="a2880-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="a2880-p109">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a2880-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="a2880-173">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="a2880-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="a2880-174">Välj **+ Lägg till en annan** i raden **CNAME (Alias)** på DNS-redigeraren för varje CNAME-post.</span><span class="sxs-lookup"><span data-stu-id="a2880-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="a2880-175">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a2880-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="a2880-176">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="a2880-176">**Host Name**</span></span>|<span data-ttu-id="a2880-177">**Pekar på**</span><span class="sxs-lookup"><span data-stu-id="a2880-177">**Points to**</span></span>|<span data-ttu-id="a2880-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a2880-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2880-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a2880-179">autodiscover</span></span>  <br/> |<span data-ttu-id="a2880-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a2880-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="a2880-181">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="a2880-182">sip</span><span class="sxs-lookup"><span data-stu-id="a2880-182">sip</span></span>  <br/> |<span data-ttu-id="a2880-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a2880-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a2880-184">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="a2880-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a2880-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a2880-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a2880-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="a2880-187">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="a2880-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a2880-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a2880-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a2880-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="a2880-190">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="a2880-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a2880-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a2880-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a2880-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="a2880-193">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="a2880-194">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="a2880-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="a2880-195">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="a2880-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a2880-196">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="a2880-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a2880-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="a2880-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2880-198">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="a2880-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a2880-199">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="a2880-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a2880-200">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2880-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a2880-201">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="a2880-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="a2880-202">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a2880-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a2880-203">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a2880-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a2880-204">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="a2880-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="a2880-205">Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="a2880-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="a2880-206">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a2880-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="a2880-207">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="a2880-207">**Host Name**</span></span>|<span data-ttu-id="a2880-208">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="a2880-208">**TXT Value**</span></span>|<span data-ttu-id="a2880-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a2880-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2880-210">[lämna det här blankt]</span><span class="sxs-lookup"><span data-stu-id="a2880-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="a2880-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a2880-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a2880-212">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="a2880-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="a2880-213">TXT</span><span class="sxs-lookup"><span data-stu-id="a2880-213">TXT</span></span>  <br/> | <span data-ttu-id="a2880-214">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-214">1 Hour</span></span> |
   
5. <span data-ttu-id="a2880-215">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="a2880-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="a2880-216">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="a2880-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a2880-217">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2880-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a2880-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="a2880-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="a2880-219">Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="a2880-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="a2880-220">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a2880-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a2880-221">Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.**</span><span class="sxs-lookup"><span data-stu-id="a2880-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="a2880-222">Välj **+ Lägg till en annan** i **SRV-raden** i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="a2880-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="a2880-223">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a2880-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="a2880-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="a2880-224">**Service**</span></span>|<span data-ttu-id="a2880-225">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="a2880-225">**Protocol**</span></span>|<span data-ttu-id="a2880-226">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="a2880-226">**Name**</span></span>|<span data-ttu-id="a2880-227">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="a2880-227">**Weight**</span></span>|<span data-ttu-id="a2880-228">**Port**</span><span class="sxs-lookup"><span data-stu-id="a2880-228">**Port**</span></span>|<span data-ttu-id="a2880-229">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="a2880-229">**Target**</span></span>|<span data-ttu-id="a2880-230">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="a2880-230">**Priority**</span></span>|<span data-ttu-id="a2880-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a2880-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a2880-232">sip</span><span class="sxs-lookup"><span data-stu-id="a2880-232">sip</span></span>  |<span data-ttu-id="a2880-233">tls</span><span class="sxs-lookup"><span data-stu-id="a2880-233">tls</span></span>  |<span data-ttu-id="a2880-234">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="a2880-234">Automatically populated</span></span> |<span data-ttu-id="a2880-235">1</span><span class="sxs-lookup"><span data-stu-id="a2880-235">1</span></span>  |<span data-ttu-id="a2880-236">443</span><span class="sxs-lookup"><span data-stu-id="a2880-236">443</span></span>   |<span data-ttu-id="a2880-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a2880-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="a2880-238">100</span><span class="sxs-lookup"><span data-stu-id="a2880-238">100</span></span> |<span data-ttu-id="a2880-239">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-239">1 Hour</span></span> |
|<span data-ttu-id="a2880-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="a2880-240">sipfed</span></span>|<span data-ttu-id="a2880-241">tcp</span><span class="sxs-lookup"><span data-stu-id="a2880-241">tcp</span></span> |<span data-ttu-id="a2880-242">Fylls i automatiskt</span><span class="sxs-lookup"><span data-stu-id="a2880-242">Automatically populated</span></span>|<span data-ttu-id="a2880-243">1</span><span class="sxs-lookup"><span data-stu-id="a2880-243">1</span></span> |<span data-ttu-id="a2880-244">5061</span><span class="sxs-lookup"><span data-stu-id="a2880-244">5061</span></span> |<span data-ttu-id="a2880-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a2880-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="a2880-246">100</span><span class="sxs-lookup"><span data-stu-id="a2880-246">100</span></span> | <span data-ttu-id="a2880-247">1 timme</span><span class="sxs-lookup"><span data-stu-id="a2880-247">1 Hour</span></span> |
   
5. <span data-ttu-id="a2880-248">Välj knappen **Spara DNS** högst upp i DNS-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="a2880-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="a2880-249">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="a2880-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="a2880-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a2880-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

