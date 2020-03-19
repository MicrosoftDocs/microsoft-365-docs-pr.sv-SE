---
title: Skapa DNS-poster på easyDNS för Office 365
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på easyDNS för Office 365.
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810142"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a><span data-ttu-id="731e6-103">Skapa DNS-poster på easyDNS för Office 365</span><span class="sxs-lookup"><span data-stu-id="731e6-103">Create DNS records at easyDNS for Office 365</span></span>

<span data-ttu-id="731e6-104">[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="731e6-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="731e6-105">Du måste lägga till alla följande DNS-poster på registratorns webbplats för att dirigera e-post till Office 365, använda domänen för Teams och Skype för företag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="731e6-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="731e6-106">SRV-poster är för närvarande INTE tillgängliga under alla easyDNS-servicepaket.</span><span class="sxs-lookup"><span data-stu-id="731e6-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="731e6-107">Du kan behöva uppgradera till en högre servicenivå med easyDNS för att lägga till SRV-poster som krävs för Office 365 Skype för företag.</span><span class="sxs-lookup"><span data-stu-id="731e6-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="731e6-108">Kontrollera att du äger domänen med en TXT-post</span><span class="sxs-lookup"><span data-stu-id="731e6-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="731e6-109">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="731e6-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="731e6-110">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="731e6-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="731e6-111">Under rubriken **TXT-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="731e6-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="731e6-112">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="731e6-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="731e6-113">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="731e6-113">**Host**</span></span>|<span data-ttu-id="731e6-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="731e6-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="731e6-115">MS=msXXXXXXXX (Använd det värde som du har angett på sidan Domäner för administrationscenter)</span><span class="sxs-lookup"><span data-stu-id="731e6-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="731e6-116">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="731e6-117">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="731e6-118">Vänta några minuter innan du fortsätter, så att posten som du just skapade kan spridas över Internet och identifieras av Office 365.</span><span class="sxs-lookup"><span data-stu-id="731e6-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.</span></span>
    
8. <span data-ttu-id="731e6-119">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="731e6-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
    
9. <span data-ttu-id="731e6-120">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="731e6-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="731e6-121">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="731e6-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="731e6-122">Välj **Starta inställningar** på sidan **Installationsprogrammet.**</span><span class="sxs-lookup"><span data-stu-id="731e6-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="731e6-123">På sidan **Verifiera domän** väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="731e6-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a><span data-ttu-id="731e6-124">Lägga till en MX-post för att dirigera e-post till Office 365</span><span class="sxs-lookup"><span data-stu-id="731e6-124">Add an MX record to route email to Office 365</span></span>

1. <span data-ttu-id="731e6-125">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="731e6-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="731e6-126">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="731e6-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="731e6-127">Under rubriken **MX-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="731e6-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="731e6-128">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="731e6-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="731e6-129">**POST FÖR ZON**</span><span class="sxs-lookup"><span data-stu-id="731e6-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="731e6-130">**E-POSTSERVER**</span><span class="sxs-lookup"><span data-stu-id="731e6-130">**MAIL SERVER**</span></span>|<span data-ttu-id="731e6-131">**Pref**</span><span class="sxs-lookup"><span data-stu-id="731e6-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="731e6-132">\<domännyckeln\>.mail.protection.outlook.com (Hämta ditt \<domännyckelvärde\> från sidan Domäner för administrationscenter)</span><span class="sxs-lookup"><span data-stu-id="731e6-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="731e6-133">0</span><span class="sxs-lookup"><span data-stu-id="731e6-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="731e6-134">Om du vill spara dina andra MX-poster för säkerhetskopiering kan du kopiera dem någonstans.</span><span class="sxs-lookup"><span data-stu-id="731e6-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="731e6-135">Innan du går vidare tar du bort alla andra MX-poster här.</span><span class="sxs-lookup"><span data-stu-id="731e6-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="731e6-136">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="731e6-137">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="731e6-138">Lägga till de CNAME-poster som krävs</span><span class="sxs-lookup"><span data-stu-id="731e6-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="731e6-139">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="731e6-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="731e6-140">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="731e6-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="731e6-141">Under rubriken **CNAME/Alias-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="731e6-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="731e6-142">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="731e6-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="731e6-143">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="731e6-143">**HOST**</span></span>|<span data-ttu-id="731e6-144">**Adress (Måste sluta med ett ".")**</span><span class="sxs-lookup"><span data-stu-id="731e6-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="731e6-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="731e6-145">autodiscover</span></span>  <br/> |<span data-ttu-id="731e6-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="731e6-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="731e6-147">sip</span><span class="sxs-lookup"><span data-stu-id="731e6-147">sip</span></span>  <br/> |<span data-ttu-id="731e6-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="731e6-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="731e6-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="731e6-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="731e6-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="731e6-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="731e6-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="731e6-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="731e6-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="731e6-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="731e6-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="731e6-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="731e6-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="731e6-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="731e6-155">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="731e6-156">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="731e6-157">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="731e6-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="731e6-158">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="731e6-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="731e6-159">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="731e6-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="731e6-160">Under rubriken **TXT-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="731e6-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="731e6-161">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="731e6-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="731e6-162">**Host (värd)**</span><span class="sxs-lookup"><span data-stu-id="731e6-162">**Host**</span></span>|<span data-ttu-id="731e6-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="731e6-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="731e6-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="731e6-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="731e6-165">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="731e6-166">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="731e6-167">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="731e6-167">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="731e6-168">SRV-poster är för närvarande INTE tillgängliga under easyDNS Domain Plus-tjänstnivå.</span><span class="sxs-lookup"><span data-stu-id="731e6-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="731e6-169">Du kan behöva uppgradera till en högre servicenivå med easyDNS för att lägga till SRV-poster</span><span class="sxs-lookup"><span data-stu-id="731e6-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="731e6-170">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="731e6-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="731e6-171">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="731e6-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="731e6-172">Under rubriken **SRV-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="731e6-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="731e6-173">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="731e6-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="731e6-174">**SERVICE (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="731e6-174">**SERVICE**</span></span>|<span data-ttu-id="731e6-175">**Proto**</span><span class="sxs-lookup"><span data-stu-id="731e6-175">**PROTO**</span></span>|<span data-ttu-id="731e6-176">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="731e6-176">**HOST**</span></span>|<span data-ttu-id="731e6-177">**Pri**</span><span class="sxs-lookup"><span data-stu-id="731e6-177">**PRI**</span></span>|<span data-ttu-id="731e6-178">**Wgt**</span><span class="sxs-lookup"><span data-stu-id="731e6-178">**WGT**</span></span>|<span data-ttu-id="731e6-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="731e6-179">**PORT**</span></span>|<span data-ttu-id="731e6-180">**TARGET(Måste sluta med ett ".")**</span><span class="sxs-lookup"><span data-stu-id="731e6-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="731e6-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="731e6-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="731e6-182">_sip</span><span class="sxs-lookup"><span data-stu-id="731e6-182">_sip</span></span>  <br/> |<span data-ttu-id="731e6-183">TLS</span><span class="sxs-lookup"><span data-stu-id="731e6-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="731e6-184">100</span><span class="sxs-lookup"><span data-stu-id="731e6-184">100</span></span>  <br/> |<span data-ttu-id="731e6-185">1</span><span class="sxs-lookup"><span data-stu-id="731e6-185">1</span></span>  <br/> |<span data-ttu-id="731e6-186">443</span><span class="sxs-lookup"><span data-stu-id="731e6-186">443</span></span>  <br/> |<span data-ttu-id="731e6-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="731e6-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="731e6-188">1800</span><span class="sxs-lookup"><span data-stu-id="731e6-188">1800</span></span>  <br/> |
    |<span data-ttu-id="731e6-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="731e6-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="731e6-190">TCP</span><span class="sxs-lookup"><span data-stu-id="731e6-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="731e6-191">100</span><span class="sxs-lookup"><span data-stu-id="731e6-191">100</span></span>  <br/> |<span data-ttu-id="731e6-192">1</span><span class="sxs-lookup"><span data-stu-id="731e6-192">1</span></span>  <br/> |<span data-ttu-id="731e6-193">5061</span><span class="sxs-lookup"><span data-stu-id="731e6-193">5061</span></span>  <br/> |<span data-ttu-id="731e6-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="731e6-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="731e6-195">1800</span><span class="sxs-lookup"><span data-stu-id="731e6-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="731e6-196">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="731e6-197">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="731e6-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

