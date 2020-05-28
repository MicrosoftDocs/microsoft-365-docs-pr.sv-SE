---
title: Skapa DNS-poster på Freenom för Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Freenom för Microsoft.
ms.openlocfilehash: f139c21915d6922c2f77281990dd09949d9db928
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400479"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="16abd-103">Skapa DNS-poster på Freenom för Microsoft</span><span class="sxs-lookup"><span data-stu-id="16abd-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="16abd-104">[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="16abd-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="16abd-105">Freenom-webbplatsen stöder inte SRV-poster, vilket innebär att flera Skype för företag – online och Outlook Web App-funktioner inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="16abd-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="16abd-106">Oavsett vilket Microsoft-abonnemang du använder finns det betydande tjänstebegränsningar, och du kanske vill byta till en annan DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="16abd-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="16abd-107">Om du trots tjänstbegränsningarna väljer att hantera dina egna Microsoft DNS-poster på Freenom följer du stegen i den här artikeln för att verifiera domänen och konfigurera DNS-poster för e-post och andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="16abd-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="16abd-p102">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16abd-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="16abd-111">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="16abd-111">Add a TXT record for verification</span></span>
<span data-ttu-id="16abd-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="16abd-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="16abd-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="16abd-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16abd-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="16abd-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="16abd-117">För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="16abd-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="16abd-118">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16abd-118">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="16abd-120">Välj **Tjänster**och välj sedan **Mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="16abd-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="16abd-122">För den domän som du vill redigera väljer du **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="16abd-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="16abd-124">Välj **Hantera Freenom DNS**.</span><span class="sxs-lookup"><span data-stu-id="16abd-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="16abd-126">Under **Add Record** går du till kolumnen **Type** och väljer **TXT** på menyn.</span><span class="sxs-lookup"><span data-stu-id="16abd-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="16abd-128">I rutorna för den nya posten skriver du in eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="16abd-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="16abd-129">**Name**</span><span class="sxs-lookup"><span data-stu-id="16abd-129">**Name**</span></span>|<span data-ttu-id="16abd-130">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="16abd-130">**Type**</span></span>|<span data-ttu-id="16abd-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16abd-131">**TTL**</span></span>|<span data-ttu-id="16abd-132">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="16abd-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16abd-133">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="16abd-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="16abd-134">TXT</span><span class="sxs-lookup"><span data-stu-id="16abd-134">TXT</span></span>  <br/> |<span data-ttu-id="16abd-135">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="16abd-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16abd-136">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="16abd-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="16abd-137">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="16abd-137">**Note:** This is an example.</span></span> <span data-ttu-id="16abd-138">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="16abd-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="16abd-139">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="16abd-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="16abd-141">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="16abd-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="16abd-143">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="16abd-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="16abd-144">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="16abd-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="16abd-145">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="16abd-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="16abd-146">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="16abd-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="16abd-147">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="16abd-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="16abd-148">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="16abd-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="16abd-149">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="16abd-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="16abd-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16abd-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="16abd-153">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16abd-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="16abd-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="16abd-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="16abd-155">För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="16abd-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="16abd-156">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16abd-156">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="16abd-158">Välj **Tjänster**och välj sedan **Mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="16abd-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="16abd-160">För den domän som du vill redigera väljer du **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="16abd-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="16abd-162">Ange namnet för din domän till standard freenom namnservrar.</span><span class="sxs-lookup"><span data-stu-id="16abd-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="16abd-163">Välj **Hanteringsverktyg**och välj sedan **Namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="16abd-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="16abd-165">Kontrollera att **Använd standardnamnservrar** är markerat och välj sedan **Ändra namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="16abd-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="16abd-167">Välj **Hantera Freenom DNS**.</span><span class="sxs-lookup"><span data-stu-id="16abd-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom välj Hantera Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="16abd-169">Under **Add Record** går du till kolumnen **Type** och väljer **MX** på menyn.</span><span class="sxs-lookup"><span data-stu-id="16abd-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="16abd-171">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="16abd-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="16abd-172">**Name**</span><span class="sxs-lookup"><span data-stu-id="16abd-172">**Name**</span></span>|<span data-ttu-id="16abd-173">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="16abd-173">**Type**</span></span>|<span data-ttu-id="16abd-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16abd-174">**TTL**</span></span>|<span data-ttu-id="16abd-175">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="16abd-175">**Target**</span></span>|<span data-ttu-id="16abd-176">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="16abd-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16abd-177">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="16abd-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="16abd-178">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="16abd-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="16abd-179">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="16abd-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16abd-180">\<domain-key\>.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="16abd-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="16abd-181">**Anm.:** Hämta ditt *\<domain-key\>* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="16abd-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="16abd-182">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="16abd-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="16abd-183">10</span><span class="sxs-lookup"><span data-stu-id="16abd-183">10</span></span>  <br/> <span data-ttu-id="16abd-184">Mer information om prioritet finns i [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="16abd-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="16abd-186">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="16abd-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="16abd-188">Om det finns några andra MX-poster tar du bort dem alla.</span><span class="sxs-lookup"><span data-stu-id="16abd-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="16abd-189">För varje post väljer du **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="16abd-189">For each record, select **Delete**.</span></span> <span data-ttu-id="16abd-190">När meddelandet Vill du verkligen ta bort den **OK** **här posten?**</span><span class="sxs-lookup"><span data-stu-id="16abd-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="16abd-191">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="16abd-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="16abd-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="16abd-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="16abd-193">För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="16abd-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="16abd-194">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16abd-194">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="16abd-196">Välj **Tjänster**och välj sedan **Mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="16abd-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="16abd-198">För den domän som du vill redigera väljer du **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="16abd-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="16abd-200">Välj **Hantera Freenom DNS**.</span><span class="sxs-lookup"><span data-stu-id="16abd-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom välj Hantera Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="16abd-202">Under **Add Record** går du till kolumnen **Type** och väljer **CNAME** på menyn.</span><span class="sxs-lookup"><span data-stu-id="16abd-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="16abd-p113">Skapa den första CNAME-posten. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="16abd-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="16abd-206">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="16abd-206">**Name**</span></span>|<span data-ttu-id="16abd-207">**Record type (posttyp)**</span><span class="sxs-lookup"><span data-stu-id="16abd-207">**Record type**</span></span>|<span data-ttu-id="16abd-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16abd-208">**TTL**</span></span>|<span data-ttu-id="16abd-209">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="16abd-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16abd-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="16abd-210">autodiscover</span></span>  <br/> |<span data-ttu-id="16abd-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="16abd-211">CNAME</span></span>  <br/> |<span data-ttu-id="16abd-212">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="16abd-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16abd-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="16abd-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="16abd-214">sip</span><span class="sxs-lookup"><span data-stu-id="16abd-214">sip</span></span>  <br/> |<span data-ttu-id="16abd-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="16abd-215">CNAME</span></span>  <br/> |<span data-ttu-id="16abd-216">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="16abd-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16abd-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16abd-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="16abd-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="16abd-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="16abd-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="16abd-219">CNAME</span></span>  <br/> |<span data-ttu-id="16abd-220">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="16abd-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16abd-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16abd-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="16abd-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="16abd-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="16abd-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="16abd-223">CNAME</span></span>  <br/> |<span data-ttu-id="16abd-224">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="16abd-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16abd-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="16abd-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="16abd-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="16abd-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="16abd-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="16abd-227">CNAME</span></span>  <br/> |<span data-ttu-id="16abd-228">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="16abd-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16abd-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="16abd-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="16abd-231">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="16abd-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="16abd-233">Upprepa föregående steg för att skapa de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="16abd-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="16abd-234">För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.</span><span class="sxs-lookup"><span data-stu-id="16abd-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="16abd-235">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="16abd-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="16abd-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="16abd-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="16abd-237">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="16abd-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="16abd-238">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="16abd-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="16abd-239">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16abd-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="16abd-240">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="16abd-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="16abd-241">För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="16abd-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="16abd-242">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="16abd-242">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="16abd-244">Välj **Tjänster**och välj sedan **Mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="16abd-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="16abd-246">För den domän som du vill redigera väljer du **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="16abd-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="16abd-248">Välj **Hantera Freenom DNS**.</span><span class="sxs-lookup"><span data-stu-id="16abd-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom välj Hantera Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="16abd-250">Under **Add Record** går du till kolumnen **Type** och väljer **TXT** på menyn.</span><span class="sxs-lookup"><span data-stu-id="16abd-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="16abd-252">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="16abd-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="16abd-253">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="16abd-253">**Name**</span></span>|<span data-ttu-id="16abd-254">**Record type (posttyp)**</span><span class="sxs-lookup"><span data-stu-id="16abd-254">**Record type**</span></span>|<span data-ttu-id="16abd-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16abd-255">**TTL**</span></span>|<span data-ttu-id="16abd-256">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="16abd-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16abd-257">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="16abd-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="16abd-258">TXT</span><span class="sxs-lookup"><span data-stu-id="16abd-258">TXT</span></span>  <br/> |<span data-ttu-id="16abd-259">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="16abd-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16abd-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="16abd-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="16abd-261">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="16abd-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="16abd-263">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="16abd-263">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

