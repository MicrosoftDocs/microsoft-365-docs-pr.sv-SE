---
title: Skapa DNS-poster på eNomCentral för Office 365
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på eNomCentral för Office 365.
ms.openlocfilehash: dec76e0dde2775851ff464e3b8765f82dfb57625
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809396"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a><span data-ttu-id="96493-103">Skapa DNS-poster på eNomCentral för Office 365</span><span class="sxs-lookup"><span data-stu-id="96493-103">Create DNS records at eNomCentral for Office 365</span></span>

 <span data-ttu-id="96493-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="96493-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="96493-105">Om eNomCentral är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="96493-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="96493-106">När du har lagt till dessa poster på eNomCentral är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="96493-106">After you add these records at eNomCentral, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="96493-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="96493-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="96493-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="96493-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="96493-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="96493-111">Add a TXT record for verification</span></span>
<span data-ttu-id="96493-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="96493-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="96493-p102">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="96493-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96493-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="96493-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="96493-117">Följ stegen nedan eller [titta på videon (börja vid 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="96493-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="96493-p104">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="96493-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="96493-121">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="96493-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="96493-123">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="96493-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verifiera-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="96493-125">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="96493-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="96493-126">(Välj värdet **Posttyp** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="96493-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="96493-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="96493-127">**Host Name**</span></span> <br/> |<span data-ttu-id="96493-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="96493-128">**Record Type**</span></span> <br/> |<span data-ttu-id="96493-129">**Adress**</span><span class="sxs-lookup"><span data-stu-id="96493-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="96493-130">TXT</span><span class="sxs-lookup"><span data-stu-id="96493-130">TXT</span></span>  <br/> |<span data-ttu-id="96493-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="96493-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="96493-p105">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="96493-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![eNom-BP-Verifiera-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="96493-136">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="96493-136">Select **save**.</span></span>
    
    ![eNom-BP-Verifiera-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="96493-138">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="96493-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="96493-139">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="96493-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="96493-140">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="96493-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="96493-141">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="96493-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="96493-142">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="96493-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="96493-143">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="96493-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="96493-144">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="96493-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="96493-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="96493-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="96493-148">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="96493-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="96493-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="96493-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="96493-150">Följ stegen nedan eller [titta på videon (börja vid 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="96493-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="96493-p107">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="96493-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="96493-154">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="96493-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="96493-156">I listrutan **Manage Domain** väljer du **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="96493-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-Konfigurera-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="96493-158">I listrutan **Service Selection** väljer du **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="96493-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-Konfigurera-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="96493-160">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="96493-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="96493-161">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="96493-161">**Host Name**</span></span>|<span data-ttu-id="96493-162">**Address (adress)**</span><span class="sxs-lookup"><span data-stu-id="96493-162">**Address**</span></span>|<span data-ttu-id="96493-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="96493-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="96493-164">*\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="96493-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="96493-165">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="96493-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="96493-166">**Obs:** Hämta din \* \<domännyckel\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="96493-166">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="96493-167">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="96493-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="96493-168">10</span><span class="sxs-lookup"><span data-stu-id="96493-168">10</span></span>  <br/> <span data-ttu-id="96493-169">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="96493-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-Konfigurera-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="96493-171">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="96493-171">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="96493-173">Om det finns andra befintliga MX-poster väljer du dem genom att markera kryssrutorna för posterna.</span><span class="sxs-lookup"><span data-stu-id="96493-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-Konfigurera-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="96493-175">Välj **ta bort markerat**.</span><span class="sxs-lookup"><span data-stu-id="96493-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-Konfigurera-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="96493-177">Lägg till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="96493-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="96493-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="96493-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="96493-179">Följ stegen nedan eller [titta på videon (börja vid 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="96493-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="96493-p109">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="96493-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="96493-183">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="96493-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="96493-185">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="96493-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="96493-187">Välj **ny rad**.</span><span class="sxs-lookup"><span data-stu-id="96493-187">Select **new row**.</span></span>
    
    ![eNom-BP-Konfigurera-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="96493-189">I rutorna för de sex nya posterna skriver du in, eller kopierar och klistrar in, följande värden.</span><span class="sxs-lookup"><span data-stu-id="96493-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="96493-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="96493-190">**Host Name**</span></span>|<span data-ttu-id="96493-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="96493-191">**Record Type**</span></span>|<span data-ttu-id="96493-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="96493-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="96493-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="96493-193">autodiscover</span></span>  <br/> |<span data-ttu-id="96493-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="96493-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="96493-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="96493-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="96493-196">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="96493-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="96493-197">sip</span><span class="sxs-lookup"><span data-stu-id="96493-197">sip</span></span>  <br/> |<span data-ttu-id="96493-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="96493-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="96493-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="96493-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="96493-200">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="96493-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="96493-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="96493-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="96493-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="96493-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="96493-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="96493-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="96493-204">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="96493-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="96493-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="96493-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="96493-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="96493-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="96493-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="96493-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="96493-208">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="96493-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="96493-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="96493-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="96493-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="96493-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="96493-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="96493-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="96493-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="96493-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Konfigurera-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="96493-214">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="96493-214">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="96493-216">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="96493-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="96493-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="96493-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="96493-218">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="96493-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="96493-219">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="96493-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="96493-220">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="96493-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="96493-221">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="96493-221">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="96493-222">Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="96493-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="96493-p111">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="96493-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="96493-226">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="96493-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="96493-228">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="96493-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="96493-230">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="96493-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="96493-231">(Välj värdet **Posttyp** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="96493-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="96493-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="96493-232">**Host Name**</span></span>|<span data-ttu-id="96493-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="96493-233">**Record Type**</span></span>|<span data-ttu-id="96493-234">**Address**</span><span class="sxs-lookup"><span data-stu-id="96493-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="96493-235">TXT</span><span class="sxs-lookup"><span data-stu-id="96493-235">TXT</span></span>  <br/> |<span data-ttu-id="96493-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="96493-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="96493-237">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="96493-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-Konfigurera-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="96493-239">Välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="96493-239">Select **save**.</span></span>
    
    ![eNom-BP-Konfigurera-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="96493-241">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="96493-241">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="96493-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="96493-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="96493-243">Följ stegen nedan eller [titta på videon (börja vid 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="96493-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="96493-p112">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="96493-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Konfigurera-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="96493-247">Under **mina domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="96493-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Konfigurera-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="96493-249">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="96493-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Konfigurera-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="96493-251">Till höger om **den nya raden**väljer du Lägg till **SRV- eller SPF-post**.</span><span class="sxs-lookup"><span data-stu-id="96493-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-Konfigurera-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="96493-253">I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="96493-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="96493-254">**Service**</span><span class="sxs-lookup"><span data-stu-id="96493-254">**Service**</span></span>|<span data-ttu-id="96493-255">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="96493-255">**Protocol**</span></span>|<span data-ttu-id="96493-256">**Priority**</span><span class="sxs-lookup"><span data-stu-id="96493-256">**Priority**</span></span>|<span data-ttu-id="96493-257">**Weight**</span><span class="sxs-lookup"><span data-stu-id="96493-257">**Weight**</span></span>|<span data-ttu-id="96493-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="96493-258">**Port**</span></span>|<span data-ttu-id="96493-259">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="96493-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="96493-260">_sip</span><span class="sxs-lookup"><span data-stu-id="96493-260">_sip</span></span>  <br/> |<span data-ttu-id="96493-261">_tls</span><span class="sxs-lookup"><span data-stu-id="96493-261">_tls</span></span>  <br/> |<span data-ttu-id="96493-262">100</span><span class="sxs-lookup"><span data-stu-id="96493-262">100</span></span>  <br/> |<span data-ttu-id="96493-263">1</span><span class="sxs-lookup"><span data-stu-id="96493-263">1</span></span>  <br/> |<span data-ttu-id="96493-264">443</span><span class="sxs-lookup"><span data-stu-id="96493-264">443</span></span>  <br/> |<span data-ttu-id="96493-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="96493-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="96493-266">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="96493-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="96493-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="96493-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="96493-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="96493-268">_tcp</span></span>  <br/> |<span data-ttu-id="96493-269">100</span><span class="sxs-lookup"><span data-stu-id="96493-269">100</span></span>  <br/> |<span data-ttu-id="96493-270">1</span><span class="sxs-lookup"><span data-stu-id="96493-270">1</span></span>  <br/> |<span data-ttu-id="96493-271">5061</span><span class="sxs-lookup"><span data-stu-id="96493-271">5061</span></span>  <br/> |<span data-ttu-id="96493-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="96493-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="96493-273">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="96493-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Konfigurera-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="96493-275">Välj **spara**</span><span class="sxs-lookup"><span data-stu-id="96493-275">Select **save**</span></span>
    
    ![eNom-BP-Konfigurera-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="96493-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="96493-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

