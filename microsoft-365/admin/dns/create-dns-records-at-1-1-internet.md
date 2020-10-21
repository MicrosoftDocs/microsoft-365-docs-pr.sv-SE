---
title: Skapa DNS-poster på 1&1 IONOS för Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på 1&1 IONOS för Microsoft.
ms.openlocfilehash: b88fa4f14104f60f22857bb9cfdc9e6366d2c303
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646397"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="01902-103">Skapa DNS-poster på 1&1 IONOS för Microsoft</span><span class="sxs-lookup"><span data-stu-id="01902-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="01902-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="01902-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="01902-105">Observera att 1&1 IONOS inte tillåter en domän att ha både en MX-post och en automatisk identifiering av CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="01902-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="01902-106">Detta begränsar hur du kan konfigurera Exchange Online för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01902-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="01902-107">Det finns en lösning, men vi rekommenderar att du **bara** använder den om du redan har erfarenhet av att skapa under domäner vid 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="01902-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="01902-108">> om trots den här [tjänst begränsningen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) du väljer att hantera dina egna Microsoft DNS-poster vid 1&1 IONOS, följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="01902-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="01902-109">När du har lagt till dessa poster på 1&1 IONOS är domänen konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="01902-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="01902-p102">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="01902-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="01902-113">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="01902-113">Add a TXT record for verification</span></span>

