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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på eNomCentral för Microsoft.
ms.openlocfilehash: 1a265f42165cd3add28b590400aa2625e098a9e6
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400491"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="dd793-103">Skapa DNS-poster på eNomCentral för Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd793-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="dd793-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="dd793-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dd793-105">Om eNomCentral är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="dd793-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="dd793-106">När du har lagt till dessa poster på eNomCentral konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="dd793-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="dd793-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dd793-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dd793-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="dd793-110">Add a TXT record for verification</span></span>
<span data-ttu-id="dd793-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dd793-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="dd793-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="dd793-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd793-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="dd793-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="dd793-116">Följ stegen nedan eller [titta på videon (börja vid 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="dd793-116">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dd793-p104">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="dd793-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dd793-120">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="dd793-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dd793-122">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="dd793-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verifiera-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="dd793-124">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="dd793-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="dd793-125">Välj värdet **Posttyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="dd793-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="dd793-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dd793-126">**Host Name**</span></span> <br/> |<span data-ttu-id="dd793-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="dd793-127">**Record Type**</span></span> <br/> |<span data-ttu-id="dd793-128">**Adress**</span><span class="sxs-lookup"><span data-stu-id="dd793-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="dd793-129">TXT</span><span class="sxs-lookup"><span data-stu-id="dd793-129">TXT</span></span>  <br/> |<span data-ttu-id="dd793-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dd793-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dd793-131">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="dd793-131">**Note:** This is an example.</span></span> <span data-ttu-id="dd793-132">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="dd793-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="dd793-133">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="dd793-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verifiera-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="dd793-135">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="dd793-135">Select **save**.</span></span>
    
    ![eNom-BP-Verifiera-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="dd793-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="dd793-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dd793-138">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="dd793-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="dd793-139">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="dd793-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dd793-140">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="dd793-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="dd793-141">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="dd793-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dd793-142">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="dd793-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dd793-143">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="dd793-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dd793-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dd793-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="dd793-147">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd793-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="dd793-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="dd793-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="dd793-149">Följ stegen nedan eller [titta på videon (börja vid 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="dd793-149">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dd793-p107">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="dd793-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dd793-153">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="dd793-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dd793-155">I listrutan **Manage Domain** väljer du **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="dd793-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-Konfigurera-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="dd793-157">I listrutan **Service Selection** väljer du **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="dd793-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-Konfigurera-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="dd793-159">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="dd793-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dd793-160">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="dd793-160">**Host Name**</span></span>|<span data-ttu-id="dd793-161">**Address (adress)**</span><span class="sxs-lookup"><span data-stu-id="dd793-161">**Address**</span></span>|<span data-ttu-id="dd793-162">**Pref**</span><span class="sxs-lookup"><span data-stu-id="dd793-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="dd793-163">*\<domain-key\>*.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="dd793-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="dd793-164">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="dd793-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="dd793-165">**Anm.:** Hämta ditt *\<domain-key\>* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="dd793-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="dd793-166">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="dd793-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="dd793-167">10</span><span class="sxs-lookup"><span data-stu-id="dd793-167">10</span></span>  <br/> <span data-ttu-id="dd793-168">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="dd793-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
       
   ![eNom-BP-Konfigurera-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="dd793-170">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="dd793-170">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="dd793-172">Om det finns andra befintliga MX-poster väljer du dem genom att markera kryssrutorna för posterna.</span><span class="sxs-lookup"><span data-stu-id="dd793-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-Konfigurera-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="dd793-174">Markera **ta bort markerat**.</span><span class="sxs-lookup"><span data-stu-id="dd793-174">Select **delete checked**.</span></span>
    
    ![eNom-BP-Konfigurera-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="dd793-176">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd793-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="dd793-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="dd793-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="dd793-178">Följ stegen nedan eller [titta på videon (börja vid 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="dd793-178">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dd793-p109">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="dd793-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dd793-182">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="dd793-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dd793-184">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="dd793-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="dd793-186">Välj **ny rad**.</span><span class="sxs-lookup"><span data-stu-id="dd793-186">Select **new row**.</span></span>
    
    ![eNom-BP-Konfigurera-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="dd793-188">I rutorna för de sex nya posterna skriver du in, eller kopierar och klistrar in, följande värden.</span><span class="sxs-lookup"><span data-stu-id="dd793-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="dd793-189">Välj värdet **Posttyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="dd793-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="dd793-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dd793-190">**Host Name**</span></span>|<span data-ttu-id="dd793-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="dd793-191">**Record Type**</span></span>|<span data-ttu-id="dd793-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="dd793-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dd793-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dd793-193">autodiscover</span></span>  <br/> |<span data-ttu-id="dd793-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="dd793-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dd793-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="dd793-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="dd793-196">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="dd793-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dd793-197">sip</span><span class="sxs-lookup"><span data-stu-id="dd793-197">sip</span></span>  <br/> |<span data-ttu-id="dd793-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="dd793-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dd793-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dd793-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dd793-200">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="dd793-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dd793-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dd793-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dd793-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="dd793-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dd793-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dd793-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dd793-204">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="dd793-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dd793-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dd793-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dd793-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="dd793-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dd793-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="dd793-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="dd793-208">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="dd793-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dd793-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dd793-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dd793-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="dd793-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dd793-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="dd793-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="dd793-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="dd793-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="dd793-213">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="dd793-213">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dd793-215">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="dd793-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dd793-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="dd793-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd793-217">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="dd793-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dd793-218">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="dd793-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dd793-219">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd793-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="dd793-220">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="dd793-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="dd793-221">Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="dd793-221">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dd793-p111">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="dd793-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dd793-225">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="dd793-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dd793-227">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="dd793-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="dd793-229">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="dd793-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="dd793-230">Välj värdet **Posttyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="dd793-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="dd793-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dd793-231">**Host Name**</span></span>|<span data-ttu-id="dd793-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="dd793-232">**Record Type**</span></span>|<span data-ttu-id="dd793-233">**Adress**</span><span class="sxs-lookup"><span data-stu-id="dd793-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="dd793-234">TXT</span><span class="sxs-lookup"><span data-stu-id="dd793-234">TXT</span></span>  <br/> |<span data-ttu-id="dd793-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dd793-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="dd793-236">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="dd793-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-Konfigurera-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="dd793-238">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="dd793-238">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="dd793-240">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd793-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="dd793-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="dd793-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="dd793-242">Följ stegen nedan eller [titta på videon (börja vid 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="dd793-242">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dd793-p112">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="dd793-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dd793-246">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="dd793-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dd793-248">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="dd793-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="dd793-250">Till höger om **den nya raden**väljer du Lägg till **SRV- eller SPF-post**.</span><span class="sxs-lookup"><span data-stu-id="dd793-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-Konfigurera-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="dd793-252">I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="dd793-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dd793-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="dd793-253">**Service**</span></span>|<span data-ttu-id="dd793-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="dd793-254">**Protocol**</span></span>|<span data-ttu-id="dd793-255">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="dd793-255">**Priority**</span></span>|<span data-ttu-id="dd793-256">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="dd793-256">**Weight**</span></span>|<span data-ttu-id="dd793-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="dd793-257">**Port**</span></span>|<span data-ttu-id="dd793-258">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="dd793-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dd793-259">_sip</span><span class="sxs-lookup"><span data-stu-id="dd793-259">_sip</span></span>  <br/> |<span data-ttu-id="dd793-260">_tls</span><span class="sxs-lookup"><span data-stu-id="dd793-260">_tls</span></span>  <br/> |<span data-ttu-id="dd793-261">100</span><span class="sxs-lookup"><span data-stu-id="dd793-261">100</span></span>  <br/> |<span data-ttu-id="dd793-262">1</span><span class="sxs-lookup"><span data-stu-id="dd793-262">1</span></span>  <br/> |<span data-ttu-id="dd793-263">443</span><span class="sxs-lookup"><span data-stu-id="dd793-263">443</span></span>  <br/> |<span data-ttu-id="dd793-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dd793-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dd793-265">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="dd793-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dd793-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="dd793-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="dd793-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="dd793-267">_tcp</span></span>  <br/> |<span data-ttu-id="dd793-268">100</span><span class="sxs-lookup"><span data-stu-id="dd793-268">100</span></span>  <br/> |<span data-ttu-id="dd793-269">1</span><span class="sxs-lookup"><span data-stu-id="dd793-269">1</span></span>  <br/> |<span data-ttu-id="dd793-270">5061</span><span class="sxs-lookup"><span data-stu-id="dd793-270">5061</span></span>  <br/> |<span data-ttu-id="dd793-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dd793-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="dd793-272">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="dd793-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Konfigurera-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="dd793-274">Välj **spara**</span><span class="sxs-lookup"><span data-stu-id="dd793-274">Select **save**</span></span>
    
    ![eNom-BP-Konfigurera-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="dd793-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dd793-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

