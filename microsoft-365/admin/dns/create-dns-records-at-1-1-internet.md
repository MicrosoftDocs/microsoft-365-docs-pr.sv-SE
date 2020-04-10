---
title: Skapa DNS-poster med 1&1 IONOS för Office 365
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på 1&1 IONOS för Office 365.
ms.openlocfilehash: e31c9d9d08e29156ff6197c030de6b0f4169b5f4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211877"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="67f5b-103">Skapa DNS-poster med 1&1 IONOS för Office 365</span><span class="sxs-lookup"><span data-stu-id="67f5b-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="67f5b-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="67f5b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="67f5b-105">Observera att 1&1 IONOS inte tillåter att en domän har både en MX-post och en CNAME-post på den högsta nivån.</span><span class="sxs-lookup"><span data-stu-id="67f5b-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="67f5b-106">Det begränsar hur du kan konfigurera Exchange Online för Office 365.</span><span class="sxs-lookup"><span data-stu-id="67f5b-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="67f5b-107">Det finns en lösning, men vi rekommenderar att du använder den **endast** om du redan har erfarenhet av att skapa underdomäner vid 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="67f5b-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="67f5b-108">> Om du trots den här [tjänstbegränsningen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) väljer att hantera dina egna Office 365 DNS-poster med 1&1 IONOS följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="67f5b-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="67f5b-109">När du har lagt till dessa poster på 1&1 IONOS konfigureras domänen så att den fungerar med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="67f5b-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="67f5b-110">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="67f5b-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="67f5b-p102">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="67f5b-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="67f5b-114">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="67f5b-114">Add a TXT record for verification</span></span>

