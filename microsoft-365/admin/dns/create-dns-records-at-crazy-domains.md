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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Crazy Domains för Microsoft.
ms.openlocfilehash: db8979d303e4749a2a04870d277b68e5aec2e52f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629701"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="9920b-103">Skapa DNS-poster på Crazy Domains för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9920b-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="9920b-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="9920b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9920b-105">Om Crazy Domains är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="9920b-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9920b-106">När du har lagt till dessa poster på Crazy Domains konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="9920b-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="9920b-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="9920b-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9920b-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9920b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9920b-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="9920b-111">Add a TXT record for verification</span></span>
<span data-ttu-id="9920b-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9920b-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9920b-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="9920b-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="9920b-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="9920b-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9920b-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="9920b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9920b-p104">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9920b-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9920b-120">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="9920b-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9920b-122">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="9920b-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9920b-124">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="9920b-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9920b-126">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="9920b-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9920b-128">Välj **TXT Record** i listrutan **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="9920b-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verifiera-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="9920b-130">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9920b-130">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verifiera-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="9920b-132">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9920b-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9920b-133">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="9920b-133">**Sub Domain**</span></span>|<span data-ttu-id="9920b-134">**Textpost**</span><span class="sxs-lookup"><span data-stu-id="9920b-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9920b-135">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="9920b-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9920b-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9920b-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9920b-137">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="9920b-137">**Note:** This is an example.</span></span> <span data-ttu-id="9920b-138">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="9920b-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9920b-139">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="9920b-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verifiera-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="9920b-141">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="9920b-141">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verifiera-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="9920b-143">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="9920b-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9920b-144">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="9920b-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9920b-145">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="9920b-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9920b-146">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="9920b-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9920b-147">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="9920b-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9920b-148">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="9920b-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9920b-149">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="9920b-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9920b-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9920b-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9920b-153">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="9920b-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9920b-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9920b-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9920b-p107">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9920b-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9920b-158">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="9920b-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9920b-160">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="9920b-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9920b-162">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="9920b-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9920b-164">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="9920b-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9920b-166">Välj **MX Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="9920b-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="9920b-168">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9920b-168">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="9920b-170">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9920b-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="9920b-171">(Välj **prioritetsvärdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="9920b-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9920b-172">**Mail for Zone**</span><span class="sxs-lookup"><span data-stu-id="9920b-172">**Mail For Zone**</span></span>|<span data-ttu-id="9920b-173">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9920b-173">**Priority**</span></span>|<span data-ttu-id="9920b-174">**Assigned To Server**</span><span class="sxs-lookup"><span data-stu-id="9920b-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9920b-175">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="9920b-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9920b-176">1</span><span class="sxs-lookup"><span data-stu-id="9920b-176">1</span></span>  <br/> <span data-ttu-id="9920b-177">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="9920b-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="9920b-178">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9920b-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9920b-179">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="9920b-179">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="9920b-180">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="9920b-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Konfigurera-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="9920b-182">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="9920b-182">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="9920b-184">Om det finns några andra MX-poster i avsnittet **MX-post** väljer du **Ändra** för en av dessa poster.</span><span class="sxs-lookup"><span data-stu-id="9920b-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="9920b-186">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="9920b-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="9920b-188">Välj **Uppdatera** för att bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="9920b-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="9920b-190">Använd samma sätt för att ta bort andra MX-poster i listan tills endast den du lade till tidigare i den här proceduren finns kvar.</span><span class="sxs-lookup"><span data-stu-id="9920b-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9920b-191">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9920b-191">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9920b-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9920b-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9920b-p109">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9920b-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9920b-196">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="9920b-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9920b-198">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="9920b-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9920b-200">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="9920b-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9920b-202">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="9920b-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9920b-204">Välj **CNAME Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="9920b-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="9920b-206">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9920b-206">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="9920b-208">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="9920b-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="9920b-209">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9920b-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="9920b-210">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="9920b-210">**Sub Domain**</span></span>|<span data-ttu-id="9920b-211">**Alias for**</span><span class="sxs-lookup"><span data-stu-id="9920b-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9920b-212">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9920b-212">autodiscover</span></span>  <br/> |<span data-ttu-id="9920b-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9920b-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9920b-214">sip</span><span class="sxs-lookup"><span data-stu-id="9920b-214">sip</span></span>  <br/> |<span data-ttu-id="9920b-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9920b-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9920b-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9920b-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9920b-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9920b-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9920b-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9920b-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9920b-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9920b-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9920b-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9920b-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9920b-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9920b-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Konfigurera-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="9920b-223">Välj **Lägg till CNAME-post**.</span><span class="sxs-lookup"><span data-stu-id="9920b-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="9920b-225">Lägg till den andra CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="9920b-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="9920b-226">I rutorna för den nya posten använder du värdena från nästa rad i tabellen och väljer sedan **Lägg till CNAME-post**igen .</span><span class="sxs-lookup"><span data-stu-id="9920b-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="9920b-227">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="9920b-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="9920b-228">Välj **Uppdatera** om du vill spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9920b-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9920b-230">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="9920b-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9920b-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9920b-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9920b-232">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="9920b-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9920b-233">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="9920b-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9920b-234">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9920b-234">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9920b-235">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="9920b-235">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9920b-p111">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9920b-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9920b-239">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="9920b-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9920b-241">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="9920b-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9920b-243">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="9920b-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9920b-245">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="9920b-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9920b-247">Välj **TXT Record** i listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="9920b-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="9920b-249">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9920b-249">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="9920b-251">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9920b-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9920b-252">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="9920b-252">**Sub Domain**</span></span>|<span data-ttu-id="9920b-253">**Textpost**</span><span class="sxs-lookup"><span data-stu-id="9920b-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9920b-254">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="9920b-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9920b-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9920b-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9920b-256">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="9920b-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Konfigurera-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="9920b-258">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="9920b-258">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9920b-260">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9920b-260">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9920b-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9920b-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9920b-p112">Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9920b-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="9920b-265">Välj **Domäner**i avsnittet **Mitt konto** .</span><span class="sxs-lookup"><span data-stu-id="9920b-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="9920b-267">Välj namnet på den domän som du uppdaterar i avsnittet **Domän** på sidan **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="9920b-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="9920b-269">Välj listrutan i avsnittet **DNS-inställningar.**</span><span class="sxs-lookup"><span data-stu-id="9920b-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="9920b-271">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="9920b-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="9920b-273">Välj **SRV Record** från listrutan **Add Record:**.</span><span class="sxs-lookup"><span data-stu-id="9920b-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="9920b-275">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9920b-275">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="9920b-277">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="9920b-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="9920b-278">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9920b-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="9920b-279">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="9920b-279">**Record Type**</span></span>|<span data-ttu-id="9920b-280">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="9920b-280">**Sub Domain**</span></span>|<span data-ttu-id="9920b-281">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="9920b-281">**Priority**</span></span>|<span data-ttu-id="9920b-282">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="9920b-282">**Weight**</span></span>|<span data-ttu-id="9920b-283">**Port**</span><span class="sxs-lookup"><span data-stu-id="9920b-283">**Port**</span></span>|<span data-ttu-id="9920b-284">**Target**</span><span class="sxs-lookup"><span data-stu-id="9920b-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9920b-285">SRV Record</span><span class="sxs-lookup"><span data-stu-id="9920b-285">SRV Record</span></span>  <br/> |<span data-ttu-id="9920b-286">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="9920b-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="9920b-287">100</span><span class="sxs-lookup"><span data-stu-id="9920b-287">100</span></span>  <br/> |<span data-ttu-id="9920b-288">1</span><span class="sxs-lookup"><span data-stu-id="9920b-288">1</span></span>  <br/> |<span data-ttu-id="9920b-289">443</span><span class="sxs-lookup"><span data-stu-id="9920b-289">443</span></span>  <br/> |<span data-ttu-id="9920b-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9920b-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9920b-291">SRV Record</span><span class="sxs-lookup"><span data-stu-id="9920b-291">SRV Record</span></span>  <br/> |<span data-ttu-id="9920b-292">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9920b-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9920b-293">100</span><span class="sxs-lookup"><span data-stu-id="9920b-293">100</span></span>  <br/> |<span data-ttu-id="9920b-294">1</span><span class="sxs-lookup"><span data-stu-id="9920b-294">1</span></span>  <br/> |<span data-ttu-id="9920b-295">5061</span><span class="sxs-lookup"><span data-stu-id="9920b-295">5061</span></span>  <br/> |<span data-ttu-id="9920b-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9920b-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Konfigurera-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="9920b-298">Välj **Lägg till SRV-post**.</span><span class="sxs-lookup"><span data-stu-id="9920b-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Konfigurera-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="9920b-300">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="9920b-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="9920b-301">I rutorna för den nya posten använder du värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="9920b-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="9920b-302">Välj **Uppdatera** om du vill spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9920b-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Konfigurera-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="9920b-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9920b-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
