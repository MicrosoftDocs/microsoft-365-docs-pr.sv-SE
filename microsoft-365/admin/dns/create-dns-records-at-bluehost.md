---
title: Skapa DNS-poster på Bluehost för Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Bluehost för Microsoft.
ms.openlocfilehash: a39e44794ad0d8c66cd0786f88642541c6978a8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629725"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="3d6b6-103">Skapa DNS-poster på Bluehost för Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d6b6-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="3d6b6-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3d6b6-105">Om Bluehost är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3d6b6-106">När du har lagt till dessa poster på Bluehost konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="3d6b6-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d6b6-108">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3d6b6-109">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3d6b6-110">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3d6b6-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="3d6b6-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3d6b6-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3d6b6-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3d6b6-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="3d6b6-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d6b6-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3d6b6-117">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3d6b6-118">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3d6b6-119">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3d6b6-120">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3d6b6-121">Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .</span><span class="sxs-lookup"><span data-stu-id="3d6b6-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3d6b6-122">På sidan \*\* DNS Zone Editor \*\* i området **Lägg till DNS-post,** skriver eller kopierar eller klistrar du in värdena från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d6b6-123">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d6b6-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-124">**Host Record**</span></span> <br/> |<span data-ttu-id="3d6b6-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-125">**TTL**</span></span> <br/> |<span data-ttu-id="3d6b6-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-126">**Type**</span></span> <br/> |<span data-ttu-id="3d6b6-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="3d6b6-128">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-128">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-129">TXT</span><span class="sxs-lookup"><span data-stu-id="3d6b6-129">TXT</span></span>  <br/> |<span data-ttu-id="3d6b6-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3d6b6-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3d6b6-131">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-131">**Note:** This is an example.</span></span> <span data-ttu-id="3d6b6-132">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="3d6b6-133">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="3d6b6-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="3d6b6-134">Välj **lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="3d6b6-135">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3d6b6-136">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="3d6b6-137">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3d6b6-138">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="3d6b6-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3d6b6-139">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3d6b6-140">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3d6b6-141">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3d6b6-142">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3d6b6-143">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3d6b6-144">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3d6b6-145">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d6b6-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3d6b6-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3d6b6-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3d6b6-147">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3d6b6-148">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3d6b6-149">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3d6b6-150">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3d6b6-151">Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .</span><span class="sxs-lookup"><span data-stu-id="3d6b6-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3d6b6-152">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d6b6-153">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d6b6-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-154">**Host Record**</span></span>|<span data-ttu-id="3d6b6-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-155">**TTL**</span></span>|<span data-ttu-id="3d6b6-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-156">**Type**</span></span>|<span data-ttu-id="3d6b6-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-157">**Points To**</span></span>|<span data-ttu-id="3d6b6-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3d6b6-159">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-159">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-160">MX</span><span class="sxs-lookup"><span data-stu-id="3d6b6-160">MX</span></span>  <br/> | <span data-ttu-id="3d6b6-161">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d6b6-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="3d6b6-162">**Anm.:** Hämta \< *domännyckeln* \> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-162">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="3d6b6-163">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="3d6b6-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3d6b6-164">0</span><span class="sxs-lookup"><span data-stu-id="3d6b6-164">0</span></span>  <br/> <span data-ttu-id="3d6b6-165">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Välj Typ i listrutan](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="3d6b6-167">Välj **lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-167">Select **add record**.</span></span>
    
    ![Välj Lägg till post](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="3d6b6-169">Om det finns andra MX-poster i avsnittet **MX (Mail Exchanger)** ska du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="3d6b6-170">För en av de andra MX-posterna väljer du **Ta bort.**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Välj Ta bort för varje ytterligare MX-post](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="3d6b6-172">Välj **OK**i bekräftelsedialogrutan .</span><span class="sxs-lookup"><span data-stu-id="3d6b6-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Välj OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="3d6b6-174">Du använder samma process för att ta bort eventuella andra MX-poster som visas.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d6b6-175">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d6b6-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3d6b6-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3d6b6-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3d6b6-177">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3d6b6-178">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3d6b6-179">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3d6b6-180">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3d6b6-181">Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .</span><span class="sxs-lookup"><span data-stu-id="3d6b6-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3d6b6-182">Leta reda på raden för posten för **automatisk upptäckt** i avsnittet **A (Värd)** och välj sedan **ta bort** för den raden.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3d6b6-183">Du måste ta bort den befintliga posten för **automatisk upptäckt** *innan* du lägger till den **automatiska upptäcktspost** som krävs av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="3d6b6-184">Bluehost tillåter inte att du har två **autodiscover** -poster samtidigt.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Välj Ta bort](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="3d6b6-186">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-186">Select **OK**.</span></span>
    
    ![Välj OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="3d6b6-188">Skapa den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3d6b6-189">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3d6b6-190">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d6b6-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-191">**Host Record**</span></span>|<span data-ttu-id="3d6b6-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-192">**TTL**</span></span>|<span data-ttu-id="3d6b6-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-193">**Type**</span></span>|<span data-ttu-id="3d6b6-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d6b6-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3d6b6-195">autodiscover</span></span>  <br/> |<span data-ttu-id="3d6b6-196">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-196">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d6b6-197">CNAME</span></span>  <br/> |<span data-ttu-id="3d6b6-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d6b6-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3d6b6-199">sip</span><span class="sxs-lookup"><span data-stu-id="3d6b6-199">sip</span></span>  <br/> |<span data-ttu-id="3d6b6-200">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-200">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d6b6-201">CNAME</span></span>  <br/> |<span data-ttu-id="3d6b6-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d6b6-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d6b6-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3d6b6-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3d6b6-204">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-204">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d6b6-205">CNAME</span></span>  <br/> |<span data-ttu-id="3d6b6-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d6b6-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d6b6-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3d6b6-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3d6b6-208">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-208">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d6b6-209">CNAME</span></span>  <br/> |<span data-ttu-id="3d6b6-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3d6b6-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="3d6b6-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3d6b6-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3d6b6-212">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-212">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d6b6-213">CNAME</span></span>  <br/> |<span data-ttu-id="3d6b6-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3d6b6-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Skapa den första CNAME-posten](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="3d6b6-216">Välj **lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-216">Select **add record**.</span></span>
    
    ![Välj Lägg till post](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="3d6b6-218">Lägg till de andra fem CNAME-posterna var för sig.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="3d6b6-219">I avsnittet **Lägg till DNS-post** skapar du en post med hjälp av värdena från nästa rad i tabellen och väljer sedan **lägga till post** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="3d6b6-220">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3d6b6-221">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="3d6b6-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3d6b6-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3d6b6-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d6b6-223">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3d6b6-224">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3d6b6-225">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3d6b6-226">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="3d6b6-227">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="3d6b6-227">Need examples?</span></span> <span data-ttu-id="3d6b6-228">Kolla in dessa [externa domännamnssystemposter för Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-228">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="3d6b6-229">Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="3d6b6-230">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3d6b6-231">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3d6b6-232">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3d6b6-233">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3d6b6-234">Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .</span><span class="sxs-lookup"><span data-stu-id="3d6b6-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3d6b6-235">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d6b6-236">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="3d6b6-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-237">**Host Record**</span></span>|<span data-ttu-id="3d6b6-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-238">**TTL**</span></span>|<span data-ttu-id="3d6b6-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-239">**Type**</span></span>|<span data-ttu-id="3d6b6-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3d6b6-241">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-241">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-242">TXT</span><span class="sxs-lookup"><span data-stu-id="3d6b6-242">TXT</span></span>  <br/> |<span data-ttu-id="3d6b6-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3d6b6-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="3d6b6-244">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="3d6b6-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopiera TXT-värdet](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="3d6b6-246">Välj **lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-246">Select **add record**.</span></span>
    
    ![Välj Lägg till post](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d6b6-248">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d6b6-248">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3d6b6-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3d6b6-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3d6b6-250">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="3d6b6-251">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3d6b6-252">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="3d6b6-253">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="3d6b6-254">Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .</span><span class="sxs-lookup"><span data-stu-id="3d6b6-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="3d6b6-255">Skapa den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3d6b6-256">Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3d6b6-257">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3d6b6-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d6b6-258">**Service**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-258">**Service**</span></span>|<span data-ttu-id="3d6b6-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-259">**Protocol**</span></span>|<span data-ttu-id="3d6b6-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-260">**Host**</span></span>|<span data-ttu-id="3d6b6-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-261">**TTL**</span></span>|<span data-ttu-id="3d6b6-262">**Type**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-262">**Type**</span></span>|<span data-ttu-id="3d6b6-263">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-263">**Priority**</span></span>|<span data-ttu-id="3d6b6-264">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-264">**Weight**</span></span>|<span data-ttu-id="3d6b6-265">**Port**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-265">**Port**</span></span>|<span data-ttu-id="3d6b6-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="3d6b6-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d6b6-267">_sip</span><span class="sxs-lookup"><span data-stu-id="3d6b6-267">_sip</span></span>  <br/> |<span data-ttu-id="3d6b6-268">_tls</span><span class="sxs-lookup"><span data-stu-id="3d6b6-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="3d6b6-269">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-269">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-270">SRV</span><span class="sxs-lookup"><span data-stu-id="3d6b6-270">SRV</span></span>  <br/> |<span data-ttu-id="3d6b6-271">100</span><span class="sxs-lookup"><span data-stu-id="3d6b6-271">100</span></span>  <br/> |<span data-ttu-id="3d6b6-272">1</span><span class="sxs-lookup"><span data-stu-id="3d6b6-272">1</span></span>  <br/> |<span data-ttu-id="3d6b6-273">443</span><span class="sxs-lookup"><span data-stu-id="3d6b6-273">443</span></span>  <br/> |<span data-ttu-id="3d6b6-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d6b6-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d6b6-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3d6b6-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="3d6b6-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="3d6b6-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="3d6b6-277">14400</span><span class="sxs-lookup"><span data-stu-id="3d6b6-277">14400</span></span>  <br/> |<span data-ttu-id="3d6b6-278">SRV</span><span class="sxs-lookup"><span data-stu-id="3d6b6-278">SRV</span></span>  <br/> |<span data-ttu-id="3d6b6-279">100</span><span class="sxs-lookup"><span data-stu-id="3d6b6-279">100</span></span>  <br/> |<span data-ttu-id="3d6b6-280">1</span><span class="sxs-lookup"><span data-stu-id="3d6b6-280">1</span></span>  <br/> |<span data-ttu-id="3d6b6-281">5061</span><span class="sxs-lookup"><span data-stu-id="3d6b6-281">5061</span></span>  <br/> |<span data-ttu-id="3d6b6-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d6b6-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Kopiera värdet för den nya posten](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="3d6b6-284">Välj **lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-284">Select **add record**.</span></span>
    
    ![Välj Lägg till post](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="3d6b6-286">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3d6b6-287">I avsnittet **Lägg till DNS-post** skapar du en post med hjälp av värdena från den andra raden i tabellen och väljer sedan **lägga till post** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3d6b6-288">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3d6b6-289">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="3d6b6-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3d6b6-290">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d6b6-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

