---
title: Skapa DNS-poster på Dreamhost för Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Dreamhost för Microsoft.
ms.openlocfilehash: 8ab617fd5d63b292a85289d2d51a0ae0fd3b26be
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646205"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="74efa-103">Skapa DNS-poster på Dreamhost för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74efa-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="74efa-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="74efa-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="74efa-105">Om DreamHost är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Lync och så vidare.</span><span class="sxs-lookup"><span data-stu-id="74efa-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="74efa-106">När du har lagt till dessa poster på DreamHost är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="74efa-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="74efa-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="74efa-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="74efa-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="74efa-110">Add a TXT record for verification</span></span>
<span data-ttu-id="74efa-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="74efa-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="74efa-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="74efa-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74efa-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="74efa-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="74efa-116">Kom igång genom att gå till sidan Domains på DreamHost med hjälp av [den här länken](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="74efa-116">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="74efa-117">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="74efa-117">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="74efa-119">Välj **domäner**på sidan **instrument panel** och sedan **hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="74efa-119">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="74efa-121">Välj **DNS** för den domän som du vill redigera i avsnittet **Domain** på sidan **hantera domäner** .</span><span class="sxs-lookup"><span data-stu-id="74efa-121">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="74efa-123">I rutorna för den nya posten i avsnittet **Add a Custom DNS Record** skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="74efa-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="74efa-124">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="74efa-125">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="74efa-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="74efa-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="74efa-126">**Name**</span></span>|<span data-ttu-id="74efa-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="74efa-127">**Type**</span></span>|<span data-ttu-id="74efa-128">**Värde**</span><span class="sxs-lookup"><span data-stu-id="74efa-128">**Value**</span></span>|<span data-ttu-id="74efa-129">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="74efa-129">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74efa-130">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="74efa-131">TXT</span><span class="sxs-lookup"><span data-stu-id="74efa-131">TXT</span></span>  <br/> |<span data-ttu-id="74efa-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="74efa-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="74efa-133">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="74efa-133">**Note:** This is an example.</span></span> <span data-ttu-id="74efa-134">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="74efa-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="74efa-135">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="74efa-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="74efa-136">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-136">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="74efa-138">Välj **Lägg till post nu!**</span><span class="sxs-lookup"><span data-stu-id="74efa-138">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="74efa-140">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="74efa-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="74efa-141">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="74efa-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="74efa-142">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="74efa-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="74efa-143">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="74efa-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="74efa-144">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="74efa-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="74efa-145">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="74efa-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="74efa-146">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="74efa-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="74efa-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="74efa-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="74efa-150">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74efa-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="74efa-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="74efa-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="74efa-152">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="74efa-152">Follow the steps below.</span></span>
  
