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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på easyDNS för Microsoft.
ms.openlocfilehash: 24f477d240af936975141c53d382e114a24c0ac5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400238"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="54e4f-103">Skapa DNS-poster på easyDNS för Microsoft</span><span class="sxs-lookup"><span data-stu-id="54e4f-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="54e4f-104">[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="54e4f-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="54e4f-105">Du måste lägga till alla följande DNS-poster på registratorns webbplats för att dirigera e-post till Microsoft, använda domänen för Teams och Skype för företag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="54e4f-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="54e4f-106">SRV-poster är för närvarande INTE tillgängliga under alla easyDNS-servicepaket.</span><span class="sxs-lookup"><span data-stu-id="54e4f-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="54e4f-107">Du kan behöva uppgradera till en högre servicenivå med easyDNS för att lägga till SRV-poster som krävs för Skype för företag.</span><span class="sxs-lookup"><span data-stu-id="54e4f-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="54e4f-108">Kontrollera att du äger domänen med en TXT-post</span><span class="sxs-lookup"><span data-stu-id="54e4f-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="54e4f-109">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54e4f-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="54e4f-110">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="54e4f-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="54e4f-111">Under rubriken **TXT-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="54e4f-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="54e4f-112">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="54e4f-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="54e4f-113">**Värd**</span><span class="sxs-lookup"><span data-stu-id="54e4f-113">**Host**</span></span>|<span data-ttu-id="54e4f-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="54e4f-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="54e4f-115">MS=msXXXXXXXX (Använd det värde som du har angett på sidan Domäner för administrationscenter)</span><span class="sxs-lookup"><span data-stu-id="54e4f-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="54e4f-116">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="54e4f-117">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="54e4f-118">Vänta några minuter innan du fortsätter, så att posten du just skapade kan spridas över Internet och identifieras av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54e4f-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="54e4f-119">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="54e4f-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="54e4f-120">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="54e4f-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="54e4f-121">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="54e4f-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="54e4f-122">Välj **Starta inställningar** på sidan **Installationsprogrammet.**</span><span class="sxs-lookup"><span data-stu-id="54e4f-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="54e4f-123">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="54e4f-124">Lägga till en MX-post för att dirigera e-post till Microsoft</span><span class="sxs-lookup"><span data-stu-id="54e4f-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="54e4f-125">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54e4f-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="54e4f-126">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="54e4f-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="54e4f-127">Under rubriken **MX-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="54e4f-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="54e4f-128">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="54e4f-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="54e4f-129">**POST FÖR ZON**</span><span class="sxs-lookup"><span data-stu-id="54e4f-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="54e4f-130">**E-POSTSERVER**</span><span class="sxs-lookup"><span data-stu-id="54e4f-130">**MAIL SERVER**</span></span>|<span data-ttu-id="54e4f-131">**Pref**</span><span class="sxs-lookup"><span data-stu-id="54e4f-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="54e4f-132">\<domain-key\>.mail.protection.outlook.com (Hämta ditt \<domain-key\> värde från sidan Domäner för administrationscenter)</span><span class="sxs-lookup"><span data-stu-id="54e4f-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="54e4f-133">0</span><span class="sxs-lookup"><span data-stu-id="54e4f-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="54e4f-134">Om du vill spara dina andra MX-poster för säkerhetskopiering kan du kopiera dem någonstans.</span><span class="sxs-lookup"><span data-stu-id="54e4f-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="54e4f-135">Innan du går vidare tar du bort alla andra MX-poster här.</span><span class="sxs-lookup"><span data-stu-id="54e4f-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="54e4f-136">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="54e4f-137">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="54e4f-138">Lägga till de CNAME-poster som krävs</span><span class="sxs-lookup"><span data-stu-id="54e4f-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="54e4f-139">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54e4f-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="54e4f-140">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="54e4f-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="54e4f-141">Under rubriken **CNAME/Alias-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="54e4f-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="54e4f-142">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="54e4f-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="54e4f-143">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="54e4f-143">**HOST**</span></span>|<span data-ttu-id="54e4f-144">**Adress (Måste sluta med ett ".")**</span><span class="sxs-lookup"><span data-stu-id="54e4f-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="54e4f-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="54e4f-145">autodiscover</span></span>  <br/> |<span data-ttu-id="54e4f-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="54e4f-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="54e4f-147">sip</span><span class="sxs-lookup"><span data-stu-id="54e4f-147">sip</span></span>  <br/> |<span data-ttu-id="54e4f-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="54e4f-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="54e4f-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="54e4f-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="54e4f-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="54e4f-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="54e4f-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="54e4f-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="54e4f-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="54e4f-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="54e4f-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="54e4f-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="54e4f-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="54e4f-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="54e4f-155">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="54e4f-156">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="54e4f-157">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="54e4f-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="54e4f-158">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54e4f-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="54e4f-159">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="54e4f-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="54e4f-160">Under rubriken **TXT-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="54e4f-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="54e4f-161">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="54e4f-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="54e4f-162">**Värd**</span><span class="sxs-lookup"><span data-stu-id="54e4f-162">**Host**</span></span>|<span data-ttu-id="54e4f-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="54e4f-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="54e4f-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="54e4f-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="54e4f-165">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="54e4f-166">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="54e4f-167">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="54e4f-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="54e4f-168">SRV-poster är för närvarande INTE tillgängliga under easyDNS Domain Plus-tjänstnivå.</span><span class="sxs-lookup"><span data-stu-id="54e4f-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="54e4f-169">Du kan behöva uppgradera till en högre servicenivå med easyDNS för att lägga till SRV-poster</span><span class="sxs-lookup"><span data-stu-id="54e4f-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="54e4f-170">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54e4f-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="54e4f-171">Välj dns under rubriken **alla domäner.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="54e4f-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="54e4f-172">Under rubriken **SRV-poster** väljer du redigeringsknappen (skiftnyckelikonen).</span><span class="sxs-lookup"><span data-stu-id="54e4f-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="54e4f-173">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="54e4f-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="54e4f-174">**SERVICE (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="54e4f-174">**SERVICE**</span></span>|<span data-ttu-id="54e4f-175">**Proto**</span><span class="sxs-lookup"><span data-stu-id="54e4f-175">**PROTO**</span></span>|<span data-ttu-id="54e4f-176">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="54e4f-176">**HOST**</span></span>|<span data-ttu-id="54e4f-177">**Pri**</span><span class="sxs-lookup"><span data-stu-id="54e4f-177">**PRI**</span></span>|<span data-ttu-id="54e4f-178">**Wgt**</span><span class="sxs-lookup"><span data-stu-id="54e4f-178">**WGT**</span></span>|<span data-ttu-id="54e4f-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="54e4f-179">**PORT**</span></span>|<span data-ttu-id="54e4f-180">**TARGET(Måste sluta med ett ".")**</span><span class="sxs-lookup"><span data-stu-id="54e4f-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="54e4f-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54e4f-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="54e4f-182">_sip</span><span class="sxs-lookup"><span data-stu-id="54e4f-182">_sip</span></span>  <br/> |<span data-ttu-id="54e4f-183">TLS</span><span class="sxs-lookup"><span data-stu-id="54e4f-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="54e4f-184">100</span><span class="sxs-lookup"><span data-stu-id="54e4f-184">100</span></span>  <br/> |<span data-ttu-id="54e4f-185">1</span><span class="sxs-lookup"><span data-stu-id="54e4f-185">1</span></span>  <br/> |<span data-ttu-id="54e4f-186">443</span><span class="sxs-lookup"><span data-stu-id="54e4f-186">443</span></span>  <br/> |<span data-ttu-id="54e4f-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="54e4f-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="54e4f-188">1800</span><span class="sxs-lookup"><span data-stu-id="54e4f-188">1800</span></span>  <br/> |
    |<span data-ttu-id="54e4f-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="54e4f-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="54e4f-190">TCP</span><span class="sxs-lookup"><span data-stu-id="54e4f-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="54e4f-191">100</span><span class="sxs-lookup"><span data-stu-id="54e4f-191">100</span></span>  <br/> |<span data-ttu-id="54e4f-192">1</span><span class="sxs-lookup"><span data-stu-id="54e4f-192">1</span></span>  <br/> |<span data-ttu-id="54e4f-193">5061</span><span class="sxs-lookup"><span data-stu-id="54e4f-193">5061</span></span>  <br/> |<span data-ttu-id="54e4f-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="54e4f-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="54e4f-195">1800</span><span class="sxs-lookup"><span data-stu-id="54e4f-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="54e4f-196">Välj **NÄSTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="54e4f-197">Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**.</span><span class="sxs-lookup"><span data-stu-id="54e4f-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

