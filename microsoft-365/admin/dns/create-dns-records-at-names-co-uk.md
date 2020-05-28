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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Names.co.uk för Microsoft.
ms.openlocfilehash: 1b519393e70483aa311354b96ebb11ad0feaa933
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400382"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="2fd5e-103">Skapa DNS-poster på Names.co.uk för Microsoft</span><span class="sxs-lookup"><span data-stu-id="2fd5e-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="2fd5e-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2fd5e-105">Om Names.co.uk är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="2fd5e-106">När du har lagt till dessa poster i Names.co.uk konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="2fd5e-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2fd5e-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="2fd5e-110">Add a TXT record for verification</span></span>
<span data-ttu-id="2fd5e-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2fd5e-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2fd5e-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2fd5e-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2fd5e-p104">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2fd5e-119">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2fd5e-120">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2fd5e-122">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2fd5e-123">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="2fd5e-124">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="2fd5e-125">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="2fd5e-126">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-126">**Host name**</span></span>|<span data-ttu-id="2fd5e-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-127">**Type**</span></span>|<span data-ttu-id="2fd5e-128">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2fd5e-129">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="2fd5e-130">TXT</span><span class="sxs-lookup"><span data-stu-id="2fd5e-130">TXT</span></span>  <br/> |<span data-ttu-id="2fd5e-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2fd5e-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2fd5e-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-132">**Note:** This is an example.</span></span> <span data-ttu-id="2fd5e-133">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="2fd5e-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="2fd5e-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verifiera-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="2fd5e-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-136">Select **Save**.</span></span>
    
    <span data-ttu-id="2fd5e-137">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verifiera-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="2fd5e-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2fd5e-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="2fd5e-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2fd5e-142">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2fd5e-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="2fd5e-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="2fd5e-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2fd5e-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2fd5e-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2fd5e-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2fd5e-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="2fd5e-p107">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2fd5e-154">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2fd5e-155">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2fd5e-157">I avsnittet **Mail exchange records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2fd5e-158">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2fd5e-159">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-159">**Host name**</span></span>|<span data-ttu-id="2fd5e-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-160">**Priority**</span></span>|<span data-ttu-id="2fd5e-161">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2fd5e-162">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="2fd5e-163">1</span><span class="sxs-lookup"><span data-stu-id="2fd5e-163">1</span></span>  <br/> <span data-ttu-id="2fd5e-164">[Mer information om prioritet finns i ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="2fd5e-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="2fd5e-165">*\<domain-key\>*.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2fd5e-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2fd5e-166">> [!NOTE]> Hämta ditt *\<domain-key\>* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="2fd5e-167">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="2fd5e-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Konfigurera-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="2fd5e-169">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-169">Select **Save**.</span></span>
    
    <span data-ttu-id="2fd5e-170">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="2fd5e-172">Om det finns andra MX-poster i avsnittet **Mail exchange records** tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Konfigurera-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="2fd5e-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-174">Select **Save**.</span></span>
    
    <span data-ttu-id="2fd5e-175">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2fd5e-177">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="2fd5e-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2fd5e-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2fd5e-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="2fd5e-p109">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2fd5e-182">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2fd5e-183">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2fd5e-185">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2fd5e-186">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="2fd5e-187">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="2fd5e-188">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2fd5e-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-189">**Host Name**</span></span>|<span data-ttu-id="2fd5e-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-190">**Type**</span></span>|<span data-ttu-id="2fd5e-191">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2fd5e-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2fd5e-192">autodiscover</span></span>  <br/> |<span data-ttu-id="2fd5e-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="2fd5e-193">CNAME</span></span>  <br/> |<span data-ttu-id="2fd5e-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2fd5e-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="2fd5e-195">sip</span><span class="sxs-lookup"><span data-stu-id="2fd5e-195">sip</span></span>  <br/> |<span data-ttu-id="2fd5e-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="2fd5e-196">CNAME</span></span>  <br/> |<span data-ttu-id="2fd5e-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fd5e-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2fd5e-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2fd5e-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2fd5e-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="2fd5e-199">CNAME</span></span>  <br/> |<span data-ttu-id="2fd5e-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fd5e-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2fd5e-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2fd5e-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2fd5e-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="2fd5e-202">CNAME</span></span>  <br/> |<span data-ttu-id="2fd5e-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2fd5e-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="2fd5e-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2fd5e-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2fd5e-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="2fd5e-205">CNAME</span></span>  <br/> |<span data-ttu-id="2fd5e-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2fd5e-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Konfigurera-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="2fd5e-208">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Konfigurera-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2fd5e-210">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="2fd5e-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2fd5e-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2fd5e-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fd5e-212">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2fd5e-213">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2fd5e-214">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2fd5e-215">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="2fd5e-p111">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2fd5e-219">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2fd5e-220">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2fd5e-222">Välj namnet på den domän som du uppdaterar i kolumnen **Domännamn** på sidan **DNS-zoner på kontot.**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Konfigurera-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="2fd5e-224">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2fd5e-225">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="2fd5e-226">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="2fd5e-227">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2fd5e-228">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-228">**Host name**</span></span>|<span data-ttu-id="2fd5e-229">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-229">**Type**</span></span>|<span data-ttu-id="2fd5e-230">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2fd5e-231">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="2fd5e-232">TXT</span><span class="sxs-lookup"><span data-stu-id="2fd5e-232">TXT</span></span>  <br/> |<span data-ttu-id="2fd5e-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2fd5e-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2fd5e-234">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="2fd5e-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Konfigurera-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="2fd5e-236">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-236">Select **Save**.</span></span>
    
    <span data-ttu-id="2fd5e-237">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2fd5e-239">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="2fd5e-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2fd5e-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2fd5e-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="2fd5e-p112">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="2fd5e-244">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="2fd5e-245">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="2fd5e-247">Under **Service records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2fd5e-248">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2fd5e-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-249">**Name**</span></span>|<span data-ttu-id="2fd5e-250">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-250">**Priority**</span></span>|<span data-ttu-id="2fd5e-251">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-251">**Weight**</span></span>|<span data-ttu-id="2fd5e-252">**Port**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-252">**Port**</span></span>|<span data-ttu-id="2fd5e-253">**Result**</span><span class="sxs-lookup"><span data-stu-id="2fd5e-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2fd5e-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="2fd5e-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="2fd5e-255">100</span><span class="sxs-lookup"><span data-stu-id="2fd5e-255">100</span></span>  <br/> |<span data-ttu-id="2fd5e-256">1</span><span class="sxs-lookup"><span data-stu-id="2fd5e-256">1</span></span>  <br/> |<span data-ttu-id="2fd5e-257">443</span><span class="sxs-lookup"><span data-stu-id="2fd5e-257">443</span></span>  <br/> |<span data-ttu-id="2fd5e-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fd5e-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2fd5e-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="2fd5e-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="2fd5e-260">100</span><span class="sxs-lookup"><span data-stu-id="2fd5e-260">100</span></span>  <br/> |<span data-ttu-id="2fd5e-261">1</span><span class="sxs-lookup"><span data-stu-id="2fd5e-261">1</span></span>  <br/> |<span data-ttu-id="2fd5e-262">5061</span><span class="sxs-lookup"><span data-stu-id="2fd5e-262">5061</span></span>  <br/> |<span data-ttu-id="2fd5e-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fd5e-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Konfigurera-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="2fd5e-265">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-265">Select **Save**.</span></span>
    
    <span data-ttu-id="2fd5e-266">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="2fd5e-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="2fd5e-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2fd5e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
