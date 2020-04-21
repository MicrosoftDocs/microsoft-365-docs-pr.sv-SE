---
title: Skapa DNS-poster på name.com för Microsoft
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på name.com för Microsoft.
ms.openlocfilehash: 8b23ab4d324b5e6d023f10f8f1d11d95d3c579ba
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629353"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="a47e1-103">Skapa DNS-poster på name.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a47e1-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="a47e1-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="a47e1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a47e1-105">Om name.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="a47e1-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a47e1-106">När du har lagt till dessa poster i name.com konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="a47e1-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="a47e1-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="a47e1-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a47e1-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a47e1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a47e1-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="a47e1-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a47e1-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a47e1-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a47e1-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="a47e1-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="a47e1-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="a47e1-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a47e1-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="a47e1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a47e1-p104">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a47e1-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a47e1-120">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="a47e1-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a47e1-122">Välj \*\* DNS Records \*\*i kolumnen **Detaljer.**</span><span class="sxs-lookup"><span data-stu-id="a47e1-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a47e1-124">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a47e1-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a47e1-125">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="a47e1-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a47e1-126">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a47e1-126">**Type**</span></span> <br/> |<span data-ttu-id="a47e1-127">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-127">**Host**</span></span> <br/> |<span data-ttu-id="a47e1-128">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-128">**Answer**</span></span> <br/> |<span data-ttu-id="a47e1-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a47e1-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="a47e1-130">TXT</span><span class="sxs-lookup"><span data-stu-id="a47e1-130">TXT</span></span>  <br/> |<span data-ttu-id="a47e1-131">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="a47e1-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a47e1-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a47e1-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a47e1-133">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="a47e1-133">**Note:** This is an example.</span></span> <span data-ttu-id="a47e1-134">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="a47e1-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a47e1-135">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="a47e1-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a47e1-136">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-136">Use the default value (300).</span></span>  <br/> |
   
    ![Namn-BP-Verifiera-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="a47e1-138">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="a47e1-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="a47e1-140">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="a47e1-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a47e1-141">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="a47e1-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a47e1-142">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="a47e1-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a47e1-143">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="a47e1-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a47e1-144">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="a47e1-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a47e1-145">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="a47e1-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a47e1-146">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="a47e1-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="a47e1-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a47e1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a47e1-150">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="a47e1-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a47e1-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a47e1-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a47e1-p107">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a47e1-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a47e1-155">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="a47e1-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a47e1-157">Välj **DNS Records**i kolumnen **Detaljer** .</span><span class="sxs-lookup"><span data-stu-id="a47e1-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a47e1-159">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a47e1-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a47e1-160">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="a47e1-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a47e1-161">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a47e1-161">**Type**</span></span>|<span data-ttu-id="a47e1-162">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-162">**Host**</span></span>|<span data-ttu-id="a47e1-163">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-163">**Answer**</span></span>|<span data-ttu-id="a47e1-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a47e1-164">**TTL**</span></span>|<span data-ttu-id="a47e1-165">**Prio**</span><span class="sxs-lookup"><span data-stu-id="a47e1-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a47e1-166">MX</span><span class="sxs-lookup"><span data-stu-id="a47e1-166">MX</span></span>  <br/> |<span data-ttu-id="a47e1-167">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="a47e1-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="a47e1-168">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a47e1-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a47e1-169">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="a47e1-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="a47e1-170">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="a47e1-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a47e1-171">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="a47e1-172">0</span><span class="sxs-lookup"><span data-stu-id="a47e1-172">0</span></span>  <br/> <span data-ttu-id="a47e1-173">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a47e1-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Namn-BP-Konfigurera-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="a47e1-175">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="a47e1-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="a47e1-177">Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:</span><span class="sxs-lookup"><span data-stu-id="a47e1-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="a47e1-178">För varandra MX-post väljer du **Ta bort** i kolumnen **Åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="a47e1-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="a47e1-180">Om du vill bekräfta varje borttagning väljer du **Ta bort** i kolumnen **Åtgärder** igen.</span><span class="sxs-lookup"><span data-stu-id="a47e1-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="a47e1-182">Upprepa den här tvåstegsproceduren tills du har tagit bort alla de andra MX-posterna.</span><span class="sxs-lookup"><span data-stu-id="a47e1-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a47e1-183">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a47e1-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a47e1-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a47e1-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a47e1-p109">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a47e1-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a47e1-188">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="a47e1-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a47e1-190">Välj **DNS Records**i kolumnen **Detaljer** .</span><span class="sxs-lookup"><span data-stu-id="a47e1-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a47e1-192">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="a47e1-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="a47e1-193">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a47e1-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="a47e1-194">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="a47e1-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a47e1-195">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a47e1-195">**Type**</span></span>|<span data-ttu-id="a47e1-196">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-196">**Host**</span></span>|<span data-ttu-id="a47e1-197">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-197">**Answer**</span></span>|<span data-ttu-id="a47e1-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a47e1-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a47e1-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="a47e1-199">CNAME</span></span>  <br/> |<span data-ttu-id="a47e1-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a47e1-200">autodiscover</span></span>  <br/> |<span data-ttu-id="a47e1-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a47e1-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="a47e1-202">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="a47e1-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="a47e1-203">CNAME</span></span>  <br/> |<span data-ttu-id="a47e1-204">sip</span><span class="sxs-lookup"><span data-stu-id="a47e1-204">sip</span></span>  <br/> |<span data-ttu-id="a47e1-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a47e1-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a47e1-206">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="a47e1-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="a47e1-207">CNAME</span></span>  <br/> |<span data-ttu-id="a47e1-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a47e1-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a47e1-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a47e1-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a47e1-210">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="a47e1-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="a47e1-211">CNAME</span></span>  <br/> |<span data-ttu-id="a47e1-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a47e1-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a47e1-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a47e1-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="a47e1-214">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="a47e1-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="a47e1-215">CNAME</span></span>  <br/> |<span data-ttu-id="a47e1-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a47e1-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a47e1-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a47e1-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="a47e1-218">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-218">Use the default value (300).</span></span>  <br/> |
   
   ![Namn-BP-Konfigurera-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="a47e1-220">Välj **Lägg till post om** du vill lägga till den första posten.</span><span class="sxs-lookup"><span data-stu-id="a47e1-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="a47e1-222">Lägg till den andra CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="a47e1-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="a47e1-223">Använd värdena från den andra raden i tabellen ovan och välj sedan **Lägg till post** för att lägga till den andra posten.</span><span class="sxs-lookup"><span data-stu-id="a47e1-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="a47e1-224">Lägg till de återstående posterna på samma sätt med värdena från den tredje, fjärde, femte och sjätte raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="a47e1-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a47e1-225">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="a47e1-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a47e1-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a47e1-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a47e1-227">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="a47e1-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a47e1-228">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="a47e1-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a47e1-229">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a47e1-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a47e1-230">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="a47e1-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a47e1-p111">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a47e1-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a47e1-234">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="a47e1-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a47e1-236">Välj **DNS Records**i kolumnen **Detaljer** .</span><span class="sxs-lookup"><span data-stu-id="a47e1-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a47e1-238">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a47e1-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a47e1-239">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="a47e1-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a47e1-240">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a47e1-240">**Type**</span></span>|<span data-ttu-id="a47e1-241">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-241">**Host**</span></span>|<span data-ttu-id="a47e1-242">**Answer (svar)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-242">**Answer**</span></span>|<span data-ttu-id="a47e1-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a47e1-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a47e1-244">TXT</span><span class="sxs-lookup"><span data-stu-id="a47e1-244">TXT</span></span>  <br/> |<span data-ttu-id="a47e1-245">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="a47e1-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a47e1-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a47e1-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a47e1-247">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="a47e1-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="a47e1-248">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-248">Use the default value (300).</span></span>  <br/> |
   
   ![Namn-BP-Konfigurera-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="a47e1-250">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="a47e1-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a47e1-252">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a47e1-252">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a47e1-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a47e1-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a47e1-p112">Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a47e1-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a47e1-257">Under **Mina domäner**väljer du namnet på den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="a47e1-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a47e1-259">Välj **DNS Records+ i**kolumnen **Detaljer.**</span><span class="sxs-lookup"><span data-stu-id="a47e1-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a47e1-261">Lägg till den första SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="a47e1-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="a47e1-262">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a47e1-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="a47e1-263">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="a47e1-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a47e1-264">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-264">**Type**</span></span>|<span data-ttu-id="a47e1-265">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-265">**Service**</span></span>|<span data-ttu-id="a47e1-266">**Weight (vikt)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-266">**Weight**</span></span>|<span data-ttu-id="a47e1-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a47e1-267">**TTL**</span></span>|<span data-ttu-id="a47e1-268">**Prio**</span><span class="sxs-lookup"><span data-stu-id="a47e1-268">**Prio**</span></span>|<span data-ttu-id="a47e1-269">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-269">**Protocol**</span></span>|<span data-ttu-id="a47e1-270">**Port**</span><span class="sxs-lookup"><span data-stu-id="a47e1-270">**Port**</span></span>|<span data-ttu-id="a47e1-271">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="a47e1-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a47e1-272">SRV</span><span class="sxs-lookup"><span data-stu-id="a47e1-272">SRV</span></span>|<span data-ttu-id="a47e1-273">sip</span><span class="sxs-lookup"><span data-stu-id="a47e1-273">sip</span></span>|<span data-ttu-id="a47e1-274">1</span><span class="sxs-lookup"><span data-stu-id="a47e1-274">1</span></span>|<span data-ttu-id="a47e1-275">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-275">Use the default value (300).</span></span>|<span data-ttu-id="a47e1-276">100</span><span class="sxs-lookup"><span data-stu-id="a47e1-276">100</span></span>|<span data-ttu-id="a47e1-277">tls</span><span class="sxs-lookup"><span data-stu-id="a47e1-277">tls</span></span>|<span data-ttu-id="a47e1-278">443</span><span class="sxs-lookup"><span data-stu-id="a47e1-278">443</span></span>|<span data-ttu-id="a47e1-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a47e1-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="a47e1-280">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="a47e1-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="a47e1-281">SRV</span><span class="sxs-lookup"><span data-stu-id="a47e1-281">SRV</span></span>|<span data-ttu-id="a47e1-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a47e1-282">sipfederationtls</span></span>|<span data-ttu-id="a47e1-283">1</span><span class="sxs-lookup"><span data-stu-id="a47e1-283">1</span></span>|<span data-ttu-id="a47e1-284">Använd standardvärdet (300).</span><span class="sxs-lookup"><span data-stu-id="a47e1-284">Use the default value (300).</span></span>|<span data-ttu-id="a47e1-285">100</span><span class="sxs-lookup"><span data-stu-id="a47e1-285">100</span></span>|<span data-ttu-id="a47e1-286">tcp</span><span class="sxs-lookup"><span data-stu-id="a47e1-286">tcp</span></span>|<span data-ttu-id="a47e1-287">5061</span><span class="sxs-lookup"><span data-stu-id="a47e1-287">5061</span></span>|<span data-ttu-id="a47e1-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a47e1-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="a47e1-289">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="a47e1-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Namn-BP-Konfigurera-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="a47e1-291">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="a47e1-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="a47e1-293">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="a47e1-293">Add the second SRV record:</span></span>

<span data-ttu-id="a47e1-294">Använd värdena från nästa rad i tabellen ovan och välj sedan **Lägg till post** för att lägga till den andra posten.</span><span class="sxs-lookup"><span data-stu-id="a47e1-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="a47e1-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a47e1-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
