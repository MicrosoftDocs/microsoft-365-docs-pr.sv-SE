---
title: Skapa DNS-poster på Bluehost för Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Bluehost för Microsoft.
ms.openlocfilehash: c0ba1b876c939632bc6c43a6e0004fbbe23a7723
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646241"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="e1cea-103">Skapa DNS-poster på Bluehost för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1cea-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="e1cea-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="e1cea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e1cea-105">Om Bluehost är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e1cea-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e1cea-106">När du har lagt till dessa poster på Bluehost är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="e1cea-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="e1cea-p101">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1cea-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e1cea-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="e1cea-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e1cea-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cea-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e1cea-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="e1cea-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1cea-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="e1cea-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e1cea-116">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e1cea-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e1cea-117">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e1cea-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e1cea-118">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e1cea-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e1cea-119">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e1cea-120">I området \*\* _domain_name_*_ väljer du*\*\* **Manage DNS Records**på raden _ DNS Zone Editor.</span><span class="sxs-lookup"><span data-stu-id="e1cea-120">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e1cea-121">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e1cea-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e1cea-122">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1cea-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="e1cea-123">**Host Record**</span></span> <br/> |<span data-ttu-id="e1cea-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1cea-124">**TTL**</span></span> <br/> |<span data-ttu-id="e1cea-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="e1cea-125">**Type**</span></span> <br/> |<span data-ttu-id="e1cea-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="e1cea-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="e1cea-127">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-127">14400</span></span>  <br/> |<span data-ttu-id="e1cea-128">TXT</span><span class="sxs-lookup"><span data-stu-id="e1cea-128">TXT</span></span>  <br/> |<span data-ttu-id="e1cea-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e1cea-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e1cea-130">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="e1cea-130">**Note:** This is an example.</span></span> <span data-ttu-id="e1cea-131">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="e1cea-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e1cea-132">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e1cea-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="e1cea-133">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="e1cea-134">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="e1cea-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e1cea-135">Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="e1cea-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="e1cea-136">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="e1cea-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e1cea-137">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="e1cea-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e1cea-138">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="e1cea-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e1cea-139">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e1cea-140">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e1cea-p106">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1cea-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e1cea-144">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1cea-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e1cea-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cea-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e1cea-146">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e1cea-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e1cea-147">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e1cea-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e1cea-148">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e1cea-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e1cea-149">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e1cea-150">I området \*\* _domain_name_*_ väljer du*\*\* **Manage DNS Records**på raden _ DNS Zone Editor.</span><span class="sxs-lookup"><span data-stu-id="e1cea-150">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e1cea-151">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e1cea-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e1cea-152">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1cea-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="e1cea-153">**Host Record**</span></span>|<span data-ttu-id="e1cea-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1cea-154">**TTL**</span></span>|<span data-ttu-id="e1cea-155">**Type**</span><span class="sxs-lookup"><span data-stu-id="e1cea-155">**Type**</span></span>|<span data-ttu-id="e1cea-156">**Points To**</span><span class="sxs-lookup"><span data-stu-id="e1cea-156">**Points To**</span></span>|<span data-ttu-id="e1cea-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e1cea-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e1cea-158">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-158">14400</span></span>  <br/> |<span data-ttu-id="e1cea-159">MX</span><span class="sxs-lookup"><span data-stu-id="e1cea-159">MX</span></span>  <br/> | <span data-ttu-id="e1cea-160">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1cea-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="e1cea-161">**Obs!** Hämta din \<*domain-key*\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="e1cea-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="e1cea-162">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="e1cea-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e1cea-163">siffrorna</span><span class="sxs-lookup"><span data-stu-id="e1cea-163">0</span></span>  <br/> <span data-ttu-id="e1cea-164">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e1cea-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Välj typ i list rutan](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="e1cea-166">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-166">Select **add record**.</span></span>
    
    ![Välj Lägg till post](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="e1cea-168">Om det finns andra MX-poster i avsnittet **MX (Mail Exchanger)** ska du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="e1cea-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="e1cea-169">Välj **ta bort** för någon av de andra MX-posterna.</span><span class="sxs-lookup"><span data-stu-id="e1cea-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![Välj Ta bort för varje ytterligare MX-post](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="e1cea-171">Välj **OK**i bekräftelse dialog rutan.</span><span class="sxs-lookup"><span data-stu-id="e1cea-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Välj OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="e1cea-173">Du använder samma process för att ta bort eventuella andra MX-poster som visas.</span><span class="sxs-lookup"><span data-stu-id="e1cea-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e1cea-174">Lägga till de sex CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1cea-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e1cea-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cea-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e1cea-176">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e1cea-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e1cea-177">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e1cea-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e1cea-178">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e1cea-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e1cea-179">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e1cea-180">I området \*\* _domain_name_*_ väljer du*\*\* **Manage DNS Records**på raden _ DNS Zone Editor.</span><span class="sxs-lookup"><span data-stu-id="e1cea-180">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e1cea-181">Leta reda på raden för posten **Autodiscover** i avsnittet **a (hosts)** Records och välj **ta bort** för den raden.</span><span class="sxs-lookup"><span data-stu-id="e1cea-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="e1cea-182">Du måste ta bort den befintliga posten för **automatisk upptäckt**  *innan*  du lägger till en post för **automatisk upptäckt** som Microsoft har angett.</span><span class="sxs-lookup"><span data-stu-id="e1cea-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="e1cea-183">Bluehost tillåter inte att du har två **autodiscover** -poster samtidigt.</span><span class="sxs-lookup"><span data-stu-id="e1cea-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Välj Ta bort](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="e1cea-185">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-185">Select **OK**.</span></span>
    
    ![Välj OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="e1cea-187">Skapa den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e1cea-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="e1cea-188">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e1cea-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e1cea-189">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1cea-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="e1cea-190">**Host Record**</span></span>|<span data-ttu-id="e1cea-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1cea-191">**TTL**</span></span>|<span data-ttu-id="e1cea-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="e1cea-192">**Type**</span></span>|<span data-ttu-id="e1cea-193">**Points To**</span><span class="sxs-lookup"><span data-stu-id="e1cea-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1cea-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e1cea-194">autodiscover</span></span>  <br/> |<span data-ttu-id="e1cea-195">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-195">14400</span></span>  <br/> |<span data-ttu-id="e1cea-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1cea-196">CNAME</span></span>  <br/> |<span data-ttu-id="e1cea-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1cea-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e1cea-198">sip</span><span class="sxs-lookup"><span data-stu-id="e1cea-198">sip</span></span>  <br/> |<span data-ttu-id="e1cea-199">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-199">14400</span></span>  <br/> |<span data-ttu-id="e1cea-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1cea-200">CNAME</span></span>  <br/> |<span data-ttu-id="e1cea-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1cea-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e1cea-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e1cea-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e1cea-203">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-203">14400</span></span>  <br/> |<span data-ttu-id="e1cea-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1cea-204">CNAME</span></span>  <br/> |<span data-ttu-id="e1cea-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1cea-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e1cea-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e1cea-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e1cea-207">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-207">14400</span></span>  <br/> |<span data-ttu-id="e1cea-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1cea-208">CNAME</span></span>  <br/> |<span data-ttu-id="e1cea-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e1cea-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="e1cea-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e1cea-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e1cea-211">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-211">14400</span></span>  <br/> |<span data-ttu-id="e1cea-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1cea-212">CNAME</span></span>  <br/> |<span data-ttu-id="e1cea-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e1cea-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Skapa den första CNAME-posten](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="e1cea-215">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-215">Select **add record**.</span></span>
    
    ![Välj Lägg till post](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="e1cea-217">Lägg till de andra fem CNAME-posterna var för sig.</span><span class="sxs-lookup"><span data-stu-id="e1cea-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="e1cea-218">I avsnittet **Add DNS Record** skapar du en post med värdena från nästa rad i tabellen och väljer sedan **Add Record** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="e1cea-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="e1cea-219">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e1cea-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e1cea-220">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="e1cea-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e1cea-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cea-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1cea-222">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="e1cea-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e1cea-223">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="e1cea-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e1cea-224">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1cea-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e1cea-225">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="e1cea-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e1cea-226">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="e1cea-226">Need examples?</span></span> <span data-ttu-id="e1cea-227">Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="e1cea-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="e1cea-228">Du kan validera SPF-posten genom att använda någon av dessa[SPF-verifierings verktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e1cea-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="e1cea-229">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e1cea-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e1cea-230">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e1cea-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e1cea-231">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e1cea-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e1cea-232">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e1cea-233">I området \*\* _domain_name_*_ väljer du*\*\* **Manage DNS Records**på raden _ DNS Zone Editor.</span><span class="sxs-lookup"><span data-stu-id="e1cea-233">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e1cea-234">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e1cea-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e1cea-235">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="e1cea-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="e1cea-236">**Host Record**</span></span>|<span data-ttu-id="e1cea-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1cea-237">**TTL**</span></span>|<span data-ttu-id="e1cea-238">**Type**</span><span class="sxs-lookup"><span data-stu-id="e1cea-238">**Type**</span></span>|<span data-ttu-id="e1cea-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="e1cea-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e1cea-240">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-240">14400</span></span>  <br/> |<span data-ttu-id="e1cea-241">TXT</span><span class="sxs-lookup"><span data-stu-id="e1cea-241">TXT</span></span>  <br/> |<span data-ttu-id="e1cea-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e1cea-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="e1cea-243">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="e1cea-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopiera TXT-värdet](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="e1cea-245">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-245">Select **add record**.</span></span>
    
    ![Välj Lägg till post](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e1cea-247">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1cea-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e1cea-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cea-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e1cea-249">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e1cea-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e1cea-250">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e1cea-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e1cea-251">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e1cea-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e1cea-252">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e1cea-253">I området \*\* _domain_name_*_ väljer du*\*\* **Manage DNS Records**på raden _ DNS Zone Editor.</span><span class="sxs-lookup"><span data-stu-id="e1cea-253">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e1cea-254">Skapa den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="e1cea-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="e1cea-255">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e1cea-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e1cea-256">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e1cea-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1cea-257">**Service**</span><span class="sxs-lookup"><span data-stu-id="e1cea-257">**Service**</span></span>|<span data-ttu-id="e1cea-258">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="e1cea-258">**Protocol**</span></span>|<span data-ttu-id="e1cea-259">**Host**</span><span class="sxs-lookup"><span data-stu-id="e1cea-259">**Host**</span></span>|<span data-ttu-id="e1cea-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1cea-260">**TTL**</span></span>|<span data-ttu-id="e1cea-261">**Type**</span><span class="sxs-lookup"><span data-stu-id="e1cea-261">**Type**</span></span>|<span data-ttu-id="e1cea-262">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="e1cea-262">**Priority**</span></span>|<span data-ttu-id="e1cea-263">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="e1cea-263">**Weight**</span></span>|<span data-ttu-id="e1cea-264">**Port**</span><span class="sxs-lookup"><span data-stu-id="e1cea-264">**Port**</span></span>|<span data-ttu-id="e1cea-265">**Points To**</span><span class="sxs-lookup"><span data-stu-id="e1cea-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1cea-266">_sip</span><span class="sxs-lookup"><span data-stu-id="e1cea-266">_sip</span></span>  <br/> |<span data-ttu-id="e1cea-267">_tls</span><span class="sxs-lookup"><span data-stu-id="e1cea-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="e1cea-268">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-268">14400</span></span>  <br/> |<span data-ttu-id="e1cea-269">SRV</span><span class="sxs-lookup"><span data-stu-id="e1cea-269">SRV</span></span>  <br/> |<span data-ttu-id="e1cea-270">100</span><span class="sxs-lookup"><span data-stu-id="e1cea-270">100</span></span>  <br/> |<span data-ttu-id="e1cea-271">9.1</span><span class="sxs-lookup"><span data-stu-id="e1cea-271">1</span></span>  <br/> |<span data-ttu-id="e1cea-272">443</span><span class="sxs-lookup"><span data-stu-id="e1cea-272">443</span></span>  <br/> |<span data-ttu-id="e1cea-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1cea-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e1cea-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e1cea-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="e1cea-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="e1cea-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="e1cea-276">14400</span><span class="sxs-lookup"><span data-stu-id="e1cea-276">14400</span></span>  <br/> |<span data-ttu-id="e1cea-277">SRV</span><span class="sxs-lookup"><span data-stu-id="e1cea-277">SRV</span></span>  <br/> |<span data-ttu-id="e1cea-278">100</span><span class="sxs-lookup"><span data-stu-id="e1cea-278">100</span></span>  <br/> |<span data-ttu-id="e1cea-279">9.1</span><span class="sxs-lookup"><span data-stu-id="e1cea-279">1</span></span>  <br/> |<span data-ttu-id="e1cea-280">5061</span><span class="sxs-lookup"><span data-stu-id="e1cea-280">5061</span></span>  <br/> |<span data-ttu-id="e1cea-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1cea-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Kopiera värdet för den nya posten](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="e1cea-283">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-283">Select **add record**.</span></span>
    
    ![Välj Lägg till post](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="e1cea-285">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="e1cea-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e1cea-286">I avsnittet **Add DNS Record** skapar du en post med värdena från den andra raden i tabellen och väljer sedan **Add Record** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="e1cea-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e1cea-p114">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1cea-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

