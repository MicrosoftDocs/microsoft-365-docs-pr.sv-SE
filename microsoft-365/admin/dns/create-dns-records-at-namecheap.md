---
title: Skapa DNS-poster på NameCheap för Microsoft
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på NameCheap för Microsoft.
ms.openlocfilehash: 25b40dad0eb47c190df9496d5df4f061d8fdba6d
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645929"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="97de4-103">Skapa DNS-poster på NameCheap för Microsoft</span><span class="sxs-lookup"><span data-stu-id="97de4-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="97de4-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="97de4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="97de4-105">Om du har Namecheap som DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="97de4-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="97de4-106">När du har lagt till dessa poster på NameCheap är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="97de4-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97de4-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="97de4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="97de4-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="97de4-110">Add a TXT record for verification</span></span>
<span data-ttu-id="97de4-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="97de4-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="97de4-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="97de4-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97de4-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="97de4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="97de4-116">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="97de4-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="97de4-p104">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="97de4-p104">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="97de4-120">Välj **domän lista** i list rutan under **konto** **på Start sidan.**</span><span class="sxs-lookup"><span data-stu-id="97de4-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="97de4-122">Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.</span><span class="sxs-lookup"><span data-stu-id="97de4-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="97de4-124">Välj **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="97de4-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="97de4-126">Välj **Add New Record**i avsnittet **Host Records** .</span><span class="sxs-lookup"><span data-stu-id="97de4-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="97de4-128">Välj **TXT Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="97de4-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97de4-129">List rutan **typ** visas automatiskt när du väljer **Lägg till ny post**.</span><span class="sxs-lookup"><span data-stu-id="97de4-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="97de4-131">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="97de4-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="97de4-132">(Välj **TTL** -värdet i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="97de4-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="97de4-133">**Typ**</span><span class="sxs-lookup"><span data-stu-id="97de4-133">**Type**</span></span>|<span data-ttu-id="97de4-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="97de4-134">**Host**</span></span>|<span data-ttu-id="97de4-135">**Värde**</span><span class="sxs-lookup"><span data-stu-id="97de4-135">**Value**</span></span>|<span data-ttu-id="97de4-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="97de4-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="97de4-137">TXT</span><span class="sxs-lookup"><span data-stu-id="97de4-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="97de4-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="97de4-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="97de4-139">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="97de4-139">**Note:** This is an example.</span></span> <span data-ttu-id="97de4-140">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="97de4-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="97de4-141">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="97de4-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="97de4-142">30 min</span><span class="sxs-lookup"><span data-stu-id="97de4-142">30 min</span></span>  <br/> |
       
    ![NameCheap-BP-verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="97de4-144">Markera kontrollen **Spara ändringar** (bock markering).</span><span class="sxs-lookup"><span data-stu-id="97de4-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="97de4-146">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="97de4-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="97de4-147">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="97de4-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="97de4-148">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="97de4-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="97de4-149">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="97de4-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="97de4-150">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="97de4-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="97de4-151">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="97de4-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="97de4-152">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="97de4-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="97de4-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="97de4-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="97de4-156">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="97de4-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="97de4-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="97de4-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="97de4-158">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="97de4-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="97de4-p107">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="97de4-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="97de4-162">Välj **domän lista** i list rutan under **konto** **på Start sidan.**</span><span class="sxs-lookup"><span data-stu-id="97de4-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="97de4-164">Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.</span><span class="sxs-lookup"><span data-stu-id="97de4-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="97de4-166">Välj **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="97de4-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="97de4-168">I avsnittet **MAIL SETTINGS** väljer du **Custom MX** från listrutan **Email Forwarding**.</span><span class="sxs-lookup"><span data-stu-id="97de4-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="97de4-169">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="97de4-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="97de4-171">Välj **Lägg till ny post**.</span><span class="sxs-lookup"><span data-stu-id="97de4-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="97de4-173">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="97de4-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="97de4-174">(Rutan **Priority** är rutan utan namn till höger om rutan **Värde**.</span><span class="sxs-lookup"><span data-stu-id="97de4-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="97de4-175">Välj **TTL** -värdet i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="97de4-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="97de4-176">**Typ**</span><span class="sxs-lookup"><span data-stu-id="97de4-176">**Type**</span></span>|<span data-ttu-id="97de4-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="97de4-177">**Host**</span></span>|<span data-ttu-id="97de4-178">**Värde**</span><span class="sxs-lookup"><span data-stu-id="97de4-178">**Value**</span></span>|<span data-ttu-id="97de4-179">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="97de4-179">**Priority**</span></span>|<span data-ttu-id="97de4-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="97de4-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="97de4-181">MX Record (MX-post)</span><span class="sxs-lookup"><span data-stu-id="97de4-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="97de4-182">\<*domain-key*\>. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="97de4-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="97de4-183">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="97de4-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="97de4-184">**Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="97de4-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="97de4-185">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="97de4-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="97de4-186">siffrorna</span><span class="sxs-lookup"><span data-stu-id="97de4-186">0</span></span>  <br/> <span data-ttu-id="97de4-187">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="97de4-187">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="97de4-188">30 min</span><span class="sxs-lookup"><span data-stu-id="97de4-188">30 min</span></span>  <br/> |
       
    ![NameCheap-BP-Configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="97de4-190">Markera kontrollen **Spara ändringar** (bock markering).</span><span class="sxs-lookup"><span data-stu-id="97de4-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="97de4-192">Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:</span><span class="sxs-lookup"><span data-stu-id="97de4-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="97de4-193">Först väljer du **ikonen Ta bort** (pappers korgen) för den post som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="97de4-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="97de4-195">Välj sedan **Ja** för att bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="97de4-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="97de4-197">Ta bort alla MX-poster förutom den du lade till tidigare i proceduren.</span><span class="sxs-lookup"><span data-stu-id="97de4-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="97de4-198">Lägga till de sex CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="97de4-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="97de4-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="97de4-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="97de4-200">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="97de4-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="97de4-p110">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="97de4-p110">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="97de4-204">Välj **domän lista** i list rutan under **konto** **på Start sidan.**</span><span class="sxs-lookup"><span data-stu-id="97de4-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="97de4-206">Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.</span><span class="sxs-lookup"><span data-stu-id="97de4-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="97de4-208">Välj **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="97de4-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="97de4-210">Välj **Add New Record**i avsnittet **Host Records** .</span><span class="sxs-lookup"><span data-stu-id="97de4-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="97de4-212">Välj **CNAME Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="97de4-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97de4-213">List rutan **typ** visas automatiskt när du väljer **Lägg till ny post**.</span><span class="sxs-lookup"><span data-stu-id="97de4-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="97de4-215">I de tomma rutorna för den nya posten väljer du **CNAME** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="97de4-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="97de4-216">**Type**</span><span class="sxs-lookup"><span data-stu-id="97de4-216">**Type**</span></span>|<span data-ttu-id="97de4-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="97de4-217">**Host**</span></span>|<span data-ttu-id="97de4-218">**Värde**</span><span class="sxs-lookup"><span data-stu-id="97de4-218">**Value**</span></span>|<span data-ttu-id="97de4-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="97de4-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="97de4-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="97de4-220">CNAME</span></span>  <br/> |<span data-ttu-id="97de4-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="97de4-221">autodiscover</span></span>  <br/> |<span data-ttu-id="97de4-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="97de4-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="97de4-223">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="97de4-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="97de4-224">3600</span><span class="sxs-lookup"><span data-stu-id="97de4-224">3600</span></span>  <br/> |
    |<span data-ttu-id="97de4-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="97de4-225">CNAME</span></span>  <br/> |<span data-ttu-id="97de4-226">sip</span><span class="sxs-lookup"><span data-stu-id="97de4-226">sip</span></span>  <br/> |<span data-ttu-id="97de4-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="97de4-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="97de4-228">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="97de4-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="97de4-229">3600</span><span class="sxs-lookup"><span data-stu-id="97de4-229">3600</span></span>  <br/> |
    |<span data-ttu-id="97de4-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="97de4-230">CNAME</span></span>  <br/> |<span data-ttu-id="97de4-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="97de4-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="97de4-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="97de4-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="97de4-233">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="97de4-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="97de4-234">3600</span><span class="sxs-lookup"><span data-stu-id="97de4-234">3600</span></span>  <br/> |
    |<span data-ttu-id="97de4-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="97de4-235">CNAME</span></span>  <br/> |<span data-ttu-id="97de4-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="97de4-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="97de4-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="97de4-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="97de4-238">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="97de4-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="97de4-239">3600</span><span class="sxs-lookup"><span data-stu-id="97de4-239">3600</span></span>  <br/> |
    |<span data-ttu-id="97de4-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="97de4-240">CNAME</span></span>  <br/> |<span data-ttu-id="97de4-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="97de4-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="97de4-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="97de4-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="97de4-243">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="97de4-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="97de4-244">3600</span><span class="sxs-lookup"><span data-stu-id="97de4-244">3600</span></span>  <br/> |
       
    ![NameCheap-BP-Configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="97de4-246">Markera kontrollen **Spara ändringar** (bock markering).</span><span class="sxs-lookup"><span data-stu-id="97de4-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="97de4-248">Upprepa de fyra föregående stegen när du lägger till de andra fem CNAME-posterna med värdena från de andra fem raderna i tabellen.</span><span class="sxs-lookup"><span data-stu-id="97de4-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="97de4-249">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="97de4-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="97de4-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="97de4-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="97de4-251">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="97de4-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="97de4-252">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="97de4-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="97de4-253">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="97de4-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="97de4-254">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="97de4-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="97de4-255">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="97de4-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="97de4-p112">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="97de4-p112">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="97de4-258">Välj **domän lista** i list rutan under **konto** **på Start sidan.**</span><span class="sxs-lookup"><span data-stu-id="97de4-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="97de4-260">Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.</span><span class="sxs-lookup"><span data-stu-id="97de4-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="97de4-262">Välj **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="97de4-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="97de4-264">Välj **Add New Record**i avsnittet **Host Records** .</span><span class="sxs-lookup"><span data-stu-id="97de4-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="97de4-266">Välj **TXT Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="97de4-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97de4-267">List rutan **typ** visas automatiskt när du väljer **Lägg till ny post**.</span><span class="sxs-lookup"><span data-stu-id="97de4-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="97de4-269">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="97de4-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="97de4-270">(Välj **TTL** -värdet i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="97de4-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="97de4-271">**Typ**</span><span class="sxs-lookup"><span data-stu-id="97de4-271">**Type**</span></span>|<span data-ttu-id="97de4-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="97de4-272">**Host**</span></span>|<span data-ttu-id="97de4-273">**Värde**</span><span class="sxs-lookup"><span data-stu-id="97de4-273">**Value**</span></span>|<span data-ttu-id="97de4-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="97de4-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="97de4-275">TXT</span><span class="sxs-lookup"><span data-stu-id="97de4-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="97de4-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="97de4-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="97de4-277">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="97de4-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="97de4-278">30 min</span><span class="sxs-lookup"><span data-stu-id="97de4-278">30 min</span></span>  <br/> |
       
    ![NameCheap-BP-Configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="97de4-280">Markera kontrollen **Spara ändringar** (bock markering).</span><span class="sxs-lookup"><span data-stu-id="97de4-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="97de4-282">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="97de4-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="97de4-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="97de4-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="97de4-p113">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="97de4-p113">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="97de4-287">Välj **domän lista** i list rutan under **konto** **på Start sidan.**</span><span class="sxs-lookup"><span data-stu-id="97de4-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="97de4-289">Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.</span><span class="sxs-lookup"><span data-stu-id="97de4-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="97de4-291">Välj **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="97de4-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="97de4-293">Välj **Add New Record**i avsnittet **Host Records** .</span><span class="sxs-lookup"><span data-stu-id="97de4-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="97de4-295">Välj **SRV Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="97de4-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97de4-296">List rutan **typ** visas automatiskt när du väljer **Lägg till ny post**.</span><span class="sxs-lookup"><span data-stu-id="97de4-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="97de4-298">I de tomma rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="97de4-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="97de4-299">**Service**</span><span class="sxs-lookup"><span data-stu-id="97de4-299">**Service**</span></span>|<span data-ttu-id="97de4-300">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="97de4-300">**Protocol**</span></span>|<span data-ttu-id="97de4-301">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="97de4-301">**Priority**</span></span>|<span data-ttu-id="97de4-302">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="97de4-302">**Weight**</span></span>|<span data-ttu-id="97de4-303">**Port**</span><span class="sxs-lookup"><span data-stu-id="97de4-303">**Port**</span></span>|<span data-ttu-id="97de4-304">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="97de4-304">**Target**</span></span>|<span data-ttu-id="97de4-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="97de4-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="97de4-306">_sip</span><span class="sxs-lookup"><span data-stu-id="97de4-306">_sip</span></span>  <br/> |<span data-ttu-id="97de4-307">_tls</span><span class="sxs-lookup"><span data-stu-id="97de4-307">_tls</span></span>  <br/> |<span data-ttu-id="97de4-308">100</span><span class="sxs-lookup"><span data-stu-id="97de4-308">100</span></span>  <br/> |<span data-ttu-id="97de4-309">9.1</span><span class="sxs-lookup"><span data-stu-id="97de4-309">1</span></span>  <br/> |<span data-ttu-id="97de4-310">443</span><span class="sxs-lookup"><span data-stu-id="97de4-310">443</span></span>  <br/> |<span data-ttu-id="97de4-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="97de4-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="97de4-312">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="97de4-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="97de4-313">30 min</span><span class="sxs-lookup"><span data-stu-id="97de4-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="97de4-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="97de4-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="97de4-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="97de4-315">_tcp</span></span>  <br/> |<span data-ttu-id="97de4-316">100</span><span class="sxs-lookup"><span data-stu-id="97de4-316">100</span></span>  <br/> |<span data-ttu-id="97de4-317">9.1</span><span class="sxs-lookup"><span data-stu-id="97de4-317">1</span></span>  <br/> |<span data-ttu-id="97de4-318">5061</span><span class="sxs-lookup"><span data-stu-id="97de4-318">5061</span></span>  <br/> |<span data-ttu-id="97de4-319">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="97de4-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="97de4-320">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="97de4-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="97de4-321">30 min</span><span class="sxs-lookup"><span data-stu-id="97de4-321">30 min</span></span>  <br/> |
       
    ![NameCheap-BP-Configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="97de4-323">Markera kontrollen **Spara ändringar** (bock markering).</span><span class="sxs-lookup"><span data-stu-id="97de4-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="97de4-325">Upprepa de fyra föregående stegen när du lägger till den andra SRV-posten med värdena från tabellens andra rad.</span><span class="sxs-lookup"><span data-stu-id="97de4-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="97de4-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="97de4-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