<span data-ttu-id="01902-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="01902-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01902-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="01902-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="01902-118">Följ stegen nedan eller [titta på videon (börja vid 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="01902-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="01902-119">Kom igång genom att gå till sidan Domains på 1&1 IONOS med hjälp av [den här länken](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="01902-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="01902-120">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="01902-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="01902-121">Välj **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="01902-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="01902-122">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan **panel** kontrollen ( **v**) för den domänen.</span><span class="sxs-lookup"><span data-stu-id="01902-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="01902-123">Välj **Edit DNS Settings**i området **Domain Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="01902-124">Välj **Add Record**i avsnittet **txt and SRV Records** .</span><span class="sxs-lookup"><span data-stu-id="01902-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="01902-125">Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="01902-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01902-126">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="01902-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="01902-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="01902-127">**Type**</span></span> <br/> |<span data-ttu-id="01902-128">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="01902-128">**Prefix**</span></span> <br/> |<span data-ttu-id="01902-129">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="01902-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="01902-130">TXT</span><span class="sxs-lookup"><span data-stu-id="01902-130">TXT</span></span>  <br/> |<span data-ttu-id="01902-131">(Lämna det här fältet tomt)</span><span class="sxs-lookup"><span data-stu-id="01902-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="01902-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="01902-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="01902-133">Obs! det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="01902-133">NOTE: This is an example.</span></span> <span data-ttu-id="01902-134">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="01902-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="01902-135">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="01902-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="01902-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="01902-137">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="01902-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="01902-138">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="01902-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="01902-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="01902-140">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="01902-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="01902-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="01902-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="01902-142">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="01902-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="01902-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="01902-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="01902-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="01902-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="01902-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="01902-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="01902-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="01902-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="01902-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01902-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="01902-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="01902-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="01902-151">Följ stegen nedan eller [titta på videon (börja vid 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="01902-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="01902-152">Om du har registrerat dig hos 1und1.de [loggar](https://go.microsoft.com/fwlink/?linkid=859152)du in här.</span><span class="sxs-lookup"><span data-stu-id="01902-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="01902-153">Kom igång genom att gå till sidan Domains på 1&1 IONOS med hjälp av [den här länken](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="01902-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="01902-154">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="01902-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="01902-155">Välj **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="01902-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="01902-156">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan **panel** kontrollen ( **v**) för den domänen.</span><span class="sxs-lookup"><span data-stu-id="01902-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="01902-157">Välj **Edit DNS Settings**i området **Domain Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="01902-158">I avsnittet **MX Records** i området **Mail Exchanger (MX Record)** väljer du **other Mail Server**.</span><span class="sxs-lookup"><span data-stu-id="01902-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="01902-159">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="01902-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="01902-160">![1 &amp; -BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="01902-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="01902-161">Om det förekommer några MX-poster sen tidigare tar du bort var och en genom att markera posten och sedan trycka på **Del**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="01902-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="01902-162">(Om det inte finns några MX-poster sen tidigare fortsätter du till nästa steg.)</span><span class="sxs-lookup"><span data-stu-id="01902-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="01902-163">![1 &amp; -BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="01902-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="01902-164">I rutorna för **MX 1**-posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="01902-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="01902-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="01902-165">**MX 1**</span></span>|<span data-ttu-id="01902-166">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="01902-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="01902-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="01902-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="01902-168">Obs! hämta din \<domain-key\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="01902-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="01902-169">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="01902-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="01902-170">10.3</span><span class="sxs-lookup"><span data-stu-id="01902-170">10</span></span>  <br/> <span data-ttu-id="01902-171">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="01902-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1 och 1 – Konfigurera 2 och 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="01902-173">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-173">Select **Save**.</span></span><br/><span data-ttu-id="01902-174">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="01902-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="01902-175">![1 &amp; -BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="01902-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="01902-176">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="01902-177">![Välja Ja i dialog rutan Edit DNS Settings](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="01902-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="01902-178">Lägga till de sex CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="01902-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="01902-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="01902-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="01902-180">1&1 IONOS kräver en lösning så att du kan använda en MX-post tillsammans med de CNAME-poster som krävs för Microsoft e-posttjänster.</span><span class="sxs-lookup"><span data-stu-id="01902-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="01902-181">Denna lösning kräver att du skapar en uppsättning under domäner vid 1&1 IONOS och tilldelar dem till CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="01902-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="01902-182">Kontrollera att du har minst två tillgängliga underdomäner innan du startar den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="01902-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="01902-183">Vi rekommenderar den här lösningen bara om du redan har erfarenhet av att skapa under domäner vid 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="01902-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="01902-184">Grundläggande CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="01902-184">Basic CNAME records</span></span>

<span data-ttu-id="01902-185">Följ stegen nedan eller [titta på videon (börja vid 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="01902-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="01902-186">Om du har registrerat dig hos 1und1.de [loggar](https://go.microsoft.com/fwlink/?linkid=859152)du in här.</span><span class="sxs-lookup"><span data-stu-id="01902-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="01902-187">Kom igång genom att gå till sidan Domains på 1&1 IONOS med hjälp av [den här länken](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="01902-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="01902-188">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="01902-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="01902-189">Välj **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="01902-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="01902-190">Leta reda på den domän som du vill uppdatera på sidan **domän Center** och välj sedan hantera under **domäner**.</span><span class="sxs-lookup"><span data-stu-id="01902-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="01902-191">![1 &amp; -BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="01902-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="01902-192">Nu ska du skapa du två underdomäner och ange ett värde för **Alias** för var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="01902-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="01902-193">(Det här krävs eftersom 1&1 IONOS endast stöder en CNAME-post på toppnivå, men Microsoft kräver flera CNAME-poster.)</span><span class="sxs-lookup"><span data-stu-id="01902-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="01902-194">Först måste du skapa Autodiscover-underdomänen.</span><span class="sxs-lookup"><span data-stu-id="01902-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="01902-195">I avsnittet under **domän översikt** väljer du **skapa under domän**.</span><span class="sxs-lookup"><span data-stu-id="01902-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="01902-p113">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="01902-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="01902-199">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="01902-199">**Create Subdomain**</span></span>|<span data-ttu-id="01902-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="01902-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="01902-201">autodiscover</span><span class="sxs-lookup"><span data-stu-id="01902-201">autodiscover</span></span>  <br/> |<span data-ttu-id="01902-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="01902-202">autodiscover.outlook.com</span></span>   | 

    ![1 &amp; -BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="01902-204">Välj **skapa under domän**.</span><span class="sxs-lookup"><span data-stu-id="01902-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="01902-205">![1 &amp; -BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="01902-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="01902-206">Leta reda på den **Autodiscover** -underdomän som du just skapade i avsnittet **subdomain Overview** **(** under domän översikt).</span><span class="sxs-lookup"><span data-stu-id="01902-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="01902-207">![1 &amp; -BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="01902-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="01902-208">I området under **domän inställningar** väljer du **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="01902-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="01902-209">![1 &amp; -BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="01902-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="01902-210">Välj **CNAME**i området **IP Address (a Record)** i avsnittet **A/AAAA Records (IP-adresser)** .</span><span class="sxs-lookup"><span data-stu-id="01902-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="01902-211">![1 &amp; -BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="01902-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="01902-212">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="01902-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="01902-213">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="01902-213">**Create Subdomain**</span></span>|<span data-ttu-id="01902-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="01902-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="01902-215">autodiscover</span><span class="sxs-lookup"><span data-stu-id="01902-215">autodiscover</span></span>  <br/> |<span data-ttu-id="01902-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="01902-216">autodiscover.outlook.com</span></span>   |

    ![1 &amp; -BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="01902-218">Markera kryssrutan för ansvarsfriskrivningen **I am aware** (jag är medveten om).</span><span class="sxs-lookup"><span data-stu-id="01902-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="01902-219">![1 &amp; -BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="01902-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="01902-220">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-220">Select **Save**.</span></span><br/><span data-ttu-id="01902-221">![1 &amp; -BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="01902-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="01902-222">Ytterligare CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="01902-222">Additional CNAME records</span></span>

<span data-ttu-id="01902-p114">De ytterligare CNAME-poster som skapas i följande proceduren aktiverar Skype för företag - Online-tjänster. Du kan utföra samma steg som du använde för att skapa de två CNAME-poster som du redan har skapat.</span><span class="sxs-lookup"><span data-stu-id="01902-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="01902-225">Skapa den tredje underdomänen (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="01902-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="01902-226">I avsnittet under **domän översikt** väljer du **skapa under domän**.</span><span class="sxs-lookup"><span data-stu-id="01902-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="01902-p115">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="01902-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="01902-229">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="01902-229">**Create Subdomain**</span></span>|<span data-ttu-id="01902-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="01902-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="01902-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="01902-231">lyncdiscover</span></span>   |<span data-ttu-id="01902-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01902-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="01902-233">Välj **skapa under domän**.</span><span class="sxs-lookup"><span data-stu-id="01902-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="01902-234">Välj **Hantera under domäner**på sidan **domän Center** .</span><span class="sxs-lookup"><span data-stu-id="01902-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="01902-235">Leta upp under domänen **Lyncdiscover** som du just skapade i avsnittet under **domän översikt** och välj sedan **panelen (v)** för den under domänen.</span><span class="sxs-lookup"><span data-stu-id="01902-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="01902-236">I området under **domän inställningar** väljer du **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="01902-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="01902-237">Välj **CNAME**i området **IP Address (a Record)** i avsnittet **A/AAAA Records (IP-adresser)** .</span><span class="sxs-lookup"><span data-stu-id="01902-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="01902-238">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="01902-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="01902-239">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="01902-239">**Create Subdomain**</span></span>|<span data-ttu-id="01902-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="01902-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="01902-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="01902-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="01902-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01902-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="01902-243">Markera kryss rutan för den **jag känner** till fri skrivning och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="01902-244">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="01902-245">Skapa den fjärde underdomänen (SIP):</span><span class="sxs-lookup"><span data-stu-id="01902-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="01902-246">I avsnittet under **domän översikt** väljer du **skapa under domän**.</span><span class="sxs-lookup"><span data-stu-id="01902-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="01902-p116">I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)</span><span class="sxs-lookup"><span data-stu-id="01902-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="01902-249">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="01902-249">**Create Subdomain**</span></span>|<span data-ttu-id="01902-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="01902-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="01902-251">sip</span><span class="sxs-lookup"><span data-stu-id="01902-251">sip</span></span>  <br/> |<span data-ttu-id="01902-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01902-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="01902-253">Välj **skapa under domän**.</span><span class="sxs-lookup"><span data-stu-id="01902-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="01902-254">Välj **Hantera under domäner**på sidan **domän Center** .</span><span class="sxs-lookup"><span data-stu-id="01902-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="01902-255">Leta upp den **SIP** -underdomän som du just skapade i avsnittet under **domän översikt** och välj sedan **panelen (v)** för den under domänen.</span><span class="sxs-lookup"><span data-stu-id="01902-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="01902-256">I området under **domän inställningar** väljer du **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="01902-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="01902-257">Välj **CNAME**i området **IP Address (a Record)** i avsnittet **A/AAAA Records (IP-adresser)** .</span><span class="sxs-lookup"><span data-stu-id="01902-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="01902-258">I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="01902-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="01902-259">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="01902-259">**Create Subdomain**</span></span>|<span data-ttu-id="01902-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="01902-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="01902-261">sip</span><span class="sxs-lookup"><span data-stu-id="01902-261">sip</span></span>  <br/> |<span data-ttu-id="01902-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01902-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="01902-263">Markera kryss rutan för den **jag känner** till fri skrivning och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="01902-264">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="01902-265">CNAME-poster som krävs för MDM</span><span class="sxs-lookup"><span data-stu-id="01902-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01902-266">Följ proceduren som används för de andra fyra CNAME-posterna, men använd värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="01902-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="01902-267">**Skapa underdomän**</span><span class="sxs-lookup"><span data-stu-id="01902-267">**Create Subdomain**</span></span>|<span data-ttu-id="01902-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="01902-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="01902-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="01902-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="01902-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="01902-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="01902-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="01902-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="01902-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="01902-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="01902-273">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="01902-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01902-274">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="01902-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="01902-275">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="01902-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="01902-276">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01902-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="01902-277">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="01902-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="01902-278">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="01902-278">Need examples?</span></span> <span data-ttu-id="01902-279">Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="01902-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="01902-280">Du kan validera SPF-posten genom att använda någon av dessa[SPF-verifierings verktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="01902-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="01902-281">Följ stegen nedan eller [titta på videon (börja vid 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="01902-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="01902-282">Om du har registrerat dig hos 1und1.de [loggar](https://go.microsoft.com/fwlink/?linkid=859152)du in här.</span><span class="sxs-lookup"><span data-stu-id="01902-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="01902-283">Kom igång genom att gå till sidan Domains på 1&1 IONOS med hjälp av [den här länken](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="01902-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="01902-284">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="01902-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="01902-285">Välj **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="01902-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="01902-286">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan **panel** kontrollen (**v**) för den domänen.</span><span class="sxs-lookup"><span data-stu-id="01902-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="01902-287">Välj **Edit DNS Settings**i området **Domain Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="01902-288">Välj **Add Record**i avsnittet **txt and SRV Records** .</span><span class="sxs-lookup"><span data-stu-id="01902-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="01902-289">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="01902-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="01902-290">Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="01902-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="01902-291">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="01902-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="01902-292">**Typ**</span><span class="sxs-lookup"><span data-stu-id="01902-292">**Type**</span></span>|<span data-ttu-id="01902-293">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="01902-293">**Prefix**</span></span>|<span data-ttu-id="01902-294">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="01902-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01902-295">TXT</span><span class="sxs-lookup"><span data-stu-id="01902-295">TXT</span></span>  <br/> |<span data-ttu-id="01902-296">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="01902-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01902-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="01902-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="01902-298">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="01902-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT-post](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="01902-300">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-300">Select **Save**.</span></span><br/><span data-ttu-id="01902-301">![Lägg till post](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="01902-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="01902-302">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-302">Select **Save**.</span></span><br/><span data-ttu-id="01902-303">![Spara post](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="01902-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="01902-304">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="01902-305">![Välja Ja i dialog rutan Edit DNS Settings](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="01902-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="01902-306">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="01902-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="01902-307">Följ stegen nedan eller [titta på videon (börja vid 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="01902-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="01902-308">Om du har registrerat dig hos 1und1.de [loggar](https://go.microsoft.com/fwlink/?linkid=859152)du in här.</span><span class="sxs-lookup"><span data-stu-id="01902-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="01902-309">Kom igång genom att gå till sidan Domains på 1&1 IONOS med hjälp av [den här länken](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="01902-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="01902-310">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="01902-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="01902-311">Välj **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="01902-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="01902-312">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan **panel** kontrollen ( **v**) för den domänen.</span><span class="sxs-lookup"><span data-stu-id="01902-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="01902-313">Välj **Edit DNS Settings**i området **Domain Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="01902-314">Välj **Add Record**i avsnittet **txt and SRV Records** .</span><span class="sxs-lookup"><span data-stu-id="01902-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="01902-315">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="01902-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="01902-316">I den nya postens rutor i området **Add Record** (lägg till post) skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="01902-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="01902-317">(Välj värdena **Type** och **TTL** i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="01902-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="01902-318">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="01902-318">**Type**</span></span>|<span data-ttu-id="01902-319">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="01902-319">**Service**</span></span>|<span data-ttu-id="01902-320">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="01902-320">**Protocol**</span></span>|<span data-ttu-id="01902-321">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="01902-321">**Name**</span></span>|<span data-ttu-id="01902-322">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="01902-322">**Host**</span></span>|<span data-ttu-id="01902-323">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="01902-323">**Priority**</span></span>|<span data-ttu-id="01902-324">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="01902-324">**Weight**</span></span>|<span data-ttu-id="01902-325">**Port**</span><span class="sxs-lookup"><span data-stu-id="01902-325">**Port**</span></span>|<span data-ttu-id="01902-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="01902-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="01902-327">SRV</span><span class="sxs-lookup"><span data-stu-id="01902-327">SRV</span></span>  <br/> |<span data-ttu-id="01902-328">sip</span><span class="sxs-lookup"><span data-stu-id="01902-328">sip</span></span>  <br/> |<span data-ttu-id="01902-329">tls</span><span class="sxs-lookup"><span data-stu-id="01902-329">tls</span></span>  <br/> |<span data-ttu-id="01902-330">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="01902-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01902-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01902-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="01902-332">100</span><span class="sxs-lookup"><span data-stu-id="01902-332">100</span></span>  <br/> |<span data-ttu-id="01902-333">9.1</span><span class="sxs-lookup"><span data-stu-id="01902-333">1</span></span>  <br/> |<span data-ttu-id="01902-334">443</span><span class="sxs-lookup"><span data-stu-id="01902-334">443</span></span>  <br/> |<span data-ttu-id="01902-335">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="01902-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="01902-336">SRV</span><span class="sxs-lookup"><span data-stu-id="01902-336">SRV</span></span>  <br/> |<span data-ttu-id="01902-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="01902-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="01902-338">tcp</span><span class="sxs-lookup"><span data-stu-id="01902-338">tcp</span></span>  <br/> |<span data-ttu-id="01902-339">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="01902-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01902-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01902-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="01902-341">100</span><span class="sxs-lookup"><span data-stu-id="01902-341">100</span></span>  <br/> |<span data-ttu-id="01902-342">9.1</span><span class="sxs-lookup"><span data-stu-id="01902-342">1</span></span>  <br/> |<span data-ttu-id="01902-343">5061</span><span class="sxs-lookup"><span data-stu-id="01902-343">5061</span></span>  <br/> |<span data-ttu-id="01902-344">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="01902-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1 &amp; -BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="01902-346">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-346">Select **Save**.</span></span> <br/><span data-ttu-id="01902-347">![1 &amp; -BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="01902-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="01902-348">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01902-348">Select **Save**.</span></span> <br/><span data-ttu-id="01902-349">![1 &amp; -BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="01902-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="01902-350">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="01902-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="01902-351">![Välja Ja i dialog rutan Edit DNS Settings](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="01902-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="01902-352">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="01902-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="01902-353">Välj **Add Record**i avsnittet **txt and SRV Records** .</span><span class="sxs-lookup"><span data-stu-id="01902-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="01902-354">I området **Add Record** skapar du en post med värdena från den andra raden i tabellen och väljer sedan **Lägg till**, **Spara**och **Ja** för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="01902-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="01902-p120">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="01902-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
