---
title: Skapa DNS-poster på 123-reg.co.uk för Microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på 123-reg.co.uk för Microsoft.
ms.openlocfilehash: 887e7e6fc42fb55d4cc09ba66b68a2bb9702bbb9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629749"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="e7fb4-103">Skapa DNS-poster på 123-reg.co.uk för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fb4-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="e7fb4-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e7fb4-105">Om 123-reg.co.uk är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e7fb4-106">När du har lagt till dessa poster i 123-reg.co.uk konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="e7fb4-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7fb4-108">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e7fb4-109">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e7fb4-110">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e7fb4-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="e7fb4-111">Add a TXT record for verification</span></span>
<span data-ttu-id="e7fb4-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fb4-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e7fb4-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="e7fb4-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7fb4-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e7fb4-p104">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e7fb4-119">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e7fb4-120">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e7fb4-121">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e7fb4-122">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7fb4-123">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7fb4-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="e7fb4-124">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-124">**Hostname**</span></span> <br/> |<span data-ttu-id="e7fb4-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-125">**Type**</span></span> <br/> |<span data-ttu-id="e7fb4-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="e7fb4-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="e7fb4-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="e7fb4-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e7fb4-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e7fb4-129">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-129">**Note:** This is an example.</span></span> <span data-ttu-id="e7fb4-130">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-130">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e7fb4-131">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e7fb4-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="e7fb4-132">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="e7fb4-133">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e7fb4-134">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="e7fb4-135">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e7fb4-136">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="e7fb4-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e7fb4-137">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e7fb4-138">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e7fb4-139">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7fb4-140">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e7fb4-141">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e7fb4-142">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e7fb4-143">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fb4-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e7fb4-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fb4-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e7fb4-145">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-145">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="e7fb4-146">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-146">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e7fb4-147">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e7fb4-148">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e7fb4-149">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e7fb4-150">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7fb4-151">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7fb4-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7fb4-152">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-152">**Hostname**</span></span>|<span data-ttu-id="e7fb4-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-153">**Type**</span></span>|<span data-ttu-id="e7fb4-154">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-154">**Priority**</span></span>|<span data-ttu-id="e7fb4-155">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e7fb4-156">MX</span><span class="sxs-lookup"><span data-stu-id="e7fb4-156">MX</span></span>  <br/> |<span data-ttu-id="e7fb4-157">1</span><span class="sxs-lookup"><span data-stu-id="e7fb4-157">1</span></span>  <br/> <span data-ttu-id="e7fb4-158">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="e7fb4-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="e7fb4-159">*\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e7fb4-160">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e7fb4-161">**Anm.:** Hämta \<domännyckeln\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-161">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="e7fb4-162">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e7fb4-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopiera och klistra in värden från tabellen](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="e7fb4-164">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-164">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="e7fb4-166">Om det finns några andra MX-poster tar du bort var och en genom att välja ikonen **Ta bort (papperskorgen)** för den posten.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Välj Ta bort (papperskorgen ikon)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e7fb4-168">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fb4-168">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e7fb4-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fb4-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e7fb4-170">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-170">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="e7fb4-171">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-171">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e7fb4-172">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e7fb4-173">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e7fb4-174">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e7fb4-175">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="e7fb4-176">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7fb4-177">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7fb4-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7fb4-178">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-178">**Hostname**</span></span>|<span data-ttu-id="e7fb4-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-179">**Type**</span></span>|<span data-ttu-id="e7fb4-180">**Mål CNAME**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e7fb4-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e7fb4-181">autodiscover</span></span>  <br/> |<span data-ttu-id="e7fb4-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7fb4-182">CNAME</span></span>  <br/> |<span data-ttu-id="e7fb4-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e7fb4-184">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e7fb4-185">sip</span><span class="sxs-lookup"><span data-stu-id="e7fb4-185">sip</span></span>  <br/> |<span data-ttu-id="e7fb4-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7fb4-186">CNAME</span></span>  <br/> |<span data-ttu-id="e7fb4-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e7fb4-188">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e7fb4-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e7fb4-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e7fb4-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7fb4-190">CNAME</span></span>  <br/> |<span data-ttu-id="e7fb4-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e7fb4-192">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e7fb4-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e7fb4-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e7fb4-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7fb4-194">CNAME</span></span>  <br/> |<span data-ttu-id="e7fb4-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="e7fb4-196">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e7fb4-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e7fb4-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e7fb4-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7fb4-198">CNAME</span></span>  <br/> |<span data-ttu-id="e7fb4-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="e7fb4-200">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="e7fb4-202">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-202">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="e7fb4-204">Lägg till de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="e7fb4-205">Skapa en post med värdena från nästa rad i tabellen i avsnittet **Avancerad DNS** och välj sedan **Lägg** till igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="e7fb4-206">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e7fb4-207">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="e7fb4-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e7fb4-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fb4-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7fb4-209">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e7fb4-210">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e7fb4-211">Om du redan har en SPF-post för din domän ska du inte skapa en ny för Microsfot.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-211">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="e7fb4-212">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-212">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e7fb4-213">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="e7fb4-213">Need examples?</span></span> <span data-ttu-id="e7fb4-214">Kolla in dessa [externa domännamnssystemposter för Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-214">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="e7fb4-215">Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="e7fb4-216">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="e7fb4-217">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e7fb4-218">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e7fb4-219">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e7fb4-220">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e7fb4-221">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7fb4-222">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7fb4-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7fb4-223">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-223">**Hostname**</span></span>|<span data-ttu-id="e7fb4-224">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-224">**Type**</span></span>|<span data-ttu-id="e7fb4-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e7fb4-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="e7fb4-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="e7fb4-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e7fb4-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e7fb4-228">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="e7fb4-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Konfigurera-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="e7fb4-230">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-230">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e7fb4-232">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fb4-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e7fb4-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fb4-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e7fb4-234">Kom igång genom att gå till domänsidan på 123-reg.co.uk genom att klicka på [den här länken](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-234">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="e7fb4-235">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-235">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e7fb4-236">På sidan **Domännamnsöversikt** markerar du namnet på den domän du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e7fb4-237">Välj **DNS** i listrutan **Välj åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="e7fb4-238">Välj fliken **Avancerat DNS** på sidan **Hantera DNS.**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="e7fb4-239">Lägg till den första av de två SRV-posterna:</span><span class="sxs-lookup"><span data-stu-id="e7fb4-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="e7fb4-240">Gå till avsnittet **Advanced DNS**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7fb4-241">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7fb4-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7fb4-242">Hostname</span><span class="sxs-lookup"><span data-stu-id="e7fb4-242">Hostname</span></span>|<span data-ttu-id="e7fb4-243">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="e7fb4-243">Type</span></span>|<span data-ttu-id="e7fb4-244">Priority</span><span class="sxs-lookup"><span data-stu-id="e7fb4-244">Priority</span></span>|<span data-ttu-id="e7fb4-245">TTL</span><span class="sxs-lookup"><span data-stu-id="e7fb4-245">TTL</span></span>|<span data-ttu-id="e7fb4-246">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="e7fb4-246">Destination SRV</span></span>|
    |<span data-ttu-id="e7fb4-247">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e7fb4-247">_sip._tls</span></span>|<span data-ttu-id="e7fb4-248">SRV</span><span class="sxs-lookup"><span data-stu-id="e7fb4-248">SRV</span></span>|<span data-ttu-id="e7fb4-249">100</span><span class="sxs-lookup"><span data-stu-id="e7fb4-249">100</span></span>|<span data-ttu-id="e7fb4-250">3600</span><span class="sxs-lookup"><span data-stu-id="e7fb4-250">3600</span></span>|<span data-ttu-id="e7fb4-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="e7fb4-252">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="e7fb4-253">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="e7fb4-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="e7fb4-254">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e7fb4-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="e7fb4-255">SRV</span><span class="sxs-lookup"><span data-stu-id="e7fb4-255">SRV</span></span>|<span data-ttu-id="e7fb4-256">100</span><span class="sxs-lookup"><span data-stu-id="e7fb4-256">100</span></span>|<span data-ttu-id="e7fb4-257">3600</span><span class="sxs-lookup"><span data-stu-id="e7fb4-257">3600</span></span>|<span data-ttu-id="e7fb4-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="e7fb4-259">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7fb4-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="e7fb4-260">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="e7fb4-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="e7fb4-262">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-262">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="e7fb4-264">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="e7fb4-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="e7fb4-265">Skapa en post i avsnittet **Avancerad DNS** med hjälp av värdena från den andra raden i tabellen och välj sedan **Lägg** till igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e7fb4-266">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e7fb4-267">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="e7fb4-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e7fb4-268">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7fb4-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
