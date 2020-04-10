---
title: Skapa DNS-poster på MyDomain för Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Läs om hur du verifierar din domän och konfigurerar DNS-poster för e-post, Skype för företag – Online och andra tjänster på MyDomain för Office 365.
ms.openlocfilehash: 1a75c2ab0077cac07781e5102c43e53ed965b1df
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211697"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="5a42a-103">Skapa DNS-poster på MyDomain för Office 365</span><span class="sxs-lookup"><span data-stu-id="5a42a-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="5a42a-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5a42a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="5a42a-p101">MyDomain-webbplatsen har inget stöd för SRV-poster. Det innebär att flera Skype för företag - Online- och Outlook Web App-funktioner inte fungerar. Oavsett vilket Office 365-abonnemang du använder, och om du hanterar dina DNS-poster hos MyDomain, finns det [betydande tjänstbegränsningar](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) som kan innebära att du vill byta till en annan DNS-värdleverantör.</span><span class="sxs-lookup"><span data-stu-id="5a42a-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="5a42a-107">Om du väljer att hantera dina egna Office 365 DNS-poster hos MyDomain trots tjänstbegränsningarna utför du stegen i den här artikeln för att konfigurera DNS-posterna för e-post, Skype för företag - Online o.s.v.</span><span class="sxs-lookup"><span data-stu-id="5a42a-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="5a42a-108">När du har lagt till dessa poster på MyDomain är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="5a42a-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5a42a-109">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="5a42a-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a42a-p102">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5a42a-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5a42a-113">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="5a42a-113">Add a TXT record for verification</span></span>
<span data-ttu-id="5a42a-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5a42a-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5a42a-p103">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="5a42a-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a42a-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="5a42a-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5a42a-p105">Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5a42a-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5a42a-121">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="5a42a-122">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="5a42a-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="5a42a-123">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="5a42a-124">I listrutan **Modify** väljer du **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="5a42a-125">Under **Content**, i rutan för den nya posten, skriver du in, eller kopierar och klistrar in, värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5a42a-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="5a42a-126">**Content**</span><span class="sxs-lookup"><span data-stu-id="5a42a-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="5a42a-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5a42a-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5a42a-128">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="5a42a-128">**Note:** This is an example.</span></span> <span data-ttu-id="5a42a-129">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="5a42a-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="5a42a-130">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="5a42a-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="5a42a-131">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="5a42a-132">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="5a42a-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5a42a-133">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="5a42a-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5a42a-134">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="5a42a-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5a42a-135">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="5a42a-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5a42a-136">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="5a42a-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5a42a-137">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5a42a-138">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5a42a-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5a42a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5a42a-142">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="5a42a-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5a42a-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5a42a-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5a42a-p108">Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5a42a-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5a42a-146">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="5a42a-147">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="5a42a-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="5a42a-148">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="5a42a-149">Välj **MX Record** i listrutan **Modify**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="5a42a-151">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5a42a-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5a42a-152">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5a42a-152">**Priority**</span></span>|<span data-ttu-id="5a42a-153">**Värd**</span><span class="sxs-lookup"><span data-stu-id="5a42a-153">**Host**</span></span>|<span data-ttu-id="5a42a-154">**Points To: (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="5a42a-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5a42a-155">0</span><span class="sxs-lookup"><span data-stu-id="5a42a-155">0</span></span>  <br/> <span data-ttu-id="5a42a-156">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5a42a-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="5a42a-157">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5a42a-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5a42a-158">**Obs!** Hämta din \<*domännyckel*\> från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="5a42a-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="5a42a-159"> > [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="5a42a-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="5a42a-161">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="5a42a-163">Om det finns andra befintliga MX-poster väljer du **Remove** i kolumnen **Action** för var och en för att ta bort den.</span><span class="sxs-lookup"><span data-stu-id="5a42a-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="5a42a-165">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5a42a-167">Lägga till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="5a42a-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5a42a-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5a42a-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5a42a-p110">Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5a42a-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5a42a-171">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="5a42a-172">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="5a42a-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="5a42a-173">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="5a42a-174">Välj **CNAME Alias** i listrutan **Modify**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="5a42a-176">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="5a42a-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="5a42a-177">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5a42a-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="5a42a-178">**Värd**</span><span class="sxs-lookup"><span data-stu-id="5a42a-178">**Host**</span></span>|<span data-ttu-id="5a42a-179">**Points To: (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="5a42a-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5a42a-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5a42a-180">autodiscover</span></span>  <br/> |<span data-ttu-id="5a42a-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5a42a-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5a42a-182">sip</span><span class="sxs-lookup"><span data-stu-id="5a42a-182">sip</span></span>  <br/> |<span data-ttu-id="5a42a-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a42a-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5a42a-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5a42a-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5a42a-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a42a-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5a42a-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5a42a-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5a42a-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5a42a-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="5a42a-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5a42a-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5a42a-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5a42a-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="5a42a-191">Välj **Add** (lägg till) för att lägga till den första posten.</span><span class="sxs-lookup"><span data-stu-id="5a42a-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="5a42a-193">Lägg till den andra CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="5a42a-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="5a42a-194">Använd värden från den andra raden i tabellen ovan och välj sedan **Add** (lägg till) för att lägga till den andra posten.</span><span class="sxs-lookup"><span data-stu-id="5a42a-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="5a42a-195">Lägg till de återstående posterna på samma sätt med värdena från den tredje, fjärde, femte och sjätte raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="5a42a-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5a42a-196">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="5a42a-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5a42a-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5a42a-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a42a-198">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="5a42a-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5a42a-199">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="5a42a-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5a42a-200">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="5a42a-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5a42a-201">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="5a42a-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="5a42a-202">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="5a42a-202">Need examples?</span></span> <span data-ttu-id="5a42a-203">Ta en titt på dessa [externa DNS-poster för Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="5a42a-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="5a42a-204">Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5a42a-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="5a42a-p112">Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5a42a-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5a42a-207">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="5a42a-208">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="5a42a-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="5a42a-209">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="5a42a-210">I listrutan **Modify** väljer du **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="5a42a-212">Under **Content**, i rutan för den nya posten, skriver du in, eller kopierar och klistrar in, värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5a42a-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="5a42a-213">**Content**</span><span class="sxs-lookup"><span data-stu-id="5a42a-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="5a42a-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5a42a-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5a42a-215">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="5a42a-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="5a42a-217">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5a42a-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5a42a-219">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="5a42a-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5a42a-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5a42a-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="5a42a-p113">MyDomain-webbplatsen har inget stöd för SRV-poster. Det innebär att flera Skype för företag - Online- och Outlook Web App-funktioner inte fungerar. Oavsett vilket Office 365-abonnemang du använder, och om du hanterar dina DNS-poster hos MyDomain, finns det [betydande tjänstbegränsningar](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) som kan innebära att du vill byta till en annan DNS-värdleverantör.</span><span class="sxs-lookup"><span data-stu-id="5a42a-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5a42a-p114">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5a42a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
