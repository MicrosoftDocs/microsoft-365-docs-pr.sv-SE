---
title: Skapa DNS-poster på Dyn.com för Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Dyn.com för Microsoft.
ms.openlocfilehash: 9d419cc26688cdbda792c0aaaa116ee01534247a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049125"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="1988c-103">Skapa DNS-poster på Dyn.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="1988c-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="1988c-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="1988c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1988c-105">Om Dyn.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="1988c-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="1988c-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1988c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1988c-109">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="1988c-109">Add a TXT record for verification</span></span>
<span data-ttu-id="1988c-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1988c-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="1988c-p102">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1988c-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1988c-114">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="1988c-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1988c-115">Välj **Inställningar**på **DNS-sidan** för domänen .</span><span class="sxs-lookup"><span data-stu-id="1988c-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1988c-116">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="1988c-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1988c-117">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1988c-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1988c-118">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="1988c-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1988c-119">**Host**</span><span class="sxs-lookup"><span data-stu-id="1988c-119">**Host**</span></span>|<span data-ttu-id="1988c-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1988c-120">**TTL**</span></span>|<span data-ttu-id="1988c-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="1988c-121">**Type**</span></span>|<span data-ttu-id="1988c-122">**Data**</span><span class="sxs-lookup"><span data-stu-id="1988c-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1988c-123">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="1988c-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1988c-124">600</span><span class="sxs-lookup"><span data-stu-id="1988c-124">600</span></span>  <br/> |<span data-ttu-id="1988c-125">TXT</span><span class="sxs-lookup"><span data-stu-id="1988c-125">TXT</span></span>  <br/> |<span data-ttu-id="1988c-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1988c-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1988c-127">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="1988c-127">**Note:** This is an example.</span></span> <span data-ttu-id="1988c-128">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="1988c-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1988c-129">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="1988c-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verifiera-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="1988c-131">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="1988c-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="1988c-133">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="1988c-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1988c-134">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="1988c-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1988c-135">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="1988c-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1988c-136">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="1988c-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1988c-137">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="1988c-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1988c-138">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="1988c-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1988c-139">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="1988c-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1988c-p104">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1988c-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1988c-143">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1988c-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1988c-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1988c-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1988c-p105">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1988c-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1988c-148">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="1988c-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1988c-149">Välj **Inställningar**på DNS-sidan för domänen .</span><span class="sxs-lookup"><span data-stu-id="1988c-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1988c-150">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="1988c-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1988c-151">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1988c-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1988c-152">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="1988c-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1988c-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="1988c-153">**Host**</span></span>|<span data-ttu-id="1988c-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1988c-154">**TTL**</span></span>|<span data-ttu-id="1988c-155">**Type**</span><span class="sxs-lookup"><span data-stu-id="1988c-155">**Type**</span></span>|<span data-ttu-id="1988c-156">**Data**</span><span class="sxs-lookup"><span data-stu-id="1988c-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1988c-157">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="1988c-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1988c-158">600</span><span class="sxs-lookup"><span data-stu-id="1988c-158">600</span></span>  <br/> |<span data-ttu-id="1988c-159">MX</span><span class="sxs-lookup"><span data-stu-id="1988c-159">MX</span></span>  <br/> |<span data-ttu-id="1988c-160">10  *\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1988c-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1988c-161">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="1988c-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1988c-p106">**10** motsvarar MX-prioritetsvärdet. Skriv 10 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="1988c-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="1988c-164">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="1988c-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="1988c-165">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="1988c-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="1988c-166">[Mer information om prioritet finns i ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="1988c-166">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Dyn-BP-Konfigurera-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="1988c-168">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="1988c-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP - Konfigurera-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="1988c-170">Om det finns andra MX-poster tar du bort dem genom att markera kryssrutan för varje post i kolumnen **Delete**.</span><span class="sxs-lookup"><span data-stu-id="1988c-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP - Konfigurera-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="1988c-172">Välj **Använd ändringar**.</span><span class="sxs-lookup"><span data-stu-id="1988c-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP - Konfigurera-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1988c-174">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="1988c-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1988c-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1988c-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1988c-p108">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1988c-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1988c-179">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="1988c-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1988c-180">Välj **Inställningar**på **DNS-sidan** för domänen .</span><span class="sxs-lookup"><span data-stu-id="1988c-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1988c-181">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="1988c-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1988c-182">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="1988c-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="1988c-183">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="1988c-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="1988c-184">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="1988c-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1988c-185">**Host**</span><span class="sxs-lookup"><span data-stu-id="1988c-185">**Host**</span></span>|<span data-ttu-id="1988c-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1988c-186">**TTL**</span></span>|<span data-ttu-id="1988c-187">**Type**</span><span class="sxs-lookup"><span data-stu-id="1988c-187">**Type**</span></span>|<span data-ttu-id="1988c-188">**Data**</span><span class="sxs-lookup"><span data-stu-id="1988c-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1988c-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1988c-189">autodiscover</span></span>  <br/> |<span data-ttu-id="1988c-190">600</span><span class="sxs-lookup"><span data-stu-id="1988c-190">600</span></span>  <br/> |<span data-ttu-id="1988c-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="1988c-191">CNAME</span></span>  <br/> |<span data-ttu-id="1988c-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1988c-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1988c-193">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="1988c-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1988c-194">sip</span><span class="sxs-lookup"><span data-stu-id="1988c-194">sip</span></span>  <br/> |<span data-ttu-id="1988c-195">600</span><span class="sxs-lookup"><span data-stu-id="1988c-195">600</span></span>  <br/> |<span data-ttu-id="1988c-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="1988c-196">CNAME</span></span>  <br/> |<span data-ttu-id="1988c-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1988c-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1988c-198">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="1988c-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1988c-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1988c-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1988c-200">600</span><span class="sxs-lookup"><span data-stu-id="1988c-200">600</span></span>  <br/> |<span data-ttu-id="1988c-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="1988c-201">CNAME</span></span>  <br/> |<span data-ttu-id="1988c-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1988c-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1988c-203">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="1988c-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1988c-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1988c-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1988c-205">600</span><span class="sxs-lookup"><span data-stu-id="1988c-205">600</span></span>  <br/> |<span data-ttu-id="1988c-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="1988c-206">CNAME</span></span>  <br/> |<span data-ttu-id="1988c-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1988c-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1988c-208">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="1988c-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1988c-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1988c-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1988c-210">600</span><span class="sxs-lookup"><span data-stu-id="1988c-210">600</span></span>  <br/> |<span data-ttu-id="1988c-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="1988c-211">CNAME</span></span>  <br/> |<span data-ttu-id="1988c-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1988c-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1988c-213">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="1988c-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-Konfigurera-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="1988c-215">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="1988c-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP - Konfigurera-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="1988c-217">Lägg till de återstående fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="1988c-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="1988c-218">Skapa en post i avsnittet **Lägg till DNS-post** med hjälp av värdena från nästa rad i tabellen och välj sedan **skapa post** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="1988c-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="1988c-219">Upprepa proceduren tills du har skapat alla sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="1988c-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1988c-220">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="1988c-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1988c-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1988c-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1988c-222">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="1988c-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1988c-223">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="1988c-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1988c-224">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1988c-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1988c-225">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="1988c-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="1988c-p110">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1988c-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1988c-229">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="1988c-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1988c-230">Välj **Inställningar**på **DNS-sidan** för domänen .</span><span class="sxs-lookup"><span data-stu-id="1988c-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1988c-231">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="1988c-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1988c-232">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1988c-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1988c-233">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="1988c-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1988c-234">**Host**</span><span class="sxs-lookup"><span data-stu-id="1988c-234">**Host**</span></span>|<span data-ttu-id="1988c-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1988c-235">**TTL**</span></span>|<span data-ttu-id="1988c-236">**Type**</span><span class="sxs-lookup"><span data-stu-id="1988c-236">**Type**</span></span>|<span data-ttu-id="1988c-237">**Data**</span><span class="sxs-lookup"><span data-stu-id="1988c-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1988c-238">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="1988c-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1988c-239">600</span><span class="sxs-lookup"><span data-stu-id="1988c-239">600</span></span>  <br/> |<span data-ttu-id="1988c-240">TXT</span><span class="sxs-lookup"><span data-stu-id="1988c-240">TXT</span></span>  <br/> |<span data-ttu-id="1988c-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1988c-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1988c-242">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="1988c-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Konfigurera-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="1988c-244">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="1988c-244">Select **Create Record**.</span></span>
    
    ![Dyn-BP - Konfigurera-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1988c-246">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="1988c-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1988c-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1988c-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1988c-248">Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="1988c-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="1988c-249">Du uppmanas att logga in först</span><span class="sxs-lookup"><span data-stu-id="1988c-249">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1988c-251">På sidan **Zonnivåtjänster** väljer du **Dyn Standard DNS-tjänst** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="1988c-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1988c-252">Välj **Inställningar**på **DNS-sidan** för domänen .</span><span class="sxs-lookup"><span data-stu-id="1988c-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1988c-253">Välj **Aktivera expertgränssnitt**.</span><span class="sxs-lookup"><span data-stu-id="1988c-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1988c-254">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="1988c-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="1988c-255">Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="1988c-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="1988c-256">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="1988c-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1988c-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="1988c-257">**Host**</span></span>|<span data-ttu-id="1988c-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1988c-258">**TTL**</span></span>|<span data-ttu-id="1988c-259">**Type**</span><span class="sxs-lookup"><span data-stu-id="1988c-259">**Type**</span></span>|<span data-ttu-id="1988c-260">**Data**</span><span class="sxs-lookup"><span data-stu-id="1988c-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1988c-261">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1988c-261">_sip._tls</span></span>|<span data-ttu-id="1988c-262">600</span><span class="sxs-lookup"><span data-stu-id="1988c-262">600</span></span>|<span data-ttu-id="1988c-263">SRV</span><span class="sxs-lookup"><span data-stu-id="1988c-263">SRV</span></span>|<span data-ttu-id="1988c-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1988c-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="1988c-265">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="1988c-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="1988c-266">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="1988c-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="1988c-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1988c-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="1988c-268">600</span><span class="sxs-lookup"><span data-stu-id="1988c-268">600</span></span>|<span data-ttu-id="1988c-269">SRV</span><span class="sxs-lookup"><span data-stu-id="1988c-269">SRV</span></span>|<span data-ttu-id="1988c-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1988c-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="1988c-271">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="1988c-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="1988c-272">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="1988c-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Konfigurera-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="1988c-274">Välj **Skapa post**.</span><span class="sxs-lookup"><span data-stu-id="1988c-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP - Konfigurera-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="1988c-276">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="1988c-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="1988c-277">Skapa en post i avsnittet **Lägg till DNS-post** med hjälp av värdena från den andra raden i tabellen och välj sedan **skapa post** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="1988c-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="1988c-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1988c-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
