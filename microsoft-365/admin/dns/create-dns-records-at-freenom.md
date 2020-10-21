---
title: Skapa DNS-poster på Freenom för Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Freenom för Microsoft.
ms.openlocfilehash: 2fc2407193d41d6e0526aacad0b2b558f1b21bdb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646193"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="adfb6-103">Skapa DNS-poster på Freenom för Microsoft</span><span class="sxs-lookup"><span data-stu-id="adfb6-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="adfb6-104">[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="adfb6-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="adfb6-105">Freenom webbplats stöder inte SRV-poster, vilket innebär att flera funktioner för Skype för företag – Online och Outlook Web App inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="adfb6-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="adfb6-106">Oavsett vilken Microsoft-plan du använder, finns det viktiga tjänst begränsningar och du kan byta till en annan DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="adfb6-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="adfb6-107">Om du trots tjänst begränsningarna väljer att hantera dina egna DNS-poster på Freenom, följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post och andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="adfb6-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="adfb6-p102">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="adfb6-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="adfb6-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="adfb6-111">Add a TXT record for verification</span></span>
<span data-ttu-id="adfb6-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="adfb6-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="adfb6-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="adfb6-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="adfb6-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="adfb6-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="adfb6-117">Kom igång genom att gå till sidan Domains i Freenom med hjälp av [den här länken](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="adfb6-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="adfb6-118">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="adfb6-118">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="adfb6-120">Välj **tjänster**och sedan **My Domains**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="adfb6-122">Välj **Manage Domain**för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="adfb6-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="adfb6-124">Välj **Manage FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="adfb6-126">Under **Add Record** går du till kolumnen **Type** och väljer **TXT** på menyn.</span><span class="sxs-lookup"><span data-stu-id="adfb6-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="adfb6-128">I rutorna för den nya posten skriver du in eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="adfb6-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="adfb6-129">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-129">**Name**</span></span>|<span data-ttu-id="adfb6-130">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-130">**Type**</span></span>|<span data-ttu-id="adfb6-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="adfb6-131">**TTL**</span></span>|<span data-ttu-id="adfb6-132">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="adfb6-133">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="adfb6-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="adfb6-134">TXT</span><span class="sxs-lookup"><span data-stu-id="adfb6-134">TXT</span></span>  <br/> |<span data-ttu-id="adfb6-135">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="adfb6-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="adfb6-136">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="adfb6-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="adfb6-137">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="adfb6-137">**Note:** This is an example.</span></span> <span data-ttu-id="adfb6-138">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="adfb6-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="adfb6-139">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="adfb6-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="adfb6-141">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="adfb6-143">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="adfb6-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="adfb6-144">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="adfb6-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="adfb6-145">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="adfb6-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="adfb6-146">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="adfb6-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="adfb6-147">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="adfb6-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="adfb6-148">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="adfb6-149">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="adfb6-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="adfb6-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="adfb6-153">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="adfb6-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="adfb6-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="adfb6-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="adfb6-155">Kom igång genom att gå till sidan Domains i Freenom med hjälp av [den här länken](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="adfb6-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="adfb6-156">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="adfb6-156">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="adfb6-158">Välj **tjänster**och sedan **My Domains**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="adfb6-160">Välj **Manage Domain**för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="adfb6-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="adfb6-162">Ange namnet bevaras för domänen till standard namnen på Freenom.</span><span class="sxs-lookup"><span data-stu-id="adfb6-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="adfb6-163">Välj **Management tools**och välj **namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="adfb6-165">Kontrol lera att **Använd standard namnservrar** är markerat och välj sedan **ändra namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="adfb6-167">Välj **Manage FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Välj Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="adfb6-169">Under **Add Record** går du till kolumnen **Type** och väljer **MX** på menyn.</span><span class="sxs-lookup"><span data-stu-id="adfb6-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="adfb6-171">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="adfb6-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="adfb6-172">**Name**</span><span class="sxs-lookup"><span data-stu-id="adfb6-172">**Name**</span></span>|<span data-ttu-id="adfb6-173">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-173">**Type**</span></span>|<span data-ttu-id="adfb6-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="adfb6-174">**TTL**</span></span>|<span data-ttu-id="adfb6-175">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-175">**Target**</span></span>|<span data-ttu-id="adfb6-176">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="adfb6-177">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="adfb6-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="adfb6-178">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="adfb6-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="adfb6-179">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="adfb6-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="adfb6-180">\<domain-key\>. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="adfb6-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="adfb6-181">**Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="adfb6-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="adfb6-182">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="adfb6-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="adfb6-183">10.3</span><span class="sxs-lookup"><span data-stu-id="adfb6-183">10</span></span>  <br/> <span data-ttu-id="adfb6-184">Mer information om prioritet finns i [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="adfb6-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="adfb6-186">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="adfb6-188">Om det finns andra MX-poster tar du bort alla.</span><span class="sxs-lookup"><span data-stu-id="adfb6-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="adfb6-189">Välj **ta bort**för varje post.</span><span class="sxs-lookup"><span data-stu-id="adfb6-189">For each record, select **Delete**.</span></span> <span data-ttu-id="adfb6-190">När meddelandet **vill du verkligen ta bort den här posten** visas väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="adfb6-191">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="adfb6-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="adfb6-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="adfb6-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="adfb6-193">Kom igång genom att gå till sidan Domains i Freenom med hjälp av [den här länken](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="adfb6-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="adfb6-194">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="adfb6-194">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="adfb6-196">Välj **tjänster**och sedan **My Domains**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="adfb6-198">Välj **Manage Domain**för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="adfb6-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="adfb6-200">Välj **Manage FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Välj Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="adfb6-202">Under **Add Record** går du till kolumnen **Type** och väljer **CNAME** på menyn.</span><span class="sxs-lookup"><span data-stu-id="adfb6-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="adfb6-p113">Skapa den första CNAME-posten. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="adfb6-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="adfb6-206">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-206">**Name**</span></span>|<span data-ttu-id="adfb6-207">**Record type (posttyp)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-207">**Record type**</span></span>|<span data-ttu-id="adfb6-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="adfb6-208">**TTL**</span></span>|<span data-ttu-id="adfb6-209">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="adfb6-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="adfb6-210">autodiscover</span></span>  <br/> |<span data-ttu-id="adfb6-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="adfb6-211">CNAME</span></span>  <br/> |<span data-ttu-id="adfb6-212">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="adfb6-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="adfb6-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="adfb6-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="adfb6-214">sip</span><span class="sxs-lookup"><span data-stu-id="adfb6-214">sip</span></span>  <br/> |<span data-ttu-id="adfb6-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="adfb6-215">CNAME</span></span>  <br/> |<span data-ttu-id="adfb6-216">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="adfb6-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="adfb6-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="adfb6-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="adfb6-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="adfb6-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="adfb6-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="adfb6-219">CNAME</span></span>  <br/> |<span data-ttu-id="adfb6-220">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="adfb6-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="adfb6-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="adfb6-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="adfb6-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="adfb6-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="adfb6-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="adfb6-223">CNAME</span></span>  <br/> |<span data-ttu-id="adfb6-224">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="adfb6-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="adfb6-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="adfb6-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="adfb6-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="adfb6-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="adfb6-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="adfb6-227">CNAME</span></span>  <br/> |<span data-ttu-id="adfb6-228">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="adfb6-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="adfb6-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="adfb6-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="adfb6-231">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="adfb6-233">Upprepa föregående steg för att skapa de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="adfb6-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="adfb6-234">För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.</span><span class="sxs-lookup"><span data-stu-id="adfb6-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="adfb6-235">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="adfb6-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="adfb6-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="adfb6-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="adfb6-237">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="adfb6-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="adfb6-238">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="adfb6-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="adfb6-239">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="adfb6-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="adfb6-240">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="adfb6-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="adfb6-241">Kom igång genom att gå till sidan Domains i Freenom med hjälp av [den här länken](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="adfb6-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="adfb6-242">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="adfb6-242">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="adfb6-244">Välj **tjänster**och sedan **My Domains**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="adfb6-246">Välj **Manage Domain**för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="adfb6-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="adfb6-248">Välj **Manage FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Välj Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="adfb6-250">Under **Add Record** går du till kolumnen **Type** och väljer **TXT** på menyn.</span><span class="sxs-lookup"><span data-stu-id="adfb6-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="adfb6-252">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="adfb6-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="adfb6-253">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-253">**Name**</span></span>|<span data-ttu-id="adfb6-254">**Record type (posttyp)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-254">**Record type**</span></span>|<span data-ttu-id="adfb6-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="adfb6-255">**TTL**</span></span>|<span data-ttu-id="adfb6-256">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="adfb6-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="adfb6-257">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="adfb6-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="adfb6-258">TXT</span><span class="sxs-lookup"><span data-stu-id="adfb6-258">TXT</span></span>  <br/> |<span data-ttu-id="adfb6-259">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="adfb6-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="adfb6-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="adfb6-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="adfb6-261">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="adfb6-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="adfb6-263">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="adfb6-263">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

