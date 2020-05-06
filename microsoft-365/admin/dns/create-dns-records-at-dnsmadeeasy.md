---
title: Skapa DNS-poster på DNSMadeEasy för Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på DNSMadeEasy för Microsoft.
ms.openlocfilehash: d69a497c08ff905c28b923ebdb0e6fba6c5f82fa
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049065"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="85ab5-103">Skapa DNS-poster på DNSMadeEasy för Microsoft</span><span class="sxs-lookup"><span data-stu-id="85ab5-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="85ab5-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="85ab5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="85ab5-105">Om DNSMadeEasy är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="85ab5-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="85ab5-106">När du har lagt till dessa poster på DNSMadeEasy konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="85ab5-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="85ab5-p101">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="85ab5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="85ab5-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="85ab5-110">Add a TXT record for verification</span></span>
<span data-ttu-id="85ab5-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="85ab5-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="85ab5-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="85ab5-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85ab5-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="85ab5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="85ab5-116">För DNSMadeEasy-konton köptes domänen som du lade till från en separat domänregistratorer.</span><span class="sxs-lookup"><span data-stu-id="85ab5-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="85ab5-117">DNSMadeEasy erbjuder inte domänregistreringstjänster.</span><span class="sxs-lookup"><span data-stu-id="85ab5-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="85ab5-118">Din förmåga att logga in på DNSMadeEasy och skapa DNS-posten är tillräckligt bevis på ägande.</span><span class="sxs-lookup"><span data-stu-id="85ab5-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="85ab5-119">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="85ab5-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="85ab5-120">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="85ab5-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="85ab5-121">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="85ab5-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="85ab5-122">På sidan **Hanterad DNS** i området **TXT** **+** Records väljer du () **(Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="85ab5-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="85ab5-123">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="85ab5-124">Gå till området **Add TXT Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="85ab5-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="85ab5-125">**Namn**</span><span class="sxs-lookup"><span data-stu-id="85ab5-125">**Name**</span></span> <br/> |<span data-ttu-id="85ab5-126">**Värde**</span><span class="sxs-lookup"><span data-stu-id="85ab5-126">**Value**</span></span> <br/> |<span data-ttu-id="85ab5-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85ab5-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="85ab5-128">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="85ab5-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="85ab5-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="85ab5-130">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="85ab5-130">**Note:** This is an example.</span></span> <span data-ttu-id="85ab5-131">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="85ab5-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="85ab5-132">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="85ab5-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="85ab5-133">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="85ab5-134">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="85ab5-135">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="85ab5-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="85ab5-136">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="85ab5-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="85ab5-137">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="85ab5-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="85ab5-138">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="85ab5-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="85ab5-139">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="85ab5-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="85ab5-140">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="85ab5-141">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="85ab5-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="85ab5-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="85ab5-145">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85ab5-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="85ab5-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="85ab5-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="85ab5-p108">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="85ab5-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="85ab5-149">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="85ab5-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="85ab5-150">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="85ab5-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Konfigurera-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="85ab5-152">På sidan **Hanterad DNS** i området **MX Records** väljer du **(+)** kontrollen ( **Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="85ab5-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="85ab5-153">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Konfigurera-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="85ab5-155">Gå till området **Add MX Records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="85ab5-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="85ab5-156">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="85ab5-157">**Namn**</span><span class="sxs-lookup"><span data-stu-id="85ab5-157">**Name**</span></span>|<span data-ttu-id="85ab5-158">**Server**</span><span class="sxs-lookup"><span data-stu-id="85ab5-158">**Server**</span></span>|<span data-ttu-id="85ab5-159">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="85ab5-159">**MX Level**</span></span>|<span data-ttu-id="85ab5-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85ab5-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85ab5-161">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="85ab5-162">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="85ab5-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="85ab5-163">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="85ab5-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="85ab5-164">**Obs!** Hämta din \<*domännyckel*\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="85ab5-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="85ab5-165">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="85ab5-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="85ab5-166">10</span><span class="sxs-lookup"><span data-stu-id="85ab5-166">10</span></span>  <br/> <span data-ttu-id="85ab5-167">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="85ab5-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="85ab5-168">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="85ab5-170">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="85ab5-172">Om det finns andra MX-poster som visas i avsnittet **MX Records** ska du ta bort alla genom att välja dem.</span><span class="sxs-lookup"><span data-stu-id="85ab5-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Konfigurera-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="85ab5-174">När alla poster är markerade väljer du **Ta bort markerat**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Konfigurera-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="85ab5-176">Välj **Ta bort** för att bekräfta ändringarna i dialogrutan Ta **bort MX-poster.**</span><span class="sxs-lookup"><span data-stu-id="85ab5-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="85ab5-178">Lägga till de fem CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="85ab5-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="85ab5-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="85ab5-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="85ab5-p110">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="85ab5-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="85ab5-182">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="85ab5-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="85ab5-183">På sidan **Hanterad DNS** i området **CNAME Records** väljer du **(+)** kontrollen ( **Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="85ab5-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="85ab5-184">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1 DNSMadeEasy-BP-Configure-3-1 DNSMadeEasy-BP-Configure-3-1 DNSMade](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="85ab5-186">Lägg till den första av de fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="85ab5-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="85ab5-187">I den nya postens rutor i området **Add CNAME Records** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="85ab5-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="85ab5-188">**Name**</span><span class="sxs-lookup"><span data-stu-id="85ab5-188">**Name**</span></span>|<span data-ttu-id="85ab5-189">**Alias to**</span><span class="sxs-lookup"><span data-stu-id="85ab5-189">**Alias to**</span></span>|<span data-ttu-id="85ab5-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85ab5-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="85ab5-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="85ab5-191">autodiscover</span></span>  <br/> |<span data-ttu-id="85ab5-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="85ab5-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="85ab5-193">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="85ab5-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="85ab5-194">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-194">1800</span></span>  <br/> |
    |<span data-ttu-id="85ab5-195">sip</span><span class="sxs-lookup"><span data-stu-id="85ab5-195">sip</span></span>  <br/> |<span data-ttu-id="85ab5-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="85ab5-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="85ab5-197">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="85ab5-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="85ab5-198">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-198">1800</span></span>  <br/> |
    |<span data-ttu-id="85ab5-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="85ab5-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="85ab5-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="85ab5-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="85ab5-201">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="85ab5-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="85ab5-202">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-202">1800</span></span>  <br/> |
    |<span data-ttu-id="85ab5-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="85ab5-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="85ab5-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="85ab5-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="85ab5-205">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="85ab5-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="85ab5-206">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-206">1800</span></span>  <br/> |
    |<span data-ttu-id="85ab5-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="85ab5-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="85ab5-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="85ab5-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="85ab5-209">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="85ab5-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="85ab5-210">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="85ab5-212">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="85ab5-214">Lägg till var och en av de fyra andra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="85ab5-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="85ab5-215">I avsnittet **CNAME-poster** markerar du **(+)** kontrollen ( **Lägg till ny**), skapar en post med hjälp av värdena från nästa rad i tabellen och väljer sedan **Skicka** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="85ab5-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="85ab5-216">Upprepa den här processen tills du har skapat alla fem CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="85ab5-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="85ab5-217">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="85ab5-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="85ab5-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="85ab5-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="85ab5-219">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="85ab5-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="85ab5-220">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="85ab5-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="85ab5-221">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85ab5-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="85ab5-222">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="85ab5-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="85ab5-223">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="85ab5-223">Need examples?</span></span> <span data-ttu-id="85ab5-224">Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="85ab5-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="85ab5-225">Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="85ab5-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="85ab5-226">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="85ab5-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="85ab5-227">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="85ab5-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="85ab5-228">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="85ab5-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="85ab5-229">På sidan **Hanterad DNS** i området **TXT Records** väljer du **(+)** kontrollen ( **Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="85ab5-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="85ab5-230">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Konfigurera-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="85ab5-232">Gå till området **Add TXT Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="85ab5-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="85ab5-233">**Namn**</span><span class="sxs-lookup"><span data-stu-id="85ab5-233">**Name**</span></span>|<span data-ttu-id="85ab5-234">**Värde**</span><span class="sxs-lookup"><span data-stu-id="85ab5-234">**Value**</span></span>|<span data-ttu-id="85ab5-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85ab5-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="85ab5-236">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="85ab5-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="85ab5-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="85ab5-238">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="85ab5-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="85ab5-239">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="85ab5-241">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Konfigurera-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="85ab5-243">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="85ab5-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="85ab5-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="85ab5-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="85ab5-p113">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="85ab5-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="85ab5-247">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="85ab5-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="85ab5-248">På sidan **Hanterad DNS** i området **SRV Records** på sidan Hanterade DNS väljer du **(+)** kontrollen ( **Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="85ab5-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="85ab5-249">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="85ab5-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="85ab5-251">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="85ab5-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="85ab5-252">I den nya postens rutor i området **Add SRV Records** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="85ab5-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="85ab5-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="85ab5-253">**Name**</span></span>|<span data-ttu-id="85ab5-254">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="85ab5-254">**Priority**</span></span>|<span data-ttu-id="85ab5-255">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="85ab5-255">**Weight**</span></span>|<span data-ttu-id="85ab5-256">**Port**</span><span class="sxs-lookup"><span data-stu-id="85ab5-256">**Port**</span></span>|<span data-ttu-id="85ab5-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="85ab5-257">**Host**</span></span>|<span data-ttu-id="85ab5-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85ab5-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85ab5-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="85ab5-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="85ab5-260">100</span><span class="sxs-lookup"><span data-stu-id="85ab5-260">100</span></span>  <br/> |<span data-ttu-id="85ab5-261">1</span><span class="sxs-lookup"><span data-stu-id="85ab5-261">1</span></span>  <br/> |<span data-ttu-id="85ab5-262">443</span><span class="sxs-lookup"><span data-stu-id="85ab5-262">443</span></span>  <br/> |<span data-ttu-id="85ab5-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="85ab5-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="85ab5-264">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="85ab5-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="85ab5-265">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-265">1800</span></span>  <br/> |
    |<span data-ttu-id="85ab5-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="85ab5-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="85ab5-267">100</span><span class="sxs-lookup"><span data-stu-id="85ab5-267">100</span></span>  <br/> |<span data-ttu-id="85ab5-268">1</span><span class="sxs-lookup"><span data-stu-id="85ab5-268">1</span></span>  <br/> |<span data-ttu-id="85ab5-269">5061</span><span class="sxs-lookup"><span data-stu-id="85ab5-269">5061</span></span>  <br/> |<span data-ttu-id="85ab5-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="85ab5-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="85ab5-271">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="85ab5-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="85ab5-272">1800</span><span class="sxs-lookup"><span data-stu-id="85ab5-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="85ab5-274">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="85ab5-276">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="85ab5-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="85ab5-277">I avsnittet **SRV-poster** markerar du **(+)** kontrollen ( **Lägg till ny**), skapar en post med hjälp av värdena från nästa rad i tabellen och väljer sedan **Skicka** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="85ab5-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="85ab5-p114">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="85ab5-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

