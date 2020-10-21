---
title: Skapa DNS-poster på easyDNS för Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på easyDNS för Microsoft.
ms.openlocfilehash: 4909a02ec56fc9720a2636e822da0339e89bccf8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645557"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="a2370-103">Skapa DNS-poster på easyDNS för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2370-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="a2370-104">[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="a2370-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a2370-105">Du måste lägga till följande DNS-poster på din registrators webbplats för att dirigera e-post till Microsoft, använda din domän för Teams och Skype för företag, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="a2370-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="a2370-106">Obs! SRV-poster är för närvarande inte tillgängliga under alla easyDNS-tjänste paket.</span><span class="sxs-lookup"><span data-stu-id="a2370-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="a2370-107">Du kan behöva uppgradera till en högre tjänst nivå med easyDNS för att lägga till SRV-poster som krävs för Skype för företag.</span><span class="sxs-lookup"><span data-stu-id="a2370-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="a2370-108">Verifiera att du äger domänen med en TXT-post</span><span class="sxs-lookup"><span data-stu-id="a2370-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="a2370-109">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a2370-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="a2370-110">Under rubriken **alla domäner** väljer du **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a2370-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="a2370-111">Under rubriken **TXT Records** väljer du knappen Redigera (Skift nyckel ikonen).</span><span class="sxs-lookup"><span data-stu-id="a2370-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="a2370-112">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="a2370-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="a2370-113">**Värd**</span><span class="sxs-lookup"><span data-stu-id="a2370-113">**Host**</span></span>|<span data-ttu-id="a2370-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="a2370-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="a2370-115">MS = msXXXXXXXX (Använd det värde du gav på sidan Domains Center-domäner)</span><span class="sxs-lookup"><span data-stu-id="a2370-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="a2370-116">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a2370-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="a2370-117">Kontrol lera att posten är korrekt och välj sedan **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="a2370-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="a2370-118">Vänta några minuter innan du fortsätter, så att den post som du just skapade kan spridas via Internet och identifieras av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2370-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="a2370-119">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="a2370-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="a2370-120">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="a2370-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="a2370-121">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="a2370-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="a2370-122">På sidan **Setup** väljer du **Start setup.**</span><span class="sxs-lookup"><span data-stu-id="a2370-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="a2370-123">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="a2370-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="a2370-124">Lägga till en MX-post för att dirigera e-post till Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2370-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="a2370-125">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a2370-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="a2370-126">Under rubriken **alla domäner** väljer du **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a2370-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="a2370-127">Under rubriken **MX Records** väljer du knappen Redigera (Skift nyckel ikonen).</span><span class="sxs-lookup"><span data-stu-id="a2370-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="a2370-128">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="a2370-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="a2370-129">**E-POST FÖR ZONEN**</span><span class="sxs-lookup"><span data-stu-id="a2370-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="a2370-130">**E-POSTSERVER**</span><span class="sxs-lookup"><span data-stu-id="a2370-130">**MAIL SERVER**</span></span>|<span data-ttu-id="a2370-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="a2370-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a2370-132">\<domain-key\>. mail.protection.outlook.com (Hämta \<domain-key\> värdet från sidan Domains för administrations centret)</span><span class="sxs-lookup"><span data-stu-id="a2370-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="a2370-133">siffrorna</span><span class="sxs-lookup"><span data-stu-id="a2370-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="a2370-134">Om du vill spara dina andra MX-poster för säkerhets kopiering kan du kopiera dem till en annan plats.</span><span class="sxs-lookup"><span data-stu-id="a2370-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="a2370-135">Innan du fortsätter tar du bort alla andra MX-poster här.</span><span class="sxs-lookup"><span data-stu-id="a2370-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="a2370-136">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a2370-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="a2370-137">Kontrol lera att posten är korrekt och välj sedan **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="a2370-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="a2370-138">Lägga till de CNAME-poster som krävs</span><span class="sxs-lookup"><span data-stu-id="a2370-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="a2370-139">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a2370-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="a2370-140">Under rubriken **alla domäner** väljer du **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a2370-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="a2370-141">Under rubriken **CNAME/Ali-poster** väljer du knappen Redigera (Skift nyckel ikonen).</span><span class="sxs-lookup"><span data-stu-id="a2370-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="a2370-142">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="a2370-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="a2370-143">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="a2370-143">**HOST**</span></span>|<span data-ttu-id="a2370-144">**Adress (måste sluta med ".")**</span><span class="sxs-lookup"><span data-stu-id="a2370-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a2370-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a2370-145">autodiscover</span></span>  <br/> |<span data-ttu-id="a2370-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a2370-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="a2370-147">sip</span><span class="sxs-lookup"><span data-stu-id="a2370-147">sip</span></span>  <br/> |<span data-ttu-id="a2370-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a2370-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="a2370-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a2370-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a2370-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a2370-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="a2370-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a2370-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a2370-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="a2370-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="a2370-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a2370-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a2370-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a2370-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="a2370-155">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a2370-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="a2370-156">Kontrol lera att posten är korrekt och välj sedan **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="a2370-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a2370-157">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="a2370-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="a2370-158">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a2370-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="a2370-159">Under rubriken **alla domäner** väljer du **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a2370-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="a2370-160">Under rubriken **TXT Records** väljer du knappen Redigera (Skift nyckel ikonen).</span><span class="sxs-lookup"><span data-stu-id="a2370-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="a2370-161">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="a2370-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="a2370-162">**Värd**</span><span class="sxs-lookup"><span data-stu-id="a2370-162">**Host**</span></span>|<span data-ttu-id="a2370-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="a2370-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="a2370-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a2370-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="a2370-165">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a2370-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="a2370-166">Kontrol lera att posten är korrekt och välj sedan **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="a2370-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a2370-167">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2370-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="a2370-168">Obs! SRV-poster är för närvarande inte tillgängliga under easyDNS ' Domain plus Service Level.</span><span class="sxs-lookup"><span data-stu-id="a2370-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="a2370-169">Du kan behöva uppgradera till en högre service nivå med easyDNS för att lägga till SRV-poster</span><span class="sxs-lookup"><span data-stu-id="a2370-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="a2370-170">Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a2370-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="a2370-171">Under rubriken **alla domäner** väljer du **DNS.**</span><span class="sxs-lookup"><span data-stu-id="a2370-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="a2370-172">Under rubriken **SRV Records** väljer du knappen Redigera (Skift nyckel ikonen).</span><span class="sxs-lookup"><span data-stu-id="a2370-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="a2370-173">Ange följande poster i textfälten:</span><span class="sxs-lookup"><span data-stu-id="a2370-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="a2370-174">**SERVICE (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="a2370-174">**SERVICE**</span></span>|<span data-ttu-id="a2370-175">**PROTO**</span><span class="sxs-lookup"><span data-stu-id="a2370-175">**PROTO**</span></span>|<span data-ttu-id="a2370-176">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="a2370-176">**HOST**</span></span>|<span data-ttu-id="a2370-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="a2370-177">**PRI**</span></span>|<span data-ttu-id="a2370-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="a2370-178">**WGT**</span></span>|<span data-ttu-id="a2370-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="a2370-179">**PORT**</span></span>|<span data-ttu-id="a2370-180">**MÅL (måste sluta med ".")**</span><span class="sxs-lookup"><span data-stu-id="a2370-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="a2370-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a2370-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a2370-182">_sip</span><span class="sxs-lookup"><span data-stu-id="a2370-182">_sip</span></span>  <br/> |<span data-ttu-id="a2370-183">TLS</span><span class="sxs-lookup"><span data-stu-id="a2370-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="a2370-184">100</span><span class="sxs-lookup"><span data-stu-id="a2370-184">100</span></span>  <br/> |<span data-ttu-id="a2370-185">9.1</span><span class="sxs-lookup"><span data-stu-id="a2370-185">1</span></span>  <br/> |<span data-ttu-id="a2370-186">443</span><span class="sxs-lookup"><span data-stu-id="a2370-186">443</span></span>  <br/> |<span data-ttu-id="a2370-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a2370-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="a2370-188">1800</span><span class="sxs-lookup"><span data-stu-id="a2370-188">1800</span></span>  <br/> |
    |<span data-ttu-id="a2370-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a2370-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a2370-190">TCP</span><span class="sxs-lookup"><span data-stu-id="a2370-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="a2370-191">100</span><span class="sxs-lookup"><span data-stu-id="a2370-191">100</span></span>  <br/> |<span data-ttu-id="a2370-192">9.1</span><span class="sxs-lookup"><span data-stu-id="a2370-192">1</span></span>  <br/> |<span data-ttu-id="a2370-193">5061</span><span class="sxs-lookup"><span data-stu-id="a2370-193">5061</span></span>  <br/> |<span data-ttu-id="a2370-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a2370-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="a2370-195">1800</span><span class="sxs-lookup"><span data-stu-id="a2370-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="a2370-196">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a2370-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="a2370-197">Kontrol lera att posten är korrekt och välj sedan **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="a2370-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

