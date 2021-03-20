---
title: Skapa DNS-poster på name.com för Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på name.com för Microsoft.
ms.openlocfilehash: 97cc83fe060f8fbfe78decff584bded3102b09b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910180"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="55344-103">Skapa DNS-poster på name.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="55344-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="55344-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="55344-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="55344-105">Om name.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="55344-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="55344-106">När du har lagt till dessa name.com domän är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="55344-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="55344-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="55344-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="55344-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="55344-110">Add a TXT record for verification</span></span>
<span data-ttu-id="55344-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="55344-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="55344-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="55344-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55344-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="55344-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="55344-p104">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="55344-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="55344-119">Under **My Domains** väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="55344-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="55344-121">Välj DNS **Records** i **kolumnen Details.**</span><span class="sxs-lookup"><span data-stu-id="55344-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="55344-123">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="55344-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="55344-124">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="55344-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="55344-125">**Typ**</span><span class="sxs-lookup"><span data-stu-id="55344-125">**Type**</span></span> <br/> |<span data-ttu-id="55344-126">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="55344-126">**Host**</span></span> <br/> |<span data-ttu-id="55344-127">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="55344-127">**Answer**</span></span> <br/> |<span data-ttu-id="55344-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="55344-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="55344-129">TXT</span><span class="sxs-lookup"><span data-stu-id="55344-129">TXT</span></span>  <br/> |<span data-ttu-id="55344-130">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="55344-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="55344-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="55344-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="55344-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="55344-132">**Note:** This is an example.</span></span> <span data-ttu-id="55344-133">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="55344-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="55344-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="55344-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="55344-135">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-135">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="55344-137">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="55344-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="55344-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="55344-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="55344-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="55344-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="55344-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="55344-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="55344-142">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="55344-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="55344-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="55344-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="55344-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="55344-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="55344-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="55344-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="55344-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="55344-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="55344-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55344-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="55344-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="55344-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="55344-p107">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="55344-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="55344-154">Under **My Domains** väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="55344-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="55344-156">Välj DNS **Records** i **kolumnen Details.**</span><span class="sxs-lookup"><span data-stu-id="55344-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="55344-158">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="55344-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="55344-159">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="55344-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="55344-160">**Typ**</span><span class="sxs-lookup"><span data-stu-id="55344-160">**Type**</span></span>|<span data-ttu-id="55344-161">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="55344-161">**Host**</span></span>|<span data-ttu-id="55344-162">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="55344-162">**Answer**</span></span>|<span data-ttu-id="55344-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="55344-163">**TTL**</span></span>|<span data-ttu-id="55344-164">**Prio**</span><span class="sxs-lookup"><span data-stu-id="55344-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="55344-165">MX</span><span class="sxs-lookup"><span data-stu-id="55344-165">MX</span></span>  <br/> |<span data-ttu-id="55344-166">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="55344-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="55344-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="55344-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="55344-168">**Obs!** Skaffa ditt  *\<domain-key\>*  Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="55344-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="55344-169">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="55344-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="55344-170">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="55344-171">0</span><span class="sxs-lookup"><span data-stu-id="55344-171">0</span></span>  <br/> <span data-ttu-id="55344-172">Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="55344-172">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="55344-174">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="55344-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="55344-176">Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:</span><span class="sxs-lookup"><span data-stu-id="55344-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="55344-177">För varje MX-post väljer du **Delete** i **kolumnen Actions.**</span><span class="sxs-lookup"><span data-stu-id="55344-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="55344-179">Bekräfta varje borttagning genom att välja **Ta bort** i **kolumnen Åtgärder** igen.</span><span class="sxs-lookup"><span data-stu-id="55344-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="55344-181">Upprepa den här tvåstegsproceduren tills du har tagit bort alla de andra MX-posterna.</span><span class="sxs-lookup"><span data-stu-id="55344-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="55344-182">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="55344-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="55344-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="55344-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="55344-p109">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="55344-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="55344-187">Under **My Domains** väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="55344-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="55344-189">Välj DNS **Records** i **kolumnen Details.**</span><span class="sxs-lookup"><span data-stu-id="55344-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="55344-191">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="55344-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="55344-192">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="55344-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="55344-193">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="55344-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="55344-194">**Typ**</span><span class="sxs-lookup"><span data-stu-id="55344-194">**Type**</span></span>|<span data-ttu-id="55344-195">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="55344-195">**Host**</span></span>|<span data-ttu-id="55344-196">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="55344-196">**Answer**</span></span>|<span data-ttu-id="55344-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="55344-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="55344-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="55344-198">CNAME</span></span>  <br/> |<span data-ttu-id="55344-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="55344-199">autodiscover</span></span>  <br/> |<span data-ttu-id="55344-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="55344-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="55344-201">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="55344-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="55344-202">CNAME</span></span>  <br/> |<span data-ttu-id="55344-203">sip</span><span class="sxs-lookup"><span data-stu-id="55344-203">sip</span></span>  <br/> |<span data-ttu-id="55344-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="55344-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="55344-205">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="55344-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="55344-206">CNAME</span></span>  <br/> |<span data-ttu-id="55344-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="55344-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="55344-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="55344-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="55344-209">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="55344-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="55344-210">CNAME</span></span>  <br/> |<span data-ttu-id="55344-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="55344-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="55344-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="55344-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="55344-213">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="55344-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="55344-214">CNAME</span></span>  <br/> |<span data-ttu-id="55344-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="55344-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="55344-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="55344-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="55344-217">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="55344-219">Välj **Add Record (lägg** till post) för att lägga till den första posten.</span><span class="sxs-lookup"><span data-stu-id="55344-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="55344-221">Lägg till den andra CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="55344-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="55344-222">Använd värdena från den andra raden i tabellen ovan och välj sedan Add Record (lägg **till post) för** att lägga till den andra posten.</span><span class="sxs-lookup"><span data-stu-id="55344-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="55344-223">Lägg till de återstående posterna på samma sätt med värdena från den tredje, fjärde, femte och sjätte raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="55344-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="55344-224">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="55344-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="55344-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="55344-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="55344-226">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="55344-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="55344-227">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="55344-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="55344-228">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55344-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="55344-229">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="55344-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="55344-p111">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="55344-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="55344-233">Under **My Domains** väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="55344-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="55344-235">Välj DNS **Records** i **kolumnen Details.**</span><span class="sxs-lookup"><span data-stu-id="55344-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="55344-237">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="55344-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="55344-238">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="55344-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="55344-239">**Typ**</span><span class="sxs-lookup"><span data-stu-id="55344-239">**Type**</span></span>|<span data-ttu-id="55344-240">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="55344-240">**Host**</span></span>|<span data-ttu-id="55344-241">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="55344-241">**Answer**</span></span>|<span data-ttu-id="55344-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="55344-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="55344-243">TXT</span><span class="sxs-lookup"><span data-stu-id="55344-243">TXT</span></span>  <br/> |<span data-ttu-id="55344-244">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="55344-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="55344-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="55344-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="55344-246">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="55344-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="55344-247">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="55344-249">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="55344-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="55344-251">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="55344-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="55344-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="55344-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="55344-p112">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="55344-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="55344-256">Under **My Domains** väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="55344-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="55344-258">Välj DNS **Records+** i **kolumnen Details.**</span><span class="sxs-lookup"><span data-stu-id="55344-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="55344-260">Lägg till den första SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="55344-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="55344-261">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="55344-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="55344-262">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="55344-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="55344-263">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="55344-263">**Type**</span></span>|<span data-ttu-id="55344-264">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="55344-264">**Service**</span></span>|<span data-ttu-id="55344-265">**Weight (vikt)**</span><span class="sxs-lookup"><span data-stu-id="55344-265">**Weight**</span></span>|<span data-ttu-id="55344-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="55344-266">**TTL**</span></span>|<span data-ttu-id="55344-267">**Prio**</span><span class="sxs-lookup"><span data-stu-id="55344-267">**Prio**</span></span>|<span data-ttu-id="55344-268">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="55344-268">**Protocol**</span></span>|<span data-ttu-id="55344-269">**Port**</span><span class="sxs-lookup"><span data-stu-id="55344-269">**Port**</span></span>|<span data-ttu-id="55344-270">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="55344-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="55344-271">SRV</span><span class="sxs-lookup"><span data-stu-id="55344-271">SRV</span></span>|<span data-ttu-id="55344-272">sip</span><span class="sxs-lookup"><span data-stu-id="55344-272">sip</span></span>|<span data-ttu-id="55344-273">1</span><span class="sxs-lookup"><span data-stu-id="55344-273">1</span></span>|<span data-ttu-id="55344-274">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-274">Use the default value (300).</span></span>|<span data-ttu-id="55344-275">100</span><span class="sxs-lookup"><span data-stu-id="55344-275">100</span></span>|<span data-ttu-id="55344-276">tls</span><span class="sxs-lookup"><span data-stu-id="55344-276">tls</span></span>|<span data-ttu-id="55344-277">443</span><span class="sxs-lookup"><span data-stu-id="55344-277">443</span></span>|<span data-ttu-id="55344-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="55344-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="55344-279">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="55344-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="55344-280">SRV</span><span class="sxs-lookup"><span data-stu-id="55344-280">SRV</span></span>|<span data-ttu-id="55344-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="55344-281">sipfederationtls</span></span>|<span data-ttu-id="55344-282">1</span><span class="sxs-lookup"><span data-stu-id="55344-282">1</span></span>|<span data-ttu-id="55344-283">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="55344-283">Use the default value (300).</span></span>|<span data-ttu-id="55344-284">100</span><span class="sxs-lookup"><span data-stu-id="55344-284">100</span></span>|<span data-ttu-id="55344-285">tcp</span><span class="sxs-lookup"><span data-stu-id="55344-285">tcp</span></span>|<span data-ttu-id="55344-286">5061</span><span class="sxs-lookup"><span data-stu-id="55344-286">5061</span></span>|<span data-ttu-id="55344-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="55344-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="55344-288">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="55344-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="55344-290">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="55344-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="55344-292">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="55344-292">Add the second SRV record:</span></span>

<span data-ttu-id="55344-293">Använd värdena från nästa rad i tabellen ovan och välj sedan Add Record (lägg **till post) för** att lägga till den andra posten.</span><span class="sxs-lookup"><span data-stu-id="55344-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="55344-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="55344-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>