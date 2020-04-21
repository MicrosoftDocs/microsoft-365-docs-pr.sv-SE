---
title: Skapa DNS-poster på Google Domains för Microsoft
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Lync och andra tjänster på Google Domains för Microsoft.
ms.openlocfilehash: 20a3ba9baefcdb26936d2d0a5fda7ed1b5db971e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629545"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="928ea-103">Skapa DNS-poster på Google Domains för Microsoft</span><span class="sxs-lookup"><span data-stu-id="928ea-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="928ea-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="928ea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="928ea-105">Om Google Domains är din DNS-värd följer du anvisningarna i den här artikeln om du vill verifiera din domän och konfigurera DNS-posterna för e-post, Lync och så vidare.</span><span class="sxs-lookup"><span data-stu-id="928ea-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="928ea-106">När du har lagt till dessa poster på Google Domains konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="928ea-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="928ea-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="928ea-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="928ea-108">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="928ea-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="928ea-109">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="928ea-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="928ea-110">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domän- eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="928ea-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="928ea-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="928ea-111">Add a TXT record for verification</span></span>
<span data-ttu-id="928ea-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="928ea-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="928ea-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="928ea-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="928ea-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="928ea-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="928ea-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="928ea-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="928ea-p104">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="928ea-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="928ea-120">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="928ea-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="928ea-121">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="928ea-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="928ea-122">Leta reda på den domän som du vill använda med Microsoft på sidan **Mina domäner** och välj länken **HANTERA** bredvid den.</span><span class="sxs-lookup"><span data-stu-id="928ea-122">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="928ea-123">Välj **DNS**i den vänstra navigeringen .</span><span class="sxs-lookup"><span data-stu-id="928ea-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="928ea-124">Skriv eller kopiera och klistra in värdena från följande tabell i rutorna för den nya posten i avsnittet \*\* Anpassade resursposter \*\* i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="928ea-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="928ea-125">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="928ea-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="928ea-126">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="928ea-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="928ea-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="928ea-127">**Name**</span></span> <br/> |<span data-ttu-id="928ea-128">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="928ea-128">**Type**</span></span> <br/> |<span data-ttu-id="928ea-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="928ea-129">**TTL**</span></span> <br/> |<span data-ttu-id="928ea-130">**Data**</span><span class="sxs-lookup"><span data-stu-id="928ea-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="928ea-131">TXT</span><span class="sxs-lookup"><span data-stu-id="928ea-131">TXT</span></span>  <br/> |<span data-ttu-id="928ea-132">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-132">1H</span></span>  <br/> |<span data-ttu-id="928ea-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="928ea-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="928ea-134">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="928ea-134">**Note:** This is an example.</span></span> <span data-ttu-id="928ea-135">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="928ea-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="928ea-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="928ea-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="928ea-137">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="928ea-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="928ea-138">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="928ea-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="928ea-139">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="928ea-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="928ea-140">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="928ea-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="928ea-141">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="928ea-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="928ea-142">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="928ea-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="928ea-143">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="928ea-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="928ea-144">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="928ea-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="928ea-145">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="928ea-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="928ea-146">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="928ea-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="928ea-147">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="928ea-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="928ea-148">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="928ea-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="928ea-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="928ea-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="928ea-p108">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="928ea-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="928ea-153">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="928ea-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="928ea-154">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="928ea-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="928ea-155">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="928ea-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="928ea-156">Om du har ett G Suite-e-postkonto måste du först ta bort MX-posterna som är kopplade till kontot.</span><span class="sxs-lookup"><span data-stu-id="928ea-156">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="928ea-157">G Suite MX-posterna hindrar dig från att lägga till andra MX-poster, inklusive de som krävs för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="928ea-157">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="928ea-158">Observera att borttagning av MX-poster inte raderar ditt G Suite-konto.</span><span class="sxs-lookup"><span data-stu-id="928ea-158">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="928ea-159">Så här tar du bort MX-posterna från ditt G Suite-konto.</span><span class="sxs-lookup"><span data-stu-id="928ea-159">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="928ea-160">Välj **Ta bort**i området **S suite** i avsnittet **Syntetiska poster** .</span><span class="sxs-lookup"><span data-stu-id="928ea-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="928ea-161">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="928ea-161">(You may have to scroll down.)</span></span>
    
    ![Välj Ta bort i avsnittet Syntetiska poster](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="928ea-163">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="928ea-163">Select **Delete**.</span></span>
    
    ![Välj Ta bort](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="928ea-165">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="928ea-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="928ea-166">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="928ea-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="928ea-167">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="928ea-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="928ea-168">**Name**</span><span class="sxs-lookup"><span data-stu-id="928ea-168">**Name**</span></span>|<span data-ttu-id="928ea-169">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="928ea-169">**Type**</span></span>|<span data-ttu-id="928ea-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="928ea-170">**TTL**</span></span>|<span data-ttu-id="928ea-171">**Data**</span><span class="sxs-lookup"><span data-stu-id="928ea-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="928ea-172">MX</span><span class="sxs-lookup"><span data-stu-id="928ea-172">MX</span></span>  <br/> |<span data-ttu-id="928ea-173">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-173">1H</span></span>  <br/> |<span data-ttu-id="928ea-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="928ea-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="928ea-175">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="928ea-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="928ea-p110">**0** motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="928ea-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="928ea-178">**Anm.:** Hämta \< *domännyckeln* \> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="928ea-178">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="928ea-179">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="928ea-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="928ea-180">[Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="928ea-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="928ea-182">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="928ea-182">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="928ea-184">Om det finns andra Custom MX-poster tar du bort dem.</span><span class="sxs-lookup"><span data-stu-id="928ea-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="928ea-185">Välj **Redigera** på MX-postraden.</span><span class="sxs-lookup"><span data-stu-id="928ea-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Välj Redigera på MX-postraden](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="928ea-187">För var och en av de andra anpassade MX-posterna markerar du posten i rutan **Data** och trycker sedan på **Delete-tangenten** på tangentbordet för att ta bort posten.</span><span class="sxs-lookup"><span data-stu-id="928ea-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="928ea-188">Fortsätt tills du har tagit bort **Data**-posten för var övriga MX-poster.</span><span class="sxs-lookup"><span data-stu-id="928ea-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="928ea-190">När du har tagit bort **dataposten** för var och en av de andra MX-posterna väljer du **Spara** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="928ea-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Välj Spara](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="928ea-192">Lägga till de fem CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="928ea-192">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="928ea-193">Kom igång genom att gå till sidanhttps://domains.google.com/registrar) [Google Domäner] ( och logga in.</span><span class="sxs-lookup"><span data-stu-id="928ea-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="928ea-194">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="928ea-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="928ea-195">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="928ea-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="928ea-196">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du, eller kopierar och klistrar, in värdena från första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="928ea-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="928ea-197">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="928ea-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="928ea-198">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="928ea-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="928ea-199">**Name**</span><span class="sxs-lookup"><span data-stu-id="928ea-199">**Name**</span></span>|<span data-ttu-id="928ea-200">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="928ea-200">**Type**</span></span>|<span data-ttu-id="928ea-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="928ea-201">**TTL**</span></span>|<span data-ttu-id="928ea-202">**Data**</span><span class="sxs-lookup"><span data-stu-id="928ea-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="928ea-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="928ea-203">autodiscover</span></span>  <br/> |<span data-ttu-id="928ea-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="928ea-204">CNAME</span></span>  <br/> |<span data-ttu-id="928ea-205">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-205">1H</span></span>  <br/> |<span data-ttu-id="928ea-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="928ea-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="928ea-207">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="928ea-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="928ea-208">sip</span><span class="sxs-lookup"><span data-stu-id="928ea-208">sip</span></span>  <br/> |<span data-ttu-id="928ea-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="928ea-209">CNAME</span></span>  <br/> |<span data-ttu-id="928ea-210">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-210">1H</span></span>  <br/> |<span data-ttu-id="928ea-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="928ea-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="928ea-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="928ea-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="928ea-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="928ea-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="928ea-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="928ea-214">CNAME</span></span>  <br/> |<span data-ttu-id="928ea-215">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-215">1H</span></span>  <br/> |<span data-ttu-id="928ea-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="928ea-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="928ea-217">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="928ea-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="928ea-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="928ea-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="928ea-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="928ea-219">CNAME</span></span>  <br/> |<span data-ttu-id="928ea-220">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-220">1H</span></span>  <br/> |<span data-ttu-id="928ea-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="928ea-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="928ea-222">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="928ea-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="928ea-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="928ea-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="928ea-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="928ea-224">CNAME</span></span>  <br/> |<span data-ttu-id="928ea-225">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-225">1H</span></span>  <br/> |<span data-ttu-id="928ea-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="928ea-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="928ea-227">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="928ea-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="928ea-229">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="928ea-229">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="928ea-231">Lägg till de andra fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="928ea-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="928ea-232">Skapa en post i avsnittet **Anpassade resursposter** med hjälp av värdena från nästa rad i tabellen och välj sedan **Lägg** till för att slutföra posten igen.</span><span class="sxs-lookup"><span data-stu-id="928ea-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="928ea-233">Upprepa den här processen tills du har skapat alla nödvändiga CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="928ea-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="928ea-234">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="928ea-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="928ea-235">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="928ea-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="928ea-236">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="928ea-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="928ea-237">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="928ea-237">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="928ea-238">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en enda SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="928ea-238">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="928ea-239">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="928ea-239">Need examples?</span></span> <span data-ttu-id="928ea-240">Kolla in dessa [externa domännamnssystemposter för Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="928ea-240">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="928ea-241">Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="928ea-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="928ea-p113">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="928ea-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="928ea-245">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="928ea-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="928ea-246">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="928ea-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="928ea-247">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="928ea-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="928ea-248">Välj **Redigera**på TXT-postraden i avsnittet **Anpassade resursposter.**</span><span class="sxs-lookup"><span data-stu-id="928ea-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="928ea-p114">I Google Domains betraktas en TXT-post som en uppsättning som kan innehålla flera poster. Om du har minst en TXT-post, till exempel TXT-posten du använde för att verifiera din domän, måste du lägga till nya TXT-poster i denna postuppsättning. Försöker du att ange ytterligare TXT-poster som separata poster får du ett felmeddelande om **Duplicate record** (dublettpost).</span><span class="sxs-lookup"><span data-stu-id="928ea-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Välj Redigera på TXT-postraden](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="928ea-253">Markera **kontrollen (+).**</span><span class="sxs-lookup"><span data-stu-id="928ea-253">Select the **(+)** control.</span></span> 
    
    ![Välj pluskontrollen](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="928ea-255">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="928ea-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="928ea-256">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="928ea-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="928ea-257">**Data**</span><span class="sxs-lookup"><span data-stu-id="928ea-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="928ea-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="928ea-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="928ea-259">Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="928ea-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="928ea-261">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="928ea-261">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="928ea-263">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="928ea-263">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="928ea-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="928ea-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="928ea-p115">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="928ea-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="928ea-268">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="928ea-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="928ea-269">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="928ea-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="928ea-270">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="928ea-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="928ea-271">Lägga till den första SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="928ea-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="928ea-272">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="928ea-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="928ea-273">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="928ea-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="928ea-274">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="928ea-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="928ea-275">**Name**</span><span class="sxs-lookup"><span data-stu-id="928ea-275">**Name**</span></span>|<span data-ttu-id="928ea-276">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="928ea-276">**Type**</span></span>|<span data-ttu-id="928ea-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="928ea-277">**TTL**</span></span>|<span data-ttu-id="928ea-278">**Data**</span><span class="sxs-lookup"><span data-stu-id="928ea-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="928ea-279">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="928ea-279">_sip._tls</span></span>|<span data-ttu-id="928ea-280">SRV</span><span class="sxs-lookup"><span data-stu-id="928ea-280">SRV</span></span>|<span data-ttu-id="928ea-281">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-281">1H</span></span>|<span data-ttu-id="928ea-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="928ea-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="928ea-283">**Det här värdet MÅSTE sluta med en punkt (.)** **Anm.:** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="928ea-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="928ea-284">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="928ea-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="928ea-285">SRV</span><span class="sxs-lookup"><span data-stu-id="928ea-285">SRV</span></span>|<span data-ttu-id="928ea-286">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="928ea-286">1H</span></span>|<span data-ttu-id="928ea-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="928ea-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="928ea-288">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="928ea-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="928ea-289">Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="928ea-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="928ea-291">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="928ea-291">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="928ea-293">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="928ea-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="928ea-294">Skapa en post i avsnittet **Anpassade resursposter** med hjälp av värdena från den andra raden i tabellen och välj sedan **Lägg** till för att slutföra posten igen.</span><span class="sxs-lookup"><span data-stu-id="928ea-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="928ea-295">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="928ea-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="928ea-296">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="928ea-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="928ea-297">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="928ea-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
