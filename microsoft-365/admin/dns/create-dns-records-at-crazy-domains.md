---
title: Skapa DNS-poster på Crazy Domains för Microsoft
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Crazy Domains för Microsoft.
ms.openlocfilehash: 425ecfa6f8b6c4085bdffb3d2701008ecb895b84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910468"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="df400-103">Skapa DNS-poster på Crazy Domains för Microsoft</span><span class="sxs-lookup"><span data-stu-id="df400-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="df400-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="df400-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="df400-105">Om Crazy Domains är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="df400-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="df400-106">När du har lagt till dessa poster på Crazy Domains är domänen konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="df400-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="df400-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df400-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="df400-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="df400-110">Add a TXT record for verification</span></span>
<span data-ttu-id="df400-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="df400-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="df400-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="df400-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df400-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="df400-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="df400-p104">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="df400-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="df400-119">I avsnittet **Mitt konto** väljer du **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="df400-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="df400-121">På **sidan Domain Names** går du till **avsnittet** Domain och väljer namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="df400-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="df400-123">I avsnittet **DNS Settings** väljer du ikonen för listrutan.</span><span class="sxs-lookup"><span data-stu-id="df400-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="df400-125">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="df400-125">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="df400-127">Välj **TXT Record** i listrutan **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="df400-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="df400-129">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="df400-129">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="df400-131">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="df400-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="df400-132">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="df400-132">**Sub Domain**</span></span>|<span data-ttu-id="df400-133">**Textpost**</span><span class="sxs-lookup"><span data-stu-id="df400-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="df400-134">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="df400-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="df400-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="df400-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="df400-136">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="df400-136">**Note:** This is an example.</span></span> <span data-ttu-id="df400-137">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="df400-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="df400-138">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="df400-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="df400-140">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="df400-140">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="df400-142">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="df400-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="df400-143">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="df400-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="df400-144">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="df400-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="df400-145">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="df400-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="df400-146">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="df400-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="df400-147">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="df400-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="df400-148">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="df400-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="df400-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df400-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="df400-152">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df400-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="df400-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="df400-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="df400-p107">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="df400-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="df400-157">I avsnittet **Mitt konto** väljer du **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="df400-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="df400-159">På **sidan Domain Names** går du till **avsnittet** Domain och väljer namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="df400-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="df400-161">I avsnittet **DNS Settings** väljer du ikonen för listrutan.</span><span class="sxs-lookup"><span data-stu-id="df400-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="df400-163">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="df400-163">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="df400-165">Välj **MX Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="df400-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="df400-167">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="df400-167">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="df400-169">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="df400-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="df400-170">(Välj **värdet Priority** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="df400-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="df400-171">**Mail for Zone**</span><span class="sxs-lookup"><span data-stu-id="df400-171">**Mail For Zone**</span></span>|<span data-ttu-id="df400-172">**Priority**</span><span class="sxs-lookup"><span data-stu-id="df400-172">**Priority**</span></span>|<span data-ttu-id="df400-173">**Assigned To Server**</span><span class="sxs-lookup"><span data-stu-id="df400-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="df400-174">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="df400-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="df400-175">1</span><span class="sxs-lookup"><span data-stu-id="df400-175">1</span></span>  <br/> <span data-ttu-id="df400-176">Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="df400-176">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="df400-177">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df400-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="df400-178">**Obs!** Skaffa ditt  *\<domain-key\>*  Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="df400-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="df400-179">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="df400-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="df400-181">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="df400-181">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="df400-183">Om det finns andra MX-poster i avsnittet **MX Record väljer** du Modify **för** en av dessa poster.</span><span class="sxs-lookup"><span data-stu-id="df400-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="df400-185">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="df400-185">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="df400-187">Bekräfta **borttagningen** genom att välja Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="df400-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="df400-189">Använd samma sätt för att ta bort andra MX-poster i listan tills endast den du lade till tidigare i den här proceduren finns kvar.</span><span class="sxs-lookup"><span data-stu-id="df400-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="df400-190">Lägg till de sex CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="df400-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="df400-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="df400-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="df400-p109">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="df400-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="df400-195">I avsnittet **Mitt konto** väljer du **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="df400-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="df400-197">På **sidan Domain Names** går du till **avsnittet** Domain och väljer namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="df400-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="df400-199">I avsnittet **DNS Settings** väljer du ikonen för listrutan.</span><span class="sxs-lookup"><span data-stu-id="df400-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="df400-201">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="df400-201">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="df400-203">Välj **CNAME Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="df400-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="df400-205">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="df400-205">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="df400-207">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="df400-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="df400-208">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="df400-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="df400-209">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="df400-209">**Sub Domain**</span></span>|<span data-ttu-id="df400-210">**Alias for**</span><span class="sxs-lookup"><span data-stu-id="df400-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="df400-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="df400-211">autodiscover</span></span>  <br/> |<span data-ttu-id="df400-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df400-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="df400-213">sip</span><span class="sxs-lookup"><span data-stu-id="df400-213">sip</span></span>  <br/> |<span data-ttu-id="df400-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df400-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df400-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="df400-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="df400-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df400-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df400-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="df400-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="df400-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="df400-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="df400-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="df400-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="df400-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="df400-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="df400-222">Välj **Add CNAME Record**.</span><span class="sxs-lookup"><span data-stu-id="df400-222">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="df400-224">Lägg till den andra CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="df400-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="df400-225">I rutorna för den nya posten använder du värdena från nästa rad i tabellen och väljer sedan **Add CNAME Record igen.**</span><span class="sxs-lookup"><span data-stu-id="df400-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="df400-226">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="df400-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="df400-227">Spara **ändringarna genom** att välja Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="df400-227">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="df400-229">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="df400-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="df400-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="df400-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df400-231">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="df400-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="df400-232">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="df400-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="df400-233">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df400-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="df400-234">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="df400-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="df400-p111">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="df400-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="df400-238">I avsnittet **Mitt konto** väljer du **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="df400-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="df400-240">På **sidan Domain Names** går du till **avsnittet** Domain och väljer namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="df400-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="df400-242">I avsnittet **DNS Settings** väljer du ikonen för listrutan.</span><span class="sxs-lookup"><span data-stu-id="df400-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="df400-244">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="df400-244">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="df400-246">Välj **TXT Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="df400-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="df400-248">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="df400-248">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="df400-250">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="df400-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="df400-251">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="df400-251">**Sub Domain**</span></span>|<span data-ttu-id="df400-252">**Textpost**</span><span class="sxs-lookup"><span data-stu-id="df400-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="df400-253">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="df400-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="df400-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="df400-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="df400-255">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="df400-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="df400-257">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="df400-257">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="df400-259">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="df400-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="df400-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="df400-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="df400-p112">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="df400-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="df400-264">I avsnittet **Mitt konto** väljer du **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="df400-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="df400-266">På **sidan Domain Names** går du till **avsnittet** Domain och väljer namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="df400-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="df400-268">I avsnittet **DNS Settings** väljer du ikonen för listrutan.</span><span class="sxs-lookup"><span data-stu-id="df400-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="df400-270">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="df400-270">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="df400-272">Välj **SRV Record** från listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="df400-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="df400-274">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="df400-274">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="df400-276">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="df400-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="df400-277">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="df400-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="df400-278">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="df400-278">**Record Type**</span></span>|<span data-ttu-id="df400-279">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="df400-279">**Sub Domain**</span></span>|<span data-ttu-id="df400-280">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="df400-280">**Priority**</span></span>|<span data-ttu-id="df400-281">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="df400-281">**Weight**</span></span>|<span data-ttu-id="df400-282">**Port**</span><span class="sxs-lookup"><span data-stu-id="df400-282">**Port**</span></span>|<span data-ttu-id="df400-283">**Target**</span><span class="sxs-lookup"><span data-stu-id="df400-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df400-284">SRV Record</span><span class="sxs-lookup"><span data-stu-id="df400-284">SRV Record</span></span>  <br/> |<span data-ttu-id="df400-285">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="df400-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="df400-286">100</span><span class="sxs-lookup"><span data-stu-id="df400-286">100</span></span>  <br/> |<span data-ttu-id="df400-287">1</span><span class="sxs-lookup"><span data-stu-id="df400-287">1</span></span>  <br/> |<span data-ttu-id="df400-288">443</span><span class="sxs-lookup"><span data-stu-id="df400-288">443</span></span>  <br/> |<span data-ttu-id="df400-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df400-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df400-290">SRV Record</span><span class="sxs-lookup"><span data-stu-id="df400-290">SRV Record</span></span>  <br/> |<span data-ttu-id="df400-291">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="df400-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="df400-292">100</span><span class="sxs-lookup"><span data-stu-id="df400-292">100</span></span>  <br/> |<span data-ttu-id="df400-293">1</span><span class="sxs-lookup"><span data-stu-id="df400-293">1</span></span>  <br/> |<span data-ttu-id="df400-294">5061</span><span class="sxs-lookup"><span data-stu-id="df400-294">5061</span></span>  <br/> |<span data-ttu-id="df400-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df400-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="df400-297">Välj **Add SRV Record**.</span><span class="sxs-lookup"><span data-stu-id="df400-297">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="df400-299">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="df400-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="df400-300">I rutorna för den nya posten använder du värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="df400-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="df400-301">Spara **ändringarna genom** att välja Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="df400-301">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="df400-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df400-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
