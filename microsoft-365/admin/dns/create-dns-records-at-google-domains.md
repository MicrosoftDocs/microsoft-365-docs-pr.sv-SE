---
title: Skapa DNS-poster på Google Domains för Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Läs mer om att verifiera din domän och konfigurera DNS-poster för e-post, Lync och andra tjänster på Google Domains för Microsoft.
ms.openlocfilehash: 417fe89bd408eba4d3b14ecb3e38af6beed196cf
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646097"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="e7e83-103">Skapa DNS-poster på Google Domains för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7e83-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="e7e83-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="e7e83-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e7e83-105">Om Google Domains är din DNS-värd följer du anvisningarna i den här artikeln om du vill verifiera din domän och konfigurera DNS-posterna för e-post, Lync och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e7e83-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="e7e83-106">När du har lagt till dessa poster på Google Domains är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="e7e83-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="e7e83-107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="e7e83-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e7e83-108">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="e7e83-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e7e83-109">Om du har problem med e-postflöde eller andra problem efter att du har lagt till DNS-poster läser du [hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7e83-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e7e83-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="e7e83-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e7e83-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e83-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e7e83-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="e7e83-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7e83-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="e7e83-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e7e83-p104">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="e7e83-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="e7e83-119">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="e7e83-120">Ange dina inloggnings uppgifter och välj sedan **Logga**in igen.</span><span class="sxs-lookup"><span data-stu-id="e7e83-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="e7e83-121">På sidan **My** Domains letar du reda på den domän som du vill använda med Microsoft och väljer **Hantera** -länken bredvid den.</span><span class="sxs-lookup"><span data-stu-id="e7e83-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="e7e83-122">I det vänstra navigerings fältet väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="e7e83-123">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7e83-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7e83-124">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e7e83-125">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7e83-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7e83-126">**Name**</span></span> <br/> |<span data-ttu-id="e7e83-127">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-127">**Type**</span></span> <br/> |<span data-ttu-id="e7e83-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7e83-128">**TTL**</span></span> <br/> |<span data-ttu-id="e7e83-129">**Data**</span><span class="sxs-lookup"><span data-stu-id="e7e83-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="e7e83-130">TXT</span><span class="sxs-lookup"><span data-stu-id="e7e83-130">TXT</span></span>  <br/> |<span data-ttu-id="e7e83-131">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-131">1H</span></span>  <br/> |<span data-ttu-id="e7e83-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e7e83-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e7e83-133">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="e7e83-133">**Note:** This is an example.</span></span> <span data-ttu-id="e7e83-134">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="e7e83-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e7e83-135">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e7e83-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="e7e83-136">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="e7e83-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="e7e83-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e7e83-138">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="e7e83-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e7e83-139">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="e7e83-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e7e83-140">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="e7e83-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e7e83-141">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="e7e83-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e7e83-142">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e7e83-143">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7e83-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7e83-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e7e83-147">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7e83-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e7e83-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e83-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e7e83-p108">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="e7e83-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="e7e83-152">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="e7e83-153">Ange dina inloggnings uppgifter och välj sedan **Logga**in igen.</span><span class="sxs-lookup"><span data-stu-id="e7e83-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="e7e83-154">Välj **Konfigurera DNS** för den domän som du vill redigera i avsnittet **Domain** **på sidan** domains.</span><span class="sxs-lookup"><span data-stu-id="e7e83-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7e83-155">Om du har ett G Suite-e-postkonto måste du först ta bort MX-posterna som är kopplade till kontot.</span><span class="sxs-lookup"><span data-stu-id="e7e83-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="e7e83-156">G Suite MX-posterna hindrar dig från att lägga till andra MX-poster, inklusive de som behövs för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7e83-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="e7e83-157">Observera att borttagning av MX-poster inte raderar ditt G Suite-konto.</span><span class="sxs-lookup"><span data-stu-id="e7e83-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="e7e83-158">Så här tar du bort MX-posterna från ditt G Suite-konto.</span><span class="sxs-lookup"><span data-stu-id="e7e83-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="e7e83-159">Välj **ta bort**i området **G Suite** i avsnittet **syntetiska poster** .</span><span class="sxs-lookup"><span data-stu-id="e7e83-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="e7e83-160">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-160">(You may have to scroll down.)</span></span>
    
    ![Välj Ta bort i avsnittet syntetiska poster](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="e7e83-162">Välj **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-162">Select **Delete**.</span></span>
    
    ![Välj Ta bort](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="e7e83-164">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7e83-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7e83-165">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e7e83-166">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7e83-167">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7e83-167">**Name**</span></span>|<span data-ttu-id="e7e83-168">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-168">**Type**</span></span>|<span data-ttu-id="e7e83-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7e83-169">**TTL**</span></span>|<span data-ttu-id="e7e83-170">**Data**</span><span class="sxs-lookup"><span data-stu-id="e7e83-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e7e83-171">MX</span><span class="sxs-lookup"><span data-stu-id="e7e83-171">MX</span></span>  <br/> |<span data-ttu-id="e7e83-172">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-172">1H</span></span>  <br/> |<span data-ttu-id="e7e83-173">0  *\<domain-key\>*  . mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e7e83-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e7e83-174">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e7e83-p110">**0** motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="e7e83-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="e7e83-177">**Obs!** Hämta din \<*domain-key*\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="e7e83-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="e7e83-178">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="e7e83-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="e7e83-179">[Mer information om prioritet finns i ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="e7e83-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Ange eller klistra in värden i avsnittet Custom Resource Records](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="e7e83-181">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-181">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="e7e83-183">Om det finns andra Custom MX-poster tar du bort dem.</span><span class="sxs-lookup"><span data-stu-id="e7e83-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="e7e83-184">Välj **redigera** i MX Record-raden.</span><span class="sxs-lookup"><span data-stu-id="e7e83-184">Select **Edit** in the MX record row.</span></span> 
    
    ![Välja Redigera i MX Record-raden](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="e7e83-186">För var och en av de andra anpassade MX-posterna markerar du posten i rutan **data** och trycker sedan på **Delete** -tangenten på tangent bordet för att ta bort posten.</span><span class="sxs-lookup"><span data-stu-id="e7e83-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="e7e83-187">Fortsätt tills du har tagit bort **Data**-posten för var övriga MX-poster.</span><span class="sxs-lookup"><span data-stu-id="e7e83-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="e7e83-189">När du har tagit bort **data** inmatningen för var och en av de andra MX-posterna väljer du **Spara** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="e7e83-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Välj Spara](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e7e83-191">Lägga till de fem CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7e83-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="e7e83-192">För att komma igång går du till sidan [Google Domains] ( https://domains.google.com/registrar) och loggar in.</span><span class="sxs-lookup"><span data-stu-id="e7e83-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="e7e83-193">Välj **Konfigurera DNS** för den domän som du vill redigera i avsnittet **Domain** **på sidan** domains.</span><span class="sxs-lookup"><span data-stu-id="e7e83-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e7e83-194">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="e7e83-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="e7e83-195">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du, eller kopierar och klistrar, in värdena från första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7e83-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="e7e83-196">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e7e83-197">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7e83-198">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7e83-198">**Name**</span></span>|<span data-ttu-id="e7e83-199">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-199">**Type**</span></span>|<span data-ttu-id="e7e83-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7e83-200">**TTL**</span></span>|<span data-ttu-id="e7e83-201">**Data**</span><span class="sxs-lookup"><span data-stu-id="e7e83-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7e83-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e7e83-202">autodiscover</span></span>  <br/> |<span data-ttu-id="e7e83-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7e83-203">CNAME</span></span>  <br/> |<span data-ttu-id="e7e83-204">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-204">1H</span></span>  <br/> |<span data-ttu-id="e7e83-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e7e83-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e7e83-206">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e7e83-207">sip</span><span class="sxs-lookup"><span data-stu-id="e7e83-207">sip</span></span>  <br/> |<span data-ttu-id="e7e83-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7e83-208">CNAME</span></span>  <br/> |<span data-ttu-id="e7e83-209">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-209">1H</span></span>  <br/> |<span data-ttu-id="e7e83-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e7e83-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e7e83-211">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e7e83-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e7e83-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e7e83-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7e83-213">CNAME</span></span>  <br/> |<span data-ttu-id="e7e83-214">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-214">1H</span></span>  <br/> |<span data-ttu-id="e7e83-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e7e83-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e7e83-216">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e7e83-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e7e83-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e7e83-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7e83-218">CNAME</span></span>  <br/> |<span data-ttu-id="e7e83-219">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-219">1H</span></span>  <br/> |<span data-ttu-id="e7e83-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e7e83-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="e7e83-221">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e7e83-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e7e83-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e7e83-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7e83-223">CNAME</span></span>  <br/> |<span data-ttu-id="e7e83-224">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-224">1H</span></span>  <br/> |<span data-ttu-id="e7e83-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e7e83-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="e7e83-226">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Ange eller klistra in värden i avsnittet Custom Resource Records](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="e7e83-228">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-228">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="e7e83-230">Lägg till de andra fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e7e83-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="e7e83-231">I avsnittet **Custom Resource Records** skapar du en post med värdena från nästa rad i tabellen och väljer sedan **Add** för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="e7e83-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="e7e83-232">Upprepa proceduren tills du har skapat alla nödvändiga CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="e7e83-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e7e83-233">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="e7e83-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7e83-234">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="e7e83-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e7e83-235">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="e7e83-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e7e83-236">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7e83-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e7e83-237">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="e7e83-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="e7e83-238">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="e7e83-238">Need examples?</span></span> <span data-ttu-id="e7e83-239">Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="e7e83-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="e7e83-240">Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e7e83-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="e7e83-p113">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="e7e83-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="e7e83-244">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="e7e83-245">Ange dina inloggnings uppgifter och välj sedan **Logga**in igen.</span><span class="sxs-lookup"><span data-stu-id="e7e83-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="e7e83-246">Välj **Konfigurera DNS** för den domän som du vill redigera i avsnittet **Domain** **på sidan** domains.</span><span class="sxs-lookup"><span data-stu-id="e7e83-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="e7e83-247">Välj **Redigera**på raden txt Record i avsnittet **Custom Resource Records** .</span><span class="sxs-lookup"><span data-stu-id="e7e83-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7e83-p114">I Google Domains betraktas en TXT-post som en uppsättning som kan innehålla flera poster. Om du har minst en TXT-post, till exempel TXT-posten du använde för att verifiera din domän, måste du lägga till nya TXT-poster i denna postuppsättning. Försöker du att ange ytterligare TXT-poster som separata poster får du ett felmeddelande om **Duplicate record** (dublettpost).</span><span class="sxs-lookup"><span data-stu-id="e7e83-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Välja Redigera i TXT-postraden](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="e7e83-252">Välj **(+)** kontroll.</span><span class="sxs-lookup"><span data-stu-id="e7e83-252">Select the **(+)** control.</span></span> 
    
    ![Välj plus kontrollen](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="e7e83-254">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7e83-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="e7e83-255">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="e7e83-256">**Data**</span><span class="sxs-lookup"><span data-stu-id="e7e83-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="e7e83-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e7e83-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="e7e83-258">Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="e7e83-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Ange eller klistra in värden i avsnittet Custom Resource Records](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="e7e83-260">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-260">Select **Save**.</span></span>
    
    ![Välj Spara](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e7e83-262">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7e83-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e7e83-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e83-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e7e83-p115">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="e7e83-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="e7e83-267">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="e7e83-268">Ange dina inloggnings uppgifter och välj sedan **Logga**in igen.</span><span class="sxs-lookup"><span data-stu-id="e7e83-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="e7e83-269">Välj **Konfigurera DNS** för den domän som du vill redigera i avsnittet **Domain** **på sidan** domains.</span><span class="sxs-lookup"><span data-stu-id="e7e83-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="e7e83-270">Lägga till den första SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="e7e83-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="e7e83-271">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7e83-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7e83-272">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e7e83-273">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="e7e83-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7e83-274">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7e83-274">**Name**</span></span>|<span data-ttu-id="e7e83-275">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-275">**Type**</span></span>|<span data-ttu-id="e7e83-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7e83-276">**TTL**</span></span>|<span data-ttu-id="e7e83-277">**Data**</span><span class="sxs-lookup"><span data-stu-id="e7e83-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7e83-278">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="e7e83-278">_sip._tls</span></span>|<span data-ttu-id="e7e83-279">SRV</span><span class="sxs-lookup"><span data-stu-id="e7e83-279">SRV</span></span>|<span data-ttu-id="e7e83-280">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-280">1H</span></span>|<span data-ttu-id="e7e83-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e7e83-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="e7e83-282">**Det här värdet måste sluta med en punkt (.)** **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="e7e83-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="e7e83-283">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e7e83-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="e7e83-284">SRV</span><span class="sxs-lookup"><span data-stu-id="e7e83-284">SRV</span></span>|<span data-ttu-id="e7e83-285">1H</span><span class="sxs-lookup"><span data-stu-id="e7e83-285">1H</span></span>|<span data-ttu-id="e7e83-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e7e83-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="e7e83-287">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="e7e83-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="e7e83-288">Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="e7e83-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Ange eller klistra in värden i avsnittet Custom Resource Records](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="e7e83-290">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e7e83-290">Select **Add**.</span></span>
    
    ![Välj Lägg till](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="e7e83-292">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="e7e83-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e7e83-293">I avsnittet **Custom Resource Records** skapar du en post med värdena från den andra raden i tabellen och väljer sedan **Add** för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="e7e83-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e7e83-p118">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7e83-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
