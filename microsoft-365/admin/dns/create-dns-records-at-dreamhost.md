---
title: Skapa DNS-poster på Dreamhost för Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Dreamhost för Microsoft.
ms.openlocfilehash: 2187cc155bc15e8482960d933d9136401ea29beb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629809"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="be6f0-103">Skapa DNS-poster på Dreamhost för Microsoft</span><span class="sxs-lookup"><span data-stu-id="be6f0-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="be6f0-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="be6f0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="be6f0-105">Om DreamHost är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Lync och så vidare.</span><span class="sxs-lookup"><span data-stu-id="be6f0-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="be6f0-106">När du har lagt till dessa poster på DreamHost konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="be6f0-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="be6f0-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="be6f0-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="be6f0-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="be6f0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="be6f0-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="be6f0-111">Add a TXT record for verification</span></span>
<span data-ttu-id="be6f0-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="be6f0-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="be6f0-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="be6f0-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="be6f0-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="be6f0-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be6f0-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="be6f0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="be6f0-117">För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="be6f0-117">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="be6f0-118">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="be6f0-118">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="be6f0-120">På **instrumentpanelssidan** väljer du **Domäner**och hanterar sedan **domäner**.</span><span class="sxs-lookup"><span data-stu-id="be6f0-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="be6f0-122">Välj **DNS** för den domän som du vill redigera i avsnittet **Domän** på sidan **Hantera domäner.**</span><span class="sxs-lookup"><span data-stu-id="be6f0-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Konfigurera-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="be6f0-124">I avsnittet **Lägg till en anpassad DNS-post** skriver eller kopierar eller klistrar du in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="be6f0-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="be6f0-125">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="be6f0-126">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="be6f0-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="be6f0-127">**Name**</span></span>|<span data-ttu-id="be6f0-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="be6f0-128">**Type**</span></span>|<span data-ttu-id="be6f0-129">**Värde**</span><span class="sxs-lookup"><span data-stu-id="be6f0-129">**Value**</span></span>|<span data-ttu-id="be6f0-130">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="be6f0-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="be6f0-131">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="be6f0-132">TXT</span><span class="sxs-lookup"><span data-stu-id="be6f0-132">TXT</span></span>  <br/> |<span data-ttu-id="be6f0-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="be6f0-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="be6f0-134">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="be6f0-134">**Note:** This is an example.</span></span> <span data-ttu-id="be6f0-135">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="be6f0-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="be6f0-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="be6f0-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="be6f0-137">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Verifiera-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="be6f0-139">Välj **Lägg till post nu!**</span><span class="sxs-lookup"><span data-stu-id="be6f0-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verifiera-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="be6f0-141">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="be6f0-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="be6f0-142">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="be6f0-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="be6f0-143">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="be6f0-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="be6f0-144">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="be6f0-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="be6f0-145">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="be6f0-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="be6f0-146">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="be6f0-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="be6f0-147">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="be6f0-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="be6f0-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="be6f0-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="be6f0-151">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="be6f0-151">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="be6f0-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="be6f0-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="be6f0-153">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="be6f0-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="be6f0-154">För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="be6f0-154">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="be6f0-155">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="be6f0-155">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="be6f0-157">På **instrumentpanelssidan** väljer du **E-post**och sedan **Anpassad MX**.</span><span class="sxs-lookup"><span data-stu-id="be6f0-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Konfigurera-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="be6f0-159">Välj **Redigera** för den domän som du vill redigera i kolumnen **Åtgärder** i avsnittet **Hantera e-postleverans.**</span><span class="sxs-lookup"><span data-stu-id="be6f0-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Konfigurera-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="be6f0-161">I avsnittet **Anpassad MX-post** skriver eller kopierar eller klistrar du in följande värden från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="be6f0-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="be6f0-162">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="be6f0-163">(Om det finns några andra befintliga MX-poster markerar du de poster som ska tas bort.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="be6f0-164">**MX-post (obligatoriskt)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="be6f0-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="be6f0-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="be6f0-166">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="be6f0-p108">0 motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="be6f0-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="be6f0-169">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="be6f0-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="be6f0-170">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="be6f0-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-Konfigurera-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="be6f0-172">Välj **Ändra den här domänen om du vill använda anpassade MX-poster nu!**</span><span class="sxs-lookup"><span data-stu-id="be6f0-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Konfigurera-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="be6f0-174">Om det finns några andra befintliga MX-poster tar du bort varje post genom att markera posten och sedan trycka på **Delete-tangenten** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="be6f0-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Konfigurera-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="be6f0-176">Om du har tagit bort några poster väljer du **Uppdatera dina anpassade MX-poster nu!**</span><span class="sxs-lookup"><span data-stu-id="be6f0-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Konfigurera-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="be6f0-178">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="be6f0-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="be6f0-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="be6f0-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="be6f0-180">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="be6f0-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="be6f0-181">För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="be6f0-181">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="be6f0-182">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="be6f0-182">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="be6f0-184">På **instrumentpanelssidan** väljer du **Domäner**och hanterar sedan **domäner**.</span><span class="sxs-lookup"><span data-stu-id="be6f0-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="be6f0-186">Välj **DNS** för den domän som du vill redigera i avsnittet **Domän** på sidan **Hantera domäner.**</span><span class="sxs-lookup"><span data-stu-id="be6f0-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Konfigurera-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="be6f0-188">I avsnittet **Lägg till en anpassad DNS-post** skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="be6f0-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="be6f0-189">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="be6f0-190">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="be6f0-191">**Name**</span><span class="sxs-lookup"><span data-stu-id="be6f0-191">**Name**</span></span>|<span data-ttu-id="be6f0-192">**Typ**</span><span class="sxs-lookup"><span data-stu-id="be6f0-192">**Type**</span></span>|<span data-ttu-id="be6f0-193">**Värde**</span><span class="sxs-lookup"><span data-stu-id="be6f0-193">**Value**</span></span>|<span data-ttu-id="be6f0-194">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="be6f0-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="be6f0-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="be6f0-195">autodiscover</span></span>  <br/> |<span data-ttu-id="be6f0-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="be6f0-196">CNAME</span></span>  <br/> |<span data-ttu-id="be6f0-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="be6f0-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="be6f0-198">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be6f0-199">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="be6f0-200">sip</span><span class="sxs-lookup"><span data-stu-id="be6f0-200">sip</span></span>  <br/> |<span data-ttu-id="be6f0-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="be6f0-201">CNAME</span></span>  <br/> |<span data-ttu-id="be6f0-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be6f0-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="be6f0-203">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be6f0-204">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="be6f0-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="be6f0-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="be6f0-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="be6f0-206">CNAME</span></span>  <br/> |<span data-ttu-id="be6f0-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be6f0-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="be6f0-208">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be6f0-209">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="be6f0-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="be6f0-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="be6f0-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="be6f0-211">CNAME</span></span>  <br/> |<span data-ttu-id="be6f0-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="be6f0-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="be6f0-213">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be6f0-214">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="be6f0-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="be6f0-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="be6f0-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="be6f0-216">CNAME</span></span>  <br/> |<span data-ttu-id="be6f0-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="be6f0-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="be6f0-218">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be6f0-219">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Konfigurera-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="be6f0-221">Välj **Lägg till post nu!**</span><span class="sxs-lookup"><span data-stu-id="be6f0-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Konfigurera-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="be6f0-223">Lägg till var och en av de två andra CNAME-posterna med hjälp av föregående två steg och värdena från de andra fem raderna i tabellen.</span><span class="sxs-lookup"><span data-stu-id="be6f0-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="be6f0-224">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="be6f0-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="be6f0-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="be6f0-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="be6f0-226">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="be6f0-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="be6f0-227">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="be6f0-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="be6f0-228">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="be6f0-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="be6f0-229">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="be6f0-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="be6f0-230">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="be6f0-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="be6f0-231">För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="be6f0-231">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="be6f0-232">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="be6f0-232">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="be6f0-234">På **instrumentpanelssidan** väljer du **Domäner**och hanterar sedan **domäner**.</span><span class="sxs-lookup"><span data-stu-id="be6f0-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="be6f0-236">Välj **DNS** för den domän som du vill redigera i avsnittet **Domän** på sidan **Hantera domäner.**</span><span class="sxs-lookup"><span data-stu-id="be6f0-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Konfigurera-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="be6f0-238">I avsnittet **Lägg till en anpassad DNS-post** skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="be6f0-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="be6f0-239">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="be6f0-240">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="be6f0-241">**Name**</span><span class="sxs-lookup"><span data-stu-id="be6f0-241">**Name**</span></span>|<span data-ttu-id="be6f0-242">**Typ**</span><span class="sxs-lookup"><span data-stu-id="be6f0-242">**Type**</span></span>|<span data-ttu-id="be6f0-243">**Värde**</span><span class="sxs-lookup"><span data-stu-id="be6f0-243">**Value**</span></span>|<span data-ttu-id="be6f0-244">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="be6f0-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="be6f0-245">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="be6f0-246">TXT</span><span class="sxs-lookup"><span data-stu-id="be6f0-246">TXT</span></span>  <br/> |<span data-ttu-id="be6f0-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="be6f0-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="be6f0-248">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="be6f0-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="be6f0-249">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Konfigurera-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="be6f0-251">Välj **Lägg till post nu!**</span><span class="sxs-lookup"><span data-stu-id="be6f0-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Konfigurera-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="be6f0-253">Lägg till den andra SRV-posten med föregående två steg och värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="be6f0-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="be6f0-254">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="be6f0-254">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="be6f0-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="be6f0-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="be6f0-256">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="be6f0-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="be6f0-257">För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="be6f0-257">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="be6f0-258">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="be6f0-258">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="be6f0-260">På **instrumentpanelssidan** väljer du **Domäner**och hanterar sedan **domäner**.</span><span class="sxs-lookup"><span data-stu-id="be6f0-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Konfigurera-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="be6f0-262">Välj **DNS** för den domän som du vill redigera i avsnittet **Domän** på sidan **Hantera domäner.**</span><span class="sxs-lookup"><span data-stu-id="be6f0-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Konfigurera-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="be6f0-264">I avsnittet **Lägg till en anpassad DNS-post** skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="be6f0-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="be6f0-265">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="be6f0-266">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="be6f0-267">**Name**</span><span class="sxs-lookup"><span data-stu-id="be6f0-267">**Name**</span></span>|<span data-ttu-id="be6f0-268">**Typ**</span><span class="sxs-lookup"><span data-stu-id="be6f0-268">**Type**</span></span>|<span data-ttu-id="be6f0-269">**Värde**</span><span class="sxs-lookup"><span data-stu-id="be6f0-269">**Value**</span></span>|<span data-ttu-id="be6f0-270">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="be6f0-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="be6f0-271">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="be6f0-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="be6f0-272">SRV</span><span class="sxs-lookup"><span data-stu-id="be6f0-272">SRV</span></span>  <br/> |<span data-ttu-id="be6f0-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="be6f0-273">100 1 443</span></span>  <br/> <span data-ttu-id="be6f0-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be6f0-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="be6f0-275">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be6f0-276">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="be6f0-277">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="be6f0-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="be6f0-278">SRV</span><span class="sxs-lookup"><span data-stu-id="be6f0-278">SRV</span></span>  <br/> |<span data-ttu-id="be6f0-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="be6f0-279">100 1 5061</span></span>  <br/> <span data-ttu-id="be6f0-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be6f0-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="be6f0-281">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="be6f0-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be6f0-282">(Det här fältet är valfritt.)</span><span class="sxs-lookup"><span data-stu-id="be6f0-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Konfigurera-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="be6f0-284">Välj **Lägg till post nu!**.</span><span class="sxs-lookup"><span data-stu-id="be6f0-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Konfigurera-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="be6f0-286">Lägg till den andra SRV-posten med föregående två steg och värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="be6f0-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="be6f0-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="be6f0-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
