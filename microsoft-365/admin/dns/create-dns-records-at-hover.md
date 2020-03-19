---
title: Skapa DNS-poster på Hover för Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Hover för Office 365.
ms.openlocfilehash: 72df2d98f3446087a1e9796cd616293a91003ad9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42813036"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="a7105-103">Skapa DNS-poster på Hover för Office 365</span><span class="sxs-lookup"><span data-stu-id="a7105-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="a7105-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="a7105-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a7105-105">Om Hover är din DNS-värd följer du stegen i den här artikeln för att verifiera domänen och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="a7105-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="a7105-106">När du har lagt till dessa poster på Hover är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="a7105-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="a7105-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="a7105-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a7105-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7105-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a7105-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="a7105-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a7105-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a7105-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a7105-p102">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="a7105-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7105-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="a7105-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a7105-117">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a7105-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a7105-p104">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a7105-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a7105-121">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a7105-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a7105-123">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a7105-123">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a7105-125">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a7105-125">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a7105-127">I rutan för den nya posten väljer du **TXT** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a7105-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="a7105-128">Hostname</span><span class="sxs-lookup"><span data-stu-id="a7105-128">Hostname</span></span>  <br/> |<span data-ttu-id="a7105-129">Record Type</span><span class="sxs-lookup"><span data-stu-id="a7105-129">Record Type</span></span>  <br/> |<span data-ttu-id="a7105-130">Value</span><span class="sxs-lookup"><span data-stu-id="a7105-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="a7105-131">TXT</span><span class="sxs-lookup"><span data-stu-id="a7105-131">TXT</span></span>  <br/> |<span data-ttu-id="a7105-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a7105-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a7105-p105">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="a7105-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="a7105-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a7105-137">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="a7105-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="a7105-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a7105-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="a7105-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a7105-141">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="a7105-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a7105-142">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="a7105-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a7105-143">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="a7105-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a7105-144">Välj **Starta inställningar**på sidan **Inställningar** .</span><span class="sxs-lookup"><span data-stu-id="a7105-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a7105-145">På sidan **Verifiera domän** väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="a7105-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a7105-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7105-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a7105-149">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="a7105-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a7105-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a7105-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a7105-151">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a7105-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a7105-p107">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a7105-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a7105-155">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a7105-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a7105-157">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a7105-157">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a7105-159">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a7105-159">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a7105-161">I rutan för den nya posten väljer du **MX** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a7105-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a7105-162">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a7105-162">**Hostname**</span></span>|<span data-ttu-id="a7105-163">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a7105-163">**Record Type**</span></span>|<span data-ttu-id="a7105-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a7105-164">**Priority**</span></span>|<span data-ttu-id="a7105-165">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a7105-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a7105-166">MX</span><span class="sxs-lookup"><span data-stu-id="a7105-166">MX</span></span>  <br/> |<span data-ttu-id="a7105-167">0</span><span class="sxs-lookup"><span data-stu-id="a7105-167">0</span></span>  <br/> <span data-ttu-id="a7105-168">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7105-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="a7105-169">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7105-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a7105-170">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="a7105-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="a7105-171">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="a7105-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="a7105-173">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a7105-173">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="a7105-175">Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:</span><span class="sxs-lookup"><span data-stu-id="a7105-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="a7105-176">Välj först **Ta bort**en post som du vill ta bort .</span><span class="sxs-lookup"><span data-stu-id="a7105-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Musen över och välj Ta bort](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="a7105-178">För det andra väljer du **Ja** för att bekräfta varje borttagning.</span><span class="sxs-lookup"><span data-stu-id="a7105-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Välj Ja för att bekräfta borttagning](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="a7105-180">Upprepa proceduren tills du har tagit bort alla MX-poster förutom den du lade till tidigare i proceduren.</span><span class="sxs-lookup"><span data-stu-id="a7105-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a7105-181">Lägg till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="a7105-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a7105-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a7105-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a7105-183">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a7105-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a7105-p109">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a7105-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a7105-187">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a7105-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a7105-189">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a7105-189">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a7105-191">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="a7105-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a7105-192">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a7105-192">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a7105-194">I de tomma rutorna för den nya posten väljer du **CNAME** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a7105-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a7105-195">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a7105-195">**Hostname**</span></span>|<span data-ttu-id="a7105-196">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a7105-196">**Record Type**</span></span>|<span data-ttu-id="a7105-197">**Target Host**</span><span class="sxs-lookup"><span data-stu-id="a7105-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a7105-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a7105-198">autodiscover</span></span>  <br/> |<span data-ttu-id="a7105-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7105-199">CNAME</span></span>  <br/> |<span data-ttu-id="a7105-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7105-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a7105-201">sip</span><span class="sxs-lookup"><span data-stu-id="a7105-201">sip</span></span>  <br/> |<span data-ttu-id="a7105-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7105-202">CNAME</span></span>  <br/> |<span data-ttu-id="a7105-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7105-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7105-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a7105-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a7105-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7105-205">CNAME</span></span>  <br/> |<span data-ttu-id="a7105-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7105-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7105-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a7105-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a7105-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7105-208">CNAME</span></span>  <br/> |<span data-ttu-id="a7105-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a7105-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a7105-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a7105-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a7105-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7105-211">CNAME</span></span>  <br/> |<span data-ttu-id="a7105-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a7105-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="a7105-214">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a7105-214">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="a7105-216">Du använder de tre föregående stegen när du lägger till de andra fem CNAME-posterna med värdena från de andra fem raderna i tabellen.</span><span class="sxs-lookup"><span data-stu-id="a7105-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a7105-217">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="a7105-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a7105-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a7105-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7105-219">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="a7105-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a7105-220">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="a7105-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a7105-221">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7105-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a7105-222">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="a7105-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="a7105-223">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a7105-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a7105-p111">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a7105-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a7105-227">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a7105-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a7105-229">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a7105-229">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a7105-231">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a7105-231">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a7105-233">I rutan för den nya posten väljer du **TXT** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a7105-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a7105-234">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a7105-234">**Hostname**</span></span>|<span data-ttu-id="a7105-235">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a7105-235">**Record Type**</span></span>|<span data-ttu-id="a7105-236">**Value (Värde)**</span><span class="sxs-lookup"><span data-stu-id="a7105-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a7105-237">TXT</span><span class="sxs-lookup"><span data-stu-id="a7105-237">TXT</span></span>  <br/> |<span data-ttu-id="a7105-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a7105-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="a7105-239">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="a7105-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="a7105-241">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a7105-241">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a7105-243">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="a7105-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a7105-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a7105-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a7105-245">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a7105-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a7105-p112">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a7105-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a7105-249">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a7105-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a7105-251">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a7105-251">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a7105-253">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="a7105-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a7105-254">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a7105-254">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a7105-256">I de tomma rutorna för den nya posten väljer du **SRV** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a7105-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a7105-257">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a7105-257">**Hostname**</span></span>|<span data-ttu-id="a7105-258">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a7105-258">**Record Type**</span></span>|<span data-ttu-id="a7105-259">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a7105-259">**Priority**</span></span>|<span data-ttu-id="a7105-260">**Weight**</span><span class="sxs-lookup"><span data-stu-id="a7105-260">**Weight**</span></span>|<span data-ttu-id="a7105-261">**Port**</span><span class="sxs-lookup"><span data-stu-id="a7105-261">**Port**</span></span>|<span data-ttu-id="a7105-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="a7105-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7105-263">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a7105-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="a7105-264">SRV</span><span class="sxs-lookup"><span data-stu-id="a7105-264">SRV</span></span>  <br/> |<span data-ttu-id="a7105-265">100</span><span class="sxs-lookup"><span data-stu-id="a7105-265">100</span></span>  <br/> |<span data-ttu-id="a7105-266">1</span><span class="sxs-lookup"><span data-stu-id="a7105-266">1</span></span>  <br/> |<span data-ttu-id="a7105-267">443</span><span class="sxs-lookup"><span data-stu-id="a7105-267">443</span></span>  <br/> |<span data-ttu-id="a7105-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7105-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7105-269">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a7105-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a7105-270">SRV</span><span class="sxs-lookup"><span data-stu-id="a7105-270">SRV</span></span>  <br/> |<span data-ttu-id="a7105-271">100</span><span class="sxs-lookup"><span data-stu-id="a7105-271">100</span></span>  <br/> |<span data-ttu-id="a7105-272">1</span><span class="sxs-lookup"><span data-stu-id="a7105-272">1</span></span>  <br/> |<span data-ttu-id="a7105-273">5061</span><span class="sxs-lookup"><span data-stu-id="a7105-273">5061</span></span>  <br/> |<span data-ttu-id="a7105-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7105-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="a7105-276">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a7105-276">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="a7105-278">Du använder de tre föregående stegen när du lägger till den andra SRV-posten med värdena från tabellens andra rad.</span><span class="sxs-lookup"><span data-stu-id="a7105-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7105-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7105-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
