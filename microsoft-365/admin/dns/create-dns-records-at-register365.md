---
title: Skapa DNS-poster på Register365 för Office 365
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Register365 för Office 365.
ms.openlocfilehash: 66c5c29d533b6897280ff99c449988c160022cf8
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211092"
---
# <a name="create-dns-records-at-register365-for-office-365"></a><span data-ttu-id="f30cc-103">Skapa DNS-poster på Register365 för Office 365</span><span class="sxs-lookup"><span data-stu-id="f30cc-103">Create DNS records at Register365 for Office 365</span></span>

 <span data-ttu-id="f30cc-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="f30cc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f30cc-105">Om Register365 är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="f30cc-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="f30cc-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="f30cc-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="f30cc-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="f30cc-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="f30cc-108">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="f30cc-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="f30cc-109">Lägg till de sex CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="f30cc-109">Add the six CNAME records that are required for Office 365</span></span>](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="f30cc-110">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="f30cc-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="f30cc-111">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="f30cc-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="f30cc-112">När du har lagt till dessa poster i Office 365 är domänen konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="f30cc-112">After you add these records at Office 365, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="f30cc-113">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="f30cc-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f30cc-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f30cc-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f30cc-117">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="f30cc-117">Add a TXT record for verification</span></span>
<span data-ttu-id="f30cc-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f30cc-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f30cc-p102">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="f30cc-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f30cc-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="f30cc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f30cc-p104">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f30cc-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="f30cc-126">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f30cc-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f30cc-127">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-127">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="f30cc-129">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="f30cc-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f30cc-130">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="f30cc-131">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="f30cc-132">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f30cc-133">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="f30cc-133">**Host name**</span></span>|<span data-ttu-id="f30cc-134">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f30cc-134">**Type**</span></span>|<span data-ttu-id="f30cc-135">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="f30cc-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f30cc-136">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f30cc-137">TXT</span><span class="sxs-lookup"><span data-stu-id="f30cc-137">TXT</span></span>  <br/> |<span data-ttu-id="f30cc-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f30cc-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f30cc-p105">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f30cc-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="f30cc-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-143">Select **Save**.</span></span>
    
    <span data-ttu-id="f30cc-144">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-144">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="f30cc-146">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="f30cc-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f30cc-147">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="f30cc-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f30cc-148">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="f30cc-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f30cc-149">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="f30cc-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f30cc-150">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="f30cc-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f30cc-151">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f30cc-152">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f30cc-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f30cc-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f30cc-156">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="f30cc-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f30cc-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f30cc-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f30cc-p107">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f30cc-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="f30cc-161">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f30cc-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f30cc-162">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-162">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="f30cc-164">I avsnittet **Mail exchange records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="f30cc-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f30cc-165">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f30cc-166">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="f30cc-166">**Host name**</span></span>|<span data-ttu-id="f30cc-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f30cc-167">**Priority**</span></span>|<span data-ttu-id="f30cc-168">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="f30cc-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f30cc-169">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f30cc-170">1</span><span class="sxs-lookup"><span data-stu-id="f30cc-170">1</span></span>  <br/> <span data-ttu-id="f30cc-171">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="f30cc-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="f30cc-172">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f30cc-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f30cc-173">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="f30cc-173">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="f30cc-174">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="f30cc-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="f30cc-176">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-176">Select **Save**.</span></span>
    
    <span data-ttu-id="f30cc-177">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-177">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="f30cc-179">Om det finns andra MX-poster i avsnittet **Mail exchange records** tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="f30cc-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="f30cc-181">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-181">Select **Save**.</span></span>
    
    <span data-ttu-id="f30cc-182">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-182">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f30cc-184">Lägg till de sex CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="f30cc-184">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f30cc-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f30cc-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f30cc-p109">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f30cc-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="f30cc-189">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f30cc-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f30cc-190">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-190">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="f30cc-192">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för de nya posterna.</span><span class="sxs-lookup"><span data-stu-id="f30cc-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f30cc-193">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="f30cc-194">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="f30cc-195">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f30cc-196">\*\*\*\*Värdnamn\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f30cc-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="f30cc-197">\*\*\*\*Typ\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f30cc-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="f30cc-198">\*\*\*\*Resultat\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f30cc-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f30cc-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f30cc-199">autodiscover</span></span>  <br/> |<span data-ttu-id="f30cc-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="f30cc-200">CNAME</span></span>  <br/> |<span data-ttu-id="f30cc-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f30cc-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f30cc-202">sip</span><span class="sxs-lookup"><span data-stu-id="f30cc-202">sip</span></span>  <br/> |<span data-ttu-id="f30cc-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="f30cc-203">CNAME</span></span>  <br/> |<span data-ttu-id="f30cc-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f30cc-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f30cc-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f30cc-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f30cc-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="f30cc-206">CNAME</span></span>  <br/> |<span data-ttu-id="f30cc-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f30cc-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f30cc-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f30cc-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f30cc-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="f30cc-209">CNAME</span></span>  <br/> |<span data-ttu-id="f30cc-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f30cc-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="f30cc-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f30cc-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f30cc-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="f30cc-212">CNAME</span></span>  <br/> |<span data-ttu-id="f30cc-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f30cc-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="f30cc-215">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-215">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f30cc-217">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="f30cc-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f30cc-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f30cc-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f30cc-219">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="f30cc-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f30cc-220">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="f30cc-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f30cc-221">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="f30cc-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f30cc-222">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="f30cc-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="f30cc-p111">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f30cc-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="f30cc-226">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f30cc-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f30cc-227">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-227">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="f30cc-229">Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="f30cc-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f30cc-230">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="f30cc-231">(Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="f30cc-232">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f30cc-233">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="f30cc-233">**Host name**</span></span>|<span data-ttu-id="f30cc-234">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f30cc-234">**Type**</span></span>|<span data-ttu-id="f30cc-235">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="f30cc-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f30cc-236">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f30cc-237">TXT</span><span class="sxs-lookup"><span data-stu-id="f30cc-237">TXT</span></span>  <br/> |<span data-ttu-id="f30cc-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f30cc-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="f30cc-239">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="f30cc-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="f30cc-241">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-241">Select **Save**.</span></span>
    
    <span data-ttu-id="f30cc-242">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-242">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f30cc-244">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="f30cc-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f30cc-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f30cc-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f30cc-p112">Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f30cc-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="f30cc-249">På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f30cc-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f30cc-250">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-250">(You may have to scroll down.)</span></span>
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="f30cc-252">Under **Service records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för de nya posterna.</span><span class="sxs-lookup"><span data-stu-id="f30cc-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f30cc-253">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f30cc-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="f30cc-254">**Name**</span></span>|<span data-ttu-id="f30cc-255">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="f30cc-255">**Priority**</span></span>|<span data-ttu-id="f30cc-256">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="f30cc-256">**Weight**</span></span>|<span data-ttu-id="f30cc-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="f30cc-257">**Port**</span></span>|<span data-ttu-id="f30cc-258">**Result**</span><span class="sxs-lookup"><span data-stu-id="f30cc-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f30cc-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="f30cc-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="f30cc-260">100</span><span class="sxs-lookup"><span data-stu-id="f30cc-260">100</span></span>  <br/> |<span data-ttu-id="f30cc-261">1</span><span class="sxs-lookup"><span data-stu-id="f30cc-261">1</span></span>  <br/> |<span data-ttu-id="f30cc-262">443</span><span class="sxs-lookup"><span data-stu-id="f30cc-262">443</span></span>  <br/> |<span data-ttu-id="f30cc-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f30cc-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f30cc-264">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="f30cc-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="f30cc-265">100</span><span class="sxs-lookup"><span data-stu-id="f30cc-265">100</span></span>  <br/> |<span data-ttu-id="f30cc-266">1</span><span class="sxs-lookup"><span data-stu-id="f30cc-266">1</span></span>  <br/> |<span data-ttu-id="f30cc-267">5061</span><span class="sxs-lookup"><span data-stu-id="f30cc-267">5061</span></span>  <br/> |<span data-ttu-id="f30cc-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f30cc-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Ange värden i avsnittet Serviceposter](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="f30cc-270">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-270">Select **Save**.</span></span>
    
    <span data-ttu-id="f30cc-271">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="f30cc-271">(You may have to scroll down.)</span></span>
    
    ![Välj Spara](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="f30cc-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f30cc-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
