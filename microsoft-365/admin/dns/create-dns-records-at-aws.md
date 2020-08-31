---
title: Skapa DNS-poster på Amazon Web Services (AWS) för Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Amazon Web Services (AWS) för Microsoft.
ms.openlocfilehash: dbbf82c9c776108c4d5e34e2eb639f9c36e9f28b
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307073"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="d3b70-103">Skapa DNS-poster på Amazon Web Services (AWS) för Microsoft</span><span class="sxs-lookup"><span data-stu-id="d3b70-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="d3b70-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="d3b70-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d3b70-105">Om AWS är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype online för företag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="d3b70-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="d3b70-106">När du har lagt till dessa poster på AWS är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="d3b70-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="d3b70-p101">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d3b70-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d3b70-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="d3b70-110">Add a TXT record for verification</span></span>
<span data-ttu-id="d3b70-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b70-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d3b70-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="d3b70-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3b70-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="d3b70-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d3b70-p104">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d3b70-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d3b70-118">På sidan **resurser** väljer du **värd zoner**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d3b70-119">Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** .</span><span class="sxs-lookup"><span data-stu-id="d3b70-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d3b70-120">Välj **skapa post uppsättning**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d3b70-121">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="d3b70-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d3b70-122">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="d3b70-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="d3b70-p105">Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="d3b70-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d3b70-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="d3b70-125">**Name**</span></span> <br/> |<span data-ttu-id="d3b70-126">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-126">**Type**</span></span> <br/> |<span data-ttu-id="d3b70-127">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d3b70-127">**Alias**</span></span> <br/> |<span data-ttu-id="d3b70-128">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="d3b70-129">**Värde**</span><span class="sxs-lookup"><span data-stu-id="d3b70-129">**Value**</span></span> <br/> |<span data-ttu-id="d3b70-130">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="d3b70-131">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="d3b70-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d3b70-132">TXT - text</span><span class="sxs-lookup"><span data-stu-id="d3b70-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="d3b70-133">Nej</span><span class="sxs-lookup"><span data-stu-id="d3b70-133">No</span></span>  <br/> |<span data-ttu-id="d3b70-134">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-134">300</span></span>  <br/> |<span data-ttu-id="d3b70-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d3b70-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="d3b70-136">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="d3b70-136">**Note:** This is an example.</span></span> <span data-ttu-id="d3b70-137">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3b70-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="d3b70-138">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="d3b70-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d3b70-139">Enkelt</span><span class="sxs-lookup"><span data-stu-id="d3b70-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="d3b70-140">Välj **skapa**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="d3b70-141">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="d3b70-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d3b70-142">Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="d3b70-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="d3b70-143">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="d3b70-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d3b70-144">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="d3b70-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d3b70-145">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="d3b70-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d3b70-146">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d3b70-147">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d3b70-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d3b70-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="d3b70-151">Lägga till en MX-post så att e-post för din domän kommer till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d3b70-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="d3b70-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b70-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d3b70-p108">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d3b70-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d3b70-155">På sidan **resurser** väljer du **värd zoner**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d3b70-156">Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** .</span><span class="sxs-lookup"><span data-stu-id="d3b70-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d3b70-157">Välj **skapa post uppsättning**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d3b70-158">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="d3b70-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d3b70-159">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="d3b70-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d3b70-160">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-160">**Name**</span></span>|<span data-ttu-id="d3b70-161">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-161">**Type**</span></span>|<span data-ttu-id="d3b70-162">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d3b70-162">**Alias**</span></span>|<span data-ttu-id="d3b70-163">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="d3b70-164">**Värde**</span><span class="sxs-lookup"><span data-stu-id="d3b70-164">**Value**</span></span>|<span data-ttu-id="d3b70-165">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d3b70-166">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="d3b70-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d3b70-167">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="d3b70-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="d3b70-168">No</span><span class="sxs-lookup"><span data-stu-id="d3b70-168">No</span></span>  <br/> |<span data-ttu-id="d3b70-169">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-169">300</span></span>  <br/> |<span data-ttu-id="d3b70-170">0  *\<domain-key\>*  . mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d3b70-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="d3b70-p109">0 motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="d3b70-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="d3b70-173">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d3b70-174">**Obs!** Hämta ditt \<*domain-key*\> från ditt Microsoft 365-konto.</span><span class="sxs-lookup"><span data-stu-id="d3b70-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="d3b70-175">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="d3b70-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d3b70-176">Enkelt</span><span class="sxs-lookup"><span data-stu-id="d3b70-176">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="d3b70-178">Välj **skapa**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="d3b70-180">Om det finns andra MX-poster tar du bort dem.</span><span class="sxs-lookup"><span data-stu-id="d3b70-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d3b70-181">AWS lagrar MX-poster som en uppsättning som kan innehålla flera poster.</span><span class="sxs-lookup"><span data-stu-id="d3b70-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="d3b70-182">Välj **inte** **ta bort post uppsättning**eftersom det här tar bort alla dina MX-poster, inklusive den du just lagt till.</span><span class="sxs-lookup"><span data-stu-id="d3b70-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="d3b70-183">Använd följande instruktioner i stället.</span><span class="sxs-lookup"><span data-stu-id="d3b70-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="d3b70-184">Välj först MX-postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="d3b70-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="d3b70-186">I **Edit Record Set** tar du sedan bort inaktuella MX-poster genom att markera respektive post i rutan **Value** och sedan trycka på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="d3b70-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="d3b70-188">Välj **Save Record set**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="d3b70-190">Lägga till de fem CNAME-poster som krävs för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d3b70-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="d3b70-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b70-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d3b70-p112">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d3b70-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d3b70-194">På sidan **resurser** väljer du **värd zoner**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d3b70-195">Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** .</span><span class="sxs-lookup"><span data-stu-id="d3b70-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d3b70-196">Välj **skapa post uppsättning**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d3b70-197">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="d3b70-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="d3b70-198">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="d3b70-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d3b70-199">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="d3b70-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d3b70-200">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-200">**Name**</span></span>|<span data-ttu-id="d3b70-201">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-201">**Type**</span></span>|<span data-ttu-id="d3b70-202">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d3b70-202">**Alias**</span></span>|<span data-ttu-id="d3b70-203">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="d3b70-204">**Värde**</span><span class="sxs-lookup"><span data-stu-id="d3b70-204">**Value**</span></span>|<span data-ttu-id="d3b70-205">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d3b70-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d3b70-206">autodiscover</span></span>  <br/> |<span data-ttu-id="d3b70-207">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="d3b70-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d3b70-208">No</span><span class="sxs-lookup"><span data-stu-id="d3b70-208">No</span></span>  <br/> |<span data-ttu-id="d3b70-209">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-209">300</span></span>  <br/> |<span data-ttu-id="d3b70-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d3b70-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d3b70-211">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d3b70-212">Simple</span><span class="sxs-lookup"><span data-stu-id="d3b70-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="d3b70-213">sip</span><span class="sxs-lookup"><span data-stu-id="d3b70-213">sip</span></span>  <br/> |<span data-ttu-id="d3b70-214">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="d3b70-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d3b70-215">No</span><span class="sxs-lookup"><span data-stu-id="d3b70-215">No</span></span>  <br/> |<span data-ttu-id="d3b70-216">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-216">300</span></span>  <br/> |<span data-ttu-id="d3b70-217">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d3b70-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d3b70-218">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d3b70-219">Simple</span><span class="sxs-lookup"><span data-stu-id="d3b70-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="d3b70-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d3b70-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d3b70-221">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="d3b70-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d3b70-222">No</span><span class="sxs-lookup"><span data-stu-id="d3b70-222">No</span></span>  <br/> |<span data-ttu-id="d3b70-223">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-223">300</span></span>  <br/> |<span data-ttu-id="d3b70-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d3b70-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d3b70-225">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d3b70-226">Enkelt</span><span class="sxs-lookup"><span data-stu-id="d3b70-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="d3b70-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d3b70-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d3b70-228">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="d3b70-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d3b70-229">No</span><span class="sxs-lookup"><span data-stu-id="d3b70-229">No</span></span>  <br/> |<span data-ttu-id="d3b70-230">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-230">300</span></span>  <br/> |<span data-ttu-id="d3b70-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="d3b70-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="d3b70-232">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d3b70-233">Simple</span><span class="sxs-lookup"><span data-stu-id="d3b70-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="d3b70-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d3b70-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d3b70-235">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="d3b70-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d3b70-236">No</span><span class="sxs-lookup"><span data-stu-id="d3b70-236">No</span></span>  <br/> |<span data-ttu-id="d3b70-237">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-237">300</span></span>  <br/> |<span data-ttu-id="d3b70-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d3b70-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="d3b70-239">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d3b70-240">Enkelt</span><span class="sxs-lookup"><span data-stu-id="d3b70-240">Simple</span></span>  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="d3b70-242">Välj **skapa**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="d3b70-244">Lägg till de andra fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="d3b70-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="d3b70-245">På sidan **Hosted Zones** väljer du **create Record set**, skapar en post med värdena från nästa rad i tabellen och väljer sedan **igen för att** slutföra den posten.</span><span class="sxs-lookup"><span data-stu-id="d3b70-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="d3b70-246">Upprepa proceduren tills du har skapat alla fem CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="d3b70-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d3b70-247">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="d3b70-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d3b70-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b70-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3b70-249">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="d3b70-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d3b70-250">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="d3b70-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d3b70-251">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3b70-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d3b70-252">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="d3b70-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="d3b70-253">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="d3b70-253">Need examples?</span></span> <span data-ttu-id="d3b70-254">Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="d3b70-254">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="d3b70-255">Du kan validera SPF-posten genom att använda någon av dessa[SPF-verifierings verktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d3b70-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="d3b70-256">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="d3b70-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="d3b70-257">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d3b70-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d3b70-258">På sidan **resurser** väljer du **värd zoner**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d3b70-259">Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** .</span><span class="sxs-lookup"><span data-stu-id="d3b70-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d3b70-260">Välj **txt** -postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="d3b70-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="d3b70-p115">Tryck på Retur på tangentbordet om du vill skapa en ny rad i området **Edit Record Set** i slutet av den aktuella inmatningen i rutan **Value:** för den befintliga posten. Skriv eller kopiera och klistra sedan in värdet från följande tabell på den nya raden (under det befintliga värdet). (Du kan se ett exempel i bilden under tabellen.)</span><span class="sxs-lookup"><span data-stu-id="d3b70-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="d3b70-264">**Värde:**</span><span class="sxs-lookup"><span data-stu-id="d3b70-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="d3b70-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d3b70-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d3b70-p116">(Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.)  </span><span class="sxs-lookup"><span data-stu-id="d3b70-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="d3b70-268">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="d3b70-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="d3b70-270">Välj **Save Record set**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="d3b70-272">Lägga till de två SRV-poster som krävs för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d3b70-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="d3b70-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b70-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d3b70-p117">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="d3b70-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d3b70-276">På sidan **resurser** väljer du **värd zoner**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d3b70-277">Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** .</span><span class="sxs-lookup"><span data-stu-id="d3b70-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d3b70-278">Välj **skapa post uppsättning**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d3b70-279">Lägg till den första SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="d3b70-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="d3b70-280">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="d3b70-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d3b70-281">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="d3b70-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d3b70-282">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-282">**Name**</span></span>|<span data-ttu-id="d3b70-283">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-283">**Type**</span></span>|<span data-ttu-id="d3b70-284">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d3b70-284">**Alias**</span></span>|<span data-ttu-id="d3b70-285">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="d3b70-286">**Värde**</span><span class="sxs-lookup"><span data-stu-id="d3b70-286">**Value**</span></span>|<span data-ttu-id="d3b70-287">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d3b70-288">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="d3b70-288">_sip._tls</span></span>|<span data-ttu-id="d3b70-289">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="d3b70-289">SRV - Service locator</span></span>|<span data-ttu-id="d3b70-290">No</span><span class="sxs-lookup"><span data-stu-id="d3b70-290">No</span></span>|<span data-ttu-id="d3b70-291">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-291">300</span></span>|<span data-ttu-id="d3b70-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d3b70-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="d3b70-293">**Det här värdet måste sluta med en punkt (.)**></span><span class="sxs-lookup"><span data-stu-id="d3b70-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="d3b70-294">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="d3b70-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d3b70-295">Enkelt</span><span class="sxs-lookup"><span data-stu-id="d3b70-295">Simple</span></span>|
    |<span data-ttu-id="d3b70-296">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="d3b70-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="d3b70-297">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="d3b70-297">SRV - Service locator</span></span>|<span data-ttu-id="d3b70-298">No</span><span class="sxs-lookup"><span data-stu-id="d3b70-298">No</span></span>|<span data-ttu-id="d3b70-299">300</span><span class="sxs-lookup"><span data-stu-id="d3b70-299">300</span></span>|<span data-ttu-id="d3b70-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d3b70-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="d3b70-301">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="d3b70-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="d3b70-302">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="d3b70-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d3b70-303">Enkelt</span><span class="sxs-lookup"><span data-stu-id="d3b70-303">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="d3b70-305">Välj **skapa**.</span><span class="sxs-lookup"><span data-stu-id="d3b70-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="d3b70-307">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="d3b70-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="d3b70-308">På sidan **Hosted Zones** väljer du **create Record set**, skapar en post med värdena från nästa rad i tabellen och väljer sedan **igen för att** slutföra den posten.</span><span class="sxs-lookup"><span data-stu-id="d3b70-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d3b70-p120">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d3b70-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
