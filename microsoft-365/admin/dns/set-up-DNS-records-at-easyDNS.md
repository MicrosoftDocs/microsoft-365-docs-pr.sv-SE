---
title: Skapa DNS-poster på easyDNS för Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på easyDNS för Microsoft.
ms.openlocfilehash: b7b29900108ab94f0fd99dcf3404cfa137ce92ff
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631363"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="c2340-103">Skapa DNS-poster på easyDNS för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2340-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="c2340-104">[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="c2340-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c2340-105">Du måste lägga till alla följande DNS-poster på registratorns webbplats för att dirigera e-post till Microsoft, använda domänen för Teams och Skype för företag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="c2340-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="c2340-106">SRV-poster är för närvarande INTE tillgängliga under alla easyDNS-servicepaket.</span><span class="sxs-lookup"><span data-stu-id="c2340-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="c2340-107">Du kan behöva uppgradera till en högre servicenivå med easyDNS för att lägga till SRV-poster som krävs för Skype för företag.</span><span class="sxs-lookup"><span data-stu-id="c2340-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="c2340-108">Kontrollera att du äger domänen med en TXT-post</span><span class="sxs-lookup"><span data-stu-id="c2340-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="c2340-109">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c2340-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c2340-110">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="c2340-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c2340-111">Under rubriken **TXT-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="c2340-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c2340-112">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="c2340-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="c2340-113">**Värd**</span><span class="sxs-lookup"><span data-stu-id="c2340-113">**Host**</span></span>|<span data-ttu-id="c2340-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="c2340-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="c2340-115">MS=msXXXXXXXX (Använd det värde som du har angett på sidan Domäner för administrationscenter)</span><span class="sxs-lookup"><span data-stu-id="c2340-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="c2340-116">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c2340-117">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="c2340-118">Vänta några minuter innan du fortsätter, så att posten du just skapade kan spridas över Internet och identifieras av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2340-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="c2340-119">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="c2340-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="c2340-120">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c2340-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="c2340-121">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="c2340-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="c2340-122">Välj **Starta inställningar** på sidan **Installationsprogrammet.**</span><span class="sxs-lookup"><span data-stu-id="c2340-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="c2340-123">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="c2340-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="c2340-124">Lägga till en MX-post för att dirigera e-post till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2340-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="c2340-125">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c2340-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c2340-126">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="c2340-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c2340-127">Under rubriken **MX-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="c2340-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c2340-128">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="c2340-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="c2340-129">**POST FÖR ZON**</span><span class="sxs-lookup"><span data-stu-id="c2340-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="c2340-130">**E-POSTSERVER**</span><span class="sxs-lookup"><span data-stu-id="c2340-130">**MAIL SERVER**</span></span>|<span data-ttu-id="c2340-131">**Pref**</span><span class="sxs-lookup"><span data-stu-id="c2340-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c2340-132">\<domännyckeln\>.mail.protection.outlook.com (Hämta ditt \<domännyckelvärde\> från sidan Domäner för administrationscenter)</span><span class="sxs-lookup"><span data-stu-id="c2340-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="c2340-133">0</span><span class="sxs-lookup"><span data-stu-id="c2340-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="c2340-134">Om du vill spara dina andra MX-poster för säkerhetskopiering kan du kopiera dem någonstans.</span><span class="sxs-lookup"><span data-stu-id="c2340-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="c2340-135">Innan du går vidare tar du bort alla andra MX-poster här.</span><span class="sxs-lookup"><span data-stu-id="c2340-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="c2340-136">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c2340-137">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="c2340-138">Lägga till de CNAME-poster som krävs</span><span class="sxs-lookup"><span data-stu-id="c2340-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="c2340-139">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c2340-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c2340-140">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="c2340-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c2340-141">Under rubriken **CNAME/Alias-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="c2340-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c2340-142">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="c2340-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="c2340-143">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="c2340-143">**HOST**</span></span>|<span data-ttu-id="c2340-144">**Adress (Måste sluta med ett ".")**</span><span class="sxs-lookup"><span data-stu-id="c2340-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="c2340-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c2340-145">autodiscover</span></span>  <br/> |<span data-ttu-id="c2340-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="c2340-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="c2340-147">sip</span><span class="sxs-lookup"><span data-stu-id="c2340-147">sip</span></span>  <br/> |<span data-ttu-id="c2340-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c2340-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="c2340-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c2340-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c2340-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c2340-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="c2340-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c2340-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c2340-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="c2340-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="c2340-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c2340-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c2340-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c2340-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="c2340-155">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c2340-156">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c2340-157">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="c2340-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="c2340-158">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c2340-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c2340-159">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="c2340-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c2340-160">Under rubriken **TXT-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="c2340-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c2340-161">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="c2340-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="c2340-162">**Värd**</span><span class="sxs-lookup"><span data-stu-id="c2340-162">**Host**</span></span>|<span data-ttu-id="c2340-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="c2340-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="c2340-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c2340-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="c2340-165">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c2340-166">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c2340-167">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2340-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="c2340-168">SRV-poster är för närvarande INTE tillgängliga under easyDNS Domain Plus-tjänstnivå.</span><span class="sxs-lookup"><span data-stu-id="c2340-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="c2340-169">Du kan behöva uppgradera till en högre servicenivå med easyDNS för att lägga till SRV-poster</span><span class="sxs-lookup"><span data-stu-id="c2340-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="c2340-170">Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c2340-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c2340-171">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="c2340-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c2340-172">Under rubriken **SRV-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="c2340-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c2340-173">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="c2340-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="c2340-174">**SERVICE (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="c2340-174">**SERVICE**</span></span>|<span data-ttu-id="c2340-175">**Proto**</span><span class="sxs-lookup"><span data-stu-id="c2340-175">**PROTO**</span></span>|<span data-ttu-id="c2340-176">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="c2340-176">**HOST**</span></span>|<span data-ttu-id="c2340-177">**Pri**</span><span class="sxs-lookup"><span data-stu-id="c2340-177">**PRI**</span></span>|<span data-ttu-id="c2340-178">**Wgt**</span><span class="sxs-lookup"><span data-stu-id="c2340-178">**WGT**</span></span>|<span data-ttu-id="c2340-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="c2340-179">**PORT**</span></span>|<span data-ttu-id="c2340-180">**TARGET(Måste sluta med ett ".")**</span><span class="sxs-lookup"><span data-stu-id="c2340-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="c2340-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2340-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2340-182">_sip</span><span class="sxs-lookup"><span data-stu-id="c2340-182">_sip</span></span>  <br/> |<span data-ttu-id="c2340-183">TLS</span><span class="sxs-lookup"><span data-stu-id="c2340-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="c2340-184">100</span><span class="sxs-lookup"><span data-stu-id="c2340-184">100</span></span>  <br/> |<span data-ttu-id="c2340-185">1</span><span class="sxs-lookup"><span data-stu-id="c2340-185">1</span></span>  <br/> |<span data-ttu-id="c2340-186">443</span><span class="sxs-lookup"><span data-stu-id="c2340-186">443</span></span>  <br/> |<span data-ttu-id="c2340-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c2340-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="c2340-188">1800</span><span class="sxs-lookup"><span data-stu-id="c2340-188">1800</span></span>  <br/> |
    |<span data-ttu-id="c2340-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c2340-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="c2340-190">TCP</span><span class="sxs-lookup"><span data-stu-id="c2340-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="c2340-191">100</span><span class="sxs-lookup"><span data-stu-id="c2340-191">100</span></span>  <br/> |<span data-ttu-id="c2340-192">1</span><span class="sxs-lookup"><span data-stu-id="c2340-192">1</span></span>  <br/> |<span data-ttu-id="c2340-193">5061</span><span class="sxs-lookup"><span data-stu-id="c2340-193">5061</span></span>  <br/> |<span data-ttu-id="c2340-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c2340-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="c2340-195">1800</span><span class="sxs-lookup"><span data-stu-id="c2340-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="c2340-196">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c2340-197">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="c2340-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

