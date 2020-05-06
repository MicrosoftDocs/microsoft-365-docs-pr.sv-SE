---
title: Skapa DNS-poster på GoDaddy för Microsoft
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på GoDaddy för Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: b1c5539af6683bbf8f94fd15880fb870caf31342
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049029"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="f9bc4-103">Skapa DNS-poster på GoDaddy för Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9bc4-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="f9bc4-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="f9bc4-105">Om GoDaddy är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="f9bc4-106">När du har lagt till dessa poster på GoDaddy konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="f9bc4-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f9bc4-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="f9bc4-110">Add a TXT record for verification</span></span>
<span data-ttu-id="f9bc4-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f9bc4-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f9bc4-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="f9bc4-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="f9bc4-116">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-116">Follow the steps below.</span></span>

1. <span data-ttu-id="f9bc4-p104">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="f9bc4-120">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="f9bc4-122">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-122">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="f9bc4-124">Välj **TXT (Text)** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="f9bc4-125">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="f9bc4-126">**Record type**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-126">**Record type**</span></span> |<span data-ttu-id="f9bc4-127">**Värd**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-127">**Host**</span></span>|<span data-ttu-id="f9bc4-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-128">**TXT Value**</span></span>|<span data-ttu-id="f9bc4-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9bc4-130">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-130">TXT (Text)</span></span>|@|<span data-ttu-id="f9bc4-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f9bc4-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="f9bc4-132">**Obs:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-132">**Note**: This is an example.</span></span> <span data-ttu-id="f9bc4-133">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="f9bc4-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="f9bc4-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="f9bc4-135">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-135">1 hour</span></span>  <br><span data-ttu-id="f9bc4-136">(Välj ett värde i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verifiera-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="f9bc4-138">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-138">Select **Save**.</span></span>

6. <span data-ttu-id="f9bc4-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="f9bc4-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="f9bc4-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f9bc4-142">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f9bc4-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f9bc4-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="f9bc4-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="f9bc4-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f9bc4-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f9bc4-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f9bc4-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="f9bc4-151">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-151">Follow the steps below.</span></span>

1. <span data-ttu-id="f9bc4-p108">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="f9bc4-155">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="f9bc4-157">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-157">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="f9bc4-159">Välj **MX (Mail Exchanger)** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Konfigurera-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="f9bc4-161">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="f9bc4-162">(Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="f9bc4-163">**Record type**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-163">**Record type**</span></span>|<span data-ttu-id="f9bc4-164">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-164">**Host**</span></span>|<span data-ttu-id="f9bc4-165">**Pekar på**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-165">**Points to**</span></span>|<span data-ttu-id="f9bc4-166">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-166">**Priority**</span></span>|<span data-ttu-id="f9bc4-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9bc4-168">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="f9bc4-169">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f9bc4-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f9bc4-170">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="f9bc4-171">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="f9bc4-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f9bc4-172">10</span><span class="sxs-lookup"><span data-stu-id="f9bc4-172">10</span></span>  <br/> <span data-ttu-id="f9bc4-173">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="f9bc4-174">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="f9bc4-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f9bc4-176">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9bc4-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="f9bc4-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f9bc4-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="f9bc4-178">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-178">Follow the steps below.</span></span>

1. <span data-ttu-id="f9bc4-p110">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="f9bc4-182">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="f9bc4-184">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-184">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="f9bc4-186">Välj **CNAME (Alias)** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Konfigurera-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="f9bc4-188">Skapa den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="f9bc4-189">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="f9bc4-190">(Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="f9bc4-191">**Record type**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-191">**Record type**</span></span>|<span data-ttu-id="f9bc4-192">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-192">**Host**</span></span>|<span data-ttu-id="f9bc4-193">**Pekar på**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-193">**Points to**</span></span>|<span data-ttu-id="f9bc4-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9bc4-195">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f9bc4-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f9bc4-196">autodiscover</span></span>  <br/> |<span data-ttu-id="f9bc4-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f9bc4-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="f9bc4-198">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="f9bc4-199">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f9bc4-200">sip</span><span class="sxs-lookup"><span data-stu-id="f9bc4-200">sip</span></span>  <br/> |<span data-ttu-id="f9bc4-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9bc4-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="f9bc4-202">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="f9bc4-203">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f9bc4-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f9bc4-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f9bc4-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9bc4-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="f9bc4-206">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="f9bc4-207">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f9bc4-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f9bc4-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f9bc4-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f9bc4-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="f9bc4-210">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="f9bc4-211">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f9bc4-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f9bc4-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f9bc4-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f9bc4-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="f9bc4-214">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="f9bc4-215">Upprepa dessa steg för att lägga till nästa CNAME-post tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f9bc4-216">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="f9bc4-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f9bc4-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f9bc4-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9bc4-218">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f9bc4-219">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f9bc4-220">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f9bc4-221">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="f9bc4-222">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-222">Follow the steps below.</span></span>

