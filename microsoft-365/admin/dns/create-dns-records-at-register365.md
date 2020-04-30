---
title: Skapa DNS-poster på Register365 för Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Register365 för Microsoft.
ms.openlocfilehash: 29aaa225a291880f0fb6b5cd039903d74e3f32a2
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938858"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="de3d1-103">Skapa DNS-poster på Register365 för Microsoft</span><span class="sxs-lookup"><span data-stu-id="de3d1-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="de3d1-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="de3d1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="de3d1-105">Om Register365 är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="de3d1-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="de3d1-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="de3d1-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="de3d1-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="de3d1-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="de3d1-108">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de3d1-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="de3d1-109">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="de3d1-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="de3d1-110">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="de3d1-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="de3d1-111">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="de3d1-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="de3d1-112">När du har lagt till dessa poster på Microsoft konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="de3d1-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="de3d1-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="de3d1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="de3d1-116">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="de3d1-116">Add a TXT record for verification</span></span>
<span data-ttu-id="de3d1-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="de3d1-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="de3d1-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="de3d1-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="de3d1-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="de3d1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="de3d1-p104">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="de3d1-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="de3d1-125">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="de3d1-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="de3d1-126">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-126">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="de3d1-128">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="de3d1-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="de3d1-129">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="de3d1-130">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="de3d1-131">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="de3d1-132">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="de3d1-132">**Host name**</span></span>|<span data-ttu-id="de3d1-133">**Typ**</span><span class="sxs-lookup"><span data-stu-id="de3d1-133">**Type**</span></span>|<span data-ttu-id="de3d1-134">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="de3d1-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="de3d1-135">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="de3d1-136">TXT</span><span class="sxs-lookup"><span data-stu-id="de3d1-136">TXT</span></span>  <br/> |<span data-ttu-id="de3d1-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="de3d1-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="de3d1-138">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="de3d1-138">**Note:** This is an example.</span></span> <span data-ttu-id="de3d1-139">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="de3d1-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="de3d1-140">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="de3d1-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="de3d1-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="de3d1-142">Select **Save**.</span></span>
    
    <span data-ttu-id="de3d1-143">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-143">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="de3d1-145">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="de3d1-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="de3d1-146">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="de3d1-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="de3d1-147">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="de3d1-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="de3d1-148">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="de3d1-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="de3d1-149">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="de3d1-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="de3d1-150">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="de3d1-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="de3d1-151">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="de3d1-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="de3d1-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="de3d1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="de3d1-155">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de3d1-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="de3d1-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="de3d1-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="de3d1-p107">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="de3d1-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="de3d1-160">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="de3d1-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="de3d1-161">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-161">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="de3d1-163">I avsnittet **Mail exchange records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="de3d1-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="de3d1-164">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="de3d1-165">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="de3d1-165">**Host name**</span></span>|<span data-ttu-id="de3d1-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="de3d1-166">**Priority**</span></span>|<span data-ttu-id="de3d1-167">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="de3d1-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="de3d1-168">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="de3d1-169">1</span><span class="sxs-lookup"><span data-stu-id="de3d1-169">1</span></span>  <br/> <span data-ttu-id="de3d1-170">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="de3d1-170">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="de3d1-171">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="de3d1-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="de3d1-172">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="de3d1-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="de3d1-173">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="de3d1-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="de3d1-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="de3d1-175">Select **Save**.</span></span>
    
    <span data-ttu-id="de3d1-176">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-176">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="de3d1-178">Om det finns andra MX-poster i avsnittet **Mail exchange records** tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="de3d1-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="de3d1-180">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="de3d1-180">Select **Save**.</span></span>
    
    <span data-ttu-id="de3d1-181">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-181">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="de3d1-183">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="de3d1-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="de3d1-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="de3d1-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="de3d1-p109">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="de3d1-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="de3d1-188">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="de3d1-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="de3d1-189">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-189">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="de3d1-191">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för de nya posterna.</span><span class="sxs-lookup"><span data-stu-id="de3d1-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="de3d1-192">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="de3d1-193">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="de3d1-194">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="de3d1-195">\*\*\*\*Värdnamn\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="de3d1-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="de3d1-196">\*\*\*\*Typ\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="de3d1-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="de3d1-197">\*\*\*\*Resultat\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="de3d1-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="de3d1-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="de3d1-198">autodiscover</span></span>  <br/> |<span data-ttu-id="de3d1-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3d1-199">CNAME</span></span>  <br/> |<span data-ttu-id="de3d1-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="de3d1-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="de3d1-201">sip</span><span class="sxs-lookup"><span data-stu-id="de3d1-201">sip</span></span>  <br/> |<span data-ttu-id="de3d1-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3d1-202">CNAME</span></span>  <br/> |<span data-ttu-id="de3d1-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de3d1-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="de3d1-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="de3d1-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="de3d1-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3d1-205">CNAME</span></span>  <br/> |<span data-ttu-id="de3d1-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de3d1-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="de3d1-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="de3d1-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="de3d1-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3d1-208">CNAME</span></span>  <br/> |<span data-ttu-id="de3d1-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="de3d1-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="de3d1-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="de3d1-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="de3d1-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3d1-211">CNAME</span></span>  <br/> |<span data-ttu-id="de3d1-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="de3d1-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="de3d1-214">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="de3d1-214">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="de3d1-216">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="de3d1-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="de3d1-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="de3d1-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de3d1-218">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="de3d1-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="de3d1-219">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="de3d1-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="de3d1-220">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de3d1-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="de3d1-221">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="de3d1-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="de3d1-p111">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="de3d1-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="de3d1-225">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="de3d1-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="de3d1-226">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-226">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="de3d1-228">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="de3d1-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="de3d1-229">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="de3d1-230">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="de3d1-231">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="de3d1-232">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="de3d1-232">**Host name**</span></span>|<span data-ttu-id="de3d1-233">**Typ**</span><span class="sxs-lookup"><span data-stu-id="de3d1-233">**Type**</span></span>|<span data-ttu-id="de3d1-234">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="de3d1-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="de3d1-235">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="de3d1-236">TXT</span><span class="sxs-lookup"><span data-stu-id="de3d1-236">TXT</span></span>  <br/> |<span data-ttu-id="de3d1-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="de3d1-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="de3d1-238">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="de3d1-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="de3d1-240">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="de3d1-240">Select **Save**.</span></span>
    
    <span data-ttu-id="de3d1-241">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-241">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="de3d1-243">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="de3d1-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="de3d1-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="de3d1-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="de3d1-p112">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="de3d1-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="de3d1-248">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="de3d1-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="de3d1-249">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-249">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="de3d1-251">Under **Service records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för de nya posterna.</span><span class="sxs-lookup"><span data-stu-id="de3d1-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="de3d1-252">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="de3d1-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="de3d1-253">**Name**</span></span>|<span data-ttu-id="de3d1-254">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="de3d1-254">**Priority**</span></span>|<span data-ttu-id="de3d1-255">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="de3d1-255">**Weight**</span></span>|<span data-ttu-id="de3d1-256">**Port**</span><span class="sxs-lookup"><span data-stu-id="de3d1-256">**Port**</span></span>|<span data-ttu-id="de3d1-257">**Result**</span><span class="sxs-lookup"><span data-stu-id="de3d1-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de3d1-258">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="de3d1-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="de3d1-259">100</span><span class="sxs-lookup"><span data-stu-id="de3d1-259">100</span></span>  <br/> |<span data-ttu-id="de3d1-260">1</span><span class="sxs-lookup"><span data-stu-id="de3d1-260">1</span></span>  <br/> |<span data-ttu-id="de3d1-261">443</span><span class="sxs-lookup"><span data-stu-id="de3d1-261">443</span></span>  <br/> |<span data-ttu-id="de3d1-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de3d1-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="de3d1-263">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="de3d1-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="de3d1-264">100</span><span class="sxs-lookup"><span data-stu-id="de3d1-264">100</span></span>  <br/> |<span data-ttu-id="de3d1-265">1</span><span class="sxs-lookup"><span data-stu-id="de3d1-265">1</span></span>  <br/> |<span data-ttu-id="de3d1-266">5061</span><span class="sxs-lookup"><span data-stu-id="de3d1-266">5061</span></span>  <br/> |<span data-ttu-id="de3d1-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de3d1-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Ange värden i avsnittet Serviceposter](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="de3d1-269">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="de3d1-269">Select **Save**.</span></span>
    
    <span data-ttu-id="de3d1-270">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="de3d1-270">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="de3d1-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="de3d1-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
