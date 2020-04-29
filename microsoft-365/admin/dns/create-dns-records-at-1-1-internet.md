---
title: Skapa DNS-poster med 1&1 IONOS för Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på 1&1 IONOS för Microsoft.
ms.openlocfilehash: a80f06287b7e4efe03804248d52b4ef43fc67b26
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919655"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="e9253-103">Skapa DNS-poster med 1&1 IONOS för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9253-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="e9253-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="e9253-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e9253-105">Observera att 1&1 IONOS inte tillåter att en domän har både en MX-post och en CNAME-post på den högsta nivån.</span><span class="sxs-lookup"><span data-stu-id="e9253-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="e9253-106">Detta begränsar hur du kan konfigurera Exchange Online för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9253-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="e9253-107">Det finns en lösning, men vi rekommenderar att du använder den **endast** om du redan har erfarenhet av att skapa underdomäner vid 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="e9253-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="e9253-108">> Om du trots den här [tjänstbegränsningen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) väljer att hantera dina egna Microsoft DNS-poster med 1&1 IONOS följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e9253-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="e9253-109">När du har lagt till dessa poster vid 1&1 IONOS konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="e9253-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="e9253-110">Mer information om webbvärdverktyg och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="e9253-110">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9253-p102">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9253-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e9253-114">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="e9253-114">Add a TXT record for verification</span></span>

