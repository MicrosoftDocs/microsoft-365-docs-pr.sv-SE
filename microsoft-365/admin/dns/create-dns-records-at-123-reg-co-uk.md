---
title: Skapa DNS-poster på 123-reg.co.uk för Microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på 123-reg.co.uk för Microsoft.
ms.openlocfilehash: d1e4d3d01a5e6b4f72c98fe09cf57374dd2417a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910432"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="0144f-103">Skapa DNS-poster på 123-reg.co.uk för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0144f-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="0144f-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="0144f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0144f-105">Om 123-reg.co.uk är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="0144f-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0144f-106">När du har lagt till dessa 123-reg.co.uk posterna är domänen konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="0144f-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="0144f-p101">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0144f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0144f-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="0144f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="0144f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0144f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0144f-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="0144f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0144f-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="0144f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0144f-p104">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0144f-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0144f-118">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0144f-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0144f-119">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="0144f-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0144f-120">På sidan **Manage your DNS** väljer du fliken Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="0144f-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0144f-121">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0144f-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0144f-122">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="0144f-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="0144f-123">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0144f-123">**Hostname**</span></span> <br/> |<span data-ttu-id="0144f-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="0144f-124">**Type**</span></span> <br/> |<span data-ttu-id="0144f-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="0144f-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="0144f-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="0144f-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="0144f-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0144f-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0144f-128">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0144f-128">**Note:** This is an example.</span></span> <span data-ttu-id="0144f-129">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="0144f-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="0144f-130">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="0144f-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="0144f-131">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0144f-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="0144f-132">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="0144f-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0144f-133">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="0144f-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="0144f-134">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="0144f-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0144f-135">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="0144f-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0144f-136">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="0144f-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0144f-137">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="0144f-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0144f-138">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="0144f-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0144f-p106">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0144f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0144f-142">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0144f-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0144f-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0144f-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0144f-144">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="0144f-144">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="0144f-145">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0144f-145">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0144f-146">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0144f-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0144f-147">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="0144f-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0144f-148">På sidan **Manage your DNS** väljer du fliken Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="0144f-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0144f-149">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0144f-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0144f-150">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="0144f-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0144f-151">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0144f-151">**Hostname**</span></span>|<span data-ttu-id="0144f-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="0144f-152">**Type**</span></span>|<span data-ttu-id="0144f-153">**Priority**</span><span class="sxs-lookup"><span data-stu-id="0144f-153">**Priority**</span></span>|<span data-ttu-id="0144f-154">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="0144f-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0144f-155">MX</span><span class="sxs-lookup"><span data-stu-id="0144f-155">MX</span></span>  <br/> |<span data-ttu-id="0144f-156">1</span><span class="sxs-lookup"><span data-stu-id="0144f-156">1</span></span>  <br/> <span data-ttu-id="0144f-157">[Mer information om prioritet finns i ](../setup/domains-faq.yml)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="0144f-157">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="0144f-158">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0144f-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0144f-159">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0144f-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="0144f-160">**Obs!** Hämta din \<domain-key\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="0144f-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="0144f-161">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="0144f-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopiera och klistra in värden från tabellen](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="0144f-163">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0144f-163">Select **Add**.</span></span>
    
    ![Skärmbild av dialogrutan med knappen Lägg till markerad](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="0144f-165">Om det finns andra MX-poster tar du bort var och en av dem genom att välja ikonen Ta bort **(papperskorg)** för den posten.</span><span class="sxs-lookup"><span data-stu-id="0144f-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Välj Ta bort (papperskorgsikonen)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0144f-167">Lägg till de fem CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0144f-167">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0144f-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0144f-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0144f-169">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="0144f-169">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="0144f-170">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0144f-170">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0144f-171">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0144f-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0144f-172">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="0144f-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0144f-173">På sidan **Manage your DNS** väljer du fliken Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="0144f-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0144f-174">Lägg till den första av de fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="0144f-174">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="0144f-175">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0144f-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0144f-176">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="0144f-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0144f-177">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0144f-177">**Hostname**</span></span>|<span data-ttu-id="0144f-178">**Type**</span><span class="sxs-lookup"><span data-stu-id="0144f-178">**Type**</span></span>|<span data-ttu-id="0144f-179">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="0144f-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0144f-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0144f-180">autodiscover</span></span>  <br/> |<span data-ttu-id="0144f-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="0144f-181">CNAME</span></span>  <br/> |<span data-ttu-id="0144f-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0144f-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="0144f-183">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0144f-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0144f-184">sip</span><span class="sxs-lookup"><span data-stu-id="0144f-184">sip</span></span>  <br/> |<span data-ttu-id="0144f-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="0144f-185">CNAME</span></span>  <br/> |<span data-ttu-id="0144f-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0144f-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0144f-187">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0144f-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0144f-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0144f-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0144f-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="0144f-189">CNAME</span></span>  <br/> |<span data-ttu-id="0144f-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0144f-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0144f-191">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0144f-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0144f-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0144f-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0144f-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="0144f-193">CNAME</span></span>  <br/> |<span data-ttu-id="0144f-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="0144f-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="0144f-195">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0144f-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0144f-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0144f-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0144f-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="0144f-197">CNAME</span></span>  <br/> |<span data-ttu-id="0144f-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0144f-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="0144f-199">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0144f-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Skärmbild med Destination CNAME för att kopiera och klistra in](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="0144f-201">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0144f-201">Select **Add**.</span></span>
    
    ![Skärmbild för att lägga till Destination CNAME](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="0144f-203">Lägg till de andra fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="0144f-203">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="0144f-204">I avsnittet **Advanced DNS** skapar du en post med värdena från nästa rad i tabellen och väljer sedan **Add** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="0144f-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="0144f-205">Upprepa proceduren tills du har skapat alla fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="0144f-205">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0144f-206">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="0144f-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0144f-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0144f-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0144f-208">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="0144f-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0144f-209">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="0144f-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0144f-210">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0144f-210">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0144f-211">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="0144f-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="0144f-212">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="0144f-212">Need examples?</span></span> <span data-ttu-id="0144f-213">Ta en titt på dessa [externa DNS-poster för Microsoft](../../enterprise/external-domain-name-system-records.md#external-dns-records-required-for-spf).</span><span class="sxs-lookup"><span data-stu-id="0144f-213">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="0144f-214">Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="0144f-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="0144f-215">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="0144f-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="0144f-216">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0144f-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0144f-217">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0144f-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0144f-218">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="0144f-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0144f-219">På sidan **Manage your DNS** väljer du fliken Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="0144f-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0144f-220">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0144f-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0144f-221">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="0144f-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0144f-222">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0144f-222">**Hostname**</span></span>|<span data-ttu-id="0144f-223">**Type**</span><span class="sxs-lookup"><span data-stu-id="0144f-223">**Type**</span></span>|<span data-ttu-id="0144f-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="0144f-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0144f-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="0144f-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="0144f-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0144f-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0144f-227">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="0144f-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP - Konfigurera-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="0144f-229">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0144f-229">Select **Add**.</span></span>
    
    ![Skärmbild med Destination TXT/SPF](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0144f-231">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0144f-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0144f-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0144f-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0144f-233">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="0144f-233">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="0144f-234">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0144f-234">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0144f-235">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0144f-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0144f-236">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="0144f-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0144f-237">På sidan **Manage your DNS** väljer du fliken Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="0144f-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0144f-238">Lägg till den första av de två SRV-posterna:</span><span class="sxs-lookup"><span data-stu-id="0144f-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="0144f-239">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0144f-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0144f-240">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="0144f-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0144f-241">Hostname</span><span class="sxs-lookup"><span data-stu-id="0144f-241">Hostname</span></span>|<span data-ttu-id="0144f-242">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="0144f-242">Type</span></span>|<span data-ttu-id="0144f-243">Prioritet</span><span class="sxs-lookup"><span data-stu-id="0144f-243">Priority</span></span>|<span data-ttu-id="0144f-244">TTL</span><span class="sxs-lookup"><span data-stu-id="0144f-244">TTL</span></span>|<span data-ttu-id="0144f-245">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="0144f-245">Destination SRV</span></span>|
    |<span data-ttu-id="0144f-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="0144f-246">_sip._tls</span></span>|<span data-ttu-id="0144f-247">SRV</span><span class="sxs-lookup"><span data-stu-id="0144f-247">SRV</span></span>|<span data-ttu-id="0144f-248">100</span><span class="sxs-lookup"><span data-stu-id="0144f-248">100</span></span>|<span data-ttu-id="0144f-249">3600</span><span class="sxs-lookup"><span data-stu-id="0144f-249">3600</span></span>|<span data-ttu-id="0144f-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0144f-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="0144f-251">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0144f-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="0144f-252">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="0144f-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="0144f-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="0144f-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="0144f-254">SRV</span><span class="sxs-lookup"><span data-stu-id="0144f-254">SRV</span></span>|<span data-ttu-id="0144f-255">100</span><span class="sxs-lookup"><span data-stu-id="0144f-255">100</span></span>|<span data-ttu-id="0144f-256">3600</span><span class="sxs-lookup"><span data-stu-id="0144f-256">3600</span></span>|<span data-ttu-id="0144f-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0144f-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="0144f-258">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0144f-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="0144f-259">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="0144f-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Skärmbild med DNS-värden från tabellen](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="0144f-261">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0144f-261">Select **Add**.</span></span>
    
    ![Skärmbild för att lägga till Destination SRV](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="0144f-263">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="0144f-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="0144f-264">I avsnittet **Advanced DNS** skapar du en post med värdena från den andra raden i tabellen och väljer sedan **Add** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="0144f-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0144f-p115">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0144f-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
