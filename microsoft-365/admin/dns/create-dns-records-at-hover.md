---
title: Skapa DNS-poster på Hover for Microsoft
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Hover för Microsoft.
ms.openlocfilehash: 7d5222ba68858f9ad50c95a0123c2cd2943ea2c0
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939445"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="8c4ca-103">Skapa DNS-poster på Hover for Microsoft</span><span class="sxs-lookup"><span data-stu-id="8c4ca-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="8c4ca-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8c4ca-105">Om Hover är din DNS-värd följer du stegen i den här artikeln för att verifiera domänen och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="8c4ca-106">När du har lagt till dessa poster på Hover konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="8c4ca-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8c4ca-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="8c4ca-110">Add a TXT record for verification</span></span>
<span data-ttu-id="8c4ca-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8c4ca-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8c4ca-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c4ca-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="8c4ca-116">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8c4ca-116">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8c4ca-p104">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8c4ca-120">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8c4ca-122">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-122">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8c4ca-124">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-124">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8c4ca-126">I rutan för den nya posten väljer du **TXT** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="8c4ca-127">Hostname</span><span class="sxs-lookup"><span data-stu-id="8c4ca-127">Hostname</span></span>  <br/> |<span data-ttu-id="8c4ca-128">Record Type</span><span class="sxs-lookup"><span data-stu-id="8c4ca-128">Record Type</span></span>  <br/> |<span data-ttu-id="8c4ca-129">Value</span><span class="sxs-lookup"><span data-stu-id="8c4ca-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="8c4ca-130">TXT</span><span class="sxs-lookup"><span data-stu-id="8c4ca-130">TXT</span></span>  <br/> |<span data-ttu-id="8c4ca-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8c4ca-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8c4ca-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-132">**Note:** This is an example.</span></span> <span data-ttu-id="8c4ca-133">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="8c4ca-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="8c4ca-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="8c4ca-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-136">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="8c4ca-138">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8c4ca-139">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="8c4ca-140">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8c4ca-141">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8c4ca-142">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8c4ca-143">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8c4ca-144">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8c4ca-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8c4ca-148">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8c4ca-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8c4ca-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8c4ca-150">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8c4ca-150">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8c4ca-p107">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8c4ca-154">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8c4ca-156">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-156">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8c4ca-158">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-158">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8c4ca-160">I rutan för den nya posten väljer du **MX** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8c4ca-161">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-161">**Hostname**</span></span>|<span data-ttu-id="8c4ca-162">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-162">**Record Type**</span></span>|<span data-ttu-id="8c4ca-163">**Priority**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-163">**Priority**</span></span>|<span data-ttu-id="8c4ca-164">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8c4ca-165">MX</span><span class="sxs-lookup"><span data-stu-id="8c4ca-165">MX</span></span>  <br/> |<span data-ttu-id="8c4ca-166">0</span><span class="sxs-lookup"><span data-stu-id="8c4ca-166">0</span></span>  <br/> <span data-ttu-id="8c4ca-167">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c4ca-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="8c4ca-168">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8c4ca-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8c4ca-169">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="8c4ca-170">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="8c4ca-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="8c4ca-172">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-172">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="8c4ca-174">Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:</span><span class="sxs-lookup"><span data-stu-id="8c4ca-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="8c4ca-175">Välj först **Ta bort**en post som du vill ta bort .</span><span class="sxs-lookup"><span data-stu-id="8c4ca-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Musen över och välj Ta bort](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="8c4ca-177">För det andra väljer du **Ja** för att bekräfta varje borttagning.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Välj Ja för att bekräfta borttagning](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="8c4ca-179">Upprepa proceduren tills du har tagit bort alla MX-poster förutom den du lade till tidigare i proceduren.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8c4ca-180">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="8c4ca-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8c4ca-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8c4ca-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8c4ca-182">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8c4ca-182">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8c4ca-p109">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8c4ca-186">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8c4ca-188">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-188">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8c4ca-190">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="8c4ca-191">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-191">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8c4ca-193">I de tomma rutorna för den nya posten väljer du **CNAME** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="8c4ca-194">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-194">**Hostname**</span></span>|<span data-ttu-id="8c4ca-195">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-195">**Record Type**</span></span>|<span data-ttu-id="8c4ca-196">**Target Host**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8c4ca-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8c4ca-197">autodiscover</span></span>  <br/> |<span data-ttu-id="8c4ca-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c4ca-198">CNAME</span></span>  <br/> |<span data-ttu-id="8c4ca-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8c4ca-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="8c4ca-200">sip</span><span class="sxs-lookup"><span data-stu-id="8c4ca-200">sip</span></span>  <br/> |<span data-ttu-id="8c4ca-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c4ca-201">CNAME</span></span>  <br/> |<span data-ttu-id="8c4ca-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8c4ca-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8c4ca-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8c4ca-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8c4ca-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c4ca-204">CNAME</span></span>  <br/> |<span data-ttu-id="8c4ca-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8c4ca-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8c4ca-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8c4ca-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8c4ca-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c4ca-207">CNAME</span></span>  <br/> |<span data-ttu-id="8c4ca-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8c4ca-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="8c4ca-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8c4ca-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8c4ca-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c4ca-210">CNAME</span></span>  <br/> |<span data-ttu-id="8c4ca-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8c4ca-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="8c4ca-213">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-213">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="8c4ca-215">Du använder de tre föregående stegen när du lägger till de andra fem CNAME-posterna med värdena från de andra fem raderna i tabellen.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8c4ca-216">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="8c4ca-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8c4ca-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8c4ca-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c4ca-218">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8c4ca-219">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8c4ca-220">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8c4ca-221">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="8c4ca-222">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8c4ca-222">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8c4ca-p111">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8c4ca-226">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8c4ca-228">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-228">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8c4ca-230">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-230">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8c4ca-232">I rutan för den nya posten väljer du **TXT** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8c4ca-233">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-233">**Hostname**</span></span>|<span data-ttu-id="8c4ca-234">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-234">**Record Type**</span></span>|<span data-ttu-id="8c4ca-235">**Value (Värde)**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8c4ca-236">TXT</span><span class="sxs-lookup"><span data-stu-id="8c4ca-236">TXT</span></span>  <br/> |<span data-ttu-id="8c4ca-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8c4ca-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="8c4ca-238">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="8c4ca-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="8c4ca-240">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-240">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8c4ca-242">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="8c4ca-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8c4ca-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8c4ca-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="8c4ca-244">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8c4ca-244">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8c4ca-p112">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8c4ca-248">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8c4ca-250">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-250">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8c4ca-252">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="8c4ca-253">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-253">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8c4ca-255">I de tomma rutorna för den nya posten väljer du **SRV** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="8c4ca-256">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-256">**Hostname**</span></span>|<span data-ttu-id="8c4ca-257">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-257">**Record Type**</span></span>|<span data-ttu-id="8c4ca-258">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-258">**Priority**</span></span>|<span data-ttu-id="8c4ca-259">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-259">**Weight**</span></span>|<span data-ttu-id="8c4ca-260">**Port**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-260">**Port**</span></span>|<span data-ttu-id="8c4ca-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="8c4ca-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8c4ca-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="8c4ca-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="8c4ca-263">SRV</span><span class="sxs-lookup"><span data-stu-id="8c4ca-263">SRV</span></span>  <br/> |<span data-ttu-id="8c4ca-264">100</span><span class="sxs-lookup"><span data-stu-id="8c4ca-264">100</span></span>  <br/> |<span data-ttu-id="8c4ca-265">1</span><span class="sxs-lookup"><span data-stu-id="8c4ca-265">1</span></span>  <br/> |<span data-ttu-id="8c4ca-266">443</span><span class="sxs-lookup"><span data-stu-id="8c4ca-266">443</span></span>  <br/> |<span data-ttu-id="8c4ca-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8c4ca-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8c4ca-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8c4ca-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="8c4ca-269">SRV</span><span class="sxs-lookup"><span data-stu-id="8c4ca-269">SRV</span></span>  <br/> |<span data-ttu-id="8c4ca-270">100</span><span class="sxs-lookup"><span data-stu-id="8c4ca-270">100</span></span>  <br/> |<span data-ttu-id="8c4ca-271">1</span><span class="sxs-lookup"><span data-stu-id="8c4ca-271">1</span></span>  <br/> |<span data-ttu-id="8c4ca-272">5061</span><span class="sxs-lookup"><span data-stu-id="8c4ca-272">5061</span></span>  <br/> |<span data-ttu-id="8c4ca-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8c4ca-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="8c4ca-275">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-275">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="8c4ca-277">Du använder de tre föregående stegen när du lägger till den andra SRV-posten med värdena från tabellens andra rad.</span><span class="sxs-lookup"><span data-stu-id="8c4ca-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8c4ca-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8c4ca-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
