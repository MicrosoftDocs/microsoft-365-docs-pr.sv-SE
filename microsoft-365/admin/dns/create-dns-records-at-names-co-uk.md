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
ms.openlocfilehash: 2df1a18f00fd7cd48b0d24860ddcf651c2fdac4e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048945"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="ba2b2-103">Skapa DNS-poster på Names.co.uk för Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba2b2-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="ba2b2-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ba2b2-105">Om Names.co.uk är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="ba2b2-106">När du har lagt till dessa poster i Names.co.uk konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="ba2b2-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ba2b2-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="ba2b2-110">Add a TXT record for verification</span></span>
<span data-ttu-id="ba2b2-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ba2b2-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ba2b2-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba2b2-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ba2b2-p104">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ba2b2-119">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ba2b2-120">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ba2b2-122">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ba2b2-123">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ba2b2-124">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ba2b2-125">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="ba2b2-126">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-126">**Host name**</span></span>|<span data-ttu-id="ba2b2-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-127">**Type**</span></span>|<span data-ttu-id="ba2b2-128">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ba2b2-129">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ba2b2-130">TXT</span><span class="sxs-lookup"><span data-stu-id="ba2b2-130">TXT</span></span>  <br/> |<span data-ttu-id="ba2b2-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ba2b2-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ba2b2-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-132">**Note:** This is an example.</span></span> <span data-ttu-id="ba2b2-133">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="ba2b2-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="ba2b2-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verifiera-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="ba2b2-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-136">Select **Save**.</span></span>
    
    <span data-ttu-id="ba2b2-137">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verifiera-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="ba2b2-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ba2b2-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ba2b2-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ba2b2-142">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ba2b2-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ba2b2-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ba2b2-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ba2b2-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ba2b2-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ba2b2-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ba2b2-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ba2b2-p107">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ba2b2-154">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ba2b2-155">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ba2b2-157">I avsnittet **Mail exchange records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ba2b2-158">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ba2b2-159">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-159">**Host name**</span></span>|<span data-ttu-id="ba2b2-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-160">**Priority**</span></span>|<span data-ttu-id="ba2b2-161">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ba2b2-162">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ba2b2-163">1</span><span class="sxs-lookup"><span data-stu-id="ba2b2-163">1</span></span>  <br/> <span data-ttu-id="ba2b2-164">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="ba2b2-165">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ba2b2-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ba2b2-166">> [!NOTE]> Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="ba2b2-167">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="ba2b2-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Konfigurera-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="ba2b2-169">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-169">Select **Save**.</span></span>
    
    <span data-ttu-id="ba2b2-170">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="ba2b2-172">Om det finns andra MX-poster i avsnittet **Mail exchange records** tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Konfigurera-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="ba2b2-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-174">Select **Save**.</span></span>
    
    <span data-ttu-id="ba2b2-175">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ba2b2-177">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba2b2-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ba2b2-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ba2b2-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ba2b2-p109">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ba2b2-182">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ba2b2-183">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ba2b2-185">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ba2b2-186">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ba2b2-187">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ba2b2-188">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ba2b2-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-189">**Host Name**</span></span>|<span data-ttu-id="ba2b2-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-190">**Type**</span></span>|<span data-ttu-id="ba2b2-191">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ba2b2-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ba2b2-192">autodiscover</span></span>  <br/> |<span data-ttu-id="ba2b2-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="ba2b2-193">CNAME</span></span>  <br/> |<span data-ttu-id="ba2b2-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ba2b2-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ba2b2-195">sip</span><span class="sxs-lookup"><span data-stu-id="ba2b2-195">sip</span></span>  <br/> |<span data-ttu-id="ba2b2-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="ba2b2-196">CNAME</span></span>  <br/> |<span data-ttu-id="ba2b2-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba2b2-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ba2b2-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ba2b2-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ba2b2-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="ba2b2-199">CNAME</span></span>  <br/> |<span data-ttu-id="ba2b2-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba2b2-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ba2b2-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ba2b2-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ba2b2-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="ba2b2-202">CNAME</span></span>  <br/> |<span data-ttu-id="ba2b2-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ba2b2-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ba2b2-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ba2b2-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ba2b2-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="ba2b2-205">CNAME</span></span>  <br/> |<span data-ttu-id="ba2b2-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ba2b2-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Konfigurera-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="ba2b2-208">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Konfigurera-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ba2b2-210">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="ba2b2-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ba2b2-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ba2b2-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba2b2-212">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ba2b2-213">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ba2b2-214">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ba2b2-215">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="ba2b2-p111">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ba2b2-219">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ba2b2-220">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ba2b2-222">Välj namnet på den domän som du uppdaterar i kolumnen **Domännamn** på sidan **DNS-zoner på kontot.**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Konfigurera-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="ba2b2-224">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ba2b2-225">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ba2b2-226">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ba2b2-227">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ba2b2-228">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-228">**Host name**</span></span>|<span data-ttu-id="ba2b2-229">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-229">**Type**</span></span>|<span data-ttu-id="ba2b2-230">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ba2b2-231">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ba2b2-232">TXT</span><span class="sxs-lookup"><span data-stu-id="ba2b2-232">TXT</span></span>  <br/> |<span data-ttu-id="ba2b2-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ba2b2-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ba2b2-234">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="ba2b2-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Konfigurera-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="ba2b2-236">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-236">Select **Save**.</span></span>
    
    <span data-ttu-id="ba2b2-237">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ba2b2-239">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba2b2-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ba2b2-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ba2b2-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ba2b2-p112">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ba2b2-244">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ba2b2-245">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ba2b2-247">Under **Service records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ba2b2-248">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ba2b2-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-249">**Name**</span></span>|<span data-ttu-id="ba2b2-250">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-250">**Priority**</span></span>|<span data-ttu-id="ba2b2-251">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-251">**Weight**</span></span>|<span data-ttu-id="ba2b2-252">**Port**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-252">**Port**</span></span>|<span data-ttu-id="ba2b2-253">**Result**</span><span class="sxs-lookup"><span data-stu-id="ba2b2-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ba2b2-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="ba2b2-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="ba2b2-255">100</span><span class="sxs-lookup"><span data-stu-id="ba2b2-255">100</span></span>  <br/> |<span data-ttu-id="ba2b2-256">1</span><span class="sxs-lookup"><span data-stu-id="ba2b2-256">1</span></span>  <br/> |<span data-ttu-id="ba2b2-257">443</span><span class="sxs-lookup"><span data-stu-id="ba2b2-257">443</span></span>  <br/> |<span data-ttu-id="ba2b2-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba2b2-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ba2b2-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ba2b2-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ba2b2-260">100</span><span class="sxs-lookup"><span data-stu-id="ba2b2-260">100</span></span>  <br/> |<span data-ttu-id="ba2b2-261">1</span><span class="sxs-lookup"><span data-stu-id="ba2b2-261">1</span></span>  <br/> |<span data-ttu-id="ba2b2-262">5061</span><span class="sxs-lookup"><span data-stu-id="ba2b2-262">5061</span></span>  <br/> |<span data-ttu-id="ba2b2-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba2b2-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Konfigurera-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="ba2b2-265">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-265">Select **Save**.</span></span>
    
    <span data-ttu-id="ba2b2-266">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="ba2b2-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba2b2-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
