---
title: Skapa DNS-poster på Names.co.uk för Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Names.co.uk för Microsoft.
ms.openlocfilehash: 91c328877d583f415ffd2b8312ff1dc899a05bcc
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939173"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="2422f-103">Skapa DNS-poster på Names.co.uk för Microsoft</span><span class="sxs-lookup"><span data-stu-id="2422f-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="2422f-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="2422f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2422f-105">Om Names.co.uk är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="2422f-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="2422f-106">När du har lagt till dessa poster i Names.co.uk konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="2422f-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="2422f-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2422f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2422f-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="2422f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="2422f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2422f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2422f-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="2422f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2422f-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="2422f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2422f-p104">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2422f-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2422f-119">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2422f-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2422f-120">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2422f-122">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2422f-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2422f-123">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="2422f-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="2422f-124">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="2422f-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="2422f-125">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="2422f-126">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="2422f-126">**Host name**</span></span>|<span data-ttu-id="2422f-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2422f-127">**Type**</span></span>|<span data-ttu-id="2422f-128">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="2422f-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2422f-129">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="2422f-130">TXT</span><span class="sxs-lookup"><span data-stu-id="2422f-130">TXT</span></span>  <br/> |<span data-ttu-id="2422f-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2422f-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2422f-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="2422f-132">**Note:** This is an example.</span></span> <span data-ttu-id="2422f-133">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="2422f-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="2422f-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="2422f-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verifiera-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="2422f-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2422f-136">Select **Save**.</span></span>
    
    <span data-ttu-id="2422f-137">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verifiera-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="2422f-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="2422f-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2422f-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="2422f-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="2422f-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="2422f-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2422f-142">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="2422f-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2422f-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="2422f-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="2422f-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="2422f-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="2422f-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="2422f-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2422f-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2422f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2422f-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2422f-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2422f-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2422f-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="2422f-p107">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2422f-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2422f-154">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2422f-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2422f-155">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2422f-157">I avsnittet **Mail exchange records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2422f-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2422f-158">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2422f-159">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="2422f-159">**Host name**</span></span>|<span data-ttu-id="2422f-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="2422f-160">**Priority**</span></span>|<span data-ttu-id="2422f-161">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="2422f-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2422f-162">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="2422f-163">1</span><span class="sxs-lookup"><span data-stu-id="2422f-163">1</span></span>  <br/> <span data-ttu-id="2422f-164">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="2422f-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="2422f-165">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2422f-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2422f-166">> [!NOTE]> Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="2422f-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="2422f-167">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="2422f-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Konfigurera-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="2422f-169">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2422f-169">Select **Save**.</span></span>
    
    <span data-ttu-id="2422f-170">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="2422f-172">Om det finns andra MX-poster i avsnittet **Mail exchange records** tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="2422f-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Konfigurera-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="2422f-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2422f-174">Select **Save**.</span></span>
    
    <span data-ttu-id="2422f-175">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2422f-177">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="2422f-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2422f-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2422f-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="2422f-p109">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2422f-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2422f-182">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2422f-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2422f-183">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2422f-185">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2422f-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2422f-186">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="2422f-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="2422f-187">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="2422f-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="2422f-188">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2422f-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2422f-189">**Host Name**</span></span>|<span data-ttu-id="2422f-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="2422f-190">**Type**</span></span>|<span data-ttu-id="2422f-191">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="2422f-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2422f-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2422f-192">autodiscover</span></span>  <br/> |<span data-ttu-id="2422f-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="2422f-193">CNAME</span></span>  <br/> |<span data-ttu-id="2422f-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2422f-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="2422f-195">sip</span><span class="sxs-lookup"><span data-stu-id="2422f-195">sip</span></span>  <br/> |<span data-ttu-id="2422f-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="2422f-196">CNAME</span></span>  <br/> |<span data-ttu-id="2422f-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2422f-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2422f-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2422f-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2422f-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="2422f-199">CNAME</span></span>  <br/> |<span data-ttu-id="2422f-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2422f-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2422f-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2422f-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2422f-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="2422f-202">CNAME</span></span>  <br/> |<span data-ttu-id="2422f-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2422f-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="2422f-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2422f-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2422f-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="2422f-205">CNAME</span></span>  <br/> |<span data-ttu-id="2422f-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2422f-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Konfigurera-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="2422f-208">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2422f-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Konfigurera-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2422f-210">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="2422f-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2422f-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2422f-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2422f-212">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="2422f-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2422f-213">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="2422f-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2422f-214">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2422f-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2422f-215">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="2422f-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="2422f-p111">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2422f-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2422f-219">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2422f-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2422f-220">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2422f-222">Välj namnet på den domän som du uppdaterar i kolumnen **Domännamn** på sidan **DNS-zoner på kontot.**</span><span class="sxs-lookup"><span data-stu-id="2422f-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Konfigurera-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="2422f-224">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2422f-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2422f-225">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="2422f-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="2422f-226">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="2422f-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="2422f-227">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2422f-228">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="2422f-228">**Host name**</span></span>|<span data-ttu-id="2422f-229">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2422f-229">**Type**</span></span>|<span data-ttu-id="2422f-230">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="2422f-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2422f-231">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="2422f-232">TXT</span><span class="sxs-lookup"><span data-stu-id="2422f-232">TXT</span></span>  <br/> |<span data-ttu-id="2422f-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2422f-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2422f-234">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="2422f-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Konfigurera-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="2422f-236">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2422f-236">Select **Save**.</span></span>
    
    <span data-ttu-id="2422f-237">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2422f-239">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="2422f-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2422f-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2422f-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="2422f-p112">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2422f-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2422f-244">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2422f-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2422f-245">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2422f-247">Under **Service records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2422f-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2422f-248">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2422f-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="2422f-249">**Name**</span></span>|<span data-ttu-id="2422f-250">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="2422f-250">**Priority**</span></span>|<span data-ttu-id="2422f-251">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="2422f-251">**Weight**</span></span>|<span data-ttu-id="2422f-252">**Port**</span><span class="sxs-lookup"><span data-stu-id="2422f-252">**Port**</span></span>|<span data-ttu-id="2422f-253">**Result**</span><span class="sxs-lookup"><span data-stu-id="2422f-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2422f-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="2422f-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="2422f-255">100</span><span class="sxs-lookup"><span data-stu-id="2422f-255">100</span></span>  <br/> |<span data-ttu-id="2422f-256">1</span><span class="sxs-lookup"><span data-stu-id="2422f-256">1</span></span>  <br/> |<span data-ttu-id="2422f-257">443</span><span class="sxs-lookup"><span data-stu-id="2422f-257">443</span></span>  <br/> |<span data-ttu-id="2422f-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2422f-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2422f-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="2422f-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="2422f-260">100</span><span class="sxs-lookup"><span data-stu-id="2422f-260">100</span></span>  <br/> |<span data-ttu-id="2422f-261">1</span><span class="sxs-lookup"><span data-stu-id="2422f-261">1</span></span>  <br/> |<span data-ttu-id="2422f-262">5061</span><span class="sxs-lookup"><span data-stu-id="2422f-262">5061</span></span>  <br/> |<span data-ttu-id="2422f-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2422f-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Konfigurera-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="2422f-265">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2422f-265">Select **Save**.</span></span>
    
    <span data-ttu-id="2422f-266">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2422f-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="2422f-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2422f-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
