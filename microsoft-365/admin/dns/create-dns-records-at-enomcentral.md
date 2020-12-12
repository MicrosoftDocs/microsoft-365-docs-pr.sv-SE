---
title: Skapa DNS-poster på eNomCentral för Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på eNomCentral för Microsoft.
ms.openlocfilehash: e6e05b987a893da582ea7fb062eafe421861b970
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658117"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="0516b-103">Skapa DNS-poster på eNomCentral för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0516b-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="0516b-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="0516b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="0516b-105">Om eNomCentral är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="0516b-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="0516b-106">När du har lagt till dessa poster på eNomCentral är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="0516b-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="0516b-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0516b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0516b-110">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="0516b-110">Add a TXT record for verification</span></span>
<span data-ttu-id="0516b-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0516b-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0516b-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="0516b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="0516b-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="0516b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="0516b-116">Följ stegen nedan eller [titta på videon (börja vid 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="0516b-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="0516b-p104">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0516b-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="0516b-120">Under **My Domains** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0516b-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="0516b-122">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="0516b-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. <span data-ttu-id="0516b-124">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0516b-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="0516b-125">Välj värdet **Record Type** i list rutan.</span><span class="sxs-lookup"><span data-stu-id="0516b-125">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="0516b-126">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="0516b-126">Host Name</span></span>|<span data-ttu-id="0516b-127">Record Type</span><span class="sxs-lookup"><span data-stu-id="0516b-127">Record Type</span></span>|<span data-ttu-id="0516b-128">Adress</span><span class="sxs-lookup"><span data-stu-id="0516b-128">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="0516b-129">TXT</span><span class="sxs-lookup"><span data-stu-id="0516b-129">TXT</span></span>|<span data-ttu-id="0516b-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0516b-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0516b-131">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0516b-131">**Note:** This is an example.</span></span> <span data-ttu-id="0516b-132">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="0516b-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="0516b-133">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="0516b-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. <span data-ttu-id="0516b-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0516b-135">Select **save**.</span></span>

   ![eNom-BP-verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. <span data-ttu-id="0516b-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="0516b-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="0516b-138">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="0516b-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>

<span data-ttu-id="0516b-139">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="0516b-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="0516b-140">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="0516b-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="0516b-141">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="0516b-141">On the **Domains** page, select the domain that you are verifying.</span></span>

3. <span data-ttu-id="0516b-142">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="0516b-142">On the **Setup** page, select **Start setup**.</span></span>

4. <span data-ttu-id="0516b-143">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="0516b-143">On the **Verify domain** page, select **Verify**.</span></span>

> [!NOTE]
> <span data-ttu-id="0516b-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0516b-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0516b-147">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0516b-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0516b-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0516b-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="0516b-149">Följ stegen nedan eller [titta på videon (börja vid 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="0516b-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="0516b-p107">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0516b-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="0516b-153">Under **My Domains** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0516b-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="0516b-155">I listrutan **Manage Domain** väljer du **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="0516b-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. <span data-ttu-id="0516b-157">I listrutan **Service Selection** väljer du **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="0516b-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. <span data-ttu-id="0516b-159">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0516b-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="0516b-160">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="0516b-160">Host Name</span></span>|<span data-ttu-id="0516b-161">Adress</span><span class="sxs-lookup"><span data-stu-id="0516b-161">Address</span></span>|<span data-ttu-id="0516b-162">Pref</span><span class="sxs-lookup"><span data-stu-id="0516b-162">Pref</span></span>|
   |---|---|---|
   |@| <span data-ttu-id="0516b-163">*\<domain-key\>*  . mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0516b-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0516b-164">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0516b-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="0516b-165">**Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="0516b-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="0516b-166">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="0516b-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="0516b-167">10.3</span><span class="sxs-lookup"><span data-stu-id="0516b-167">10</span></span>  <br/> <span data-ttu-id="0516b-168">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="0516b-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span>|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. <span data-ttu-id="0516b-170">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0516b-170">Select **save**.</span></span>

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. <span data-ttu-id="0516b-172">Om det finns andra befintliga MX-poster väljer du dem genom att markera kryssrutorna för posterna.</span><span class="sxs-lookup"><span data-stu-id="0516b-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. <span data-ttu-id="0516b-174">Välj **ta bort markerad**.</span><span class="sxs-lookup"><span data-stu-id="0516b-174">Select **delete checked**.</span></span>

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0516b-176">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0516b-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0516b-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0516b-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="0516b-178">Följ stegen nedan eller [titta på videon (börja vid 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="0516b-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="0516b-p109">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0516b-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="0516b-182">Under **My Domains** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0516b-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="0516b-184">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="0516b-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="0516b-186">Välj **ny rad**.</span><span class="sxs-lookup"><span data-stu-id="0516b-186">Select **new row**.</span></span>

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. <span data-ttu-id="0516b-188">I rutorna för de sex nya posterna skriver du in, eller kopierar och klistrar in, följande värden.</span><span class="sxs-lookup"><span data-stu-id="0516b-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>

   <span data-ttu-id="0516b-189">Välj värdet **Record Type** i list rutan.</span><span class="sxs-lookup"><span data-stu-id="0516b-189">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="0516b-190">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="0516b-190">Host Name</span></span>|<span data-ttu-id="0516b-191">Record Type</span><span class="sxs-lookup"><span data-stu-id="0516b-191">Record Type</span></span>|<span data-ttu-id="0516b-192">Adress</span><span class="sxs-lookup"><span data-stu-id="0516b-192">Address</span></span>|
   |---|---|---|
   |<span data-ttu-id="0516b-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0516b-193">autodiscover</span></span>|<span data-ttu-id="0516b-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="0516b-194">CNAME (Alias)</span></span>|<span data-ttu-id="0516b-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0516b-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="0516b-196">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0516b-196">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="0516b-197">sip</span><span class="sxs-lookup"><span data-stu-id="0516b-197">sip</span></span>|<span data-ttu-id="0516b-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="0516b-198">CNAME (Alias)</span></span>|<span data-ttu-id="0516b-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0516b-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0516b-200">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0516b-200">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="0516b-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0516b-201">lyncdiscover</span></span>|<span data-ttu-id="0516b-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="0516b-202">CNAME (Alias)</span></span>|<span data-ttu-id="0516b-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0516b-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0516b-204">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0516b-204">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="0516b-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0516b-205">enterpriseregistration</span></span>|<span data-ttu-id="0516b-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="0516b-206">CNAME (Alias)</span></span>|<span data-ttu-id="0516b-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="0516b-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="0516b-208">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0516b-208">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="0516b-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0516b-209">enterpriseenrollment</span></span>|<span data-ttu-id="0516b-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="0516b-210">CNAME (Alias)</span></span>|<span data-ttu-id="0516b-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0516b-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="0516b-212">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0516b-212">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. <span data-ttu-id="0516b-214">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0516b-214">Select **save**.</span></span>

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0516b-216">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="0516b-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0516b-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0516b-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0516b-218">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="0516b-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0516b-219">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="0516b-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0516b-220">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0516b-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0516b-221">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="0516b-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="0516b-222">Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="0516b-222">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="0516b-p111">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0516b-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="0516b-226">Under **My Domains** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0516b-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="0516b-228">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="0516b-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="0516b-230">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0516b-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="0516b-231">Välj värdet **Record Type** i list rutan.</span><span class="sxs-lookup"><span data-stu-id="0516b-231">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="0516b-232">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="0516b-232">Host Name</span></span>|<span data-ttu-id="0516b-233">Record Type</span><span class="sxs-lookup"><span data-stu-id="0516b-233">Record Type</span></span>|<span data-ttu-id="0516b-234">Adress</span><span class="sxs-lookup"><span data-stu-id="0516b-234">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="0516b-235">TXT</span><span class="sxs-lookup"><span data-stu-id="0516b-235">TXT</span></span>|<span data-ttu-id="0516b-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0516b-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="0516b-237">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="0516b-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. <span data-ttu-id="0516b-239">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0516b-239">Select **save**.</span></span>

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0516b-241">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0516b-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0516b-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0516b-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="0516b-243">Följ stegen nedan eller [titta på videon (börja vid 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="0516b-243">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="0516b-p112">Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="0516b-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="0516b-247">Under **My Domains** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0516b-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="0516b-249">I listrutan **Manage Domain** väljer du **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="0516b-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="0516b-251">Till höger om **ny rad** väljer du **Add SRV or SPF record**.</span><span class="sxs-lookup"><span data-stu-id="0516b-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. <span data-ttu-id="0516b-253">I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0516b-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="0516b-254">Tjänst</span><span class="sxs-lookup"><span data-stu-id="0516b-254">Service</span></span>|<span data-ttu-id="0516b-255">Protokoll</span><span class="sxs-lookup"><span data-stu-id="0516b-255">Protocol</span></span>|<span data-ttu-id="0516b-256">Ordningen</span><span class="sxs-lookup"><span data-stu-id="0516b-256">Priority</span></span>|<span data-ttu-id="0516b-257">Väga</span><span class="sxs-lookup"><span data-stu-id="0516b-257">Weight</span></span>|<span data-ttu-id="0516b-258">Port</span><span class="sxs-lookup"><span data-stu-id="0516b-258">Port</span></span>|<span data-ttu-id="0516b-259">Mål (värdnamn)</span><span class="sxs-lookup"><span data-stu-id="0516b-259">Target (Hostname)</span></span>|
   |---|---|---|---|---|---|
   |<span data-ttu-id="0516b-260">_sip</span><span class="sxs-lookup"><span data-stu-id="0516b-260">_sip</span></span>|<span data-ttu-id="0516b-261">_tls</span><span class="sxs-lookup"><span data-stu-id="0516b-261">_tls</span></span>|<span data-ttu-id="0516b-262">100</span><span class="sxs-lookup"><span data-stu-id="0516b-262">100</span></span>|<span data-ttu-id="0516b-263">9.1</span><span class="sxs-lookup"><span data-stu-id="0516b-263">1</span></span>|<span data-ttu-id="0516b-264">443</span><span class="sxs-lookup"><span data-stu-id="0516b-264">443</span></span>|<span data-ttu-id="0516b-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0516b-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0516b-266">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0516b-266">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="0516b-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0516b-267">_sipfederationtls</span></span>|<span data-ttu-id="0516b-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="0516b-268">_tcp</span></span>|<span data-ttu-id="0516b-269">100</span><span class="sxs-lookup"><span data-stu-id="0516b-269">100</span></span>|<span data-ttu-id="0516b-270">9.1</span><span class="sxs-lookup"><span data-stu-id="0516b-270">1</span></span>|<span data-ttu-id="0516b-271">5061</span><span class="sxs-lookup"><span data-stu-id="0516b-271">5061</span></span>|<span data-ttu-id="0516b-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0516b-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="0516b-273">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="0516b-273">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. <span data-ttu-id="0516b-275">Välj **Spara**</span><span class="sxs-lookup"><span data-stu-id="0516b-275">Select **save**</span></span>

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> <span data-ttu-id="0516b-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0516b-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
