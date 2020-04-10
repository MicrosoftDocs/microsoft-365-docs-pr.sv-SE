---
title: Skapa DNS-poster på Dyn.com för Office 365
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Dyn.com för Office 365.
ms.openlocfilehash: d25d4d9712dcd2e2a171c6ad0eac70b8c01e75ab
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211781"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="48c15-103">Skapa DNS-poster på Dyn.com för Office 365</span><span class="sxs-lookup"><span data-stu-id="48c15-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="48c15-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="48c15-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="48c15-105">Om Dyn.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="48c15-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="48c15-106">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="48c15-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="48c15-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="48c15-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="48c15-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="48c15-110">Add a TXT record for verification</span></span>
<span data-ttu-id="48c15-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="48c15-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="48c15-p102">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="48c15-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="48c15-115">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="48c15-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="48c15-116">Välj **Inställningar**på **DNS-sidan** för domänen .</span><span class="sxs-lookup"><span data-stu-id="48c15-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="48c15-117">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="48c15-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="48c15-118">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="48c15-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="48c15-119">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="48c15-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="48c15-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="48c15-120">**Host**</span></span>|<span data-ttu-id="48c15-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48c15-121">**TTL**</span></span>|<span data-ttu-id="48c15-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="48c15-122">**Type**</span></span>|<span data-ttu-id="48c15-123">**Data**</span><span class="sxs-lookup"><span data-stu-id="48c15-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48c15-124">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="48c15-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="48c15-125">600</span><span class="sxs-lookup"><span data-stu-id="48c15-125">600</span></span>  <br/> |<span data-ttu-id="48c15-126">TXT</span><span class="sxs-lookup"><span data-stu-id="48c15-126">TXT</span></span>  <br/> |<span data-ttu-id="48c15-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="48c15-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="48c15-p103">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="48c15-p103">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![Dyn-BP-Verifiera-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="48c15-132">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="48c15-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="48c15-134">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="48c15-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="48c15-135">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="48c15-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="48c15-136">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="48c15-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="48c15-137">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="48c15-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="48c15-138">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="48c15-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="48c15-139">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="48c15-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="48c15-140">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="48c15-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="48c15-p104">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="48c15-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="48c15-144">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="48c15-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="48c15-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="48c15-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="48c15-p105">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="48c15-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="48c15-149">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="48c15-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="48c15-150">Välj **Inställningar**på DNS-sidan för domänen .</span><span class="sxs-lookup"><span data-stu-id="48c15-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="48c15-151">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="48c15-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="48c15-152">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="48c15-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="48c15-153">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="48c15-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="48c15-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="48c15-154">**Host**</span></span>|<span data-ttu-id="48c15-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48c15-155">**TTL**</span></span>|<span data-ttu-id="48c15-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="48c15-156">**Type**</span></span>|<span data-ttu-id="48c15-157">**Data**</span><span class="sxs-lookup"><span data-stu-id="48c15-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48c15-158">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="48c15-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="48c15-159">600</span><span class="sxs-lookup"><span data-stu-id="48c15-159">600</span></span>  <br/> |<span data-ttu-id="48c15-160">MX</span><span class="sxs-lookup"><span data-stu-id="48c15-160">MX</span></span>  <br/> |<span data-ttu-id="48c15-161">10  *\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="48c15-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="48c15-162">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48c15-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="48c15-p106">**10** motsvarar MX-prioritetsvärdet. Skriv 10 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="48c15-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="48c15-165">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="48c15-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="48c15-166">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="48c15-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="48c15-167">[Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="48c15-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-Konfigurera-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="48c15-169">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="48c15-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP - Konfigurera-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="48c15-171">Om det finns andra MX-poster tar du bort dem genom att markera kryssrutan för varje post i kolumnen **Delete**.</span><span class="sxs-lookup"><span data-stu-id="48c15-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP - Konfigurera-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="48c15-173">Välj **Använd ändringar**.</span><span class="sxs-lookup"><span data-stu-id="48c15-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP - Konfigurera-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="48c15-175">Lägg till de sex CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="48c15-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="48c15-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="48c15-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="48c15-p108">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="48c15-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="48c15-180">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="48c15-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="48c15-181">Välj **Inställningar**på **DNS-sidan** för domänen .</span><span class="sxs-lookup"><span data-stu-id="48c15-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="48c15-182">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="48c15-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="48c15-183">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="48c15-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="48c15-184">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="48c15-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="48c15-185">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="48c15-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="48c15-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="48c15-186">**Host**</span></span>|<span data-ttu-id="48c15-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48c15-187">**TTL**</span></span>|<span data-ttu-id="48c15-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="48c15-188">**Type**</span></span>|<span data-ttu-id="48c15-189">**Data**</span><span class="sxs-lookup"><span data-stu-id="48c15-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48c15-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="48c15-190">autodiscover</span></span>  <br/> |<span data-ttu-id="48c15-191">600</span><span class="sxs-lookup"><span data-stu-id="48c15-191">600</span></span>  <br/> |<span data-ttu-id="48c15-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="48c15-192">CNAME</span></span>  <br/> |<span data-ttu-id="48c15-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="48c15-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="48c15-194">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48c15-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48c15-195">sip</span><span class="sxs-lookup"><span data-stu-id="48c15-195">sip</span></span>  <br/> |<span data-ttu-id="48c15-196">600</span><span class="sxs-lookup"><span data-stu-id="48c15-196">600</span></span>  <br/> |<span data-ttu-id="48c15-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="48c15-197">CNAME</span></span>  <br/> |<span data-ttu-id="48c15-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48c15-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="48c15-199">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48c15-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48c15-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="48c15-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="48c15-201">600</span><span class="sxs-lookup"><span data-stu-id="48c15-201">600</span></span>  <br/> |<span data-ttu-id="48c15-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="48c15-202">CNAME</span></span>  <br/> |<span data-ttu-id="48c15-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48c15-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="48c15-204">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48c15-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48c15-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="48c15-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="48c15-206">600</span><span class="sxs-lookup"><span data-stu-id="48c15-206">600</span></span>  <br/> |<span data-ttu-id="48c15-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="48c15-207">CNAME</span></span>  <br/> |<span data-ttu-id="48c15-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="48c15-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="48c15-209">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48c15-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48c15-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="48c15-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="48c15-211">600</span><span class="sxs-lookup"><span data-stu-id="48c15-211">600</span></span>  <br/> |<span data-ttu-id="48c15-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="48c15-212">CNAME</span></span>  <br/> |<span data-ttu-id="48c15-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="48c15-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="48c15-214">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48c15-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-Konfigurera-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="48c15-216">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="48c15-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP - Konfigurera-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="48c15-218">Lägg till de återstående fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="48c15-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="48c15-219">Skapa en post i avsnittet **Lägg till DNS-post** med hjälp av värdena från nästa rad i tabellen och välj sedan **skapa post** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="48c15-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="48c15-220">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="48c15-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="48c15-221">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="48c15-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="48c15-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="48c15-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="48c15-223">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="48c15-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="48c15-224">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="48c15-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="48c15-225">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="48c15-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="48c15-226">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="48c15-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="48c15-p110">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="48c15-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="48c15-230">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="48c15-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="48c15-231">Välj **Inställningar**på **DNS-sidan** för domänen .</span><span class="sxs-lookup"><span data-stu-id="48c15-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="48c15-232">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="48c15-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="48c15-233">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="48c15-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="48c15-234">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="48c15-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="48c15-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="48c15-235">**Host**</span></span>|<span data-ttu-id="48c15-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48c15-236">**TTL**</span></span>|<span data-ttu-id="48c15-237">**Type**</span><span class="sxs-lookup"><span data-stu-id="48c15-237">**Type**</span></span>|<span data-ttu-id="48c15-238">**Data**</span><span class="sxs-lookup"><span data-stu-id="48c15-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48c15-239">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="48c15-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="48c15-240">600</span><span class="sxs-lookup"><span data-stu-id="48c15-240">600</span></span>  <br/> |<span data-ttu-id="48c15-241">TXT</span><span class="sxs-lookup"><span data-stu-id="48c15-241">TXT</span></span>  <br/> |<span data-ttu-id="48c15-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="48c15-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="48c15-243">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="48c15-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Konfigurera-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="48c15-245">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="48c15-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP - Konfigurera-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="48c15-247">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="48c15-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="48c15-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="48c15-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="48c15-249">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="48c15-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="48c15-250">Du uppmanas att logga in först</span><span class="sxs-lookup"><span data-stu-id="48c15-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="48c15-252">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="48c15-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="48c15-253">Välj **Inställningar**på **DNS-sidan** för domänen .</span><span class="sxs-lookup"><span data-stu-id="48c15-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="48c15-254">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="48c15-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="48c15-255">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="48c15-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="48c15-256">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="48c15-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="48c15-257">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="48c15-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="48c15-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="48c15-258">**Host**</span></span>|<span data-ttu-id="48c15-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48c15-259">**TTL**</span></span>|<span data-ttu-id="48c15-260">**Type**</span><span class="sxs-lookup"><span data-stu-id="48c15-260">**Type**</span></span>|<span data-ttu-id="48c15-261">**Data**</span><span class="sxs-lookup"><span data-stu-id="48c15-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48c15-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="48c15-262">_sip._tls</span></span>|<span data-ttu-id="48c15-263">600</span><span class="sxs-lookup"><span data-stu-id="48c15-263">600</span></span>|<span data-ttu-id="48c15-264">SRV</span><span class="sxs-lookup"><span data-stu-id="48c15-264">SRV</span></span>|<span data-ttu-id="48c15-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48c15-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="48c15-266">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48c15-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="48c15-267">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="48c15-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="48c15-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="48c15-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="48c15-269">600</span><span class="sxs-lookup"><span data-stu-id="48c15-269">600</span></span>|<span data-ttu-id="48c15-270">SRV</span><span class="sxs-lookup"><span data-stu-id="48c15-270">SRV</span></span>|<span data-ttu-id="48c15-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48c15-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="48c15-272">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48c15-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="48c15-273">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="48c15-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Konfigurera-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="48c15-275">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="48c15-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP - Konfigurera-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="48c15-277">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="48c15-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="48c15-278">Skapa en post i avsnittet **Lägg till DNS-post** med hjälp av värdena från den andra raden i tabellen och välj sedan **skapa post** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="48c15-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="48c15-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="48c15-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
