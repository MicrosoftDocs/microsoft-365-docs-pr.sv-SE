---
title: Skapa DNS-poster på 123-reg.co.uk för Office 365
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på 123-reg.co.uk för Office 365.
ms.openlocfilehash: 327f55dcedfda6eef31d56af1833a5c5438af2a6
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42813017"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="b4860-103">Skapa DNS-poster på 123-reg.co.uk för Office 365</span><span class="sxs-lookup"><span data-stu-id="b4860-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="b4860-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="b4860-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b4860-105">Om 123-reg.co.uk är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="b4860-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b4860-106">När du har lagt till dessa poster på 123-reg.co.uk konfigureras domänen så att den fungerar med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="b4860-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="b4860-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="b4860-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b4860-p101">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b4860-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b4860-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="b4860-111">Add a TXT record for verification</span></span>
<span data-ttu-id="b4860-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b4860-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b4860-p102">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="b4860-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b4860-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="b4860-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b4860-p104">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b4860-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b4860-119">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="b4860-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b4860-120">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="b4860-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b4860-121">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="b4860-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b4860-122">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b4860-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b4860-123">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b4860-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="b4860-124">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="b4860-124">**Hostname**</span></span> <br/> |<span data-ttu-id="b4860-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="b4860-125">**Type**</span></span> <br/> |<span data-ttu-id="b4860-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="b4860-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b4860-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="b4860-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="b4860-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b4860-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b4860-129">**Anm.:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="b4860-129">**Note:** This is an example.</span></span> <span data-ttu-id="b4860-130">Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4860-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="b4860-131">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="b4860-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="b4860-132">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b4860-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="b4860-133">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="b4860-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b4860-134">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="b4860-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b4860-135">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="b4860-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b4860-136">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="b4860-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b4860-137">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="b4860-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b4860-138">Välj **Starta inställningar**på sidan **Inställningar** .</span><span class="sxs-lookup"><span data-stu-id="b4860-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b4860-139">På sidan **Verifiera domän** väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="b4860-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b4860-p106">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b4860-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="b4860-143">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="b4860-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="b4860-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b4860-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b4860-145">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="b4860-145">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="b4860-146">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b4860-146">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b4860-147">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="b4860-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b4860-148">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="b4860-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b4860-149">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="b4860-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b4860-150">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b4860-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b4860-151">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b4860-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b4860-152">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="b4860-152">**Hostname**</span></span>|<span data-ttu-id="b4860-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="b4860-153">**Type**</span></span>|<span data-ttu-id="b4860-154">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b4860-154">**Priority**</span></span>|<span data-ttu-id="b4860-155">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="b4860-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b4860-156">MX</span><span class="sxs-lookup"><span data-stu-id="b4860-156">MX</span></span>  <br/> |<span data-ttu-id="b4860-157">1</span><span class="sxs-lookup"><span data-stu-id="b4860-157">1</span></span>  <br/> <span data-ttu-id="b4860-158">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4860-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="b4860-159">*\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b4860-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b4860-160">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="b4860-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b4860-161">**Anm.:** Hämta \<domännyckeln\> från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="b4860-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="b4860-162">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="b4860-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopiera och klistra in värden från tabellen](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="b4860-164">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b4860-164">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="b4860-166">Om det finns några andra MX-poster tar du bort var och en genom att välja ikonen **Ta bort (papperskorgen)** för den posten.</span><span class="sxs-lookup"><span data-stu-id="b4860-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Välj Ta bort (papperskorgen ikon)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="b4860-168">Lägg till de sex CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="b4860-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="b4860-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b4860-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b4860-170">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="b4860-170">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="b4860-171">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b4860-171">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b4860-172">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="b4860-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b4860-173">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="b4860-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b4860-174">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="b4860-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b4860-175">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="b4860-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="b4860-176">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b4860-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b4860-177">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b4860-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b4860-178">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="b4860-178">**Hostname**</span></span>|<span data-ttu-id="b4860-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="b4860-179">**Type**</span></span>|<span data-ttu-id="b4860-180">**Mål CNAME**</span><span class="sxs-lookup"><span data-stu-id="b4860-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b4860-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b4860-181">autodiscover</span></span>  <br/> |<span data-ttu-id="b4860-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="b4860-182">CNAME</span></span>  <br/> |<span data-ttu-id="b4860-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b4860-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b4860-184">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="b4860-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b4860-185">sip</span><span class="sxs-lookup"><span data-stu-id="b4860-185">sip</span></span>  <br/> |<span data-ttu-id="b4860-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="b4860-186">CNAME</span></span>  <br/> |<span data-ttu-id="b4860-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b4860-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b4860-188">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="b4860-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b4860-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b4860-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b4860-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="b4860-190">CNAME</span></span>  <br/> |<span data-ttu-id="b4860-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b4860-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b4860-192">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="b4860-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b4860-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b4860-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b4860-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="b4860-194">CNAME</span></span>  <br/> |<span data-ttu-id="b4860-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="b4860-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="b4860-196">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="b4860-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b4860-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b4860-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b4860-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="b4860-198">CNAME</span></span>  <br/> |<span data-ttu-id="b4860-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b4860-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="b4860-200">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="b4860-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="b4860-202">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b4860-202">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="b4860-204">Lägg till de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="b4860-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="b4860-205">Skapa en post med värdena från nästa rad i tabellen i avsnittet **Avancerad DNS** och välj sedan **Lägg** till igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="b4860-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="b4860-206">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="b4860-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b4860-207">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="b4860-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b4860-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b4860-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4860-209">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="b4860-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b4860-210">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="b4860-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b4860-211">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4860-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="b4860-212">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="b4860-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="b4860-213">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="b4860-213">Need examples?</span></span> <span data-ttu-id="b4860-214">Kolla in dessa [externa domännamnssystemposter för Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="b4860-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="b4860-215">Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="b4860-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="b4860-216">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="b4860-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="b4860-217">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b4860-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b4860-218">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="b4860-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b4860-219">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="b4860-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b4860-220">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="b4860-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b4860-221">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b4860-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b4860-222">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b4860-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b4860-223">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="b4860-223">**Hostname**</span></span>|<span data-ttu-id="b4860-224">**Type**</span><span class="sxs-lookup"><span data-stu-id="b4860-224">**Type**</span></span>|<span data-ttu-id="b4860-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="b4860-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b4860-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="b4860-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="b4860-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b4860-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b4860-228">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="b4860-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Konfigurera-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="b4860-230">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b4860-230">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="b4860-232">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="b4860-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="b4860-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b4860-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b4860-234">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="b4860-234">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="b4860-235">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b4860-235">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b4860-236">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="b4860-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b4860-237">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="b4860-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b4860-238">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="b4860-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b4860-239">Lägg till den första av de två SRV-posterna:</span><span class="sxs-lookup"><span data-stu-id="b4860-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="b4860-240">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b4860-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b4860-241">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b4860-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b4860-242">Hostname</span><span class="sxs-lookup"><span data-stu-id="b4860-242">Hostname</span></span>|<span data-ttu-id="b4860-243">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="b4860-243">Type</span></span>|<span data-ttu-id="b4860-244">Prioritet</span><span class="sxs-lookup"><span data-stu-id="b4860-244">Priority</span></span>|<span data-ttu-id="b4860-245">TTL</span><span class="sxs-lookup"><span data-stu-id="b4860-245">TTL</span></span>|<span data-ttu-id="b4860-246">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="b4860-246">Destination SRV</span></span>|
    |<span data-ttu-id="b4860-247">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="b4860-247">_sip._tls</span></span>|<span data-ttu-id="b4860-248">SRV</span><span class="sxs-lookup"><span data-stu-id="b4860-248">SRV</span></span>|<span data-ttu-id="b4860-249">100</span><span class="sxs-lookup"><span data-stu-id="b4860-249">100</span></span>|<span data-ttu-id="b4860-250">3600</span><span class="sxs-lookup"><span data-stu-id="b4860-250">3600</span></span>|<span data-ttu-id="b4860-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b4860-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="b4860-252">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="b4860-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="b4860-253">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="b4860-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="b4860-254">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="b4860-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="b4860-255">SRV</span><span class="sxs-lookup"><span data-stu-id="b4860-255">SRV</span></span>|<span data-ttu-id="b4860-256">100</span><span class="sxs-lookup"><span data-stu-id="b4860-256">100</span></span>|<span data-ttu-id="b4860-257">3600</span><span class="sxs-lookup"><span data-stu-id="b4860-257">3600</span></span>|<span data-ttu-id="b4860-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b4860-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="b4860-259">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="b4860-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="b4860-260">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="b4860-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="b4860-262">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b4860-262">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="b4860-264">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="b4860-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="b4860-265">Skapa en post i avsnittet **Avancerad DNS** med hjälp av värdena från den andra raden i tabellen och välj sedan **Lägg** till igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="b4860-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b4860-p115">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b4860-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
