---
title: Skapa DNS-poster på netregistry för Microsoft
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på netregistry för Microsoft.
ms.openlocfilehash: 857645c685cce946b39a7c3dcadb0a45b43686cf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657809"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="5aea0-103">Skapa DNS-poster på netregistry för Microsoft</span><span class="sxs-lookup"><span data-stu-id="5aea0-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="5aea0-104">[Läs frågor och svar om domäner](../setup/domains-faq.yml) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5aea0-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5aea0-105">Om netregistry är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="5aea0-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5aea0-106">Det här är de viktigaste posterna att lägga till:</span><span class="sxs-lookup"><span data-stu-id="5aea0-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="5aea0-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="5aea0-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="5aea0-108">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5aea0-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="5aea0-109">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="5aea0-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="5aea0-110">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="5aea0-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="5aea0-111">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="5aea0-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="5aea0-112">När du har lagt till dessa poster på netregistry är domänen konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="5aea0-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="5aea0-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5aea0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5aea0-116">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="5aea0-116">Add a TXT record for verification</span></span>
<span data-ttu-id="5aea0-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="5aea0-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="5aea0-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="5aea0-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5aea0-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="5aea0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5aea0-122">För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="5aea0-122">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="5aea0-123">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="5aea0-123">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="5aea0-125">Välj **Hantera** bredvid den domän som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="5aea0-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="5aea0-127">Välj **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="5aea0-129">Under **Lägg till en zonfil** väljer du **txt Record** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="5aea0-131">Du måste använda citat tecken före och efter posten i TXT-rutan.</span><span class="sxs-lookup"><span data-stu-id="5aea0-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="5aea0-132">Skriv eller kopiera och klistra in värdena från följande tabell i formuläret **ny TXT-post** .</span><span class="sxs-lookup"><span data-stu-id="5aea0-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="5aea0-133">**Namn**</span><span class="sxs-lookup"><span data-stu-id="5aea0-133">**Name**</span></span>|<span data-ttu-id="5aea0-134">**TTL (SEK)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-134">**TTL (SEC)**</span></span>|<span data-ttu-id="5aea0-135">**TXT (pekar på adress eller värde)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5aea0-136">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="5aea0-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="5aea0-137">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-138">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="5aea0-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="5aea0-139">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="5aea0-139">**Note:** This is an example.</span></span> <span data-ttu-id="5aea0-140">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="5aea0-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5aea0-141">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="5aea0-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="5aea0-143">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-143">Select **Add record**.</span></span>
    