<span data-ttu-id="e9253-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9253-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="e9253-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="e9253-119">Följ stegen nedan eller [titta på videon (börja vid 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9253-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="e9253-120">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9253-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9253-121">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="e9253-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9253-122">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="e9253-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9253-123">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e9253-124">Välj **Redigera DNS-inställningar**i området **Domäninställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e9253-125">I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="e9253-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="e9253-126">Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e9253-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e9253-127">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e9253-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="e9253-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e9253-128">**Type**</span></span> <br/> |<span data-ttu-id="e9253-129">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="e9253-129">**Prefix**</span></span> <br/> |<span data-ttu-id="e9253-130">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="e9253-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="e9253-131">TXT</span><span class="sxs-lookup"><span data-stu-id="e9253-131">TXT</span></span>  <br/> |<span data-ttu-id="e9253-132">(Lämna det här fältet tomt)</span><span class="sxs-lookup"><span data-stu-id="e9253-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="e9253-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e9253-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e9253-134">Obs: Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="e9253-134">NOTE: This is an example.</span></span> <span data-ttu-id="e9253-135">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="e9253-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e9253-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e9253-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="e9253-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="e9253-138">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="e9253-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="e9253-139">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="e9253-140">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="e9253-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e9253-141">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="e9253-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="e9253-142">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="e9253-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e9253-143">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="e9253-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e9253-144">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="e9253-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e9253-145">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="e9253-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e9253-146">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="e9253-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e9253-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9253-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e9253-150">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9253-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e9253-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e9253-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e9253-152">Följ stegen nedan eller [titta på videon (börja vid 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9253-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9253-153">Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="e9253-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e9253-154">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9253-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9253-155">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="e9253-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9253-156">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="e9253-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9253-157">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e9253-158">Välj **Redigera DNS-inställningar**i området **Domäninställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e9253-159">Välj **Annan e-postserver**i området **MX Record (MX Record)** i avsnittet **MX** Records .</span><span class="sxs-lookup"><span data-stu-id="e9253-159">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="e9253-160">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e9253-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="e9253-161">![1&amp;1-BP-Konfigurera-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="e9253-162">Om det förekommer några MX-poster sen tidigare tar du bort var och en genom att markera posten och sedan trycka på **Del**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="e9253-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="e9253-163">(Om det inte finns några MX-poster sen tidigare fortsätter du till nästa steg.)</span><span class="sxs-lookup"><span data-stu-id="e9253-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="e9253-164">![1&amp;1-BP-Konfigurera-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="e9253-165">I rutorna för **MX 1**-posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e9253-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="e9253-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="e9253-166">**MX 1**</span></span>|<span data-ttu-id="e9253-167">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="e9253-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="e9253-168">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e9253-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="e9253-169">Skaffa domännyckeln \<\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="e9253-169">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="e9253-170">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="e9253-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e9253-171">10</span><span class="sxs-lookup"><span data-stu-id="e9253-171">10</span></span>  <br/> <span data-ttu-id="e9253-172">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9253-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 och 1 - konfigurera 2 och 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="e9253-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-174">Select **Save**.</span></span><br/><span data-ttu-id="e9253-175">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e9253-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="e9253-176">![1&amp;1-BP-Konfigurera-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="e9253-177">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="e9253-178">![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e9253-179">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9253-179">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e9253-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e9253-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e9253-181">1&1 IONOS kräver en lösning så att du kan använda en MX-post tillsammans med CNAME-posterna som krävs för Microsofts e-posttjänster.</span><span class="sxs-lookup"><span data-stu-id="e9253-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="e9253-182">Den här lösningen kräver att du skapar en uppsättning underdomäner vid 1&1 IONOS och tilldela dem till CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="e9253-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e9253-183">Kontrollera att du har minst två tillgängliga underdomäner innan du startar den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="e9253-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="e9253-184">Vi rekommenderar den här lösningen endast om du redan har erfarenhet av att skapa underdomäner vid 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="e9253-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="e9253-185">Grundläggande CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="e9253-185">Basic CNAME records</span></span>

<span data-ttu-id="e9253-186">Följ stegen nedan eller [titta på videon (börja vid 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9253-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9253-187">Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="e9253-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e9253-188">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9253-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9253-189">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="e9253-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9253-190">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="e9253-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9253-191">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan **Hantera underdomäner**.</span><span class="sxs-lookup"><span data-stu-id="e9253-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="e9253-192">![1&amp;1-BP-Konfigurera-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="e9253-193">Nu ska du skapa du två underdomäner och ange ett värde för **Alias** för var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="e9253-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="e9253-194">(Detta krävs eftersom 1&1 IONOS stöder endast en CNAME-post på den högsta nivån, men Microsoft kräver flera CNAME-poster.)</span><span class="sxs-lookup"><span data-stu-id="e9253-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="e9253-195">Först måste du skapa Autodiscover-underdomänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="e9253-196">I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**</span><span class="sxs-lookup"><span data-stu-id="e9253-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="e9253-p113">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="e9253-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="e9253-200">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="e9253-200">**Create Subdomain**</span></span>|<span data-ttu-id="e9253-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9253-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9253-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e9253-202">autodiscover</span></span>  <br/> |<span data-ttu-id="e9253-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e9253-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-Konfigurera-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="e9253-205">Välj **Skapa underdomän**.</span><span class="sxs-lookup"><span data-stu-id="e9253-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="e9253-206">![1&amp;1-BP-Konfigurera-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="e9253-207">Leta reda på underdomänen **autodiscover** i **underdomänen i översikten** och välj sedan **panelkontrollen (v)** för underdomänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e9253-208">![1&amp;1-BP-Konfigurera-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="e9253-209">I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e9253-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="e9253-210">![1&amp;1-BP-Konfigurera-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="e9253-211">Välj **CNAME i området IP-adress (AAAA Records)** i området **IP-adress (A Record).** **CNAME**</span><span class="sxs-lookup"><span data-stu-id="e9253-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="e9253-212">![1&amp;1-BP-Konfigurera-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="e9253-213">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="e9253-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="e9253-214">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="e9253-214">**Create Subdomain**</span></span>|<span data-ttu-id="e9253-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9253-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9253-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e9253-216">autodiscover</span></span>  <br/> |<span data-ttu-id="e9253-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e9253-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-Konfigurera-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="e9253-219">Markera kryssrutan för ansvarsfriskrivningen **I am aware** (jag är medveten om).</span><span class="sxs-lookup"><span data-stu-id="e9253-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="e9253-220">![1&amp;1-BP-Konfigurera-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="e9253-221">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-221">Select **Save**.</span></span><br/><span data-ttu-id="e9253-222">![1&amp;1-BP-Konfigurera-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="e9253-223">Ytterligare CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="e9253-223">Additional CNAME records</span></span>

<span data-ttu-id="e9253-p114">De ytterligare CNAME-poster som skapas i följande proceduren aktiverar Skype för företag - Online-tjänster. Du kan utföra samma steg som du använde för att skapa de två CNAME-poster som du redan har skapat.</span><span class="sxs-lookup"><span data-stu-id="e9253-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="e9253-226">Skapa den tredje underdomänen (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="e9253-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="e9253-227">I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**</span><span class="sxs-lookup"><span data-stu-id="e9253-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="e9253-p115">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="e9253-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="e9253-230">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="e9253-230">**Create Subdomain**</span></span>|<span data-ttu-id="e9253-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9253-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9253-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e9253-232">lyncdiscover</span></span>   |<span data-ttu-id="e9253-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9253-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="e9253-234">Välj **Skapa underdomän**.</span><span class="sxs-lookup"><span data-stu-id="e9253-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="e9253-235">På sidan **Domain Center** väljer du **Hantera underdomäner**.</span><span class="sxs-lookup"><span data-stu-id="e9253-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="e9253-236">Leta reda på **lyncdiscover** underdomänunderdomänen som du just skapade i avsnittet **Underdomänöver** och välj sedan **panelkontrollen (v)** för underdomänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e9253-237">I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e9253-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="e9253-238">Välj **CNAME i området IP-adress (AAAA Records)** i området **IP-adress (A Record).** **CNAME**</span><span class="sxs-lookup"><span data-stu-id="e9253-238">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="e9253-239">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="e9253-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="e9253-240">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="e9253-240">**Create Subdomain**</span></span>|<span data-ttu-id="e9253-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9253-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9253-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e9253-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e9253-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9253-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="e9253-244">Markera kryssrutan för **ansvarsfriskrivningen Jag är medveten** om och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="e9253-245">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="e9253-246">Skapa den fjärde underdomänen (SIP):</span><span class="sxs-lookup"><span data-stu-id="e9253-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="e9253-247">I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**</span><span class="sxs-lookup"><span data-stu-id="e9253-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="e9253-p116">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="e9253-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="e9253-250">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="e9253-250">**Create Subdomain**</span></span>|<span data-ttu-id="e9253-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9253-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9253-252">sip</span><span class="sxs-lookup"><span data-stu-id="e9253-252">sip</span></span>  <br/> |<span data-ttu-id="e9253-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9253-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="e9253-254">Välj **Skapa underdomän**.</span><span class="sxs-lookup"><span data-stu-id="e9253-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="e9253-255">På sidan **Domain Center** väljer du **Hantera underdomäner**.</span><span class="sxs-lookup"><span data-stu-id="e9253-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="e9253-256">Leta reda på den **sip-underdomän** som du just skapade i avsnittet **Underdomänöversikt** och välj sedan **panelkontrollen (v)** för underdomänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e9253-257">I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e9253-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="e9253-258">Välj **CNAME i området IP-adress (AAAA Records)** i området **IP-adress (A Record).** **CNAME**</span><span class="sxs-lookup"><span data-stu-id="e9253-258">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="e9253-259">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="e9253-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="e9253-260">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="e9253-260">**Create Subdomain**</span></span>|<span data-ttu-id="e9253-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9253-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9253-262">sip</span><span class="sxs-lookup"><span data-stu-id="e9253-262">sip</span></span>  <br/> |<span data-ttu-id="e9253-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9253-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="e9253-264">Markera kryssrutan för **ansvarsfriskrivningen Jag är medveten** om och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="e9253-265">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="e9253-266">CNAME-poster som krävs för MDM</span><span class="sxs-lookup"><span data-stu-id="e9253-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9253-267">Följ proceduren som används för de andra fyra CNAME-posterna, men använd värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e9253-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="e9253-268">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="e9253-268">**Create Subdomain**</span></span>|<span data-ttu-id="e9253-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9253-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9253-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e9253-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e9253-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e9253-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="e9253-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e9253-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e9253-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e9253-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e9253-274">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="e9253-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9253-275">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="e9253-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e9253-276">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="e9253-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e9253-277">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9253-277">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e9253-278">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="e9253-278">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e9253-279">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="e9253-279">Need examples?</span></span> <span data-ttu-id="e9253-280">Ta en titt på dessa [externa DNS-poster för Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="e9253-280">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="e9253-281">Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e9253-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="e9253-282">Följ stegen nedan eller [titta på videon (börja vid 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9253-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9253-283">Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="e9253-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e9253-284">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9253-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9253-285">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="e9253-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9253-286">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="e9253-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9253-287">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e9253-288">Välj **Redigera DNS-inställningar**i området **Domäninställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e9253-289">I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="e9253-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="e9253-290">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e9253-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="e9253-291">Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e9253-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="e9253-292">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e9253-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="e9253-293">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e9253-293">**Type**</span></span>|<span data-ttu-id="e9253-294">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="e9253-294">**Prefix**</span></span>|<span data-ttu-id="e9253-295">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="e9253-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e9253-296">TXT</span><span class="sxs-lookup"><span data-stu-id="e9253-296">TXT</span></span>  <br/> |<span data-ttu-id="e9253-297">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="e9253-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e9253-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e9253-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e9253-299">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="e9253-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT-post](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="e9253-301">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-301">Select **Save**.</span></span><br/><span data-ttu-id="e9253-302">![Lägg till post](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="e9253-303">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-303">Select **Save**.</span></span><br/><span data-ttu-id="e9253-304">![Spara post](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="e9253-305">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="e9253-306">![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e9253-307">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9253-307">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="e9253-308">Följ stegen nedan eller [titta på videon (börja vid 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9253-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9253-309">Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="e9253-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e9253-310">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9253-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9253-311">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="e9253-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9253-312">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="e9253-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9253-313">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.</span><span class="sxs-lookup"><span data-stu-id="e9253-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e9253-314">Välj **Redigera DNS-inställningar**i området **Domäninställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e9253-315">I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="e9253-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="e9253-316">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="e9253-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="e9253-317">I den nya postens rutor i området **Add Record** (lägg till post) skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="e9253-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="e9253-318">(Välj **typ-** och **TTL-värden** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e9253-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9253-319">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e9253-319">**Type**</span></span>|<span data-ttu-id="e9253-320">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="e9253-320">**Service**</span></span>|<span data-ttu-id="e9253-321">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="e9253-321">**Protocol**</span></span>|<span data-ttu-id="e9253-322">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="e9253-322">**Name**</span></span>|<span data-ttu-id="e9253-323">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="e9253-323">**Host**</span></span>|<span data-ttu-id="e9253-324">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="e9253-324">**Priority**</span></span>|<span data-ttu-id="e9253-325">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="e9253-325">**Weight**</span></span>|<span data-ttu-id="e9253-326">**Port**</span><span class="sxs-lookup"><span data-stu-id="e9253-326">**Port**</span></span>|<span data-ttu-id="e9253-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e9253-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9253-328">SRV</span><span class="sxs-lookup"><span data-stu-id="e9253-328">SRV</span></span>  <br/> |<span data-ttu-id="e9253-329">sip</span><span class="sxs-lookup"><span data-stu-id="e9253-329">sip</span></span>  <br/> |<span data-ttu-id="e9253-330">tls</span><span class="sxs-lookup"><span data-stu-id="e9253-330">tls</span></span>  <br/> |<span data-ttu-id="e9253-331">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="e9253-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e9253-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9253-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e9253-333">100</span><span class="sxs-lookup"><span data-stu-id="e9253-333">100</span></span>  <br/> |<span data-ttu-id="e9253-334">1</span><span class="sxs-lookup"><span data-stu-id="e9253-334">1</span></span>  <br/> |<span data-ttu-id="e9253-335">443</span><span class="sxs-lookup"><span data-stu-id="e9253-335">443</span></span>  <br/> |<span data-ttu-id="e9253-336">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="e9253-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="e9253-337">SRV</span><span class="sxs-lookup"><span data-stu-id="e9253-337">SRV</span></span>  <br/> |<span data-ttu-id="e9253-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e9253-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="e9253-339">tcp</span><span class="sxs-lookup"><span data-stu-id="e9253-339">tcp</span></span>  <br/> |<span data-ttu-id="e9253-340">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="e9253-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e9253-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9253-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="e9253-342">100</span><span class="sxs-lookup"><span data-stu-id="e9253-342">100</span></span>  <br/> |<span data-ttu-id="e9253-343">1</span><span class="sxs-lookup"><span data-stu-id="e9253-343">1</span></span>  <br/> |<span data-ttu-id="e9253-344">5061</span><span class="sxs-lookup"><span data-stu-id="e9253-344">5061</span></span>  <br/> |<span data-ttu-id="e9253-345">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="e9253-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-Konfigurera-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="e9253-347">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-347">Select **Save**.</span></span> <br/><span data-ttu-id="e9253-348">![1&amp;1-BP-Konfigurera-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="e9253-349">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9253-349">Select **Save**.</span></span> <br/><span data-ttu-id="e9253-350">![1&amp;1-BP-Konfigurera-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="e9253-351">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="e9253-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="e9253-352">![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e9253-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="e9253-353">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="e9253-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="e9253-354">I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="e9253-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="e9253-355">Skapa en post med värdena från den andra raden i tabellen i området **Lägg till post** och välj sedan Lägg **till**, **Spara**och **Ja** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="e9253-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e9253-p120">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9253-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
