---
title: Skapa DNS-poster på Crazy Domains för Microsoft
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Crazy Domains för Microsoft.
ms.openlocfilehash: af154db43f486f71443497180fe64cff89e11b5f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400539"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="1b3a3-103">Skapa DNS-poster på Crazy Domains för Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b3a3-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="1b3a3-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1b3a3-105">Om Crazy Domains är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1b3a3-106">När du har lagt till dessa poster på Crazy Domains konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="1b3a3-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1b3a3-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="1b3a3-110">Add a TXT record for verification</span></span>
<span data-ttu-id="1b3a3-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1b3a3-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1b3a3-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1b3a3-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1b3a3-p104">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1b3a3-119">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="1b3a3-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1b3a3-121">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1b3a3-123">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1b3a3-125">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-125">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1b3a3-127">Välj **TXT Record** i listrutan **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verifiera-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="1b3a3-129">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-129">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verifiera-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="1b3a3-131">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1b3a3-132">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-132">**Sub Domain**</span></span>|<span data-ttu-id="1b3a3-133">**Textpost**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1b3a3-134">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="1b3a3-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1b3a3-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1b3a3-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1b3a3-136">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-136">**Note:** This is an example.</span></span> <span data-ttu-id="1b3a3-137">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1b3a3-138">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="1b3a3-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verifiera-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="1b3a3-140">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-140">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verifiera-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="1b3a3-142">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1b3a3-143">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1b3a3-144">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1b3a3-145">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1b3a3-146">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1b3a3-147">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1b3a3-148">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1b3a3-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1b3a3-152">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1b3a3-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1b3a3-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1b3a3-p107">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1b3a3-157">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="1b3a3-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1b3a3-159">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1b3a3-161">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1b3a3-163">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-163">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1b3a3-165">Välj **MX Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="1b3a3-167">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-167">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="1b3a3-169">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="1b3a3-170">(Välj **prioritetsvärdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="1b3a3-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1b3a3-171">**Mail for Zone**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-171">**Mail For Zone**</span></span>|<span data-ttu-id="1b3a3-172">**Priority**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-172">**Priority**</span></span>|<span data-ttu-id="1b3a3-173">**Assigned To Server**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1b3a3-174">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="1b3a3-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1b3a3-175">1</span><span class="sxs-lookup"><span data-stu-id="1b3a3-175">1</span></span>  <br/> <span data-ttu-id="1b3a3-176">[Mer information om prioritet finns i ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="1b3a3-176">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="1b3a3-177">*\<domain-key\>*.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1b3a3-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1b3a3-178">**Anm.:** Hämta ditt *\<domain-key\>* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="1b3a3-179">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="1b3a3-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Konfigurera-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="1b3a3-181">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-181">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="1b3a3-183">Om det finns några andra MX-poster i avsnittet **MX-post** väljer du **Ändra** för en av dessa poster.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="1b3a3-185">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-185">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="1b3a3-187">Välj **Uppdatera** för att bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="1b3a3-189">Använd samma sätt för att ta bort andra MX-poster i listan tills endast den du lade till tidigare i den här proceduren finns kvar.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1b3a3-190">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b3a3-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1b3a3-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1b3a3-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1b3a3-p109">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1b3a3-195">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="1b3a3-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1b3a3-197">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1b3a3-199">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1b3a3-201">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-201">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1b3a3-203">Välj **CNAME Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="1b3a3-205">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-205">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="1b3a3-207">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="1b3a3-208">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="1b3a3-209">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-209">**Sub Domain**</span></span>|<span data-ttu-id="1b3a3-210">**Alias for**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1b3a3-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1b3a3-211">autodiscover</span></span>  <br/> |<span data-ttu-id="1b3a3-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1b3a3-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="1b3a3-213">sip</span><span class="sxs-lookup"><span data-stu-id="1b3a3-213">sip</span></span>  <br/> |<span data-ttu-id="1b3a3-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1b3a3-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1b3a3-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1b3a3-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1b3a3-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1b3a3-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1b3a3-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1b3a3-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1b3a3-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1b3a3-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="1b3a3-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1b3a3-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1b3a3-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1b3a3-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Konfigurera-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="1b3a3-222">Välj **Lägg till CNAME-post**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-222">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="1b3a3-224">Lägg till den andra CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="1b3a3-225">I rutorna för den nya posten använder du värdena från nästa rad i tabellen och väljer sedan **Lägg till CNAME-post**igen .</span><span class="sxs-lookup"><span data-stu-id="1b3a3-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="1b3a3-226">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="1b3a3-227">Välj **Uppdatera** om du vill spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-227">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1b3a3-229">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="1b3a3-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1b3a3-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1b3a3-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b3a3-231">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1b3a3-232">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1b3a3-233">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1b3a3-234">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="1b3a3-p111">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1b3a3-238">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="1b3a3-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1b3a3-240">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1b3a3-242">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1b3a3-244">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-244">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1b3a3-246">Välj **TXT Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="1b3a3-248">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-248">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="1b3a3-250">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1b3a3-251">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-251">**Sub Domain**</span></span>|<span data-ttu-id="1b3a3-252">**Textpost**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1b3a3-253">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="1b3a3-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1b3a3-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1b3a3-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1b3a3-255">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="1b3a3-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Konfigurera-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="1b3a3-257">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-257">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1b3a3-259">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b3a3-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1b3a3-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1b3a3-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1b3a3-p112">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1b3a3-264">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="1b3a3-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1b3a3-266">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1b3a3-268">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1b3a3-270">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-270">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1b3a3-272">Välj **SRV Record** från listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="1b3a3-274">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-274">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="1b3a3-276">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="1b3a3-277">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="1b3a3-278">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-278">**Record Type**</span></span>|<span data-ttu-id="1b3a3-279">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-279">**Sub Domain**</span></span>|<span data-ttu-id="1b3a3-280">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-280">**Priority**</span></span>|<span data-ttu-id="1b3a3-281">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-281">**Weight**</span></span>|<span data-ttu-id="1b3a3-282">**Port**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-282">**Port**</span></span>|<span data-ttu-id="1b3a3-283">**Target**</span><span class="sxs-lookup"><span data-stu-id="1b3a3-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1b3a3-284">SRV Record</span><span class="sxs-lookup"><span data-stu-id="1b3a3-284">SRV Record</span></span>  <br/> |<span data-ttu-id="1b3a3-285">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1b3a3-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="1b3a3-286">100</span><span class="sxs-lookup"><span data-stu-id="1b3a3-286">100</span></span>  <br/> |<span data-ttu-id="1b3a3-287">1</span><span class="sxs-lookup"><span data-stu-id="1b3a3-287">1</span></span>  <br/> |<span data-ttu-id="1b3a3-288">443</span><span class="sxs-lookup"><span data-stu-id="1b3a3-288">443</span></span>  <br/> |<span data-ttu-id="1b3a3-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1b3a3-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1b3a3-290">SRV Record</span><span class="sxs-lookup"><span data-stu-id="1b3a3-290">SRV Record</span></span>  <br/> |<span data-ttu-id="1b3a3-291">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1b3a3-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="1b3a3-292">100</span><span class="sxs-lookup"><span data-stu-id="1b3a3-292">100</span></span>  <br/> |<span data-ttu-id="1b3a3-293">1</span><span class="sxs-lookup"><span data-stu-id="1b3a3-293">1</span></span>  <br/> |<span data-ttu-id="1b3a3-294">5061</span><span class="sxs-lookup"><span data-stu-id="1b3a3-294">5061</span></span>  <br/> |<span data-ttu-id="1b3a3-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1b3a3-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Konfigurera-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="1b3a3-297">Välj **Lägg till SRV-post**.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-297">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="1b3a3-299">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="1b3a3-300">I rutorna för den nya posten använder du värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="1b3a3-301">Välj **Uppdatera** om du vill spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="1b3a3-301">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="1b3a3-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1b3a3-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
