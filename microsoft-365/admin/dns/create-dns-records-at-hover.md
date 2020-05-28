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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Hover för Microsoft.
ms.openlocfilehash: 74662f37c3f72f02767f2434d9b251e3bd37ff1b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400431"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="a6f76-103">Skapa DNS-poster på Hover for Microsoft</span><span class="sxs-lookup"><span data-stu-id="a6f76-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="a6f76-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="a6f76-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a6f76-105">Om Hover är din DNS-värd följer du stegen i den här artikeln för att verifiera domänen och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="a6f76-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="a6f76-106">När du har lagt till dessa poster på Hover konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="a6f76-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="a6f76-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a6f76-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a6f76-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="a6f76-110">Add a TXT record for verification</span></span>
<span data-ttu-id="a6f76-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a6f76-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a6f76-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="a6f76-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6f76-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="a6f76-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a6f76-116">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a6f76-116">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a6f76-p104">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a6f76-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a6f76-120">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a6f76-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a6f76-122">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a6f76-122">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a6f76-124">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-124">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a6f76-126">I rutan för den nya posten väljer du **TXT** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a6f76-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="a6f76-127">Hostname</span><span class="sxs-lookup"><span data-stu-id="a6f76-127">Hostname</span></span>  <br/> |<span data-ttu-id="a6f76-128">Record Type</span><span class="sxs-lookup"><span data-stu-id="a6f76-128">Record Type</span></span>  <br/> |<span data-ttu-id="a6f76-129">Value</span><span class="sxs-lookup"><span data-stu-id="a6f76-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="a6f76-130">TXT</span><span class="sxs-lookup"><span data-stu-id="a6f76-130">TXT</span></span>  <br/> |<span data-ttu-id="a6f76-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a6f76-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a6f76-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="a6f76-132">**Note:** This is an example.</span></span> <span data-ttu-id="a6f76-133">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="a6f76-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a6f76-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="a6f76-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="a6f76-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-136">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="a6f76-138">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="a6f76-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a6f76-139">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="a6f76-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="a6f76-140">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="a6f76-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a6f76-141">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="a6f76-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a6f76-142">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="a6f76-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a6f76-143">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a6f76-144">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a6f76-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a6f76-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a6f76-148">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6f76-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a6f76-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a6f76-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a6f76-150">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a6f76-150">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a6f76-p107">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a6f76-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a6f76-154">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a6f76-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a6f76-156">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a6f76-156">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a6f76-158">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-158">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a6f76-160">I rutan för den nya posten väljer du **MX** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a6f76-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a6f76-161">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a6f76-161">**Hostname**</span></span>|<span data-ttu-id="a6f76-162">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a6f76-162">**Record Type**</span></span>|<span data-ttu-id="a6f76-163">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a6f76-163">**Priority**</span></span>|<span data-ttu-id="a6f76-164">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a6f76-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a6f76-165">MX</span><span class="sxs-lookup"><span data-stu-id="a6f76-165">MX</span></span>  <br/> |<span data-ttu-id="a6f76-166">0</span><span class="sxs-lookup"><span data-stu-id="a6f76-166">0</span></span>  <br/> <span data-ttu-id="a6f76-167">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="a6f76-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="a6f76-168">*\<domain-key\>*.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a6f76-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a6f76-169">**Anm.:** Hämta ditt *\<domain-key\>* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="a6f76-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="a6f76-170">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="a6f76-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="a6f76-172">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-172">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="a6f76-174">Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:</span><span class="sxs-lookup"><span data-stu-id="a6f76-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="a6f76-175">Välj först **Ta bort**en post som du vill ta bort .</span><span class="sxs-lookup"><span data-stu-id="a6f76-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Musen över och välj Ta bort](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="a6f76-177">För det andra väljer du **Ja** för att bekräfta varje borttagning.</span><span class="sxs-lookup"><span data-stu-id="a6f76-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Välj Ja för att bekräfta borttagning](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="a6f76-179">Upprepa proceduren tills du har tagit bort alla MX-poster förutom den du lade till tidigare i proceduren.</span><span class="sxs-lookup"><span data-stu-id="a6f76-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a6f76-180">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a6f76-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a6f76-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a6f76-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a6f76-182">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a6f76-182">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a6f76-p109">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a6f76-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a6f76-186">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a6f76-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a6f76-188">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a6f76-188">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a6f76-190">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="a6f76-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a6f76-191">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-191">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a6f76-193">I de tomma rutorna för den nya posten väljer du **CNAME** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a6f76-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a6f76-194">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a6f76-194">**Hostname**</span></span>|<span data-ttu-id="a6f76-195">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a6f76-195">**Record Type**</span></span>|<span data-ttu-id="a6f76-196">**Target Host**</span><span class="sxs-lookup"><span data-stu-id="a6f76-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a6f76-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a6f76-197">autodiscover</span></span>  <br/> |<span data-ttu-id="a6f76-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6f76-198">CNAME</span></span>  <br/> |<span data-ttu-id="a6f76-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a6f76-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a6f76-200">sip</span><span class="sxs-lookup"><span data-stu-id="a6f76-200">sip</span></span>  <br/> |<span data-ttu-id="a6f76-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6f76-201">CNAME</span></span>  <br/> |<span data-ttu-id="a6f76-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a6f76-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a6f76-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a6f76-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a6f76-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6f76-204">CNAME</span></span>  <br/> |<span data-ttu-id="a6f76-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a6f76-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a6f76-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a6f76-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a6f76-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6f76-207">CNAME</span></span>  <br/> |<span data-ttu-id="a6f76-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a6f76-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a6f76-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a6f76-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a6f76-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6f76-210">CNAME</span></span>  <br/> |<span data-ttu-id="a6f76-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a6f76-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="a6f76-213">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-213">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="a6f76-215">Du använder de tre föregående stegen när du lägger till de andra fem CNAME-posterna med värdena från de andra fem raderna i tabellen.</span><span class="sxs-lookup"><span data-stu-id="a6f76-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a6f76-216">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="a6f76-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a6f76-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a6f76-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6f76-218">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="a6f76-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a6f76-219">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="a6f76-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a6f76-220">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6f76-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a6f76-221">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="a6f76-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="a6f76-222">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a6f76-222">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a6f76-p111">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a6f76-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a6f76-226">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a6f76-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a6f76-228">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a6f76-228">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a6f76-230">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-230">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a6f76-232">I rutan för den nya posten väljer du **TXT** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a6f76-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a6f76-233">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a6f76-233">**Hostname**</span></span>|<span data-ttu-id="a6f76-234">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a6f76-234">**Record Type**</span></span>|<span data-ttu-id="a6f76-235">**Value (Värde)**</span><span class="sxs-lookup"><span data-stu-id="a6f76-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a6f76-236">TXT</span><span class="sxs-lookup"><span data-stu-id="a6f76-236">TXT</span></span>  <br/> |<span data-ttu-id="a6f76-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a6f76-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="a6f76-238">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="a6f76-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="a6f76-240">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-240">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a6f76-242">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a6f76-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a6f76-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a6f76-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a6f76-244">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a6f76-244">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a6f76-p112">Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a6f76-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a6f76-248">Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a6f76-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a6f76-250">Välj fliken **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a6f76-250">Select the **DNS** tab.</span></span> 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a6f76-252">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="a6f76-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a6f76-253">Välj **Lägg till ny**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-253">Select **Add New**.</span></span>
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a6f76-255">I de tomma rutorna för den nya posten väljer du **SRV** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a6f76-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a6f76-256">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a6f76-256">**Hostname**</span></span>|<span data-ttu-id="a6f76-257">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a6f76-257">**Record Type**</span></span>|<span data-ttu-id="a6f76-258">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="a6f76-258">**Priority**</span></span>|<span data-ttu-id="a6f76-259">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="a6f76-259">**Weight**</span></span>|<span data-ttu-id="a6f76-260">**Port**</span><span class="sxs-lookup"><span data-stu-id="a6f76-260">**Port**</span></span>|<span data-ttu-id="a6f76-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="a6f76-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a6f76-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a6f76-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="a6f76-263">SRV</span><span class="sxs-lookup"><span data-stu-id="a6f76-263">SRV</span></span>  <br/> |<span data-ttu-id="a6f76-264">100</span><span class="sxs-lookup"><span data-stu-id="a6f76-264">100</span></span>  <br/> |<span data-ttu-id="a6f76-265">1</span><span class="sxs-lookup"><span data-stu-id="a6f76-265">1</span></span>  <br/> |<span data-ttu-id="a6f76-266">443</span><span class="sxs-lookup"><span data-stu-id="a6f76-266">443</span></span>  <br/> |<span data-ttu-id="a6f76-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a6f76-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a6f76-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a6f76-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a6f76-269">SRV</span><span class="sxs-lookup"><span data-stu-id="a6f76-269">SRV</span></span>  <br/> |<span data-ttu-id="a6f76-270">100</span><span class="sxs-lookup"><span data-stu-id="a6f76-270">100</span></span>  <br/> |<span data-ttu-id="a6f76-271">1</span><span class="sxs-lookup"><span data-stu-id="a6f76-271">1</span></span>  <br/> |<span data-ttu-id="a6f76-272">5061</span><span class="sxs-lookup"><span data-stu-id="a6f76-272">5061</span></span>  <br/> |<span data-ttu-id="a6f76-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a6f76-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="a6f76-275">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a6f76-275">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="a6f76-277">Du använder de tre föregående stegen när du lägger till den andra SRV-posten med värdena från tabellens andra rad.</span><span class="sxs-lookup"><span data-stu-id="a6f76-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a6f76-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a6f76-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