<span data-ttu-id="67f5b-p103">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="67f5b-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="67f5b-119">Följ stegen nedan eller [titta på videon (börja vid 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="67f5b-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="67f5b-120">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="67f5b-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="67f5b-121">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="67f5b-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="67f5b-122">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="67f5b-123">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="67f5b-124">Välj **Redigera DNS-inställningar**i området **Domäninställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="67f5b-125">I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="67f5b-126">Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="67f5b-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="67f5b-127">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="67f5b-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="67f5b-128">**Type**</span></span> <br/> |<span data-ttu-id="67f5b-129">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="67f5b-129">**Prefix**</span></span> <br/> |<span data-ttu-id="67f5b-130">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="67f5b-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="67f5b-131">TXT</span><span class="sxs-lookup"><span data-stu-id="67f5b-131">TXT</span></span>  <br/> |<span data-ttu-id="67f5b-132">(Lämna det här fältet tomt)</span><span class="sxs-lookup"><span data-stu-id="67f5b-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="67f5b-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="67f5b-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="67f5b-134">Obs: Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="67f5b-134">NOTE: This is an example.</span></span> <span data-ttu-id="67f5b-135">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="67f5b-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="67f5b-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="67f5b-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="67f5b-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="67f5b-138">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="67f5b-139">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="67f5b-140">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="67f5b-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="67f5b-141">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="67f5b-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="67f5b-142">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="67f5b-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="67f5b-143">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="67f5b-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="67f5b-144">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="67f5b-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="67f5b-145">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="67f5b-146">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="67f5b-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="67f5b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="67f5b-150">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="67f5b-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="67f5b-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="67f5b-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="67f5b-152">Följ stegen nedan eller [titta på videon (börja vid 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="67f5b-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="67f5b-153">Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="67f5b-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="67f5b-154">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="67f5b-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="67f5b-155">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="67f5b-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="67f5b-156">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="67f5b-157">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="67f5b-158">Välj **Redigera DNS-inställningar**i området **Domäninställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="67f5b-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="67f5b-160">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="67f5b-161">![1&amp;1-BP-Konfigurera-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="67f5b-162">Om det förekommer några MX-poster sen tidigare tar du bort var och en genom att markera posten och sedan trycka på **Del**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="67f5b-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="67f5b-163">(Om det inte finns några MX-poster sen tidigare fortsätter du till nästa steg.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="67f5b-164">![1&amp;1-BP-Konfigurera-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="67f5b-165">I rutorna för **MX 1**-posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="67f5b-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="67f5b-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="67f5b-166">**MX 1**</span></span>|<span data-ttu-id="67f5b-167">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="67f5b-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="67f5b-168">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="67f5b-169">Skaffa domännyckeln \<\> från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="67f5b-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="67f5b-170">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="67f5b-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="67f5b-171">10</span><span class="sxs-lookup"><span data-stu-id="67f5b-171">10</span></span>  <br/> <span data-ttu-id="67f5b-172">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="67f5b-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 och 1 - konfigurera 2 och 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="67f5b-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-174">Select **Save**.</span></span><br/><span data-ttu-id="67f5b-175">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="67f5b-176">![1&amp;1-BP-Konfigurera-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="67f5b-177">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="67f5b-178">![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="67f5b-179">Lägg till de sex CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="67f5b-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="67f5b-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="67f5b-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="67f5b-181">1&1 IONOS kräver en lösning så att du kan använda en MX-post tillsammans med CNAME-posterna som krävs för Office 365-e-posttjänster.</span><span class="sxs-lookup"><span data-stu-id="67f5b-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="67f5b-182">Den här lösningen kräver att du skapar en uppsättning underdomäner vid 1&1 IONOS och tilldela dem till CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="67f5b-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="67f5b-183">Kontrollera att du har minst två tillgängliga underdomäner innan du startar den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="67f5b-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="67f5b-184">Vi rekommenderar den här lösningen endast om du redan har erfarenhet av att skapa underdomäner vid 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="67f5b-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="67f5b-185">Grundläggande CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="67f5b-185">Basic CNAME records</span></span>

<span data-ttu-id="67f5b-186">Följ stegen nedan eller [titta på videon (börja vid 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="67f5b-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="67f5b-187">Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="67f5b-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="67f5b-188">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="67f5b-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="67f5b-189">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="67f5b-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="67f5b-190">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="67f5b-191">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan **Hantera underdomäner**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="67f5b-192">![1&amp;1-BP-Konfigurera-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="67f5b-193">Nu ska du skapa du två underdomäner och ange ett värde för **Alias** för var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="67f5b-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="67f5b-194">(Detta krävs eftersom 1&1 IONOS endast stöder en CNAME-post på högsta nivå, men Office 365 kräver flera CNAME-poster.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="67f5b-195">Först måste du skapa Autodiscover-underdomänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="67f5b-196">I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**</span><span class="sxs-lookup"><span data-stu-id="67f5b-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="67f5b-p113">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="67f5b-200">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="67f5b-200">**Create Subdomain**</span></span>|<span data-ttu-id="67f5b-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="67f5b-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="67f5b-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="67f5b-202">autodiscover</span></span>  <br/> |<span data-ttu-id="67f5b-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-Konfigurera-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="67f5b-205">Välj **Skapa underdomän**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="67f5b-206">![1&amp;1-BP-Konfigurera-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="67f5b-207">Leta reda på underdomänen **autodiscover** i **underdomänen i översikten** och välj sedan **panelkontrollen (v)** för underdomänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="67f5b-208">![1&amp;1-BP-Konfigurera-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="67f5b-209">I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="67f5b-210">![1&amp;1-BP-Konfigurera-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="67f5b-211">Välj **CNAME i området IP-adress (AAAA Records)** i området **IP-adress (A Record).** **CNAME**</span><span class="sxs-lookup"><span data-stu-id="67f5b-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="67f5b-212">![1&amp;1-BP-Konfigurera-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="67f5b-213">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="67f5b-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="67f5b-214">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="67f5b-214">**Create Subdomain**</span></span>|<span data-ttu-id="67f5b-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="67f5b-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="67f5b-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="67f5b-216">autodiscover</span></span>  <br/> |<span data-ttu-id="67f5b-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-Konfigurera-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="67f5b-219">Markera kryssrutan för ansvarsfriskrivningen **I am aware** (jag är medveten om).</span><span class="sxs-lookup"><span data-stu-id="67f5b-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="67f5b-220">![1&amp;1-BP-Konfigurera-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="67f5b-221">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-221">Select **Save**.</span></span><br/><span data-ttu-id="67f5b-222">![1&amp;1-BP-Konfigurera-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="67f5b-223">Ytterligare CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="67f5b-223">Additional CNAME records</span></span>

<span data-ttu-id="67f5b-p114">De ytterligare CNAME-poster som skapas i följande proceduren aktiverar Skype för företag - Online-tjänster. Du kan utföra samma steg som du använde för att skapa de två CNAME-poster som du redan har skapat.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="67f5b-226">Skapa den tredje underdomänen (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="67f5b-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="67f5b-227">I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**</span><span class="sxs-lookup"><span data-stu-id="67f5b-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="67f5b-p115">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="67f5b-230">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="67f5b-230">**Create Subdomain**</span></span>|<span data-ttu-id="67f5b-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="67f5b-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="67f5b-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="67f5b-232">lyncdiscover</span></span>   |<span data-ttu-id="67f5b-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="67f5b-234">Välj **Skapa underdomän**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="67f5b-235">På sidan **Domain Center** väljer du **Hantera underdomäner**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="67f5b-236">Leta reda på **lyncdiscover** underdomänunderdomänen som du just skapade i avsnittet **Underdomänöver** och välj sedan **panelkontrollen (v)** för underdomänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="67f5b-237">I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="67f5b-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="67f5b-239">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="67f5b-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="67f5b-240">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="67f5b-240">**Create Subdomain**</span></span>|<span data-ttu-id="67f5b-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="67f5b-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="67f5b-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="67f5b-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="67f5b-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="67f5b-244">Markera kryssrutan för **ansvarsfriskrivningen Jag är medveten** om och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="67f5b-245">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="67f5b-246">Skapa den fjärde underdomänen (SIP):</span><span class="sxs-lookup"><span data-stu-id="67f5b-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="67f5b-247">I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**</span><span class="sxs-lookup"><span data-stu-id="67f5b-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="67f5b-p116">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="67f5b-250">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="67f5b-250">**Create Subdomain**</span></span>|<span data-ttu-id="67f5b-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="67f5b-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="67f5b-252">sip</span><span class="sxs-lookup"><span data-stu-id="67f5b-252">sip</span></span>  <br/> |<span data-ttu-id="67f5b-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="67f5b-254">Välj **Skapa underdomän**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="67f5b-255">På sidan **Domain Center** väljer du **Hantera underdomäner**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="67f5b-256">Leta reda på den **sip-underdomän** som du just skapade i avsnittet **Underdomänöversikt** och välj sedan **panelkontrollen (v)** för underdomänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="67f5b-257">I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="67f5b-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="67f5b-259">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="67f5b-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="67f5b-260">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="67f5b-260">**Create Subdomain**</span></span>|<span data-ttu-id="67f5b-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="67f5b-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="67f5b-262">sip</span><span class="sxs-lookup"><span data-stu-id="67f5b-262">sip</span></span>  <br/> |<span data-ttu-id="67f5b-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="67f5b-264">Markera kryssrutan för **ansvarsfriskrivningen Jag är medveten** om och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="67f5b-265">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="67f5b-266">CNAME-poster som krävs för MDM</span><span class="sxs-lookup"><span data-stu-id="67f5b-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67f5b-267">Följ proceduren som används för de andra fyra CNAME-posterna, men använd värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="67f5b-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="67f5b-268">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="67f5b-268">**Create Subdomain**</span></span>|<span data-ttu-id="67f5b-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="67f5b-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67f5b-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="67f5b-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="67f5b-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="67f5b-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="67f5b-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="67f5b-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="67f5b-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="67f5b-274">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="67f5b-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67f5b-275">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="67f5b-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="67f5b-276">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="67f5b-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="67f5b-277">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="67f5b-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="67f5b-278">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="67f5b-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="67f5b-279">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="67f5b-279">Need examples?</span></span> <span data-ttu-id="67f5b-280">Ta en titt på dessa [externa DNS-poster för Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="67f5b-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="67f5b-281">Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="67f5b-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="67f5b-282">Följ stegen nedan eller [titta på videon (börja vid 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="67f5b-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="67f5b-283">Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="67f5b-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="67f5b-284">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="67f5b-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="67f5b-285">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="67f5b-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="67f5b-286">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="67f5b-287">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="67f5b-288">Välj **Redigera DNS-inställningar**i området **Domäninställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="67f5b-289">I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="67f5b-290">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="67f5b-291">Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="67f5b-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="67f5b-292">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="67f5b-293">**Typ**</span><span class="sxs-lookup"><span data-stu-id="67f5b-293">**Type**</span></span>|<span data-ttu-id="67f5b-294">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="67f5b-294">**Prefix**</span></span>|<span data-ttu-id="67f5b-295">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="67f5b-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="67f5b-296">TXT</span><span class="sxs-lookup"><span data-stu-id="67f5b-296">TXT</span></span>  <br/> |<span data-ttu-id="67f5b-297">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="67f5b-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="67f5b-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="67f5b-299">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="67f5b-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT-post](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="67f5b-301">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-301">Select **Save**.</span></span><br/><span data-ttu-id="67f5b-302">![Lägg till post](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="67f5b-303">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-303">Select **Save**.</span></span><br/><span data-ttu-id="67f5b-304">![Spara post](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="67f5b-305">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="67f5b-306">![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="67f5b-307">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="67f5b-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="67f5b-308">Följ stegen nedan eller [titta på videon (börja vid 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="67f5b-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="67f5b-309">Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="67f5b-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="67f5b-310">För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="67f5b-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="67f5b-311">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="67f5b-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="67f5b-312">Välj **Hantera domäner**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="67f5b-313">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="67f5b-314">Välj **Redigera DNS-inställningar**i området **Domäninställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="67f5b-315">I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="67f5b-316">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="67f5b-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="67f5b-317">I den nya postens rutor i området **Add Record** (lägg till post) skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="67f5b-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="67f5b-318">(Välj **typ-** och **TTL-värden** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="67f5b-319">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="67f5b-319">**Type**</span></span>|<span data-ttu-id="67f5b-320">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="67f5b-320">**Service**</span></span>|<span data-ttu-id="67f5b-321">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="67f5b-321">**Protocol**</span></span>|<span data-ttu-id="67f5b-322">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="67f5b-322">**Name**</span></span>|<span data-ttu-id="67f5b-323">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="67f5b-323">**Host**</span></span>|<span data-ttu-id="67f5b-324">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="67f5b-324">**Priority**</span></span>|<span data-ttu-id="67f5b-325">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="67f5b-325">**Weight**</span></span>|<span data-ttu-id="67f5b-326">**Port**</span><span class="sxs-lookup"><span data-stu-id="67f5b-326">**Port**</span></span>|<span data-ttu-id="67f5b-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67f5b-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="67f5b-328">SRV</span><span class="sxs-lookup"><span data-stu-id="67f5b-328">SRV</span></span>  <br/> |<span data-ttu-id="67f5b-329">sip</span><span class="sxs-lookup"><span data-stu-id="67f5b-329">sip</span></span>  <br/> |<span data-ttu-id="67f5b-330">tls</span><span class="sxs-lookup"><span data-stu-id="67f5b-330">tls</span></span>  <br/> |<span data-ttu-id="67f5b-331">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="67f5b-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="67f5b-333">100</span><span class="sxs-lookup"><span data-stu-id="67f5b-333">100</span></span>  <br/> |<span data-ttu-id="67f5b-334">1</span><span class="sxs-lookup"><span data-stu-id="67f5b-334">1</span></span>  <br/> |<span data-ttu-id="67f5b-335">443</span><span class="sxs-lookup"><span data-stu-id="67f5b-335">443</span></span>  <br/> |<span data-ttu-id="67f5b-336">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="67f5b-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="67f5b-337">SRV</span><span class="sxs-lookup"><span data-stu-id="67f5b-337">SRV</span></span>  <br/> |<span data-ttu-id="67f5b-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="67f5b-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="67f5b-339">tcp</span><span class="sxs-lookup"><span data-stu-id="67f5b-339">tcp</span></span>  <br/> |<span data-ttu-id="67f5b-340">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="67f5b-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="67f5b-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67f5b-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="67f5b-342">100</span><span class="sxs-lookup"><span data-stu-id="67f5b-342">100</span></span>  <br/> |<span data-ttu-id="67f5b-343">1</span><span class="sxs-lookup"><span data-stu-id="67f5b-343">1</span></span>  <br/> |<span data-ttu-id="67f5b-344">5061</span><span class="sxs-lookup"><span data-stu-id="67f5b-344">5061</span></span>  <br/> |<span data-ttu-id="67f5b-345">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="67f5b-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-Konfigurera-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="67f5b-347">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-347">Select **Save**.</span></span> <br/><span data-ttu-id="67f5b-348">![1&amp;1-BP-Konfigurera-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="67f5b-349">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-349">Select **Save**.</span></span> <br/><span data-ttu-id="67f5b-350">![1&amp;1-BP-Konfigurera-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="67f5b-351">Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .</span><span class="sxs-lookup"><span data-stu-id="67f5b-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="67f5b-352">![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="67f5b-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="67f5b-353">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="67f5b-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="67f5b-354">I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="67f5b-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="67f5b-355">Skapa en post med värdena från den andra raden i tabellen i området **Lägg till post** och välj sedan Lägg **till**, **Spara**och **Ja** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="67f5b-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="67f5b-p120">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="67f5b-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
