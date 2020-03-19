---
title: Skapa DNS-poster på Amazon Web Services (AWS) för Office 365
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Amazon Web Services (AWS) för Office 365.
ms.openlocfilehash: baba7bb7275303604d241166f4dc1d2af77b3f17
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42813018"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-office-365"></a><span data-ttu-id="992db-103">Skapa DNS-poster på Amazon Web Services (AWS) för Office 365</span><span class="sxs-lookup"><span data-stu-id="992db-103">Create DNS records at Amazon Web Services (AWS) for Office 365</span></span>

 <span data-ttu-id="992db-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="992db-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="992db-105">Om AWS är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype Online för företag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="992db-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="992db-106">När du har lagt till dessa poster i AWS är domänen konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="992db-106">After you add these records at AWS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="992db-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="992db-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="992db-p101">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="992db-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="992db-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="992db-111">Add a TXT record for verification</span></span>
<span data-ttu-id="992db-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="992db-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="992db-p102">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="992db-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="992db-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="992db-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="992db-117">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="992db-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="992db-118">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="992db-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="992db-119">Välj **Värdbaserade zoner**på sidan **Resurser** .</span><span class="sxs-lookup"><span data-stu-id="992db-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="992db-120">Markera namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan \*\* Värdbaserade zoner \*\* .</span><span class="sxs-lookup"><span data-stu-id="992db-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="992db-121">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="992db-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="992db-122">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="992db-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="992db-123">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="992db-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="992db-p105">Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="992db-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="992db-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="992db-126">**Name**</span></span> <br/> |<span data-ttu-id="992db-127">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="992db-127">**Type**</span></span> <br/> |<span data-ttu-id="992db-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="992db-128">**Alias**</span></span> <br/> |<span data-ttu-id="992db-129">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="992db-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="992db-130">**Värde**</span><span class="sxs-lookup"><span data-stu-id="992db-130">**Value**</span></span> <br/> |<span data-ttu-id="992db-131">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="992db-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="992db-132">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="992db-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="992db-133">TXT - text</span><span class="sxs-lookup"><span data-stu-id="992db-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="992db-134">Nej</span><span class="sxs-lookup"><span data-stu-id="992db-134">No</span></span>  <br/> |<span data-ttu-id="992db-135">300</span><span class="sxs-lookup"><span data-stu-id="992db-135">300</span></span>  <br/> |<span data-ttu-id="992db-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="992db-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="992db-137">**Obs:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="992db-137">**Note:** This is an example.</span></span> <span data-ttu-id="992db-138">Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="992db-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="992db-139">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="992db-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="992db-140">Enkelt</span><span class="sxs-lookup"><span data-stu-id="992db-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="992db-141">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="992db-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="992db-142">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="992db-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="992db-143">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="992db-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="992db-144">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="992db-144">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="992db-145">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="992db-145">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="992db-146">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="992db-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="992db-147">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="992db-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="992db-148">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="992db-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="992db-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="992db-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="992db-152">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="992db-152">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="992db-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="992db-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="992db-p108">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="992db-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="992db-156">Välj **Värdbaserade zoner**på sidan **Resurser** .</span><span class="sxs-lookup"><span data-stu-id="992db-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="992db-157">Markera namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdbaserade zoner.**</span><span class="sxs-lookup"><span data-stu-id="992db-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="992db-158">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="992db-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="992db-159">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="992db-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="992db-160">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="992db-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="992db-161">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="992db-161">**Name**</span></span>|<span data-ttu-id="992db-162">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="992db-162">**Type**</span></span>|<span data-ttu-id="992db-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="992db-163">**Alias**</span></span>|<span data-ttu-id="992db-164">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="992db-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="992db-165">**Värde**</span><span class="sxs-lookup"><span data-stu-id="992db-165">**Value**</span></span>|<span data-ttu-id="992db-166">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="992db-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="992db-167">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="992db-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="992db-168">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="992db-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="992db-169">Nej</span><span class="sxs-lookup"><span data-stu-id="992db-169">No</span></span>  <br/> |<span data-ttu-id="992db-170">300</span><span class="sxs-lookup"><span data-stu-id="992db-170">300</span></span>  <br/> |<span data-ttu-id="992db-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="992db-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="992db-p109">0 motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="992db-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="992db-174">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="992db-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="992db-175">**Obs:** Hämta \<din domännyckel\> från ditt Office 365-konto. *domain-key*</span><span class="sxs-lookup"><span data-stu-id="992db-175">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="992db-176">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="992db-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="992db-177">Enkelt</span><span class="sxs-lookup"><span data-stu-id="992db-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-Konfigurera-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="992db-179">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="992db-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="992db-181">Om det finns andra MX-poster tar du bort dem.</span><span class="sxs-lookup"><span data-stu-id="992db-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="992db-182">AWS lagrar MX-poster som en uppsättning som kan innehålla flera poster.</span><span class="sxs-lookup"><span data-stu-id="992db-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="992db-183">**Välj INTE** **Ta bort postuppsättning,** eftersom det tar bort alla MX-poster, inklusive den du just lagt till.</span><span class="sxs-lookup"><span data-stu-id="992db-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="992db-184">Använd följande instruktioner i stället.</span><span class="sxs-lookup"><span data-stu-id="992db-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="992db-185">Välj först MX-postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="992db-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="992db-187">I **Edit Record Set** tar du sedan bort inaktuella MX-poster genom att markera respektive post i rutan **Value** och sedan trycka på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="992db-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="992db-189">Välj **Spara postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="992db-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="992db-191">Lägga till de fem CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="992db-191">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="992db-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="992db-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="992db-p112">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="992db-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="992db-195">Välj **Värdbaserade zoner**på sidan **Resurser** .</span><span class="sxs-lookup"><span data-stu-id="992db-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="992db-196">Markera namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdbaserade zoner.**</span><span class="sxs-lookup"><span data-stu-id="992db-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="992db-197">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="992db-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="992db-198">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="992db-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="992db-199">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="992db-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="992db-200">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="992db-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="992db-201">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="992db-201">**Name**</span></span>|<span data-ttu-id="992db-202">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="992db-202">**Type**</span></span>|<span data-ttu-id="992db-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="992db-203">**Alias**</span></span>|<span data-ttu-id="992db-204">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="992db-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="992db-205">**Värde**</span><span class="sxs-lookup"><span data-stu-id="992db-205">**Value**</span></span>|<span data-ttu-id="992db-206">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="992db-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="992db-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="992db-207">autodiscover</span></span>  <br/> |<span data-ttu-id="992db-208">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="992db-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="992db-209">No</span><span class="sxs-lookup"><span data-stu-id="992db-209">No</span></span>  <br/> |<span data-ttu-id="992db-210">300</span><span class="sxs-lookup"><span data-stu-id="992db-210">300</span></span>  <br/> |<span data-ttu-id="992db-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="992db-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="992db-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="992db-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="992db-213">Enkelt</span><span class="sxs-lookup"><span data-stu-id="992db-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="992db-214">sip</span><span class="sxs-lookup"><span data-stu-id="992db-214">sip</span></span>  <br/> |<span data-ttu-id="992db-215">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="992db-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="992db-216">No</span><span class="sxs-lookup"><span data-stu-id="992db-216">No</span></span>  <br/> |<span data-ttu-id="992db-217">300</span><span class="sxs-lookup"><span data-stu-id="992db-217">300</span></span>  <br/> |<span data-ttu-id="992db-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="992db-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="992db-219">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="992db-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="992db-220">Simple</span><span class="sxs-lookup"><span data-stu-id="992db-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="992db-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="992db-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="992db-222">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="992db-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="992db-223">Nej</span><span class="sxs-lookup"><span data-stu-id="992db-223">No</span></span>  <br/> |<span data-ttu-id="992db-224">300</span><span class="sxs-lookup"><span data-stu-id="992db-224">300</span></span>  <br/> |<span data-ttu-id="992db-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="992db-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="992db-226">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="992db-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="992db-227">Enkelt</span><span class="sxs-lookup"><span data-stu-id="992db-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="992db-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="992db-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="992db-229">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="992db-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="992db-230">Nej</span><span class="sxs-lookup"><span data-stu-id="992db-230">No</span></span>  <br/> |<span data-ttu-id="992db-231">300</span><span class="sxs-lookup"><span data-stu-id="992db-231">300</span></span>  <br/> |<span data-ttu-id="992db-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="992db-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="992db-233">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="992db-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="992db-234">Simple</span><span class="sxs-lookup"><span data-stu-id="992db-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="992db-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="992db-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="992db-236">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="992db-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="992db-237">Nej</span><span class="sxs-lookup"><span data-stu-id="992db-237">No</span></span>  <br/> |<span data-ttu-id="992db-238">300</span><span class="sxs-lookup"><span data-stu-id="992db-238">300</span></span>  <br/> |<span data-ttu-id="992db-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="992db-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="992db-240">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="992db-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="992db-241">Enkelt</span><span class="sxs-lookup"><span data-stu-id="992db-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-Konfigurera-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="992db-243">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="992db-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="992db-245">Lägg till de andra fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="992db-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="992db-246">På sidan **Värdbaserade zoner** väljer du **Skapa postuppsättning,** skapar en post med värdena från nästa rad i tabellen och väljer sedan igen **Skapa** för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="992db-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="992db-247">Upprepa den här processen tills du har skapat alla fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="992db-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="992db-248">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="992db-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="992db-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="992db-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="992db-250">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="992db-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="992db-251">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="992db-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="992db-252">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="992db-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="992db-253">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="992db-253">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="992db-254">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="992db-254">Need examples?</span></span> <span data-ttu-id="992db-255">Kolla in dessa [externa domännamnssystemposter för Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="992db-255">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="992db-256">Om du vill validera din SPF-post kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="992db-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="992db-257">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="992db-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="992db-258">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="992db-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="992db-259">Välj **Värdbaserade zoner**på sidan **Resurser** .</span><span class="sxs-lookup"><span data-stu-id="992db-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="992db-260">Markera namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdbaserade zoner.**</span><span class="sxs-lookup"><span data-stu-id="992db-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="992db-261">Markera **TXT-postuppsättningen.**</span><span class="sxs-lookup"><span data-stu-id="992db-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="992db-p115">Tryck på Retur på tangentbordet om du vill skapa en ny rad i området **Edit Record Set** i slutet av den aktuella inmatningen i rutan **Value:** för den befintliga posten. Skriv eller kopiera och klistra sedan in värdet från följande tabell på den nya raden (under det befintliga värdet). (Du kan se ett exempel i bilden under tabellen.)</span><span class="sxs-lookup"><span data-stu-id="992db-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="992db-265">**Värde:**</span><span class="sxs-lookup"><span data-stu-id="992db-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="992db-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="992db-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="992db-p116">(Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.)  </span><span class="sxs-lookup"><span data-stu-id="992db-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="992db-269">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="992db-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Konfigurera-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="992db-271">Välj **Spara postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="992db-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="992db-273">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="992db-273">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="992db-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="992db-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="992db-p117">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="992db-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="992db-277">Välj **Värdbaserade zoner**på sidan **Resurser** .</span><span class="sxs-lookup"><span data-stu-id="992db-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="992db-278">Markera namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdbaserade zoner.**</span><span class="sxs-lookup"><span data-stu-id="992db-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="992db-279">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="992db-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="992db-280">Lägg till den första SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="992db-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="992db-281">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="992db-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="992db-282">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="992db-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="992db-283">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="992db-283">**Name**</span></span>|<span data-ttu-id="992db-284">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="992db-284">**Type**</span></span>|<span data-ttu-id="992db-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="992db-285">**Alias**</span></span>|<span data-ttu-id="992db-286">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="992db-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="992db-287">**Värde**</span><span class="sxs-lookup"><span data-stu-id="992db-287">**Value**</span></span>|<span data-ttu-id="992db-288">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="992db-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="992db-289">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="992db-289">_sip._tls</span></span>|<span data-ttu-id="992db-290">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="992db-290">SRV - Service locator</span></span>|<span data-ttu-id="992db-291">No</span><span class="sxs-lookup"><span data-stu-id="992db-291">No</span></span>|<span data-ttu-id="992db-292">300</span><span class="sxs-lookup"><span data-stu-id="992db-292">300</span></span>|<span data-ttu-id="992db-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="992db-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="992db-294">**Det här värdet MÅSTE sluta med en punkt (.)**></span><span class="sxs-lookup"><span data-stu-id="992db-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="992db-295">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="992db-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="992db-296">Enkelt</span><span class="sxs-lookup"><span data-stu-id="992db-296">Simple</span></span>|
    |<span data-ttu-id="992db-297">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="992db-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="992db-298">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="992db-298">SRV - Service locator</span></span>|<span data-ttu-id="992db-299">No</span><span class="sxs-lookup"><span data-stu-id="992db-299">No</span></span>|<span data-ttu-id="992db-300">300</span><span class="sxs-lookup"><span data-stu-id="992db-300">300</span></span>|<span data-ttu-id="992db-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="992db-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="992db-302">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="992db-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="992db-303">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="992db-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="992db-304">Enkelt</span><span class="sxs-lookup"><span data-stu-id="992db-304">Simple</span></span>|
   
    ![AWS-BP-Konfigurera-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="992db-306">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="992db-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="992db-308">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="992db-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="992db-309">På sidan **Värdbaserade zoner** väljer du **Skapa postuppsättning,** skapar en post med värdena från nästa rad i tabellen och väljer sedan igen **Skapa** för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="992db-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="992db-p120">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="992db-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
