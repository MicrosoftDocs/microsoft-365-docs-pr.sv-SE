---
title: Skapa DNS-poster på GoDaddy för Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på GoDaddy för Office 365.
ms.custom: okr_smb
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42813003"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="cce49-103">Skapa DNS-poster på GoDaddy för Office 365</span><span class="sxs-lookup"><span data-stu-id="cce49-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="cce49-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="cce49-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="cce49-105">Om GoDaddy är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="cce49-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="cce49-106">När du har lagt till dessa poster på GoDaddy är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="cce49-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="cce49-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="cce49-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="cce49-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cce49-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cce49-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="cce49-111">Add a TXT record for verification</span></span>
<span data-ttu-id="cce49-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cce49-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cce49-p102">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="cce49-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="cce49-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="cce49-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="cce49-117">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="cce49-117">Follow the steps below.</span></span>

1. <span data-ttu-id="cce49-p104">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="cce49-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cce49-121">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="cce49-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cce49-123">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="cce49-123">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="cce49-125">Välj **TXT (Text)** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="cce49-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="cce49-126">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="cce49-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="cce49-127">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cce49-127">**Record type**</span></span> |<span data-ttu-id="cce49-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="cce49-128">**Host**</span></span>|<span data-ttu-id="cce49-129">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="cce49-129">**TXT Value**</span></span>|<span data-ttu-id="cce49-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cce49-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cce49-131">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="cce49-131">TXT (Text)</span></span>|@|<span data-ttu-id="cce49-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cce49-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="cce49-133">**Obs:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="cce49-133">**Note**: This is an example.</span></span> <span data-ttu-id="cce49-134">Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="cce49-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="cce49-135">Hur hittar jag detta?</span><span class="sxs-lookup"><span data-stu-id="cce49-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="cce49-136">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-136">1 hour</span></span>  <br><span data-ttu-id="cce49-137">(Välj ett värde i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="cce49-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verifiera-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="cce49-139">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cce49-139">Select **Save**.</span></span>

6. <span data-ttu-id="cce49-140">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="cce49-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="cce49-141">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="cce49-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="cce49-142">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="cce49-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cce49-143">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="cce49-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cce49-144">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="cce49-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cce49-145">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="cce49-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="cce49-146">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="cce49-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="cce49-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cce49-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cce49-150">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="cce49-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cce49-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cce49-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cce49-152">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="cce49-152">Follow the steps below.</span></span>

1. <span data-ttu-id="cce49-p108">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="cce49-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cce49-156">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="cce49-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cce49-158">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="cce49-158">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="cce49-160">Välj **MX (Mail Exchanger)** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="cce49-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Konfigurera-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="cce49-162">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="cce49-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="cce49-163">(Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="cce49-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="cce49-164">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cce49-164">**Record type**</span></span>|<span data-ttu-id="cce49-165">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="cce49-165">**Host**</span></span>|<span data-ttu-id="cce49-166">**Points to (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="cce49-166">**Points to**</span></span>|<span data-ttu-id="cce49-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="cce49-167">**Priority**</span></span>|<span data-ttu-id="cce49-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cce49-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cce49-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="cce49-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="cce49-170">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cce49-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cce49-171">**Obs:** Hämta din \* \<domännyckel\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="cce49-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="cce49-172">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="cce49-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cce49-173">10</span><span class="sxs-lookup"><span data-stu-id="cce49-173">10</span></span>  <br/> <span data-ttu-id="cce49-174">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="cce49-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="cce49-175">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="cce49-176">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cce49-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cce49-177">Lägg till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="cce49-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="cce49-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cce49-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cce49-179">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="cce49-179">Follow the steps below.</span></span>

1. <span data-ttu-id="cce49-p110">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="cce49-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cce49-183">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="cce49-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cce49-185">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="cce49-185">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="cce49-187">Välj **CNAME (Alias)** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="cce49-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Konfigurera-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="cce49-189">Skapa den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="cce49-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="cce49-190">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="cce49-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="cce49-191">(Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="cce49-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="cce49-192">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cce49-192">**Record type**</span></span>|<span data-ttu-id="cce49-193">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="cce49-193">**Host**</span></span>|<span data-ttu-id="cce49-194">**Points to (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="cce49-194">**Points to**</span></span>|<span data-ttu-id="cce49-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cce49-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cce49-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cce49-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cce49-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cce49-197">autodiscover</span></span>  <br/> |<span data-ttu-id="cce49-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cce49-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="cce49-199">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cce49-200">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cce49-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cce49-201">sip</span><span class="sxs-lookup"><span data-stu-id="cce49-201">sip</span></span>  <br/> |<span data-ttu-id="cce49-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cce49-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cce49-203">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cce49-204">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cce49-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cce49-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cce49-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cce49-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cce49-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cce49-207">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cce49-208">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cce49-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cce49-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cce49-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cce49-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cce49-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="cce49-211">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cce49-212">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cce49-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cce49-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cce49-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cce49-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cce49-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="cce49-215">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="cce49-216">Upprepa dessa steg om du vill lägga till nästa CNAME-post tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="cce49-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cce49-217">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="cce49-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cce49-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cce49-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cce49-219">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="cce49-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cce49-220">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="cce49-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cce49-221">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cce49-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cce49-222">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="cce49-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="cce49-223">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="cce49-223">Follow the steps below.</span></span>

1. <span data-ttu-id="cce49-p112">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="cce49-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cce49-227">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="cce49-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cce49-229">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="cce49-229">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="cce49-231">Välj **TXT (Text)** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="cce49-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Konfigurera-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="cce49-233">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="cce49-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="cce49-234">(Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="cce49-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="cce49-235">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cce49-235">**Record type**</span></span>|<span data-ttu-id="cce49-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="cce49-236">**Host**</span></span>|<span data-ttu-id="cce49-237">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="cce49-237">**TXT Value**</span></span>|<span data-ttu-id="cce49-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cce49-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cce49-239">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="cce49-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="cce49-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cce49-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cce49-241">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="cce49-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="cce49-242">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Konfigurera-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="cce49-244">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cce49-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cce49-245">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="cce49-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cce49-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cce49-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="cce49-247">Följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="cce49-247">Follow the steps below.</span></span>

1. <span data-ttu-id="cce49-p113">Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="cce49-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cce49-251">Under **Domäner**väljer du DNS under den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="cce49-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cce49-253">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="cce49-253">Select **Add**.</span></span>

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="cce49-255">Välj **SRV (Service)** (SRV (tjänst)) i listrutan.</span><span class="sxs-lookup"><span data-stu-id="cce49-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Konfigurera-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="cce49-257">Skapa den första SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="cce49-257">Create the first SRV record.</span></span>

    <span data-ttu-id="cce49-258">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="cce49-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="cce49-259">(Välj **posttyp** och **TTL-värden** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="cce49-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="cce49-260">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cce49-260">**Record type**</span></span>|<span data-ttu-id="cce49-261">**Namn**</span><span class="sxs-lookup"><span data-stu-id="cce49-261">**Name**</span></span>|<span data-ttu-id="cce49-262">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="cce49-262">**Target**</span></span>|<span data-ttu-id="cce49-263">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="cce49-263">**Protocol**</span></span>|<span data-ttu-id="cce49-264">**Tjänst**</span><span class="sxs-lookup"><span data-stu-id="cce49-264">**Service**</span></span>|<span data-ttu-id="cce49-265">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="cce49-265">**Priority**</span></span>|<span data-ttu-id="cce49-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="cce49-266">**Weight**</span></span>|<span data-ttu-id="cce49-267">**Port**</span><span class="sxs-lookup"><span data-stu-id="cce49-267">**Port**</span></span>|<span data-ttu-id="cce49-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cce49-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cce49-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="cce49-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="cce49-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cce49-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cce49-271">_tls</span><span class="sxs-lookup"><span data-stu-id="cce49-271">_tls</span></span>  <br/> |<span data-ttu-id="cce49-272">_sip</span><span class="sxs-lookup"><span data-stu-id="cce49-272">_sip</span></span>  <br/> |<span data-ttu-id="cce49-273">100</span><span class="sxs-lookup"><span data-stu-id="cce49-273">100</span></span>  <br/> |<span data-ttu-id="cce49-274">1</span><span class="sxs-lookup"><span data-stu-id="cce49-274">1</span></span>  <br/> |<span data-ttu-id="cce49-275">443</span><span class="sxs-lookup"><span data-stu-id="cce49-275">443</span></span>  <br/> |<span data-ttu-id="cce49-276">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cce49-277">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="cce49-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="cce49-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cce49-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="cce49-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="cce49-279">_tcp</span></span>  <br/> |<span data-ttu-id="cce49-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cce49-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="cce49-281">100</span><span class="sxs-lookup"><span data-stu-id="cce49-281">100</span></span>  <br/> |<span data-ttu-id="cce49-282">1</span><span class="sxs-lookup"><span data-stu-id="cce49-282">1</span></span>  <br/> |<span data-ttu-id="cce49-283">5061</span><span class="sxs-lookup"><span data-stu-id="cce49-283">5061</span></span>  <br/> |<span data-ttu-id="cce49-284">1 timme</span><span class="sxs-lookup"><span data-stu-id="cce49-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Konfigurera-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="cce49-286">Upprepa **steg 5** för att skapa den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="cce49-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="cce49-287">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cce49-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="cce49-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cce49-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
