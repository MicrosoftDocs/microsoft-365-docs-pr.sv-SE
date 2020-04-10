---
title: Skapa DNS-poster på Google Domains för Office 365
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Lync och andra tjänster på Google Domains för Office 365.
ms.openlocfilehash: f0a9a42127fc5b722679013b899255f77840d670
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211733"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="3afa1-103">Skapa DNS-poster på Google Domains för Office 365</span><span class="sxs-lookup"><span data-stu-id="3afa1-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="3afa1-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="3afa1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3afa1-105">Om Google Domains är din DNS-värd följer du anvisningarna i den här artikeln om du vill verifiera din domän och konfigurera DNS-posterna för e-post, Lync och så vidare.</span><span class="sxs-lookup"><span data-stu-id="3afa1-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="3afa1-106">När du har lagt till dessa poster på Google Domains konfigureras domänen så att den fungerar med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="3afa1-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="3afa1-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="3afa1-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3afa1-p101">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3afa1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3afa1-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="3afa1-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3afa1-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3afa1-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3afa1-p102">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="3afa1-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3afa1-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="3afa1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3afa1-p104">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="3afa1-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="3afa1-120">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="3afa1-121">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="3afa1-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="3afa1-122">Leta reda på den domän som du vill använda med Office 365 på sidan **Mina domäner** och välj länken **HANTERA** bredvid den.</span><span class="sxs-lookup"><span data-stu-id="3afa1-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="3afa1-123">Välj **DNS**i den vänstra navigeringen .</span><span class="sxs-lookup"><span data-stu-id="3afa1-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="3afa1-124">Skriv eller kopiera och klistra in värdena från följande tabell i rutorna för den nya posten i avsnittet \*\* Anpassade resursposter \*\* i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="3afa1-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3afa1-125">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3afa1-126">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3afa1-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="3afa1-127">**Name**</span></span> <br/> |<span data-ttu-id="3afa1-128">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-128">**Type**</span></span> <br/> |<span data-ttu-id="3afa1-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3afa1-129">**TTL**</span></span> <br/> |<span data-ttu-id="3afa1-130">**Data**</span><span class="sxs-lookup"><span data-stu-id="3afa1-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="3afa1-131">TXT</span><span class="sxs-lookup"><span data-stu-id="3afa1-131">TXT</span></span>  <br/> |<span data-ttu-id="3afa1-132">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-132">1H</span></span>  <br/> |<span data-ttu-id="3afa1-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3afa1-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3afa1-134">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="3afa1-134">**Note:** This is an example.</span></span> <span data-ttu-id="3afa1-135">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="3afa1-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="3afa1-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="3afa1-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="3afa1-137">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="3afa1-138">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="3afa1-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3afa1-139">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="3afa1-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="3afa1-140">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="3afa1-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3afa1-141">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="3afa1-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3afa1-142">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="3afa1-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3afa1-143">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3afa1-144">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3afa1-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3afa1-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="3afa1-148">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="3afa1-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="3afa1-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3afa1-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3afa1-p108">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="3afa1-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="3afa1-153">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="3afa1-154">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="3afa1-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="3afa1-155">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="3afa1-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3afa1-p109">Om du har ett G Suite-e-postkonto måste du först ta bort MX-posterna som är kopplade till kontot. MX-posterna kopplade till G Suite förhindrar tillägg av MX-poster, däribland dem som krävs för Office 365. Observera att borttagning av MX-poster inte raderar ditt G Suite-konto. Så här tar du bort MX-posterna från ditt G Suite-konto.</span><span class="sxs-lookup"><span data-stu-id="3afa1-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="3afa1-160">Välj **Ta bort**i området **S suite** i avsnittet **Syntetiska poster** .</span><span class="sxs-lookup"><span data-stu-id="3afa1-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="3afa1-161">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-161">(You may have to scroll down.)</span></span>
    
    ![Välj Ta bort i avsnittet Syntetiska poster](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="3afa1-163">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-163">Select **Delete**.</span></span>
    
    ![Välj Ta bort](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="3afa1-165">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3afa1-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3afa1-166">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3afa1-167">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3afa1-168">**Name**</span><span class="sxs-lookup"><span data-stu-id="3afa1-168">**Name**</span></span>|<span data-ttu-id="3afa1-169">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-169">**Type**</span></span>|<span data-ttu-id="3afa1-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3afa1-170">**TTL**</span></span>|<span data-ttu-id="3afa1-171">**Data**</span><span class="sxs-lookup"><span data-stu-id="3afa1-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3afa1-172">MX</span><span class="sxs-lookup"><span data-stu-id="3afa1-172">MX</span></span>  <br/> |<span data-ttu-id="3afa1-173">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-173">1H</span></span>  <br/> |<span data-ttu-id="3afa1-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3afa1-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3afa1-175">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3afa1-p110">**0** motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="3afa1-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="3afa1-178">**Obs!** Hämta din \<*domännyckel*\> från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="3afa1-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  [<span data-ttu-id="3afa1-179">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="3afa1-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="3afa1-180">[Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="3afa1-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="3afa1-182">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-182">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="3afa1-184">Om det finns andra Custom MX-poster tar du bort dem.</span><span class="sxs-lookup"><span data-stu-id="3afa1-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="3afa1-185">Välj **Redigera** på MX-postraden.</span><span class="sxs-lookup"><span data-stu-id="3afa1-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Välj Redigera på MX-postraden](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="3afa1-187">För var och en av de andra anpassade MX-posterna markerar du posten i rutan **Data** och trycker sedan på **Delete-tangenten** på tangentbordet för att ta bort posten.</span><span class="sxs-lookup"><span data-stu-id="3afa1-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="3afa1-188">Fortsätt tills du har tagit bort **Data**-posten för var övriga MX-poster.</span><span class="sxs-lookup"><span data-stu-id="3afa1-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="3afa1-190">När du har tagit bort **dataposten** för var och en av de andra MX-posterna väljer du **Spara** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="3afa1-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Välj Spara](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="3afa1-192">Lägga till de fem CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="3afa1-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="3afa1-193">Kom igång genom att gå till sidanhttps://domains.google.com/registrar) [Google Domäner] ( och logga in.</span><span class="sxs-lookup"><span data-stu-id="3afa1-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="3afa1-194">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="3afa1-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3afa1-195">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="3afa1-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="3afa1-196">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du, eller kopierar och klistrar, in värdena från första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3afa1-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="3afa1-197">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3afa1-198">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3afa1-199">**Name**</span><span class="sxs-lookup"><span data-stu-id="3afa1-199">**Name**</span></span>|<span data-ttu-id="3afa1-200">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-200">**Type**</span></span>|<span data-ttu-id="3afa1-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3afa1-201">**TTL**</span></span>|<span data-ttu-id="3afa1-202">**Data**</span><span class="sxs-lookup"><span data-stu-id="3afa1-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3afa1-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3afa1-203">autodiscover</span></span>  <br/> |<span data-ttu-id="3afa1-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="3afa1-204">CNAME</span></span>  <br/> |<span data-ttu-id="3afa1-205">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-205">1H</span></span>  <br/> |<span data-ttu-id="3afa1-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3afa1-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3afa1-207">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3afa1-208">sip</span><span class="sxs-lookup"><span data-stu-id="3afa1-208">sip</span></span>  <br/> |<span data-ttu-id="3afa1-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="3afa1-209">CNAME</span></span>  <br/> |<span data-ttu-id="3afa1-210">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-210">1H</span></span>  <br/> |<span data-ttu-id="3afa1-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3afa1-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3afa1-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3afa1-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3afa1-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3afa1-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="3afa1-214">CNAME</span></span>  <br/> |<span data-ttu-id="3afa1-215">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-215">1H</span></span>  <br/> |<span data-ttu-id="3afa1-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3afa1-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3afa1-217">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3afa1-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3afa1-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3afa1-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="3afa1-219">CNAME</span></span>  <br/> |<span data-ttu-id="3afa1-220">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-220">1H</span></span>  <br/> |<span data-ttu-id="3afa1-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="3afa1-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3afa1-222">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3afa1-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3afa1-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3afa1-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="3afa1-224">CNAME</span></span>  <br/> |<span data-ttu-id="3afa1-225">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-225">1H</span></span>  <br/> |<span data-ttu-id="3afa1-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3afa1-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3afa1-227">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="3afa1-229">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-229">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="3afa1-231">Lägg till de andra fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="3afa1-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="3afa1-232">Skapa en post i avsnittet **Anpassade resursposter** med hjälp av värdena från nästa rad i tabellen och välj sedan **Lägg** till för att slutföra posten igen.</span><span class="sxs-lookup"><span data-stu-id="3afa1-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="3afa1-233">Upprepa den här processen tills du har skapat alla nödvändiga CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="3afa1-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3afa1-234">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="3afa1-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3afa1-235">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="3afa1-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3afa1-236">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="3afa1-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3afa1-237">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="3afa1-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="3afa1-238">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="3afa1-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="3afa1-239">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="3afa1-239">Need examples?</span></span> <span data-ttu-id="3afa1-240">Ta en titt på dessa [externa DNS-poster för Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="3afa1-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="3afa1-241">Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="3afa1-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="3afa1-p113">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="3afa1-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="3afa1-245">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="3afa1-246">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="3afa1-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="3afa1-247">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="3afa1-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="3afa1-248">Välj **Redigera**på TXT-postraden i avsnittet **Anpassade resursposter.**</span><span class="sxs-lookup"><span data-stu-id="3afa1-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3afa1-p114">I Google Domains betraktas en TXT-post som en uppsättning som kan innehålla flera poster. Om du har minst en TXT-post, till exempel TXT-posten du använde för att verifiera din domän, måste du lägga till nya TXT-poster i denna postuppsättning. Försöker du att ange ytterligare TXT-poster som separata poster får du ett felmeddelande om **Duplicate record** (dublettpost).</span><span class="sxs-lookup"><span data-stu-id="3afa1-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Välj Redigera på TXT-postraden](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="3afa1-253">Markera **kontrollen (+).**</span><span class="sxs-lookup"><span data-stu-id="3afa1-253">Select the **(+)** control.</span></span> 
    
    ![Välj pluskontrollen](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="3afa1-255">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3afa1-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="3afa1-256">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3afa1-257">**Data**</span><span class="sxs-lookup"><span data-stu-id="3afa1-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="3afa1-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3afa1-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="3afa1-259">Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="3afa1-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="3afa1-261">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-261">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="3afa1-263">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="3afa1-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="3afa1-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3afa1-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3afa1-p115">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="3afa1-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="3afa1-268">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="3afa1-269">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="3afa1-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="3afa1-270">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="3afa1-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="3afa1-271">Lägga till den första SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="3afa1-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="3afa1-272">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3afa1-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3afa1-273">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3afa1-274">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="3afa1-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3afa1-275">**Name**</span><span class="sxs-lookup"><span data-stu-id="3afa1-275">**Name**</span></span>|<span data-ttu-id="3afa1-276">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-276">**Type**</span></span>|<span data-ttu-id="3afa1-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3afa1-277">**TTL**</span></span>|<span data-ttu-id="3afa1-278">**Data**</span><span class="sxs-lookup"><span data-stu-id="3afa1-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3afa1-279">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3afa1-279">_sip._tls</span></span>|<span data-ttu-id="3afa1-280">SRV</span><span class="sxs-lookup"><span data-stu-id="3afa1-280">SRV</span></span>|<span data-ttu-id="3afa1-281">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-281">1H</span></span>|<span data-ttu-id="3afa1-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3afa1-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="3afa1-283">**Det här värdet MÅSTE sluta med en punkt (.)** **Anm.:** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="3afa1-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="3afa1-284">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3afa1-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3afa1-285">SRV</span><span class="sxs-lookup"><span data-stu-id="3afa1-285">SRV</span></span>|<span data-ttu-id="3afa1-286">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="3afa1-286">1H</span></span>|<span data-ttu-id="3afa1-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3afa1-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="3afa1-288">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="3afa1-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="3afa1-289">Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="3afa1-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="3afa1-291">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3afa1-291">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="3afa1-293">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="3afa1-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3afa1-294">Skapa en post i avsnittet **Anpassade resursposter** med hjälp av värdena från den andra raden i tabellen och välj sedan **Lägg** till för att slutföra posten igen.</span><span class="sxs-lookup"><span data-stu-id="3afa1-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3afa1-p118">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3afa1-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