1. <span data-ttu-id="f9bc4-p112">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="f9bc4-226">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="f9bc4-228">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-228">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="f9bc4-230">Välj **TXT (Text)** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Konfigurera-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="f9bc4-232">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="f9bc4-233">(Välj **TTL-värdet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="f9bc4-234">**Record type**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-234">**Record type**</span></span>|<span data-ttu-id="f9bc4-235">**Värd**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-235">**Host**</span></span>|<span data-ttu-id="f9bc4-236">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-236">**TXT Value**</span></span>|<span data-ttu-id="f9bc4-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9bc4-238">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="f9bc4-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f9bc4-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f9bc4-240">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="f9bc4-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="f9bc4-241">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Konfigurera-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="f9bc4-243">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f9bc4-244">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9bc4-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="f9bc4-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f9bc4-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="f9bc4-246">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-246">Follow the steps below.</span></span>

1. <span data-ttu-id="f9bc4-p113">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="f9bc4-250">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="f9bc4-252">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-252">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="f9bc4-254">Välj **SRV (Service)** (SRV (tjänst)) i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Konfigurera-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="f9bc4-256">Skapa den första SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-256">Create the first SRV record.</span></span>

    <span data-ttu-id="f9bc4-257">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="f9bc4-258">(Välj **värden för posttyp** och **TTL** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="f9bc4-259">**Record type**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-259">**Record type**</span></span>|<span data-ttu-id="f9bc4-260">**Namn**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-260">**Name**</span></span>|<span data-ttu-id="f9bc4-261">**Mål**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-261">**Target**</span></span>|<span data-ttu-id="f9bc4-262">**Protokoll**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-262">**Protocol**</span></span>|<span data-ttu-id="f9bc4-263">**Tjänst**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-263">**Service**</span></span>|<span data-ttu-id="f9bc4-264">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-264">**Priority**</span></span>|<span data-ttu-id="f9bc4-265">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-265">**Weight**</span></span>|<span data-ttu-id="f9bc4-266">**Port**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-266">**Port**</span></span>|<span data-ttu-id="f9bc4-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9bc4-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9bc4-268">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="f9bc4-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9bc4-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="f9bc4-270">_tls</span><span class="sxs-lookup"><span data-stu-id="f9bc4-270">_tls</span></span>  <br/> |<span data-ttu-id="f9bc4-271">_sip</span><span class="sxs-lookup"><span data-stu-id="f9bc4-271">_sip</span></span>  <br/> |<span data-ttu-id="f9bc4-272">100</span><span class="sxs-lookup"><span data-stu-id="f9bc4-272">100</span></span>  <br/> |<span data-ttu-id="f9bc4-273">1</span><span class="sxs-lookup"><span data-stu-id="f9bc4-273">1</span></span>  <br/> |<span data-ttu-id="f9bc4-274">443</span><span class="sxs-lookup"><span data-stu-id="f9bc4-274">443</span></span>  <br/> |<span data-ttu-id="f9bc4-275">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="f9bc4-276">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="f9bc4-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="f9bc4-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9bc4-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="f9bc4-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="f9bc4-278">_tcp</span></span>  <br/> |<span data-ttu-id="f9bc4-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f9bc4-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="f9bc4-280">100</span><span class="sxs-lookup"><span data-stu-id="f9bc4-280">100</span></span>  <br/> |<span data-ttu-id="f9bc4-281">1</span><span class="sxs-lookup"><span data-stu-id="f9bc4-281">1</span></span>  <br/> |<span data-ttu-id="f9bc4-282">5061</span><span class="sxs-lookup"><span data-stu-id="f9bc4-282">5061</span></span>  <br/> |<span data-ttu-id="f9bc4-283">1 timme</span><span class="sxs-lookup"><span data-stu-id="f9bc4-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Konfigurera-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="f9bc4-285">Upprepa **steg 5** för att skapa den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="f9bc4-286">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f9bc4-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="f9bc4-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9bc4-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
