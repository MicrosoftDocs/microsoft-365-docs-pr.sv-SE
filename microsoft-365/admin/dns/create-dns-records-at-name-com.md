---
title: Skapa DNS-poster på name.com för Office 365
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på name.com för Office 365.
ms.openlocfilehash: f39cf9f241851e555ea23ca7b63453796a5f471b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211661"
---
# <a name="create-dns-records-at-namecom-for-office-365"></a><span data-ttu-id="79f0c-103">Skapa DNS-poster på name.com för Office 365</span><span class="sxs-lookup"><span data-stu-id="79f0c-103">Create DNS records at name.com for Office 365</span></span>

 <span data-ttu-id="79f0c-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="79f0c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="79f0c-105">Om name.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="79f0c-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="79f0c-106">När du har lagt till dessa poster på name.com är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="79f0c-106">After you add these records at name.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="79f0c-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="79f0c-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="79f0c-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="79f0c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="79f0c-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="79f0c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="79f0c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="79f0c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="79f0c-p102">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79f0c-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="79f0c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="79f0c-p104">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="79f0c-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="79f0c-120">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="79f0c-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="79f0c-122">Välj \*\* DNS Records \*\*i kolumnen **Detaljer.**</span><span class="sxs-lookup"><span data-stu-id="79f0c-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="79f0c-124">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="79f0c-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="79f0c-125">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="79f0c-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79f0c-126">**Typ**</span><span class="sxs-lookup"><span data-stu-id="79f0c-126">**Type**</span></span> <br/> |<span data-ttu-id="79f0c-127">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-127">**Host**</span></span> <br/> |<span data-ttu-id="79f0c-128">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-128">**Answer**</span></span> <br/> |<span data-ttu-id="79f0c-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79f0c-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="79f0c-130">TXT</span><span class="sxs-lookup"><span data-stu-id="79f0c-130">TXT</span></span>  <br/> |<span data-ttu-id="79f0c-131">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="79f0c-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="79f0c-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="79f0c-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="79f0c-p105">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="79f0c-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="79f0c-136">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-136">Use the default value (300).</span></span>  <br/> |
   
    ![Namn-BP-Verifiera-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="79f0c-138">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="79f0c-140">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="79f0c-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="79f0c-141">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="79f0c-142">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="79f0c-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="79f0c-143">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="79f0c-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="79f0c-144">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="79f0c-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="79f0c-145">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="79f0c-146">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="79f0c-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="79f0c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="79f0c-150">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="79f0c-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="79f0c-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="79f0c-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="79f0c-p107">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="79f0c-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="79f0c-155">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="79f0c-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="79f0c-157">Välj **DNS Records**i kolumnen **Detaljer** .</span><span class="sxs-lookup"><span data-stu-id="79f0c-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="79f0c-159">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="79f0c-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="79f0c-160">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="79f0c-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="79f0c-161">**Typ**</span><span class="sxs-lookup"><span data-stu-id="79f0c-161">**Type**</span></span>|<span data-ttu-id="79f0c-162">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-162">**Host**</span></span>|<span data-ttu-id="79f0c-163">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-163">**Answer**</span></span>|<span data-ttu-id="79f0c-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79f0c-164">**TTL**</span></span>|<span data-ttu-id="79f0c-165">**Prio**</span><span class="sxs-lookup"><span data-stu-id="79f0c-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79f0c-166">MX</span><span class="sxs-lookup"><span data-stu-id="79f0c-166">MX</span></span>  <br/> |<span data-ttu-id="79f0c-167">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="79f0c-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="79f0c-168">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="79f0c-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="79f0c-169">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="79f0c-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="79f0c-170">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="79f0c-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="79f0c-171">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="79f0c-172">0</span><span class="sxs-lookup"><span data-stu-id="79f0c-172">0</span></span>  <br/> <span data-ttu-id="79f0c-173">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="79f0c-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Namn-BP-Konfigurera-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="79f0c-175">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="79f0c-177">Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:</span><span class="sxs-lookup"><span data-stu-id="79f0c-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="79f0c-178">För varandra MX-post väljer du **Ta bort** i kolumnen **Åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="79f0c-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="79f0c-180">Om du vill bekräfta varje borttagning väljer du **Ta bort** i kolumnen **Åtgärder** igen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="79f0c-182">Upprepa den här tvåstegsproceduren tills du har tagit bort alla de andra MX-posterna.</span><span class="sxs-lookup"><span data-stu-id="79f0c-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="79f0c-183">Lägga till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="79f0c-183">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="79f0c-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="79f0c-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="79f0c-p109">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="79f0c-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="79f0c-188">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="79f0c-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="79f0c-190">Välj **DNS Records**i kolumnen **Detaljer** .</span><span class="sxs-lookup"><span data-stu-id="79f0c-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="79f0c-192">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="79f0c-193">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="79f0c-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="79f0c-194">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="79f0c-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="79f0c-195">**Typ**</span><span class="sxs-lookup"><span data-stu-id="79f0c-195">**Type**</span></span>|<span data-ttu-id="79f0c-196">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-196">**Host**</span></span>|<span data-ttu-id="79f0c-197">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-197">**Answer**</span></span>|<span data-ttu-id="79f0c-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79f0c-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79f0c-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="79f0c-199">CNAME</span></span>  <br/> |<span data-ttu-id="79f0c-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="79f0c-200">autodiscover</span></span>  <br/> |<span data-ttu-id="79f0c-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="79f0c-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="79f0c-202">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="79f0c-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="79f0c-203">CNAME</span></span>  <br/> |<span data-ttu-id="79f0c-204">sip</span><span class="sxs-lookup"><span data-stu-id="79f0c-204">sip</span></span>  <br/> |<span data-ttu-id="79f0c-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79f0c-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="79f0c-206">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="79f0c-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="79f0c-207">CNAME</span></span>  <br/> |<span data-ttu-id="79f0c-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="79f0c-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="79f0c-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79f0c-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="79f0c-210">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="79f0c-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="79f0c-211">CNAME</span></span>  <br/> |<span data-ttu-id="79f0c-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="79f0c-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="79f0c-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="79f0c-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="79f0c-214">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="79f0c-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="79f0c-215">CNAME</span></span>  <br/> |<span data-ttu-id="79f0c-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="79f0c-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="79f0c-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="79f0c-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="79f0c-218">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-218">Use the default value (300).</span></span>  <br/> |
   
   ![Namn-BP-Konfigurera-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="79f0c-220">Välj **Lägg till post om** du vill lägga till den första posten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="79f0c-222">Lägg till den andra CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="79f0c-223">Använd värdena från den andra raden i tabellen ovan och välj sedan **Lägg till post** för att lägga till den andra posten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="79f0c-224">Lägg till de återstående posterna på samma sätt med värdena från den tredje, fjärde, femte och sjätte raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="79f0c-225">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="79f0c-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="79f0c-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="79f0c-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="79f0c-227">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="79f0c-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="79f0c-228">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="79f0c-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="79f0c-229">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="79f0c-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="79f0c-230">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="79f0c-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="79f0c-p111">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="79f0c-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="79f0c-234">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="79f0c-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="79f0c-236">Välj **DNS Records**i kolumnen **Detaljer** .</span><span class="sxs-lookup"><span data-stu-id="79f0c-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="79f0c-238">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="79f0c-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="79f0c-239">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="79f0c-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="79f0c-240">**Typ**</span><span class="sxs-lookup"><span data-stu-id="79f0c-240">**Type**</span></span>|<span data-ttu-id="79f0c-241">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-241">**Host**</span></span>|<span data-ttu-id="79f0c-242">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-242">**Answer**</span></span>|<span data-ttu-id="79f0c-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79f0c-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79f0c-244">TXT</span><span class="sxs-lookup"><span data-stu-id="79f0c-244">TXT</span></span>  <br/> |<span data-ttu-id="79f0c-245">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="79f0c-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="79f0c-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="79f0c-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="79f0c-247">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="79f0c-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="79f0c-248">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-248">Use the default value (300).</span></span>  <br/> |
   
   ![Namn-BP-Konfigurera-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="79f0c-250">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="79f0c-252">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="79f0c-252">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="79f0c-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="79f0c-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="79f0c-p112">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="79f0c-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="79f0c-257">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="79f0c-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="79f0c-259">Välj **DNS Records+ i**kolumnen **Detaljer.**</span><span class="sxs-lookup"><span data-stu-id="79f0c-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="79f0c-261">Lägg till den första SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="79f0c-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="79f0c-262">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="79f0c-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="79f0c-263">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="79f0c-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="79f0c-264">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-264">**Type**</span></span>|<span data-ttu-id="79f0c-265">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-265">**Service**</span></span>|<span data-ttu-id="79f0c-266">**Weight (vikt)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-266">**Weight**</span></span>|<span data-ttu-id="79f0c-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79f0c-267">**TTL**</span></span>|<span data-ttu-id="79f0c-268">**Prio**</span><span class="sxs-lookup"><span data-stu-id="79f0c-268">**Prio**</span></span>|<span data-ttu-id="79f0c-269">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-269">**Protocol**</span></span>|<span data-ttu-id="79f0c-270">**Port**</span><span class="sxs-lookup"><span data-stu-id="79f0c-270">**Port**</span></span>|<span data-ttu-id="79f0c-271">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="79f0c-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79f0c-272">SRV</span><span class="sxs-lookup"><span data-stu-id="79f0c-272">SRV</span></span>|<span data-ttu-id="79f0c-273">sip</span><span class="sxs-lookup"><span data-stu-id="79f0c-273">sip</span></span>|<span data-ttu-id="79f0c-274">1</span><span class="sxs-lookup"><span data-stu-id="79f0c-274">1</span></span>|<span data-ttu-id="79f0c-275">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-275">Use the default value (300).</span></span>|<span data-ttu-id="79f0c-276">100</span><span class="sxs-lookup"><span data-stu-id="79f0c-276">100</span></span>|<span data-ttu-id="79f0c-277">tls</span><span class="sxs-lookup"><span data-stu-id="79f0c-277">tls</span></span>|<span data-ttu-id="79f0c-278">443</span><span class="sxs-lookup"><span data-stu-id="79f0c-278">443</span></span>|<span data-ttu-id="79f0c-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79f0c-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="79f0c-280">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="79f0c-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="79f0c-281">SRV</span><span class="sxs-lookup"><span data-stu-id="79f0c-281">SRV</span></span>|<span data-ttu-id="79f0c-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="79f0c-282">sipfederationtls</span></span>|<span data-ttu-id="79f0c-283">1</span><span class="sxs-lookup"><span data-stu-id="79f0c-283">1</span></span>|<span data-ttu-id="79f0c-284">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="79f0c-284">Use the default value (300).</span></span>|<span data-ttu-id="79f0c-285">100</span><span class="sxs-lookup"><span data-stu-id="79f0c-285">100</span></span>|<span data-ttu-id="79f0c-286">tcp</span><span class="sxs-lookup"><span data-stu-id="79f0c-286">tcp</span></span>|<span data-ttu-id="79f0c-287">5061</span><span class="sxs-lookup"><span data-stu-id="79f0c-287">5061</span></span>|<span data-ttu-id="79f0c-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79f0c-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="79f0c-289">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="79f0c-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Namn-BP-Konfigurera-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="79f0c-291">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="79f0c-293">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-293">Add the second SRV record:</span></span>

<span data-ttu-id="79f0c-294">Använd värdena från nästa rad i tabellen ovan och välj sedan **Lägg till post** för att lägga till den andra posten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="79f0c-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="79f0c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
