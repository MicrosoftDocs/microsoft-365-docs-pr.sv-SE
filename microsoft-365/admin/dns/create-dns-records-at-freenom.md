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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Freenom för Microsoft.
ms.openlocfilehash: 828a1728606338017383857e4b59d6a62d087fc7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629569"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="401f1-103">Skapa DNS-poster på Freenom för Microsoft</span><span class="sxs-lookup"><span data-stu-id="401f1-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="401f1-104">[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="401f1-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="401f1-105">Freenom-webbplatsen stöder inte SRV-poster, vilket innebär att flera Skype för företag – online och Outlook Web App-funktioner inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="401f1-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="401f1-106">Oavsett vilket Microsoft-abonnemang du använder finns det betydande tjänstebegränsningar, och du kanske vill byta till en annan DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="401f1-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="401f1-107">Om du trots tjänstbegränsningarna väljer att hantera dina egna Microsoft DNS-poster på Freenom följer du stegen i den här artikeln för att verifiera domänen och konfigurera DNS-poster för e-post och andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="401f1-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="401f1-108">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="401f1-108">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="401f1-p102">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="401f1-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="401f1-112">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="401f1-112">Add a TXT record for verification</span></span>
<span data-ttu-id="401f1-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="401f1-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="401f1-114">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="401f1-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="401f1-115">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="401f1-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="401f1-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="401f1-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="401f1-118">För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="401f1-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="401f1-119">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="401f1-119">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="401f1-121">Välj **Tjänster**och välj sedan **Mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="401f1-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="401f1-123">För den domän som du vill redigera väljer du **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="401f1-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="401f1-125">Välj **Hantera Freenom DNS**.</span><span class="sxs-lookup"><span data-stu-id="401f1-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="401f1-127">Under **Add Record** går du till kolumnen **Type** och väljer **TXT** på menyn.</span><span class="sxs-lookup"><span data-stu-id="401f1-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="401f1-129">I rutorna för den nya posten skriver du in eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="401f1-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="401f1-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="401f1-130">**Name**</span></span>|<span data-ttu-id="401f1-131">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="401f1-131">**Type**</span></span>|<span data-ttu-id="401f1-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="401f1-132">**TTL**</span></span>|<span data-ttu-id="401f1-133">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="401f1-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="401f1-134">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="401f1-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="401f1-135">TXT</span><span class="sxs-lookup"><span data-stu-id="401f1-135">TXT</span></span>  <br/> |<span data-ttu-id="401f1-136">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="401f1-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="401f1-137">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="401f1-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="401f1-138">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="401f1-138">**Note:** This is an example.</span></span> <span data-ttu-id="401f1-139">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="401f1-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="401f1-140">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="401f1-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="401f1-142">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="401f1-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="401f1-144">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="401f1-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="401f1-145">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="401f1-145">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="401f1-146">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="401f1-146">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="401f1-147">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="401f1-147">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="401f1-148">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="401f1-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="401f1-149">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="401f1-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="401f1-150">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="401f1-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="401f1-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="401f1-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="401f1-154">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="401f1-154">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="401f1-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="401f1-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="401f1-156">För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="401f1-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="401f1-157">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="401f1-157">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="401f1-159">Välj **Tjänster**och välj sedan **Mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="401f1-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="401f1-161">För den domän som du vill redigera väljer du **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="401f1-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="401f1-163">Ange namnet för din domän till standard freenom namnservrar.</span><span class="sxs-lookup"><span data-stu-id="401f1-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="401f1-164">Välj **Hanteringsverktyg**och välj sedan **Namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="401f1-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="401f1-166">Kontrollera att **Använd standardnamnservrar** är markerat och välj sedan **Ändra namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="401f1-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="401f1-168">Välj **Hantera Freenom DNS**.</span><span class="sxs-lookup"><span data-stu-id="401f1-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom välj Hantera Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="401f1-170">Under **Add Record** går du till kolumnen **Type** och väljer **MX** på menyn.</span><span class="sxs-lookup"><span data-stu-id="401f1-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="401f1-172">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="401f1-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="401f1-173">**Name**</span><span class="sxs-lookup"><span data-stu-id="401f1-173">**Name**</span></span>|<span data-ttu-id="401f1-174">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="401f1-174">**Type**</span></span>|<span data-ttu-id="401f1-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="401f1-175">**TTL**</span></span>|<span data-ttu-id="401f1-176">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="401f1-176">**Target**</span></span>|<span data-ttu-id="401f1-177">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="401f1-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="401f1-178">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="401f1-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="401f1-179">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="401f1-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="401f1-180">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="401f1-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="401f1-181">\<domännyckeln\>.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="401f1-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="401f1-182">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="401f1-182">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="401f1-183">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="401f1-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="401f1-184">10</span><span class="sxs-lookup"><span data-stu-id="401f1-184">10</span></span>  <br/> <span data-ttu-id="401f1-185">Mer information om prioritet finns i [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="401f1-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="401f1-187">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="401f1-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="401f1-189">Om det finns några andra MX-poster tar du bort dem alla.</span><span class="sxs-lookup"><span data-stu-id="401f1-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="401f1-190">För varje post väljer du **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="401f1-190">For each record, select **Delete**.</span></span> <span data-ttu-id="401f1-191">När meddelandet Vill du verkligen ta bort den **OK** **här posten?**</span><span class="sxs-lookup"><span data-stu-id="401f1-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="401f1-192">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="401f1-192">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="401f1-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="401f1-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="401f1-194">För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="401f1-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="401f1-195">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="401f1-195">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="401f1-197">Välj **Tjänster**och välj sedan **Mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="401f1-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="401f1-199">För den domän som du vill redigera väljer du **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="401f1-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="401f1-201">Välj **Hantera Freenom DNS**.</span><span class="sxs-lookup"><span data-stu-id="401f1-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom välj Hantera Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="401f1-203">Under **Add Record** går du till kolumnen **Type** och väljer **CNAME** på menyn.</span><span class="sxs-lookup"><span data-stu-id="401f1-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="401f1-p113">Skapa den första CNAME-posten. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="401f1-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="401f1-207">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="401f1-207">**Name**</span></span>|<span data-ttu-id="401f1-208">**Record type (posttyp)**</span><span class="sxs-lookup"><span data-stu-id="401f1-208">**Record type**</span></span>|<span data-ttu-id="401f1-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="401f1-209">**TTL**</span></span>|<span data-ttu-id="401f1-210">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="401f1-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="401f1-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="401f1-211">autodiscover</span></span>  <br/> |<span data-ttu-id="401f1-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="401f1-212">CNAME</span></span>  <br/> |<span data-ttu-id="401f1-213">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="401f1-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="401f1-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="401f1-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="401f1-215">sip</span><span class="sxs-lookup"><span data-stu-id="401f1-215">sip</span></span>  <br/> |<span data-ttu-id="401f1-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="401f1-216">CNAME</span></span>  <br/> |<span data-ttu-id="401f1-217">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="401f1-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="401f1-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="401f1-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="401f1-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="401f1-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="401f1-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="401f1-220">CNAME</span></span>  <br/> |<span data-ttu-id="401f1-221">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="401f1-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="401f1-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="401f1-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="401f1-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="401f1-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="401f1-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="401f1-224">CNAME</span></span>  <br/> |<span data-ttu-id="401f1-225">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="401f1-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="401f1-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="401f1-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="401f1-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="401f1-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="401f1-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="401f1-228">CNAME</span></span>  <br/> |<span data-ttu-id="401f1-229">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="401f1-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="401f1-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="401f1-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="401f1-232">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="401f1-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="401f1-234">Upprepa föregående steg för att skapa de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="401f1-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="401f1-235">För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.</span><span class="sxs-lookup"><span data-stu-id="401f1-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="401f1-236">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="401f1-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="401f1-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="401f1-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="401f1-238">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="401f1-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="401f1-239">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="401f1-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="401f1-240">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="401f1-240">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="401f1-241">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="401f1-241">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="401f1-242">För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="401f1-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="401f1-243">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="401f1-243">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="401f1-245">Välj **Tjänster**och välj sedan **Mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="401f1-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="401f1-247">För den domän som du vill redigera väljer du **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="401f1-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="401f1-249">Välj **Hantera Freenom DNS**.</span><span class="sxs-lookup"><span data-stu-id="401f1-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom välj Hantera Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="401f1-251">Under **Add Record** går du till kolumnen **Type** och väljer **TXT** på menyn.</span><span class="sxs-lookup"><span data-stu-id="401f1-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="401f1-253">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="401f1-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="401f1-254">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="401f1-254">**Name**</span></span>|<span data-ttu-id="401f1-255">**Record type (posttyp)**</span><span class="sxs-lookup"><span data-stu-id="401f1-255">**Record type**</span></span>|<span data-ttu-id="401f1-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="401f1-256">**TTL**</span></span>|<span data-ttu-id="401f1-257">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="401f1-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="401f1-258">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="401f1-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="401f1-259">TXT</span><span class="sxs-lookup"><span data-stu-id="401f1-259">TXT</span></span>  <br/> |<span data-ttu-id="401f1-260">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="401f1-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="401f1-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="401f1-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="401f1-262">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="401f1-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="401f1-264">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="401f1-264">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

