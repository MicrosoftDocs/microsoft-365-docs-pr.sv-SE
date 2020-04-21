---
title: Skapa DNS-poster på eNomCentral för Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på eNomCentral för Microsoft.
ms.openlocfilehash: 33231896b69c0883bc9af3153fa57533096a1a0f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629581"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="421a0-103">Skapa DNS-poster på eNomCentral för Microsoft</span><span class="sxs-lookup"><span data-stu-id="421a0-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="421a0-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="421a0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="421a0-105">Om eNomCentral är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="421a0-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="421a0-106">När du har lagt till dessa poster på eNomCentral konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="421a0-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="421a0-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="421a0-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="421a0-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="421a0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="421a0-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="421a0-111">Add a TXT record for verification</span></span>
<span data-ttu-id="421a0-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="421a0-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="421a0-113">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="421a0-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="421a0-114">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="421a0-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="421a0-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="421a0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="421a0-117">Följ stegen nedan eller [titta på videon (börja vid 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="421a0-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="421a0-p104">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="421a0-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="421a0-121">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="421a0-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="421a0-123">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="421a0-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verifiera-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="421a0-125">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="421a0-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="421a0-126">(Välj värdet **Posttyp** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="421a0-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="421a0-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="421a0-127">**Host Name**</span></span> <br/> |<span data-ttu-id="421a0-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="421a0-128">**Record Type**</span></span> <br/> |<span data-ttu-id="421a0-129">**Adress**</span><span class="sxs-lookup"><span data-stu-id="421a0-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="421a0-130">TXT</span><span class="sxs-lookup"><span data-stu-id="421a0-130">TXT</span></span>  <br/> |<span data-ttu-id="421a0-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="421a0-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="421a0-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="421a0-132">**Note:** This is an example.</span></span> <span data-ttu-id="421a0-133">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="421a0-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="421a0-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="421a0-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verifiera-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="421a0-136">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="421a0-136">Select **save**.</span></span>
    
    ![eNom-BP-Verifiera-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="421a0-138">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="421a0-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="421a0-139">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 ska söka efter posten.</span><span class="sxs-lookup"><span data-stu-id="421a0-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="421a0-140">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="421a0-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="421a0-141">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="421a0-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="421a0-142">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="421a0-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="421a0-143">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="421a0-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="421a0-144">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="421a0-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="421a0-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="421a0-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="421a0-148">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="421a0-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="421a0-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="421a0-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="421a0-150">Följ stegen nedan eller [titta på videon (börja vid 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="421a0-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="421a0-p107">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="421a0-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="421a0-154">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="421a0-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="421a0-156">I listrutan **Manage Domain** väljer du **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="421a0-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-Konfigurera-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="421a0-158">I listrutan **Service Selection** väljer du **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="421a0-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-Konfigurera-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="421a0-160">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="421a0-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="421a0-161">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="421a0-161">**Host Name**</span></span>|<span data-ttu-id="421a0-162">**Address (adress)**</span><span class="sxs-lookup"><span data-stu-id="421a0-162">**Address**</span></span>|<span data-ttu-id="421a0-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="421a0-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="421a0-164">*\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="421a0-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="421a0-165">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="421a0-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="421a0-166">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="421a0-166">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="421a0-167">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="421a0-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="421a0-168">10</span><span class="sxs-lookup"><span data-stu-id="421a0-168">10</span></span>  <br/> <span data-ttu-id="421a0-169">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="421a0-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-Konfigurera-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="421a0-171">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="421a0-171">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="421a0-173">Om det finns andra befintliga MX-poster väljer du dem genom att markera kryssrutorna för posterna.</span><span class="sxs-lookup"><span data-stu-id="421a0-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-Konfigurera-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="421a0-175">Markera **ta bort markerat**.</span><span class="sxs-lookup"><span data-stu-id="421a0-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-Konfigurera-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="421a0-177">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="421a0-177">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="421a0-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="421a0-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="421a0-179">Följ stegen nedan eller [titta på videon (börja vid 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="421a0-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="421a0-p109">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="421a0-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="421a0-183">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="421a0-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="421a0-185">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="421a0-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="421a0-187">Välj **ny rad**.</span><span class="sxs-lookup"><span data-stu-id="421a0-187">Select **new row**.</span></span>
    
    ![eNom-BP-Konfigurera-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="421a0-189">I rutorna för de sex nya posterna skriver du in, eller kopierar och klistrar in, följande värden.</span><span class="sxs-lookup"><span data-stu-id="421a0-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="421a0-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="421a0-190">**Host Name**</span></span>|<span data-ttu-id="421a0-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="421a0-191">**Record Type**</span></span>|<span data-ttu-id="421a0-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="421a0-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="421a0-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="421a0-193">autodiscover</span></span>  <br/> |<span data-ttu-id="421a0-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="421a0-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="421a0-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="421a0-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="421a0-196">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="421a0-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="421a0-197">sip</span><span class="sxs-lookup"><span data-stu-id="421a0-197">sip</span></span>  <br/> |<span data-ttu-id="421a0-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="421a0-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="421a0-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="421a0-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="421a0-200">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="421a0-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="421a0-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="421a0-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="421a0-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="421a0-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="421a0-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="421a0-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="421a0-204">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="421a0-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="421a0-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="421a0-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="421a0-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="421a0-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="421a0-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="421a0-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="421a0-208">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="421a0-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="421a0-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="421a0-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="421a0-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="421a0-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="421a0-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="421a0-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="421a0-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="421a0-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Konfigurera-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="421a0-214">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="421a0-214">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="421a0-216">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="421a0-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="421a0-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="421a0-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="421a0-218">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="421a0-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="421a0-219">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="421a0-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="421a0-220">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="421a0-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="421a0-221">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="421a0-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="421a0-222">Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="421a0-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="421a0-p111">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="421a0-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="421a0-226">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="421a0-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="421a0-228">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="421a0-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="421a0-230">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="421a0-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="421a0-231">(Välj värdet **Posttyp** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="421a0-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="421a0-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="421a0-232">**Host Name**</span></span>|<span data-ttu-id="421a0-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="421a0-233">**Record Type**</span></span>|<span data-ttu-id="421a0-234">**Address**</span><span class="sxs-lookup"><span data-stu-id="421a0-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="421a0-235">TXT</span><span class="sxs-lookup"><span data-stu-id="421a0-235">TXT</span></span>  <br/> |<span data-ttu-id="421a0-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="421a0-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="421a0-237">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="421a0-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-Konfigurera-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="421a0-239">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="421a0-239">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="421a0-241">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="421a0-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="421a0-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="421a0-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="421a0-243">Följ stegen nedan eller [titta på videon (börja vid 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="421a0-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="421a0-p112">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="421a0-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="421a0-247">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="421a0-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="421a0-249">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="421a0-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="421a0-251">Till höger om **den nya raden**väljer du Lägg till **SRV- eller SPF-post**.</span><span class="sxs-lookup"><span data-stu-id="421a0-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-Konfigurera-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="421a0-253">I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="421a0-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="421a0-254">**Service**</span><span class="sxs-lookup"><span data-stu-id="421a0-254">**Service**</span></span>|<span data-ttu-id="421a0-255">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="421a0-255">**Protocol**</span></span>|<span data-ttu-id="421a0-256">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="421a0-256">**Priority**</span></span>|<span data-ttu-id="421a0-257">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="421a0-257">**Weight**</span></span>|<span data-ttu-id="421a0-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="421a0-258">**Port**</span></span>|<span data-ttu-id="421a0-259">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="421a0-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="421a0-260">_sip</span><span class="sxs-lookup"><span data-stu-id="421a0-260">_sip</span></span>  <br/> |<span data-ttu-id="421a0-261">_tls</span><span class="sxs-lookup"><span data-stu-id="421a0-261">_tls</span></span>  <br/> |<span data-ttu-id="421a0-262">100</span><span class="sxs-lookup"><span data-stu-id="421a0-262">100</span></span>  <br/> |<span data-ttu-id="421a0-263">1</span><span class="sxs-lookup"><span data-stu-id="421a0-263">1</span></span>  <br/> |<span data-ttu-id="421a0-264">443</span><span class="sxs-lookup"><span data-stu-id="421a0-264">443</span></span>  <br/> |<span data-ttu-id="421a0-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="421a0-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="421a0-266">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="421a0-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="421a0-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="421a0-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="421a0-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="421a0-268">_tcp</span></span>  <br/> |<span data-ttu-id="421a0-269">100</span><span class="sxs-lookup"><span data-stu-id="421a0-269">100</span></span>  <br/> |<span data-ttu-id="421a0-270">1</span><span class="sxs-lookup"><span data-stu-id="421a0-270">1</span></span>  <br/> |<span data-ttu-id="421a0-271">5061</span><span class="sxs-lookup"><span data-stu-id="421a0-271">5061</span></span>  <br/> |<span data-ttu-id="421a0-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="421a0-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="421a0-273">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="421a0-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Konfigurera-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="421a0-275">Välj **spara**</span><span class="sxs-lookup"><span data-stu-id="421a0-275">Select **save**</span></span>
    
    ![eNom-BP-Konfigurera-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="421a0-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="421a0-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

