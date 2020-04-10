---
title: Skapa DNS-poster på Names.co.uk för Office 365
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Names.co.uk för Office 365.
ms.openlocfilehash: 8f8d76c1aebaa7fec80b264e0a9d2c8fffec9f41
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211673"
---
# <a name="create-dns-records-at-namescouk-for-office-365"></a><span data-ttu-id="94a36-103">Skapa DNS-poster på Names.co.uk för Office 365</span><span class="sxs-lookup"><span data-stu-id="94a36-103">Create DNS records at Names.co.uk for Office 365</span></span>

 <span data-ttu-id="94a36-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="94a36-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="94a36-105">Om Names.co.uk är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="94a36-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="94a36-106">När du har lagt till dessa poster på Names.co.uk är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="94a36-106">After you add these records at Names.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="94a36-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="94a36-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="94a36-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94a36-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="94a36-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="94a36-111">Add a TXT record for verification</span></span>
<span data-ttu-id="94a36-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="94a36-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="94a36-p102">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="94a36-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94a36-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="94a36-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="94a36-p104">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="94a36-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="94a36-120">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="94a36-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="94a36-121">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="94a36-123">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="94a36-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94a36-124">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="94a36-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="94a36-125">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="94a36-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="94a36-126">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="94a36-127">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="94a36-127">**Host name**</span></span>|<span data-ttu-id="94a36-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="94a36-128">**Type**</span></span>|<span data-ttu-id="94a36-129">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="94a36-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="94a36-130">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="94a36-131">TXT</span><span class="sxs-lookup"><span data-stu-id="94a36-131">TXT</span></span>  <br/> |<span data-ttu-id="94a36-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="94a36-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="94a36-p105">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="94a36-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
       
    ![NamesUK-BP-Verifiera-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="94a36-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="94a36-137">Select **Save**.</span></span>
    
    <span data-ttu-id="94a36-138">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verifiera-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="94a36-140">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="94a36-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="94a36-141">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="94a36-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="94a36-142">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="94a36-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="94a36-143">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="94a36-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="94a36-144">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="94a36-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="94a36-145">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="94a36-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="94a36-146">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="94a36-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="94a36-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94a36-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="94a36-150">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="94a36-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="94a36-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="94a36-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="94a36-p107">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="94a36-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="94a36-155">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="94a36-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="94a36-156">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="94a36-158">I avsnittet **Mail exchange records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="94a36-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94a36-159">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="94a36-160">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="94a36-160">**Host name**</span></span>|<span data-ttu-id="94a36-161">**Priority**</span><span class="sxs-lookup"><span data-stu-id="94a36-161">**Priority**</span></span>|<span data-ttu-id="94a36-162">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="94a36-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="94a36-163">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="94a36-164">1</span><span class="sxs-lookup"><span data-stu-id="94a36-164">1</span></span>  <br/> <span data-ttu-id="94a36-165">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="94a36-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="94a36-166">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="94a36-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="94a36-167">> [!NOTE]> Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="94a36-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="94a36-168">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="94a36-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Konfigurera-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="94a36-170">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="94a36-170">Select **Save**.</span></span>
    
    <span data-ttu-id="94a36-171">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="94a36-173">Om det finns andra MX-poster i avsnittet **Mail exchange records** tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="94a36-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Konfigurera-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="94a36-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="94a36-175">Select **Save**.</span></span>
    
    <span data-ttu-id="94a36-176">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="94a36-178">Lägg till de sex CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="94a36-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="94a36-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="94a36-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="94a36-p109">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="94a36-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="94a36-183">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="94a36-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="94a36-184">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="94a36-186">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="94a36-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94a36-187">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="94a36-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="94a36-188">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="94a36-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="94a36-189">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="94a36-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="94a36-190">**Host Name**</span></span>|<span data-ttu-id="94a36-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="94a36-191">**Type**</span></span>|<span data-ttu-id="94a36-192">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="94a36-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="94a36-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="94a36-193">autodiscover</span></span>  <br/> |<span data-ttu-id="94a36-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="94a36-194">CNAME</span></span>  <br/> |<span data-ttu-id="94a36-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="94a36-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="94a36-196">sip</span><span class="sxs-lookup"><span data-stu-id="94a36-196">sip</span></span>  <br/> |<span data-ttu-id="94a36-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="94a36-197">CNAME</span></span>  <br/> |<span data-ttu-id="94a36-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94a36-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="94a36-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="94a36-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="94a36-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="94a36-200">CNAME</span></span>  <br/> |<span data-ttu-id="94a36-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94a36-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="94a36-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="94a36-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="94a36-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="94a36-203">CNAME</span></span>  <br/> |<span data-ttu-id="94a36-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="94a36-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="94a36-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="94a36-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="94a36-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="94a36-206">CNAME</span></span>  <br/> |<span data-ttu-id="94a36-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="94a36-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Konfigurera-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="94a36-209">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="94a36-209">Select **Save**.</span></span>
    
    ![NamesUK-BP-Konfigurera-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="94a36-211">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="94a36-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="94a36-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="94a36-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="94a36-213">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="94a36-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="94a36-214">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="94a36-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="94a36-215">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="94a36-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="94a36-216">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="94a36-216">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="94a36-p111">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="94a36-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="94a36-220">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="94a36-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="94a36-221">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="94a36-223">Välj namnet på den domän som du uppdaterar i kolumnen **Domännamn** på sidan **DNS-zoner på kontot.**</span><span class="sxs-lookup"><span data-stu-id="94a36-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Konfigurera-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="94a36-225">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="94a36-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94a36-226">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="94a36-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="94a36-227">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="94a36-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="94a36-228">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="94a36-229">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="94a36-229">**Host name**</span></span>|<span data-ttu-id="94a36-230">**Typ**</span><span class="sxs-lookup"><span data-stu-id="94a36-230">**Type**</span></span>|<span data-ttu-id="94a36-231">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="94a36-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="94a36-232">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="94a36-233">TXT</span><span class="sxs-lookup"><span data-stu-id="94a36-233">TXT</span></span>  <br/> |<span data-ttu-id="94a36-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="94a36-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="94a36-235">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="94a36-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Konfigurera-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="94a36-237">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="94a36-237">Select **Save**.</span></span>
    
    <span data-ttu-id="94a36-238">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="94a36-240">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="94a36-240">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="94a36-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="94a36-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="94a36-p112">Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="94a36-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="94a36-245">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="94a36-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="94a36-246">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="94a36-248">Under **Service records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="94a36-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94a36-249">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="94a36-250">**Name**</span><span class="sxs-lookup"><span data-stu-id="94a36-250">**Name**</span></span>|<span data-ttu-id="94a36-251">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="94a36-251">**Priority**</span></span>|<span data-ttu-id="94a36-252">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="94a36-252">**Weight**</span></span>|<span data-ttu-id="94a36-253">**Port**</span><span class="sxs-lookup"><span data-stu-id="94a36-253">**Port**</span></span>|<span data-ttu-id="94a36-254">**Result**</span><span class="sxs-lookup"><span data-stu-id="94a36-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94a36-255">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="94a36-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="94a36-256">100</span><span class="sxs-lookup"><span data-stu-id="94a36-256">100</span></span>  <br/> |<span data-ttu-id="94a36-257">1</span><span class="sxs-lookup"><span data-stu-id="94a36-257">1</span></span>  <br/> |<span data-ttu-id="94a36-258">443</span><span class="sxs-lookup"><span data-stu-id="94a36-258">443</span></span>  <br/> |<span data-ttu-id="94a36-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94a36-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="94a36-260">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="94a36-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="94a36-261">100</span><span class="sxs-lookup"><span data-stu-id="94a36-261">100</span></span>  <br/> |<span data-ttu-id="94a36-262">1</span><span class="sxs-lookup"><span data-stu-id="94a36-262">1</span></span>  <br/> |<span data-ttu-id="94a36-263">5061</span><span class="sxs-lookup"><span data-stu-id="94a36-263">5061</span></span>  <br/> |<span data-ttu-id="94a36-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94a36-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Konfigurera-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="94a36-266">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="94a36-266">Select **Save**.</span></span>
    
    <span data-ttu-id="94a36-267">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="94a36-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Konfigurera-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="94a36-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94a36-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