1. <span data-ttu-id="74efa-153">Kom igång genom att gå till sidan Domains på DreamHost med hjälp av [den här länken](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="74efa-153">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="74efa-154">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="74efa-154">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="74efa-156">Välj **e-post**på sidan **Dashboard** och sedan **anpassad MX**.</span><span class="sxs-lookup"><span data-stu-id="74efa-156">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="74efa-158">I avsnittet **Hantera e-postleverans** i kolumnen **åtgärder** väljer du **Redigera** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="74efa-158">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="74efa-160">I den **anpassade MX-post** -rutan, i rutorna för den nya posten, skriver du in, eller kopierar, följande värden från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="74efa-160">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="74efa-161">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-161">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="74efa-162">(Om det finns andra befintliga MX-poster markerar du de poster som ska tas bort.)</span><span class="sxs-lookup"><span data-stu-id="74efa-162">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="74efa-163">**MX-post (obligatoriskt)**</span><span class="sxs-lookup"><span data-stu-id="74efa-163">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="74efa-164">0  *\<domain-key\>*  . mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="74efa-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="74efa-165">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="74efa-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="74efa-p108">0 motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="74efa-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="74efa-168">**Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="74efa-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="74efa-169">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="74efa-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="74efa-171">Välj **ändra den här domänen för att använda anpassade MX-poster nu!**</span><span class="sxs-lookup"><span data-stu-id="74efa-171">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="74efa-173">Om det finns andra befintliga MX-poster tar du bort varje post genom att välja posten och sedan trycka på **Delete** -tangenten på tangent bordet.</span><span class="sxs-lookup"><span data-stu-id="74efa-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="74efa-175">Om du har tagit bort några poster väljer du **Uppdatera dina MX-poster nu!**</span><span class="sxs-lookup"><span data-stu-id="74efa-175">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="74efa-177">Lägga till de sex CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74efa-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="74efa-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="74efa-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="74efa-179">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="74efa-179">Follow the steps below.</span></span>
  
1. <span data-ttu-id="74efa-180">Kom igång genom att gå till sidan Domains på DreamHost med hjälp av [den här länken](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="74efa-180">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="74efa-181">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="74efa-181">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="74efa-183">Välj **domäner**på sidan **instrument panel** och sedan **hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="74efa-183">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="74efa-185">Välj **DNS** för den domän som du vill redigera i avsnittet **Domain** på sidan **hantera domäner** .</span><span class="sxs-lookup"><span data-stu-id="74efa-185">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="74efa-187">Skriv eller kopiera och klistra in värdena från den första raden i följande tabell i rutorna för den nya posten i avsnittet **Lägg till en anpassad DNS-post** .</span><span class="sxs-lookup"><span data-stu-id="74efa-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="74efa-188">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-188">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="74efa-189">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="74efa-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="74efa-190">**Name**</span><span class="sxs-lookup"><span data-stu-id="74efa-190">**Name**</span></span>|<span data-ttu-id="74efa-191">**Typ**</span><span class="sxs-lookup"><span data-stu-id="74efa-191">**Type**</span></span>|<span data-ttu-id="74efa-192">**Värde**</span><span class="sxs-lookup"><span data-stu-id="74efa-192">**Value**</span></span>|<span data-ttu-id="74efa-193">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="74efa-193">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74efa-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="74efa-194">autodiscover</span></span>  <br/> |<span data-ttu-id="74efa-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="74efa-195">CNAME</span></span>  <br/> |<span data-ttu-id="74efa-196">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="74efa-196">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="74efa-197">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="74efa-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="74efa-198">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-198">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="74efa-199">sip</span><span class="sxs-lookup"><span data-stu-id="74efa-199">sip</span></span>  <br/> |<span data-ttu-id="74efa-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="74efa-200">CNAME</span></span>  <br/> |<span data-ttu-id="74efa-201">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="74efa-201">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="74efa-202">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="74efa-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="74efa-203">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-203">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="74efa-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="74efa-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="74efa-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="74efa-205">CNAME</span></span>  <br/> |<span data-ttu-id="74efa-206">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="74efa-206">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="74efa-207">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="74efa-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="74efa-208">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-208">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="74efa-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="74efa-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="74efa-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="74efa-210">CNAME</span></span>  <br/> |<span data-ttu-id="74efa-211">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="74efa-211">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="74efa-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="74efa-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="74efa-213">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-213">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="74efa-214">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="74efa-214">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="74efa-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="74efa-215">CNAME</span></span>  <br/> |<span data-ttu-id="74efa-216">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="74efa-216">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="74efa-217">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="74efa-217">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="74efa-218">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-218">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="74efa-220">Välj **Lägg till post nu!**</span><span class="sxs-lookup"><span data-stu-id="74efa-220">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="74efa-222">Med föregående två steg och värdena från de andra fem raderna i tabellen lägger du till var och en av de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="74efa-222">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="74efa-223">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="74efa-223">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="74efa-224"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="74efa-224"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="74efa-225">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="74efa-225">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="74efa-226">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="74efa-226">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="74efa-227">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74efa-227">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="74efa-228">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="74efa-228">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="74efa-229">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="74efa-229">Follow the steps below.</span></span>
  
1. <span data-ttu-id="74efa-230">Kom igång genom att gå till sidan Domains på DreamHost med hjälp av [den här länken](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="74efa-230">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="74efa-231">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="74efa-231">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="74efa-233">Välj **domäner**på sidan **instrument panel** och sedan **hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="74efa-233">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="74efa-235">Välj **DNS** för den domän som du vill redigera i avsnittet **Domain** på sidan **hantera domäner** .</span><span class="sxs-lookup"><span data-stu-id="74efa-235">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="74efa-237">Skriv eller kopiera och klistra in värdena från den första raden i följande tabell i rutorna för den nya posten i avsnittet **Lägg till en anpassad DNS-post** .</span><span class="sxs-lookup"><span data-stu-id="74efa-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="74efa-238">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-238">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="74efa-239">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="74efa-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="74efa-240">**Name**</span><span class="sxs-lookup"><span data-stu-id="74efa-240">**Name**</span></span>|<span data-ttu-id="74efa-241">**Typ**</span><span class="sxs-lookup"><span data-stu-id="74efa-241">**Type**</span></span>|<span data-ttu-id="74efa-242">**Värde**</span><span class="sxs-lookup"><span data-stu-id="74efa-242">**Value**</span></span>|<span data-ttu-id="74efa-243">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="74efa-243">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74efa-244">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="74efa-245">TXT</span><span class="sxs-lookup"><span data-stu-id="74efa-245">TXT</span></span>  <br/> |<span data-ttu-id="74efa-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="74efa-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="74efa-247">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="74efa-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="74efa-248">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-248">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="74efa-250">Välj **Lägg till post nu!**</span><span class="sxs-lookup"><span data-stu-id="74efa-250">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="74efa-252">Med föregående två steg och värdena från den andra raden i tabellen lägger du till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="74efa-252">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="74efa-253">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74efa-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="74efa-254"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="74efa-254"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="74efa-255">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="74efa-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="74efa-256">Kom igång genom att gå till sidan Domains på DreamHost med hjälp av [den här länken](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="74efa-256">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="74efa-257">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="74efa-257">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="74efa-259">Välj **domäner**på sidan **instrument panel** och sedan **hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="74efa-259">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="74efa-261">Välj **DNS** för den domän som du vill redigera i avsnittet **Domain** på sidan **hantera domäner** .</span><span class="sxs-lookup"><span data-stu-id="74efa-261">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="74efa-263">Skriv eller kopiera och klistra in värdena från den första raden i följande tabell i rutorna för den nya posten i avsnittet **Lägg till en anpassad DNS-post** .</span><span class="sxs-lookup"><span data-stu-id="74efa-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="74efa-264">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-264">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="74efa-265">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="74efa-265">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="74efa-266">**Name**</span><span class="sxs-lookup"><span data-stu-id="74efa-266">**Name**</span></span>|<span data-ttu-id="74efa-267">**Typ**</span><span class="sxs-lookup"><span data-stu-id="74efa-267">**Type**</span></span>|<span data-ttu-id="74efa-268">**Värde**</span><span class="sxs-lookup"><span data-stu-id="74efa-268">**Value**</span></span>|<span data-ttu-id="74efa-269">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="74efa-269">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74efa-270">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="74efa-270">_sip._tls</span></span>  <br/> |<span data-ttu-id="74efa-271">SRV</span><span class="sxs-lookup"><span data-stu-id="74efa-271">SRV</span></span>  <br/> |<span data-ttu-id="74efa-272">100 1 443</span><span class="sxs-lookup"><span data-stu-id="74efa-272">100 1 443</span></span>  <br/> <span data-ttu-id="74efa-273">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="74efa-273">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="74efa-274">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="74efa-274">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="74efa-275">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-275">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="74efa-276">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="74efa-276">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="74efa-277">SRV</span><span class="sxs-lookup"><span data-stu-id="74efa-277">SRV</span></span>  <br/> |<span data-ttu-id="74efa-278">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="74efa-278">100 1 5061</span></span>  <br/> <span data-ttu-id="74efa-279">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="74efa-279">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="74efa-280">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="74efa-280">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="74efa-281">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="74efa-281">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="74efa-283">Välj **Lägg till post nu!**.</span><span class="sxs-lookup"><span data-stu-id="74efa-283">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="74efa-285">Med föregående två steg och värdena från den andra raden i tabellen lägger du till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="74efa-285">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="74efa-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="74efa-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
