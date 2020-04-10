---
title: Skapa DNS-poster i Netregistry för Office 365
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster i Netregistry för Office 365.
ms.openlocfilehash: e1f2414817357b8435bc002860a35c6e76d4314e
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211140"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="4e2ca-103">Skapa DNS-poster i Netregistry för Office 365</span><span class="sxs-lookup"><span data-stu-id="4e2ca-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="4e2ca-104">[Läs frågor och svar om domäner](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4e2ca-105">Om Netregistry är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4e2ca-106">Det här är de viktigaste posterna att lägga till:</span><span class="sxs-lookup"><span data-stu-id="4e2ca-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="4e2ca-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="4e2ca-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="4e2ca-108">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="4e2ca-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="4e2ca-109">Lägg till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="4e2ca-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="4e2ca-110">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="4e2ca-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="4e2ca-111">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="4e2ca-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="4e2ca-112">När du har lagt till dessa poster i Netregistry konfigureras domänen så att den fungerar med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="4e2ca-113">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e2ca-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4e2ca-117">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="4e2ca-117">Add a TXT record for verification</span></span>
<span data-ttu-id="4e2ca-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="4e2ca-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="4e2ca-p102">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e2ca-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4e2ca-123">För att komma igång, gå till din domänsida i Netregistry med hjälp av [denna länk](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-123">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="4e2ca-124">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-124">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="4e2ca-126">Bredvid den domän som du vill hantera väljer du **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="4e2ca-128">Välj **Zonhanteraren**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="4e2ca-130">Under **Lägg till en zonpost**väljer du **TXT-post** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="4e2ca-132">Du måste använda citattecken före och efter posten i rutan TXT.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="4e2ca-133">Skriv eller kopiera och klistra in värdena från följande tabell i formuläret **Ny TXT-post.**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="4e2ca-134">**Namn**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-134">**Name**</span></span>|<span data-ttu-id="4e2ca-135">**TTL (SEK)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-135">**TTL (SEC)**</span></span>|<span data-ttu-id="4e2ca-136">**TXT (Pekar på adress eller värde)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4e2ca-137">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="4e2ca-138">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-139">"MS=msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="4e2ca-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="4e2ca-140">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-140">**Note:** This is an example.</span></span> <span data-ttu-id="4e2ca-141">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="4e2ca-142">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="4e2ca-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="4e2ca-144">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-144">Select **Add record**.</span></span>
    
<span data-ttu-id="4e2ca-145">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="4e2ca-146">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4e2ca-147">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4e2ca-148">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4e2ca-149">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4e2ca-150">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4e2ca-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="4e2ca-154">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="4e2ca-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="4e2ca-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="4e2ca-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="4e2ca-156">För att komma igång, gå till din domänsida i Netregistry med hjälp av [denna länk](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-156">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="4e2ca-157">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-157">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="4e2ca-159">Bredvid den domän som du vill hantera väljer du **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="4e2ca-161">Välj **Zonhanteraren**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="4e2ca-163">Under **Aktuella zonposter**tar du bort standard-MX-posterna genom att välja **Ta bort** bredvid varje MX-post i listan.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="4e2ca-165">Under **Lägg till en zonpost**väljer du **MX Record** i listan och väljer sedan Skapa ny **post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="4e2ca-167">Skriv eller kopiera och klistra in värdena från följande tabell i formuläret **Ny MX-post.**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="4e2ca-168">**Namn**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-168">**Name**</span></span>|<span data-ttu-id="4e2ca-169">**TTL (SEK)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-169">**TTL (SEC)**</span></span>|<span data-ttu-id="4e2ca-170">**Exchange (Pekar på adress eller värde)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="4e2ca-171">**Är värden fullt kvalificerad?**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="4e2ca-172">**Preferens (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4e2ca-173">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="4e2ca-174">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="4e2ca-175">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4e2ca-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4e2ca-176">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="4e2ca-177">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="4e2ca-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="4e2ca-178">(markera kryssrutan)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="4e2ca-179">10</span><span class="sxs-lookup"><span data-stu-id="4e2ca-179">10</span></span>  <br/> <span data-ttu-id="4e2ca-180">Mer information om prioritet finns i Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="4e2ca-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="4e2ca-182">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="4e2ca-184">Lägga till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="4e2ca-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="4e2ca-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="4e2ca-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="4e2ca-186">För att komma igång, gå till din domänsida i Netregistry med hjälp av [denna länk](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-186">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="4e2ca-187">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-187">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="4e2ca-189">Bredvid den domän som du vill hantera väljer du **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="4e2ca-191">Välj **Zonhanteraren**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="4e2ca-193">Under **Lägg till en zonpost**väljer du **CNAME-post** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="4e2ca-195">I rutorna för den nya posten skriver du in eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="4e2ca-196">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-196">**Name**</span></span>|<span data-ttu-id="4e2ca-197">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-197">**Type**</span></span>|<span data-ttu-id="4e2ca-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-198">**TTL**</span></span>|<span data-ttu-id="4e2ca-199">**HOST (Pekar på eller adressvärde)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4e2ca-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4e2ca-200">autodiscover</span></span>  <br/> |<span data-ttu-id="4e2ca-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="4e2ca-201">CNAME</span></span>  <br/> |<span data-ttu-id="4e2ca-202">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4e2ca-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="4e2ca-204">sip</span><span class="sxs-lookup"><span data-stu-id="4e2ca-204">sip</span></span>  <br/> |<span data-ttu-id="4e2ca-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="4e2ca-205">CNAME</span></span>  <br/> |<span data-ttu-id="4e2ca-206">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4e2ca-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4e2ca-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4e2ca-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4e2ca-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="4e2ca-209">CNAME</span></span>  <br/> |<span data-ttu-id="4e2ca-210">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4e2ca-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4e2ca-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4e2ca-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4e2ca-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="4e2ca-213">CNAME</span></span>  <br/> |<span data-ttu-id="4e2ca-214">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4e2ca-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="4e2ca-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4e2ca-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4e2ca-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="4e2ca-217">CNAME</span></span>  <br/> |<span data-ttu-id="4e2ca-218">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4e2ca-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="4e2ca-221">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="4e2ca-223">Upprepa föregående steg för att skapa de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="4e2ca-224">För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4e2ca-225">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="4e2ca-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4e2ca-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="4e2ca-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e2ca-227">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4e2ca-228">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4e2ca-229">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="4e2ca-230">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="4e2ca-231">För att komma igång, gå till din domänsida i Netregistry med hjälp av [denna länk](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-231">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="4e2ca-232">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-232">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="4e2ca-234">Bredvid den domän som du vill hantera väljer du **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="4e2ca-236">Välj **Zonhanteraren**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="4e2ca-238">Under **Lägg till en zonpost**väljer du **TXT-post** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="4e2ca-240">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4e2ca-241">Du måste använda citattecken före och efter posten i rutan TXT.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="4e2ca-242">**Name**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-242">**Name**</span></span>|<span data-ttu-id="4e2ca-243">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-243">**Type**</span></span>|<span data-ttu-id="4e2ca-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-244">**TTL**</span></span>|<span data-ttu-id="4e2ca-245">**TXT-data (mål)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4e2ca-246">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="4e2ca-247">TXT</span><span class="sxs-lookup"><span data-stu-id="4e2ca-247">TXT</span></span>  <br/> |<span data-ttu-id="4e2ca-248">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-249">"v=spf1 include:spf.protection.outlook.com -all"</span><span class="sxs-lookup"><span data-stu-id="4e2ca-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="4e2ca-250">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="4e2ca-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXT-värden](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="4e2ca-252">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="4e2ca-254">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="4e2ca-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="4e2ca-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="4e2ca-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="4e2ca-256">För att komma igång, gå till din domänsida i Netregistry med hjälp av [denna länk](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-256">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="4e2ca-257">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-257">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="4e2ca-259">Bredvid den domän som du vill hantera väljer du **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="4e2ca-261">Välj **Zonhanteraren**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="4e2ca-263">Under **Lägg till en zonpost**väljer du **SRV-post** i listan och väljer sedan **Skapa ny post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="4e2ca-265">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4e2ca-266">Fältet Namn är en kombination av tjänsten (till exempel _sip) och protokoll (till exempel _tls).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="4e2ca-267">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-267">**Type**</span></span>|<span data-ttu-id="4e2ca-268">**Namn**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-268">**Name**</span></span>|<span data-ttu-id="4e2ca-269">**TTL (SEK)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-269">**TTL (SEC)**</span></span>|<span data-ttu-id="4e2ca-270">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-270">**Priority**</span></span>|<span data-ttu-id="4e2ca-271">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-271">**Weight**</span></span>|<span data-ttu-id="4e2ca-272">**Port**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-272">**Port**</span></span>|<span data-ttu-id="4e2ca-273">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="4e2ca-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4e2ca-274">SRV (tjänst)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="4e2ca-275">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="4e2ca-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="4e2ca-276">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-277">100</span><span class="sxs-lookup"><span data-stu-id="4e2ca-277">100</span></span>  <br/> |<span data-ttu-id="4e2ca-278">1</span><span class="sxs-lookup"><span data-stu-id="4e2ca-278">1</span></span>  <br/> |<span data-ttu-id="4e2ca-279">443</span><span class="sxs-lookup"><span data-stu-id="4e2ca-279">443</span></span>  <br/> |<span data-ttu-id="4e2ca-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4e2ca-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4e2ca-281">SRV (tjänst)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="4e2ca-282">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4e2ca-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="4e2ca-283">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="4e2ca-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4e2ca-284">100</span><span class="sxs-lookup"><span data-stu-id="4e2ca-284">100</span></span>  <br/> |<span data-ttu-id="4e2ca-285">1</span><span class="sxs-lookup"><span data-stu-id="4e2ca-285">1</span></span>  <br/> |<span data-ttu-id="4e2ca-286">5061</span><span class="sxs-lookup"><span data-stu-id="4e2ca-286">5061</span></span>  <br/> |<span data-ttu-id="4e2ca-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4e2ca-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="4e2ca-289">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="4e2ca-291">Upprepa stegen för att skapa den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="4e2ca-292">I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="4e2ca-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4e2ca-p113">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4e2ca-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

