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
ms.openlocfilehash: dde060b6e03eebb89029b742402558e95031b1d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629689"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="d0484-103">Skapa DNS-poster på DNSMadeEasy för Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0484-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="d0484-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="d0484-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d0484-105">Om DNSMadeEasy är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="d0484-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d0484-106">När du har lagt till dessa poster på DNSMadeEasy konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="d0484-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="d0484-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="d0484-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0484-108">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="d0484-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d0484-109">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="d0484-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d0484-110">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0484-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d0484-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="d0484-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d0484-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d0484-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d0484-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="d0484-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="d0484-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="d0484-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0484-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="d0484-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d0484-117">För DNSMadeEasy-konton köptes domänen som du lade till från en separat domänregistratorer.</span><span class="sxs-lookup"><span data-stu-id="d0484-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="d0484-118">DNSMadeEasy erbjuder inte domänregistreringstjänster.</span><span class="sxs-lookup"><span data-stu-id="d0484-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="d0484-119">Din förmåga att logga in på DNSMadeEasy och skapa DNS-posten är tillräckligt bevis på ägande.</span><span class="sxs-lookup"><span data-stu-id="d0484-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="d0484-120">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="d0484-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="d0484-121">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d0484-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="d0484-122">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="d0484-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="d0484-123">På sidan **Hanterad DNS** i området **TXT** **+** Records väljer du () **(Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="d0484-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="d0484-124">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="d0484-125">Gå till området **Add TXT Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="d0484-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="d0484-126">**Namn**</span><span class="sxs-lookup"><span data-stu-id="d0484-126">**Name**</span></span> <br/> |<span data-ttu-id="d0484-127">**Värde**</span><span class="sxs-lookup"><span data-stu-id="d0484-127">**Value**</span></span> <br/> |<span data-ttu-id="d0484-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0484-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="d0484-129">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d0484-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d0484-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d0484-131">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="d0484-131">**Note:** This is an example.</span></span> <span data-ttu-id="d0484-132">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="d0484-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="d0484-133">Hur hittar jag detta?</span><span class="sxs-lookup"><span data-stu-id="d0484-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d0484-134">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="d0484-135">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d0484-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="d0484-136">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="d0484-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d0484-137">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="d0484-137">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d0484-138">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="d0484-138">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d0484-139">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="d0484-139">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d0484-140">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="d0484-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d0484-141">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="d0484-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d0484-142">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="d0484-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d0484-143">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="d0484-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d0484-144">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="d0484-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d0484-145">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0484-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d0484-146">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0484-146">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d0484-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d0484-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d0484-p108">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d0484-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="d0484-150">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="d0484-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="d0484-151">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="d0484-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Konfigurera-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="d0484-153">På sidan **Hanterad DNS** i området **MX Records** väljer du **(+)** kontrollen ( **Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="d0484-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="d0484-154">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Konfigurera-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="d0484-156">Gå till området **Add MX Records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="d0484-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d0484-157">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d0484-158">**Namn**</span><span class="sxs-lookup"><span data-stu-id="d0484-158">**Name**</span></span>|<span data-ttu-id="d0484-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="d0484-159">**Server**</span></span>|<span data-ttu-id="d0484-160">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="d0484-160">**MX Level**</span></span>|<span data-ttu-id="d0484-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0484-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0484-162">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="d0484-163">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d0484-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d0484-164">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d0484-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d0484-165">**Anm.:** Hämta \< *domännyckeln* \> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="d0484-165">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="d0484-166">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="d0484-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d0484-167">10</span><span class="sxs-lookup"><span data-stu-id="d0484-167">10</span></span>  <br/> <span data-ttu-id="d0484-168">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="d0484-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="d0484-169">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="d0484-171">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d0484-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="d0484-173">Om det finns andra MX-poster som visas i avsnittet **MX Records** ska du ta bort alla genom att välja dem.</span><span class="sxs-lookup"><span data-stu-id="d0484-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Konfigurera-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="d0484-175">När alla poster är markerade väljer du **Ta bort markerat**.</span><span class="sxs-lookup"><span data-stu-id="d0484-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Konfigurera-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="d0484-177">Välj **Ta bort** för att bekräfta ändringarna i dialogrutan Ta **bort MX-poster.**</span><span class="sxs-lookup"><span data-stu-id="d0484-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d0484-179">Lägga till de fem CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0484-179">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d0484-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d0484-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d0484-p110">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d0484-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="d0484-183">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="d0484-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="d0484-184">På sidan **Hanterad DNS** i området **CNAME Records** väljer du **(+)** kontrollen ( **Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="d0484-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="d0484-185">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1 DNSMadeEasy-BP-Configure-3-1 DNSMadeEasy-BP-Configure-3-1 DNSMade](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="d0484-187">Lägg till den första av de fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="d0484-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="d0484-188">I den nya postens rutor i området **Add CNAME Records** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="d0484-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="d0484-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="d0484-189">**Name**</span></span>|<span data-ttu-id="d0484-190">**Alias to**</span><span class="sxs-lookup"><span data-stu-id="d0484-190">**Alias to**</span></span>|<span data-ttu-id="d0484-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0484-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d0484-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d0484-192">autodiscover</span></span>  <br/> |<span data-ttu-id="d0484-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d0484-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d0484-194">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d0484-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0484-195">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-195">1800</span></span>  <br/> |
    |<span data-ttu-id="d0484-196">sip</span><span class="sxs-lookup"><span data-stu-id="d0484-196">sip</span></span>  <br/> |<span data-ttu-id="d0484-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0484-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d0484-198">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d0484-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0484-199">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-199">1800</span></span>  <br/> |
    |<span data-ttu-id="d0484-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d0484-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d0484-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0484-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d0484-202">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d0484-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0484-203">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-203">1800</span></span>  <br/> |
    |<span data-ttu-id="d0484-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d0484-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d0484-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="d0484-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="d0484-206">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d0484-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0484-207">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-207">1800</span></span>  <br/> |
    |<span data-ttu-id="d0484-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d0484-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d0484-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d0484-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="d0484-210">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d0484-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0484-211">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="d0484-213">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d0484-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="d0484-215">Lägg till var och en av de fyra andra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="d0484-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="d0484-216">I avsnittet **CNAME-poster** markerar du **(+)** kontrollen ( **Lägg till ny**), skapar en post med hjälp av värdena från nästa rad i tabellen och väljer sedan **Skicka** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="d0484-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="d0484-217">Upprepa den här processen tills du har skapat alla fem CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="d0484-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d0484-218">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="d0484-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d0484-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d0484-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0484-220">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="d0484-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d0484-221">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="d0484-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d0484-222">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0484-222">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d0484-223">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="d0484-223">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="d0484-224">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="d0484-224">Need examples?</span></span> <span data-ttu-id="d0484-225">Kolla in dessa [externa domännamnssystemposter för Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="d0484-225">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="d0484-226">Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d0484-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="d0484-227">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="d0484-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="d0484-228">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d0484-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="d0484-229">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="d0484-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="d0484-230">På sidan **Hanterad DNS** i området **TXT Records** väljer du **(+)** kontrollen ( **Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="d0484-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="d0484-231">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Konfigurera-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="d0484-233">Gå till området **Add TXT Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="d0484-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="d0484-234">**Namn**</span><span class="sxs-lookup"><span data-stu-id="d0484-234">**Name**</span></span>|<span data-ttu-id="d0484-235">**Värde**</span><span class="sxs-lookup"><span data-stu-id="d0484-235">**Value**</span></span>|<span data-ttu-id="d0484-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0484-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d0484-237">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d0484-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d0484-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d0484-239">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="d0484-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d0484-240">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="d0484-242">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d0484-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Konfigurera-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d0484-244">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0484-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d0484-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d0484-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d0484-p113">Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d0484-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="d0484-248">Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.**</span><span class="sxs-lookup"><span data-stu-id="d0484-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="d0484-249">På sidan **Hanterad DNS** i området **SRV Records** på sidan Hanterade DNS väljer du **(+)** kontrollen ( **Lägg till ny**).</span><span class="sxs-lookup"><span data-stu-id="d0484-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="d0484-250">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="d0484-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="d0484-252">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="d0484-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="d0484-253">I den nya postens rutor i området **Add SRV Records** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="d0484-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="d0484-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="d0484-254">**Name**</span></span>|<span data-ttu-id="d0484-255">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="d0484-255">**Priority**</span></span>|<span data-ttu-id="d0484-256">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="d0484-256">**Weight**</span></span>|<span data-ttu-id="d0484-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="d0484-257">**Port**</span></span>|<span data-ttu-id="d0484-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="d0484-258">**Host**</span></span>|<span data-ttu-id="d0484-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0484-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0484-260">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="d0484-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="d0484-261">100</span><span class="sxs-lookup"><span data-stu-id="d0484-261">100</span></span>  <br/> |<span data-ttu-id="d0484-262">1</span><span class="sxs-lookup"><span data-stu-id="d0484-262">1</span></span>  <br/> |<span data-ttu-id="d0484-263">443</span><span class="sxs-lookup"><span data-stu-id="d0484-263">443</span></span>  <br/> |<span data-ttu-id="d0484-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0484-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d0484-265">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d0484-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0484-266">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-266">1800</span></span>  <br/> |
    |<span data-ttu-id="d0484-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="d0484-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="d0484-268">100</span><span class="sxs-lookup"><span data-stu-id="d0484-268">100</span></span>  <br/> |<span data-ttu-id="d0484-269">1</span><span class="sxs-lookup"><span data-stu-id="d0484-269">1</span></span>  <br/> |<span data-ttu-id="d0484-270">5061</span><span class="sxs-lookup"><span data-stu-id="d0484-270">5061</span></span>  <br/> |<span data-ttu-id="d0484-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0484-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="d0484-272">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d0484-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0484-273">1800</span><span class="sxs-lookup"><span data-stu-id="d0484-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="d0484-275">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d0484-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="d0484-277">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="d0484-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="d0484-278">I avsnittet **SRV-poster** markerar du **(+)** kontrollen ( **Lägg till ny**), skapar en post med hjälp av värdena från nästa rad i tabellen och väljer sedan **Skicka** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="d0484-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d0484-279">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="d0484-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d0484-280">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="d0484-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d0484-281">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0484-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