<span data-ttu-id="5aea0-144">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="5aea0-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5aea0-145">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="5aea0-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5aea0-146">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="5aea0-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5aea0-147">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="5aea0-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5aea0-148">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5aea0-149">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5aea0-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5aea0-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5aea0-153">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5aea0-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5aea0-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="5aea0-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="5aea0-155">För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="5aea0-155">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="5aea0-156">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="5aea0-156">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="5aea0-158">Välj **Hantera** bredvid den domän som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="5aea0-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="5aea0-160">Välj **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="5aea0-162">Under **aktuella zondata** tar du bort de förvalda MX-posterna genom att välja **ta bort** bredvid varje MX-post i listan.</span><span class="sxs-lookup"><span data-stu-id="5aea0-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="5aea0-164">Under **Lägg till en zonfil** väljer du **MX Record** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="5aea0-166">Skriv in, eller kopiera och klistra in, värdena från följande tabell i det **nya MX Record** -formuläret.</span><span class="sxs-lookup"><span data-stu-id="5aea0-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="5aea0-167">**Namn**</span><span class="sxs-lookup"><span data-stu-id="5aea0-167">**Name**</span></span>|<span data-ttu-id="5aea0-168">**TTL (SEK)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-168">**TTL (SEC)**</span></span>|<span data-ttu-id="5aea0-169">**Utbyte (pekar på adress eller värde)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="5aea0-170">**Är värden fullt kvalificerad?**</span><span class="sxs-lookup"><span data-stu-id="5aea0-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="5aea0-171">**Preferens (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5aea0-172">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="5aea0-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="5aea0-173">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="5aea0-174">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5aea0-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5aea0-175">**Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="5aea0-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="5aea0-176">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="5aea0-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="5aea0-177">(Markera kryss rutan)</span><span class="sxs-lookup"><span data-stu-id="5aea0-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="5aea0-178">10.3</span><span class="sxs-lookup"><span data-stu-id="5aea0-178">10</span></span>  <br/> <span data-ttu-id="5aea0-179">Mer information om prioritet finns i Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="5aea0-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="5aea0-181">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5aea0-183">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="5aea0-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5aea0-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="5aea0-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="5aea0-185">För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="5aea0-185">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="5aea0-186">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="5aea0-186">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="5aea0-188">Välj **Hantera** bredvid den domän som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="5aea0-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="5aea0-190">Välj **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="5aea0-192">Under  **Lägg till en zonfil** väljer du **CNAME-post** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="5aea0-194">I rutorna för den nya posten skriver du in eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5aea0-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5aea0-195">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-195">**Name**</span></span>|<span data-ttu-id="5aea0-196">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-196">**Type**</span></span>|<span data-ttu-id="5aea0-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5aea0-197">**TTL**</span></span>|<span data-ttu-id="5aea0-198">**VÄRD (pekar på eller adress värde)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5aea0-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5aea0-199">autodiscover</span></span>  <br/> |<span data-ttu-id="5aea0-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="5aea0-200">CNAME</span></span>  <br/> |<span data-ttu-id="5aea0-201">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5aea0-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5aea0-203">sip</span><span class="sxs-lookup"><span data-stu-id="5aea0-203">sip</span></span>  <br/> |<span data-ttu-id="5aea0-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="5aea0-204">CNAME</span></span>  <br/> |<span data-ttu-id="5aea0-205">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5aea0-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5aea0-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5aea0-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5aea0-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="5aea0-208">CNAME</span></span>  <br/> |<span data-ttu-id="5aea0-209">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5aea0-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5aea0-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5aea0-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5aea0-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="5aea0-212">CNAME</span></span>  <br/> |<span data-ttu-id="5aea0-213">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5aea0-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="5aea0-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5aea0-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5aea0-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="5aea0-216">CNAME</span></span>  <br/> |<span data-ttu-id="5aea0-217">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5aea0-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="5aea0-220">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="5aea0-222">Upprepa föregående steg för att skapa de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="5aea0-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="5aea0-223">För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.</span><span class="sxs-lookup"><span data-stu-id="5aea0-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5aea0-224">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="5aea0-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5aea0-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="5aea0-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5aea0-226">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="5aea0-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5aea0-227">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="5aea0-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5aea0-228">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5aea0-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5aea0-229">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="5aea0-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="5aea0-230">För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="5aea0-230">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="5aea0-231">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="5aea0-231">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="5aea0-233">Välj **Hantera** bredvid den domän som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="5aea0-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="5aea0-235">Välj **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="5aea0-237">Under **Lägg till en zonfil** väljer du **txt Record** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="5aea0-239">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5aea0-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5aea0-240">Du måste använda citat tecken före och efter posten i TXT-rutan.</span><span class="sxs-lookup"><span data-stu-id="5aea0-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="5aea0-241">**Name**</span><span class="sxs-lookup"><span data-stu-id="5aea0-241">**Name**</span></span>|<span data-ttu-id="5aea0-242">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-242">**Type**</span></span>|<span data-ttu-id="5aea0-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5aea0-243">**TTL**</span></span>|<span data-ttu-id="5aea0-244">**TXT-data (mål)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5aea0-245">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="5aea0-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="5aea0-246">TXT</span><span class="sxs-lookup"><span data-stu-id="5aea0-246">TXT</span></span>  <br/> |<span data-ttu-id="5aea0-247">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-248">"v = spf1 inkluderar include SPF. Protection. Outlook. com-all"</span><span class="sxs-lookup"><span data-stu-id="5aea0-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="5aea0-249">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="5aea0-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="5aea0-251">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5aea0-253">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="5aea0-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5aea0-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="5aea0-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="5aea0-255">För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="5aea0-255">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="5aea0-256">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="5aea0-256">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="5aea0-258">Välj  **Hantera** bredvid den domän som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="5aea0-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="5aea0-260">Välj **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="5aea0-262">Under  **Lägg till en zonfil** väljer du **SRV-post** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="5aea0-264">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5aea0-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5aea0-265">Fältet Name är en kombination av tjänsten (till exempel _sip) och protokoll (till exempel _tls).</span><span class="sxs-lookup"><span data-stu-id="5aea0-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="5aea0-266">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-266">**Type**</span></span>|<span data-ttu-id="5aea0-267">**Namn**</span><span class="sxs-lookup"><span data-stu-id="5aea0-267">**Name**</span></span>|<span data-ttu-id="5aea0-268">**TTL (SEK)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-268">**TTL (SEC)**</span></span>|<span data-ttu-id="5aea0-269">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="5aea0-269">**Priority**</span></span>|<span data-ttu-id="5aea0-270">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="5aea0-270">**Weight**</span></span>|<span data-ttu-id="5aea0-271">**Port**</span><span class="sxs-lookup"><span data-stu-id="5aea0-271">**Port**</span></span>|<span data-ttu-id="5aea0-272">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="5aea0-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5aea0-273">SRV (tjänst)</span><span class="sxs-lookup"><span data-stu-id="5aea0-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="5aea0-274">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="5aea0-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="5aea0-275">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-276">100</span><span class="sxs-lookup"><span data-stu-id="5aea0-276">100</span></span>  <br/> |<span data-ttu-id="5aea0-277">9.1</span><span class="sxs-lookup"><span data-stu-id="5aea0-277">1</span></span>  <br/> |<span data-ttu-id="5aea0-278">443</span><span class="sxs-lookup"><span data-stu-id="5aea0-278">443</span></span>  <br/> |<span data-ttu-id="5aea0-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5aea0-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5aea0-280">SRV (tjänst)</span><span class="sxs-lookup"><span data-stu-id="5aea0-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="5aea0-281">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="5aea0-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5aea0-282">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="5aea0-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="5aea0-283">100</span><span class="sxs-lookup"><span data-stu-id="5aea0-283">100</span></span>  <br/> |<span data-ttu-id="5aea0-284">9.1</span><span class="sxs-lookup"><span data-stu-id="5aea0-284">1</span></span>  <br/> |<span data-ttu-id="5aea0-285">5061</span><span class="sxs-lookup"><span data-stu-id="5aea0-285">5061</span></span>  <br/> |<span data-ttu-id="5aea0-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5aea0-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="5aea0-288">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="5aea0-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="5aea0-290">Upprepa stegen för att skapa den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="5aea0-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="5aea0-291">I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="5aea0-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5aea0-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5aea0-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

