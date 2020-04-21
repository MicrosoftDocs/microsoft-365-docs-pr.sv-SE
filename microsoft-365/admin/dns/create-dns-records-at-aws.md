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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Amazon Web Services (AWS) för Microsoft.
ms.openlocfilehash: 086a5d7210d2c722aeda701dc62a699ca0eaec87
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629737"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="eec79-103">Skapa DNS-poster på Amazon Web Services (AWS) för Microsoft</span><span class="sxs-lookup"><span data-stu-id="eec79-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="eec79-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="eec79-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="eec79-105">Om AWS är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype Online för företag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="eec79-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="eec79-106">När du har lagt till dessa poster på AWS konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="eec79-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="eec79-107">Mer information om webbhotell och DNS för webbplatser med Microsfot finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="eec79-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eec79-108">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="eec79-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="eec79-109">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="eec79-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="eec79-110">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eec79-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="eec79-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="eec79-111">Add a TXT record for verification</span></span>
<span data-ttu-id="eec79-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="eec79-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="eec79-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="eec79-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="eec79-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="eec79-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eec79-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="eec79-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="eec79-117">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="eec79-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="eec79-118">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eec79-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eec79-119">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="eec79-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="eec79-120">Välj namnet på den domän som du vill redigera i kolumnen Domännamn på sidan \*\* Värdbaserade zoner \*\* i kolumnen **Domännamn.**</span><span class="sxs-lookup"><span data-stu-id="eec79-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="eec79-121">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="eec79-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="eec79-122">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="eec79-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eec79-123">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="eec79-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="eec79-p105">Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="eec79-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eec79-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="eec79-126">**Name**</span></span> <br/> |<span data-ttu-id="eec79-127">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="eec79-127">**Type**</span></span> <br/> |<span data-ttu-id="eec79-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eec79-128">**Alias**</span></span> <br/> |<span data-ttu-id="eec79-129">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="eec79-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="eec79-130">**Värde**</span><span class="sxs-lookup"><span data-stu-id="eec79-130">**Value**</span></span> <br/> |<span data-ttu-id="eec79-131">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="eec79-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="eec79-132">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="eec79-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eec79-133">TXT - text</span><span class="sxs-lookup"><span data-stu-id="eec79-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="eec79-134">Nej</span><span class="sxs-lookup"><span data-stu-id="eec79-134">No</span></span>  <br/> |<span data-ttu-id="eec79-135">300</span><span class="sxs-lookup"><span data-stu-id="eec79-135">300</span></span>  <br/> |<span data-ttu-id="eec79-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="eec79-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="eec79-137">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="eec79-137">**Note:** This is an example.</span></span> <span data-ttu-id="eec79-138">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eec79-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="eec79-139">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="eec79-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="eec79-140">Enkelt</span><span class="sxs-lookup"><span data-stu-id="eec79-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="eec79-141">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="eec79-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="eec79-142">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="eec79-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="eec79-143">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="eec79-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="eec79-144">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="eec79-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="eec79-145">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="eec79-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="eec79-146">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="eec79-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="eec79-147">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="eec79-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="eec79-148">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="eec79-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eec79-149">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="eec79-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="eec79-150">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="eec79-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="eec79-151">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eec79-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="eec79-152">Lägg till en MX-post så att e-post för din domän kommer till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eec79-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="eec79-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="eec79-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="eec79-p108">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eec79-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eec79-156">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="eec79-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="eec79-157">Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.**</span><span class="sxs-lookup"><span data-stu-id="eec79-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="eec79-158">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="eec79-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="eec79-159">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="eec79-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eec79-160">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="eec79-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="eec79-161">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="eec79-161">**Name**</span></span>|<span data-ttu-id="eec79-162">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="eec79-162">**Type**</span></span>|<span data-ttu-id="eec79-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eec79-163">**Alias**</span></span>|<span data-ttu-id="eec79-164">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="eec79-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="eec79-165">**Värde**</span><span class="sxs-lookup"><span data-stu-id="eec79-165">**Value**</span></span>|<span data-ttu-id="eec79-166">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="eec79-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eec79-167">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="eec79-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eec79-168">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="eec79-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="eec79-169">Nej</span><span class="sxs-lookup"><span data-stu-id="eec79-169">No</span></span>  <br/> |<span data-ttu-id="eec79-170">300</span><span class="sxs-lookup"><span data-stu-id="eec79-170">300</span></span>  <br/> |<span data-ttu-id="eec79-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="eec79-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="eec79-p109">0 motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  </span><span class="sxs-lookup"><span data-stu-id="eec79-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="eec79-174">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="eec79-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="eec79-175">**Anm.:** Hämta \< *domännyckeln* \> från ditt Microsoft 365-konto.</span><span class="sxs-lookup"><span data-stu-id="eec79-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="eec79-176">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="eec79-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="eec79-177">Enkelt</span><span class="sxs-lookup"><span data-stu-id="eec79-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-Konfigurera-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="eec79-179">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="eec79-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="eec79-181">Om det finns andra MX-poster tar du bort dem.</span><span class="sxs-lookup"><span data-stu-id="eec79-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="eec79-182">AWS lagrar MX-poster som en uppsättning som kan innehålla flera poster.</span><span class="sxs-lookup"><span data-stu-id="eec79-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="eec79-183">Välj **INTE** **Ta bort postuppsättning,** eftersom det kommer att ta bort alla dina MX-poster, inklusive den du just lagt till.</span><span class="sxs-lookup"><span data-stu-id="eec79-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="eec79-184">Använd följande instruktioner i stället.</span><span class="sxs-lookup"><span data-stu-id="eec79-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="eec79-185">Välj först MX-postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="eec79-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="eec79-187">I **Edit Record Set** tar du sedan bort inaktuella MX-poster genom att markera respektive post i rutan **Value** och sedan trycka på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="eec79-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="eec79-189">Välj **Spara postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="eec79-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="eec79-191">Lägga till de fem CNAME-poster som krävs för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eec79-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="eec79-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="eec79-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="eec79-p112">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eec79-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eec79-195">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="eec79-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="eec79-196">Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.**</span><span class="sxs-lookup"><span data-stu-id="eec79-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="eec79-197">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="eec79-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="eec79-198">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="eec79-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="eec79-199">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="eec79-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="eec79-200">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="eec79-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="eec79-201">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="eec79-201">**Name**</span></span>|<span data-ttu-id="eec79-202">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="eec79-202">**Type**</span></span>|<span data-ttu-id="eec79-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eec79-203">**Alias**</span></span>|<span data-ttu-id="eec79-204">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="eec79-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="eec79-205">**Värde**</span><span class="sxs-lookup"><span data-stu-id="eec79-205">**Value**</span></span>|<span data-ttu-id="eec79-206">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="eec79-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eec79-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eec79-207">autodiscover</span></span>  <br/> |<span data-ttu-id="eec79-208">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="eec79-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="eec79-209">No</span><span class="sxs-lookup"><span data-stu-id="eec79-209">No</span></span>  <br/> |<span data-ttu-id="eec79-210">300</span><span class="sxs-lookup"><span data-stu-id="eec79-210">300</span></span>  <br/> |<span data-ttu-id="eec79-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="eec79-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="eec79-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="eec79-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eec79-213">Simple</span><span class="sxs-lookup"><span data-stu-id="eec79-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="eec79-214">sip</span><span class="sxs-lookup"><span data-stu-id="eec79-214">sip</span></span>  <br/> |<span data-ttu-id="eec79-215">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="eec79-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="eec79-216">No</span><span class="sxs-lookup"><span data-stu-id="eec79-216">No</span></span>  <br/> |<span data-ttu-id="eec79-217">300</span><span class="sxs-lookup"><span data-stu-id="eec79-217">300</span></span>  <br/> |<span data-ttu-id="eec79-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eec79-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="eec79-219">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="eec79-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eec79-220">Enkelt</span><span class="sxs-lookup"><span data-stu-id="eec79-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="eec79-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eec79-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="eec79-222">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="eec79-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="eec79-223">Nej</span><span class="sxs-lookup"><span data-stu-id="eec79-223">No</span></span>  <br/> |<span data-ttu-id="eec79-224">300</span><span class="sxs-lookup"><span data-stu-id="eec79-224">300</span></span>  <br/> |<span data-ttu-id="eec79-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eec79-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="eec79-226">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="eec79-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eec79-227">Enkelt</span><span class="sxs-lookup"><span data-stu-id="eec79-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="eec79-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="eec79-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="eec79-229">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="eec79-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="eec79-230">Nej</span><span class="sxs-lookup"><span data-stu-id="eec79-230">No</span></span>  <br/> |<span data-ttu-id="eec79-231">300</span><span class="sxs-lookup"><span data-stu-id="eec79-231">300</span></span>  <br/> |<span data-ttu-id="eec79-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="eec79-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="eec79-233">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="eec79-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eec79-234">Simple</span><span class="sxs-lookup"><span data-stu-id="eec79-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="eec79-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="eec79-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="eec79-236">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="eec79-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="eec79-237">Nej</span><span class="sxs-lookup"><span data-stu-id="eec79-237">No</span></span>  <br/> |<span data-ttu-id="eec79-238">300</span><span class="sxs-lookup"><span data-stu-id="eec79-238">300</span></span>  <br/> |<span data-ttu-id="eec79-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="eec79-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="eec79-240">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="eec79-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eec79-241">Enkelt</span><span class="sxs-lookup"><span data-stu-id="eec79-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-Konfigurera-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="eec79-243">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="eec79-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="eec79-245">Lägg till de andra fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="eec79-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="eec79-246">På sidan **Värdzoner** väljer du **Skapa postuppsättning,** skapar en post med värdena från nästa rad i tabellen och väljer sedan **Skapa** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="eec79-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="eec79-247">Upprepa den här processen tills du har skapat alla fem CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="eec79-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="eec79-248">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="eec79-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="eec79-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="eec79-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="eec79-250">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="eec79-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="eec79-251">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="eec79-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="eec79-252">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eec79-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="eec79-253">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="eec79-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="eec79-254">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="eec79-254">Need examples?</span></span> <span data-ttu-id="eec79-255">Kolla in dessa [externa domännamnssystemposter för Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="eec79-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="eec79-256">Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="eec79-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="eec79-257">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="eec79-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="eec79-258">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eec79-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eec79-259">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="eec79-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="eec79-260">Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.**</span><span class="sxs-lookup"><span data-stu-id="eec79-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="eec79-261">Välj **TXT-postuppsättningen.**</span><span class="sxs-lookup"><span data-stu-id="eec79-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="eec79-p115">Tryck på Retur på tangentbordet om du vill skapa en ny rad i området **Edit Record Set** i slutet av den aktuella inmatningen i rutan **Value:** för den befintliga posten. Skriv eller kopiera och klistra sedan in värdet från följande tabell på den nya raden (under det befintliga värdet). (Du kan se ett exempel i bilden under tabellen.)</span><span class="sxs-lookup"><span data-stu-id="eec79-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="eec79-265">**Värde:**</span><span class="sxs-lookup"><span data-stu-id="eec79-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="eec79-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="eec79-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="eec79-p116">(Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.)  </span><span class="sxs-lookup"><span data-stu-id="eec79-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="eec79-269">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="eec79-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Konfigurera-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="eec79-271">Välj **Spara postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="eec79-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="eec79-273">Lägg till de två SRV-poster som krävs för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eec79-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="eec79-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="eec79-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="eec79-p117">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="eec79-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="eec79-277">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="eec79-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="eec79-278">Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.**</span><span class="sxs-lookup"><span data-stu-id="eec79-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="eec79-279">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="eec79-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="eec79-280">Lägg till den första SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="eec79-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="eec79-281">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="eec79-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="eec79-282">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="eec79-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="eec79-283">**Name (Namn)**</span><span class="sxs-lookup"><span data-stu-id="eec79-283">**Name**</span></span>|<span data-ttu-id="eec79-284">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="eec79-284">**Type**</span></span>|<span data-ttu-id="eec79-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eec79-285">**Alias**</span></span>|<span data-ttu-id="eec79-286">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="eec79-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="eec79-287">**Värde**</span><span class="sxs-lookup"><span data-stu-id="eec79-287">**Value**</span></span>|<span data-ttu-id="eec79-288">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="eec79-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eec79-289">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="eec79-289">_sip._tls</span></span>|<span data-ttu-id="eec79-290">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="eec79-290">SRV - Service locator</span></span>|<span data-ttu-id="eec79-291">No</span><span class="sxs-lookup"><span data-stu-id="eec79-291">No</span></span>|<span data-ttu-id="eec79-292">300</span><span class="sxs-lookup"><span data-stu-id="eec79-292">300</span></span>|<span data-ttu-id="eec79-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eec79-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="eec79-294">**Det här värdet MÅSTE sluta med en punkt (.)**></span><span class="sxs-lookup"><span data-stu-id="eec79-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="eec79-295">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="eec79-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="eec79-296">Enkelt</span><span class="sxs-lookup"><span data-stu-id="eec79-296">Simple</span></span>|
    |<span data-ttu-id="eec79-297">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="eec79-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="eec79-298">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="eec79-298">SRV - Service locator</span></span>|<span data-ttu-id="eec79-299">No</span><span class="sxs-lookup"><span data-stu-id="eec79-299">No</span></span>|<span data-ttu-id="eec79-300">300</span><span class="sxs-lookup"><span data-stu-id="eec79-300">300</span></span>|<span data-ttu-id="eec79-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eec79-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="eec79-302">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="eec79-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="eec79-303">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="eec79-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="eec79-304">Enkelt</span><span class="sxs-lookup"><span data-stu-id="eec79-304">Simple</span></span>|
   
    ![AWS-BP-Konfigurera-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="eec79-306">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="eec79-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="eec79-308">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="eec79-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="eec79-309">På sidan **Värdzoner** väljer du **Skapa postuppsättning,** skapar en post med värdena från nästa rad i tabellen och väljer sedan **Skapa** igen för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="eec79-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="eec79-310">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="eec79-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="eec79-311">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="eec79-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="eec79-312">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eec79-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
