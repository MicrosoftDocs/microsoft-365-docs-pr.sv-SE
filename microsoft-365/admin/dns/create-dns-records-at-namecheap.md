---
title: Skapa DNS-poster på Namecheap för Microsoft
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Namecheap för Microsoft.
ms.openlocfilehash: 2b55e529ab4a66dbada95914f213807884b4b6c0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629341"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="90bf8-103">Skapa DNS-poster på Namecheap för Microsoft</span><span class="sxs-lookup"><span data-stu-id="90bf8-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="90bf8-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="90bf8-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="90bf8-105">Om du har Namecheap som DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="90bf8-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="90bf8-106">När du har lagt till dessa poster på Namecheap konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="90bf8-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90bf8-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90bf8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="90bf8-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="90bf8-110">Add a TXT record for verification</span></span>
<span data-ttu-id="90bf8-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="90bf8-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="90bf8-112">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="90bf8-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="90bf8-113">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="90bf8-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90bf8-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="90bf8-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="90bf8-116">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="90bf8-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="90bf8-p104">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="90bf8-p104">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="90bf8-120">Välj **Domänlista** i listrutan under **Konto**på sidan **Mål.**</span><span class="sxs-lookup"><span data-stu-id="90bf8-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="90bf8-122">Leta reda på namnet på den domän som du vill redigera på sidan **Domänlista** och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="90bf8-124">Välj **Avancerad DNS**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="90bf8-126">Välj **LÄGG TILL NY POST i**avsnittet **VÄRDPOSTER** .</span><span class="sxs-lookup"><span data-stu-id="90bf8-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="90bf8-128">Välj **TXT Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90bf8-129">Listrutan **Typ** visas automatiskt när du väljer **LÄGG TILL NY POST**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="90bf8-131">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="90bf8-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="90bf8-132">(Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="90bf8-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="90bf8-133">**Typ**</span><span class="sxs-lookup"><span data-stu-id="90bf8-133">**Type**</span></span>|<span data-ttu-id="90bf8-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="90bf8-134">**Host**</span></span>|<span data-ttu-id="90bf8-135">**Value**</span><span class="sxs-lookup"><span data-stu-id="90bf8-135">**Value**</span></span>|<span data-ttu-id="90bf8-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90bf8-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90bf8-137">TXT</span><span class="sxs-lookup"><span data-stu-id="90bf8-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="90bf8-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="90bf8-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="90bf8-139">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="90bf8-139">**Note:** This is an example.</span></span> <span data-ttu-id="90bf8-140">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="90bf8-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="90bf8-141">Hur hittar jag detta?</span><span class="sxs-lookup"><span data-stu-id="90bf8-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="90bf8-142">30 min</span><span class="sxs-lookup"><span data-stu-id="90bf8-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verifiera-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="90bf8-144">Markera kontrollen **Spara ändringar** (markera).</span><span class="sxs-lookup"><span data-stu-id="90bf8-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="90bf8-146">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="90bf8-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="90bf8-147">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="90bf8-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="90bf8-148">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="90bf8-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="90bf8-149">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="90bf8-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="90bf8-150">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="90bf8-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="90bf8-151">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="90bf8-152">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="90bf8-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90bf8-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="90bf8-156">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="90bf8-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="90bf8-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="90bf8-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="90bf8-158">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="90bf8-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="90bf8-p107">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="90bf8-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="90bf8-162">Välj **Domänlista** i listrutan under **Konto**på sidan **Mål.**</span><span class="sxs-lookup"><span data-stu-id="90bf8-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="90bf8-164">Leta reda på namnet på den domän som du vill redigera på sidan **Domänlista** och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="90bf8-166">Välj **Avancerad DNS**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="90bf8-168">I avsnittet **MAIL SETTINGS** väljer du **Custom MX** från listrutan **Email Forwarding**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="90bf8-169">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="90bf8-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="90bf8-171">Välj **Lägg till ny post**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="90bf8-173">I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="90bf8-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="90bf8-174">(Rutan **Priority** är rutan utan namn till höger om rutan **Värde**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="90bf8-175">Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="90bf8-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="90bf8-176">**Typ**</span><span class="sxs-lookup"><span data-stu-id="90bf8-176">**Type**</span></span>|<span data-ttu-id="90bf8-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="90bf8-177">**Host**</span></span>|<span data-ttu-id="90bf8-178">**Värde**</span><span class="sxs-lookup"><span data-stu-id="90bf8-178">**Value**</span></span>|<span data-ttu-id="90bf8-179">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="90bf8-179">**Priority**</span></span>|<span data-ttu-id="90bf8-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90bf8-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90bf8-181">MX Record (MX-post)</span><span class="sxs-lookup"><span data-stu-id="90bf8-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="90bf8-182">\<*domännyckeln*\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="90bf8-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="90bf8-183">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="90bf8-184">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="90bf8-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="90bf8-185">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="90bf8-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="90bf8-186">0</span><span class="sxs-lookup"><span data-stu-id="90bf8-186">0</span></span>  <br/> <span data-ttu-id="90bf8-187">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="90bf8-187">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="90bf8-188">30 min</span><span class="sxs-lookup"><span data-stu-id="90bf8-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Konfigurera-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="90bf8-190">Markera kontrollen **Spara ändringar** (markera).</span><span class="sxs-lookup"><span data-stu-id="90bf8-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="90bf8-192">Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:</span><span class="sxs-lookup"><span data-stu-id="90bf8-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="90bf8-193">Välj först **ikonen Ta bort** (papperskorgen) för den post som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="90bf8-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="90bf8-195">För det andra väljer du **Ja** för att bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="90bf8-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="90bf8-197">Ta bort alla MX-poster förutom den du lade till tidigare i proceduren.</span><span class="sxs-lookup"><span data-stu-id="90bf8-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="90bf8-198">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="90bf8-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="90bf8-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="90bf8-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="90bf8-200">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="90bf8-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="90bf8-p110">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="90bf8-p110">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="90bf8-204">Välj **Domänlista** i listrutan under **Konto**på sidan **Mål.**</span><span class="sxs-lookup"><span data-stu-id="90bf8-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="90bf8-206">Leta reda på namnet på den domän som du vill redigera på sidan **Domänlista** och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="90bf8-208">Välj **Avancerad DNS**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="90bf8-210">Välj **LÄGG TILL NY POST i**avsnittet **VÄRDPOSTER** .</span><span class="sxs-lookup"><span data-stu-id="90bf8-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="90bf8-212">Välj **CNAME Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90bf8-213">Listrutan **Typ** visas automatiskt när du väljer **LÄGG TILL NY POST**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="90bf8-215">I de tomma rutorna för den nya posten väljer du **CNAME** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="90bf8-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="90bf8-216">**Type**</span><span class="sxs-lookup"><span data-stu-id="90bf8-216">**Type**</span></span>|<span data-ttu-id="90bf8-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="90bf8-217">**Host**</span></span>|<span data-ttu-id="90bf8-218">**Värde**</span><span class="sxs-lookup"><span data-stu-id="90bf8-218">**Value**</span></span>|<span data-ttu-id="90bf8-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90bf8-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90bf8-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="90bf8-220">CNAME</span></span>  <br/> |<span data-ttu-id="90bf8-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="90bf8-221">autodiscover</span></span>  <br/> |<span data-ttu-id="90bf8-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="90bf8-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="90bf8-223">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="90bf8-224">3600</span><span class="sxs-lookup"><span data-stu-id="90bf8-224">3600</span></span>  <br/> |
    |<span data-ttu-id="90bf8-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="90bf8-225">CNAME</span></span>  <br/> |<span data-ttu-id="90bf8-226">sip</span><span class="sxs-lookup"><span data-stu-id="90bf8-226">sip</span></span>  <br/> |<span data-ttu-id="90bf8-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="90bf8-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="90bf8-228">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="90bf8-229">3600</span><span class="sxs-lookup"><span data-stu-id="90bf8-229">3600</span></span>  <br/> |
    |<span data-ttu-id="90bf8-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="90bf8-230">CNAME</span></span>  <br/> |<span data-ttu-id="90bf8-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="90bf8-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="90bf8-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="90bf8-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="90bf8-233">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="90bf8-234">3600</span><span class="sxs-lookup"><span data-stu-id="90bf8-234">3600</span></span>  <br/> |
    |<span data-ttu-id="90bf8-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="90bf8-235">CNAME</span></span>  <br/> |<span data-ttu-id="90bf8-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="90bf8-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="90bf8-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="90bf8-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="90bf8-238">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="90bf8-239">3600</span><span class="sxs-lookup"><span data-stu-id="90bf8-239">3600</span></span>  <br/> |
    |<span data-ttu-id="90bf8-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="90bf8-240">CNAME</span></span>  <br/> |<span data-ttu-id="90bf8-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="90bf8-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="90bf8-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="90bf8-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="90bf8-243">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="90bf8-244">3600</span><span class="sxs-lookup"><span data-stu-id="90bf8-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-Konfigurera-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="90bf8-246">Markera kontrollen **Spara ändringar** (markera).</span><span class="sxs-lookup"><span data-stu-id="90bf8-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="90bf8-248">Upprepa de fyra föregående stegen när du lägger till de andra fem CNAME-posterna med värdena från de andra fem raderna i tabellen.</span><span class="sxs-lookup"><span data-stu-id="90bf8-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="90bf8-249">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="90bf8-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="90bf8-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="90bf8-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="90bf8-251">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="90bf8-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="90bf8-252">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="90bf8-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="90bf8-253">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90bf8-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="90bf8-254">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="90bf8-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="90bf8-255">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="90bf8-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="90bf8-p112">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="90bf8-p112">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="90bf8-258">Välj **Domänlista** i listrutan under **Konto**på sidan **Mål.**</span><span class="sxs-lookup"><span data-stu-id="90bf8-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="90bf8-260">Leta reda på namnet på den domän som du vill redigera på sidan **Domänlista** och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="90bf8-262">Välj **Avancerad DNS**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="90bf8-264">Välj **LÄGG TILL NY POST i**avsnittet **VÄRDPOSTER** .</span><span class="sxs-lookup"><span data-stu-id="90bf8-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="90bf8-266">Välj **TXT Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90bf8-267">Listrutan **Typ** visas automatiskt när du väljer **LÄGG TILL NY POST**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="90bf8-269">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="90bf8-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="90bf8-270">(Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="90bf8-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="90bf8-271">**Typ**</span><span class="sxs-lookup"><span data-stu-id="90bf8-271">**Type**</span></span>|<span data-ttu-id="90bf8-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="90bf8-272">**Host**</span></span>|<span data-ttu-id="90bf8-273">**Värde**</span><span class="sxs-lookup"><span data-stu-id="90bf8-273">**Value**</span></span>|<span data-ttu-id="90bf8-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90bf8-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90bf8-275">TXT</span><span class="sxs-lookup"><span data-stu-id="90bf8-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="90bf8-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="90bf8-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="90bf8-277">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="90bf8-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="90bf8-278">30 min</span><span class="sxs-lookup"><span data-stu-id="90bf8-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Konfigurera-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="90bf8-280">Markera kontrollen **Spara ändringar** (markera).</span><span class="sxs-lookup"><span data-stu-id="90bf8-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="90bf8-282">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="90bf8-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="90bf8-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="90bf8-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="90bf8-p113">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="90bf8-p113">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="90bf8-287">Välj **Domänlista** i listrutan under **Konto**på sidan **Mål.**</span><span class="sxs-lookup"><span data-stu-id="90bf8-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="90bf8-289">Leta reda på namnet på den domän som du vill redigera på sidan **Domänlista** och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="90bf8-291">Välj **Avancerad DNS**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="90bf8-293">Välj **LÄGG TILL NY POST i**avsnittet **VÄRDPOSTER** .</span><span class="sxs-lookup"><span data-stu-id="90bf8-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="90bf8-295">Välj **SRV Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90bf8-296">Listrutan **Typ** visas automatiskt när du väljer **LÄGG TILL NY POST**.</span><span class="sxs-lookup"><span data-stu-id="90bf8-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="90bf8-298">I de tomma rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="90bf8-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="90bf8-299">**Service**</span><span class="sxs-lookup"><span data-stu-id="90bf8-299">**Service**</span></span>|<span data-ttu-id="90bf8-300">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="90bf8-300">**Protocol**</span></span>|<span data-ttu-id="90bf8-301">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="90bf8-301">**Priority**</span></span>|<span data-ttu-id="90bf8-302">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="90bf8-302">**Weight**</span></span>|<span data-ttu-id="90bf8-303">**Port**</span><span class="sxs-lookup"><span data-stu-id="90bf8-303">**Port**</span></span>|<span data-ttu-id="90bf8-304">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-304">**Target**</span></span>|<span data-ttu-id="90bf8-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90bf8-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90bf8-306">_sip</span><span class="sxs-lookup"><span data-stu-id="90bf8-306">_sip</span></span>  <br/> |<span data-ttu-id="90bf8-307">_tls</span><span class="sxs-lookup"><span data-stu-id="90bf8-307">_tls</span></span>  <br/> |<span data-ttu-id="90bf8-308">100</span><span class="sxs-lookup"><span data-stu-id="90bf8-308">100</span></span>  <br/> |<span data-ttu-id="90bf8-309">1</span><span class="sxs-lookup"><span data-stu-id="90bf8-309">1</span></span>  <br/> |<span data-ttu-id="90bf8-310">443</span><span class="sxs-lookup"><span data-stu-id="90bf8-310">443</span></span>  <br/> |<span data-ttu-id="90bf8-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="90bf8-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="90bf8-312">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="90bf8-313">30 min</span><span class="sxs-lookup"><span data-stu-id="90bf8-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="90bf8-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="90bf8-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="90bf8-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="90bf8-315">_tcp</span></span>  <br/> |<span data-ttu-id="90bf8-316">100</span><span class="sxs-lookup"><span data-stu-id="90bf8-316">100</span></span>  <br/> |<span data-ttu-id="90bf8-317">1</span><span class="sxs-lookup"><span data-stu-id="90bf8-317">1</span></span>  <br/> |<span data-ttu-id="90bf8-318">5061</span><span class="sxs-lookup"><span data-stu-id="90bf8-318">5061</span></span>  <br/> |<span data-ttu-id="90bf8-319">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="90bf8-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="90bf8-320">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="90bf8-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="90bf8-321">30 min</span><span class="sxs-lookup"><span data-stu-id="90bf8-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Konfigurera-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="90bf8-323">Markera kontrollen **Spara ändringar** (markera).</span><span class="sxs-lookup"><span data-stu-id="90bf8-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="90bf8-325">Upprepa de fyra föregående stegen när du lägger till den andra SRV-posten med värdena från tabellens andra rad.</span><span class="sxs-lookup"><span data-stu-id="90bf8-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="90bf8-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90bf8-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
