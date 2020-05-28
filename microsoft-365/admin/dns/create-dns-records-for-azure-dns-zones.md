---
title: Skapa DNS-poster för Azure DNS-zoner
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster i Azure DNS-zoner för Microsoft.
ms.openlocfilehash: fcc3ea42b7414cdd5fc0c34bfae91104287d2379
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400274"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="e7048-103">Skapa DNS-poster för Azure DNS-zoner</span><span class="sxs-lookup"><span data-stu-id="e7048-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="e7048-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="e7048-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e7048-105">Om Azure är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e7048-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e7048-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="e7048-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="e7048-107">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="e7048-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="e7048-108">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="e7048-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="e7048-109">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7048-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="e7048-110">Lägga till de fyra CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7048-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="e7048-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="e7048-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="e7048-112">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7048-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="e7048-113">När du har lagt till dessa poster i Azure konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="e7048-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7048-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7048-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e7048-117">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="e7048-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="e7048-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="e7048-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7048-119">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="e7048-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="e7048-120">När du registrerade dig för Azure skapade du en resursgrupp inom en DNS-zon och tilldelade sedan ditt domännamn till den resursgruppen.</span><span class="sxs-lookup"><span data-stu-id="e7048-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="e7048-121">Domännamnet är registrerat hos en extern domänregistristist. Azure erbjuder inte domänregistreringstjänster.</span><span class="sxs-lookup"><span data-stu-id="e7048-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="e7048-122">Om du vill verifiera och skapa DNS-poster för din domän i Microsoft måste du först ändra namnservrarna på domänregistraren så att de använder de Azure-namnservrar som tilldelats din resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="e7048-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="e7048-123">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="e7048-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="e7048-124">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="e7048-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="e7048-125">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="e7048-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="e7048-126">Ett exempel på Azure-tilldelade namnservrar visas nedan.</span><span class="sxs-lookup"><span data-stu-id="e7048-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="e7048-127">**Förnamnserver:** Använd namnservervärdet som tilldelats av Azure.</span><span class="sxs-lookup"><span data-stu-id="e7048-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="e7048-128">**Andra namnserver:** Använd namnservervärdet som tilldelats av Azure.</span><span class="sxs-lookup"><span data-stu-id="e7048-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="e7048-130">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="e7048-130">You should use at least two name server records.</span></span> <span data-ttu-id="e7048-131">Om det finns några andra namnservrar som anges på domänregistratorerns webbplats bör du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="e7048-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="e7048-132">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="e7048-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7048-133">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="e7048-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e7048-134">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="e7048-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e7048-135">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="e7048-135">Add a TXT record for verification</span></span>
<span data-ttu-id="e7048-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e7048-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e7048-p106">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="e7048-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7048-p107">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="e7048-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e7048-141">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e7048-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e7048-142">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7048-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e7048-144">Skriv i **DNS-zoner**med hjälp av **sökfältet** på **sidan Instrumentpanel** .</span><span class="sxs-lookup"><span data-stu-id="e7048-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="e7048-145">I resultatvisningen väljer du **DNS-zoner** under delen **Tjänster.**</span><span class="sxs-lookup"><span data-stu-id="e7048-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="e7048-146">När du har omdirigerats väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="e7048-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e7048-148">Välj **+ Postuppsättning**i **området DNS-zon** på sidan **Inställningar** för domänen .</span><span class="sxs-lookup"><span data-stu-id="e7048-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e7048-150">I området **Lägg till postuppsättning** väljer du värdena i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e7048-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e7048-151">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="e7048-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e7048-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7048-152">**Name**</span></span>|<span data-ttu-id="e7048-153">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7048-153">**Type**</span></span>|<span data-ttu-id="e7048-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7048-154">**TTL**</span></span>|<span data-ttu-id="e7048-155">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e7048-155">**TTL unit**</span></span>|<span data-ttu-id="e7048-156">**Värde**</span><span class="sxs-lookup"><span data-stu-id="e7048-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e7048-157">TXT</span><span class="sxs-lookup"><span data-stu-id="e7048-157">TXT</span></span>  <br/> |<span data-ttu-id="e7048-158">1</span><span class="sxs-lookup"><span data-stu-id="e7048-158">1</span></span>  <br/> |<span data-ttu-id="e7048-159">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-159">Hours</span></span>  <br/> |<span data-ttu-id="e7048-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e7048-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e7048-161">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="e7048-161">**Note:** This is an example.</span></span> <span data-ttu-id="e7048-162">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="e7048-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e7048-163">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e7048-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verifiera-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="e7048-165">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7048-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="e7048-166">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="e7048-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e7048-167">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="e7048-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e7048-168">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="e7048-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e7048-169">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="e7048-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e7048-170">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="e7048-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e7048-171">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="e7048-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e7048-172">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="e7048-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e7048-p111">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7048-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e7048-176">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7048-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e7048-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e7048-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e7048-178">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e7048-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e7048-179">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7048-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e7048-181">Välj den domän som du vill uppdatera i området **Alla resurser** på sidan **Instrumentpanel.**</span><span class="sxs-lookup"><span data-stu-id="e7048-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e7048-183">Välj **+ Postuppsättning**i **området DNS-zon** på sidan **Inställningar** för domänen .</span><span class="sxs-lookup"><span data-stu-id="e7048-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e7048-185">I området **Lägg till postuppsättning** väljer du värdena i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e7048-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e7048-186">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="e7048-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e7048-187">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7048-187">**Name**</span></span>|<span data-ttu-id="e7048-188">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7048-188">**Type**</span></span>|<span data-ttu-id="e7048-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7048-189">**TTL**</span></span>|<span data-ttu-id="e7048-190">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e7048-190">**TTL unit**</span></span>|<span data-ttu-id="e7048-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="e7048-191">**Preference**</span></span>|<span data-ttu-id="e7048-192">**Utbyte av e-post**</span><span class="sxs-lookup"><span data-stu-id="e7048-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e7048-193">MX</span><span class="sxs-lookup"><span data-stu-id="e7048-193">MX</span></span>  <br/> |<span data-ttu-id="e7048-194">1</span><span class="sxs-lookup"><span data-stu-id="e7048-194">1</span></span>  <br/> |<span data-ttu-id="e7048-195">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-195">Hours</span></span>  <br/> |<span data-ttu-id="e7048-196">10</span><span class="sxs-lookup"><span data-stu-id="e7048-196">10</span></span>  <br/> <span data-ttu-id="e7048-197">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e7048-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="e7048-198">*\<domain-key\>*.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e7048-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e7048-199">**Anm.:** Hämta ditt *\<domain-key\>* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="e7048-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="e7048-200">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e7048-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="e7048-202">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7048-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="e7048-204">Om det finns några andra MX-poster i avsnittet **MX-poster** måste du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="e7048-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="e7048-205">Välj först **MX-postuppsättningen**i **DNS-zonområdet** .</span><span class="sxs-lookup"><span data-stu-id="e7048-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="e7048-207">Välj sedan den MX-post som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="e7048-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="e7048-209">Markera **snabbmenyn (...)** och välj sedan **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="e7048-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="e7048-211">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e7048-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e7048-213">Lägga till de fyra CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7048-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e7048-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e7048-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e7048-215">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e7048-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e7048-216">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7048-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e7048-218">Välj den domän som du vill uppdatera i området **Alla resurser** på sidan **Instrumentpanel.**</span><span class="sxs-lookup"><span data-stu-id="e7048-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e7048-220">Välj **+ Postuppsättning**i **området DNS-zon** på sidan **Inställningar** för domänen .</span><span class="sxs-lookup"><span data-stu-id="e7048-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e7048-222">Lägg till den första av de fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e7048-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="e7048-223">I området **Lägg till postuppsättning** skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e7048-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e7048-224">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="e7048-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e7048-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7048-225">**Name**</span></span>|<span data-ttu-id="e7048-226">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7048-226">**Type**</span></span>|<span data-ttu-id="e7048-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7048-227">**TTL**</span></span>|<span data-ttu-id="e7048-228">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e7048-228">**TTL unit**</span></span>|<span data-ttu-id="e7048-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e7048-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7048-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e7048-230">autodiscover</span></span>  <br/> |<span data-ttu-id="e7048-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7048-231">CNAME</span></span>  <br/> |<span data-ttu-id="e7048-232">1</span><span class="sxs-lookup"><span data-stu-id="e7048-232">1</span></span>  <br/> |<span data-ttu-id="e7048-233">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-233">Hours</span></span>  <br/> |<span data-ttu-id="e7048-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e7048-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e7048-235">sip</span><span class="sxs-lookup"><span data-stu-id="e7048-235">sip</span></span>  <br/> |<span data-ttu-id="e7048-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7048-236">CNAME</span></span>  <br/> |<span data-ttu-id="e7048-237">1</span><span class="sxs-lookup"><span data-stu-id="e7048-237">1</span></span>  <br/> |<span data-ttu-id="e7048-238">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-238">Hours</span></span>  <br/> |<span data-ttu-id="e7048-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7048-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e7048-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e7048-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e7048-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7048-241">CNAME</span></span>  <br/> |<span data-ttu-id="e7048-242">1</span><span class="sxs-lookup"><span data-stu-id="e7048-242">1</span></span>  <br/> |<span data-ttu-id="e7048-243">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-243">Hours</span></span>  <br/> |<span data-ttu-id="e7048-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7048-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="e7048-246">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7048-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="e7048-248">Lägg till var och en av de tre andra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e7048-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="e7048-249">I **OMRÅDET DNS-zon** väljer du **+ Postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="e7048-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="e7048-250">Skapa sedan en post i den tomma postuppsättningen med hjälp av värdena från nästa rad i tabellen och välj återigen **OK** för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="e7048-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="e7048-251">Upprepa den här processen tills du har skapat alla fyra CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="e7048-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="e7048-252">(Valfritt) Lägg till 2 CNAME-poster för MDM.</span><span class="sxs-lookup"><span data-stu-id="e7048-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7048-253">Om du har MDM (Mobile Device Management) för Microsoft måste du skapa ytterligare två CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="e7048-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="e7048-254">Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e7048-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="e7048-255">(Om du inte har MDM kan du hoppa över det här steget.)</span><span class="sxs-lookup"><span data-stu-id="e7048-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="e7048-256">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7048-256">**Name**</span></span>|<span data-ttu-id="e7048-257">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7048-257">**Type**</span></span>|<span data-ttu-id="e7048-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7048-258">**TTL**</span></span>|<span data-ttu-id="e7048-259">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e7048-259">**TTL unit**</span></span>|<span data-ttu-id="e7048-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e7048-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7048-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e7048-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e7048-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7048-262">CNAME</span></span>  <br/> |<span data-ttu-id="e7048-263">1</span><span class="sxs-lookup"><span data-stu-id="e7048-263">1</span></span>  <br/> |<span data-ttu-id="e7048-264">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-264">Hours</span></span>  <br/> |<span data-ttu-id="e7048-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e7048-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="e7048-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e7048-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e7048-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7048-267">CNAME</span></span>  <br/> |<span data-ttu-id="e7048-268">1</span><span class="sxs-lookup"><span data-stu-id="e7048-268">1</span></span>  <br/> |<span data-ttu-id="e7048-269">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-269">Hours</span></span>  <br/> |<span data-ttu-id="e7048-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e7048-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e7048-271">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="e7048-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e7048-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e7048-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7048-273">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="e7048-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e7048-274">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="e7048-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e7048-275">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7048-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e7048-276">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="e7048-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e7048-277">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e7048-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e7048-278">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7048-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e7048-280">Välj den domän som du vill uppdatera i området **Alla resurser** på sidan **Instrumentpanel.**</span><span class="sxs-lookup"><span data-stu-id="e7048-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e7048-282">I **DNS-zonområdet** väljer du **TXT-postuppsättningen**.</span><span class="sxs-lookup"><span data-stu-id="e7048-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="e7048-284">I **egenskapsområdet Postuppsättning** väljer du värdena i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e7048-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e7048-285">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="e7048-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e7048-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7048-286">**Name**</span></span>|<span data-ttu-id="e7048-287">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7048-287">**Type**</span></span>|<span data-ttu-id="e7048-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7048-288">**TTL**</span></span>|<span data-ttu-id="e7048-289">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e7048-289">**TTL unit**</span></span>|<span data-ttu-id="e7048-290">**Värde**</span><span class="sxs-lookup"><span data-stu-id="e7048-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e7048-291">TXT</span><span class="sxs-lookup"><span data-stu-id="e7048-291">TXT</span></span>  <br/> |<span data-ttu-id="e7048-292">1</span><span class="sxs-lookup"><span data-stu-id="e7048-292">1</span></span>  <br/> |<span data-ttu-id="e7048-293">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-293">Hours</span></span>  <br/> |<span data-ttu-id="e7048-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e7048-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e7048-295">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="e7048-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="e7048-297">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e7048-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e7048-299">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7048-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e7048-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e7048-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e7048-301">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e7048-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e7048-302">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e7048-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e7048-304">Välj den domän som du vill uppdatera i området **Alla resurser** på sidan **Instrumentpanel.**</span><span class="sxs-lookup"><span data-stu-id="e7048-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e7048-306">Välj **+ Postuppsättning**i **området DNS-zon** på sidan **Inställningar** för domänen .</span><span class="sxs-lookup"><span data-stu-id="e7048-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e7048-308">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="e7048-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="e7048-309">I området **Lägg till postuppsättning** väljer du värdena från den första raden i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e7048-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e7048-310">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="e7048-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e7048-311">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7048-311">**Name**</span></span>|<span data-ttu-id="e7048-312">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e7048-312">**Type**</span></span>|<span data-ttu-id="e7048-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7048-313">**TTL**</span></span>|<span data-ttu-id="e7048-314">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e7048-314">**TTL unit**</span></span>|<span data-ttu-id="e7048-315">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="e7048-315">**Priority**</span></span>|<span data-ttu-id="e7048-316">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="e7048-316">**Weight**</span></span>|<span data-ttu-id="e7048-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="e7048-317">**Port**</span></span>|<span data-ttu-id="e7048-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="e7048-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7048-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e7048-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="e7048-320">SRV</span><span class="sxs-lookup"><span data-stu-id="e7048-320">SRV</span></span>  <br/> |<span data-ttu-id="e7048-321">1</span><span class="sxs-lookup"><span data-stu-id="e7048-321">1</span></span>  <br/> |<span data-ttu-id="e7048-322">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-322">Hours</span></span>  <br/> |<span data-ttu-id="e7048-323">100</span><span class="sxs-lookup"><span data-stu-id="e7048-323">100</span></span>  <br/> |<span data-ttu-id="e7048-324">1</span><span class="sxs-lookup"><span data-stu-id="e7048-324">1</span></span>  <br/> |<span data-ttu-id="e7048-325">443</span><span class="sxs-lookup"><span data-stu-id="e7048-325">443</span></span>  <br/> |<span data-ttu-id="e7048-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7048-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e7048-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e7048-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e7048-328">SRV</span><span class="sxs-lookup"><span data-stu-id="e7048-328">SRV</span></span>  <br/> |<span data-ttu-id="e7048-329">1</span><span class="sxs-lookup"><span data-stu-id="e7048-329">1</span></span>  <br/> |<span data-ttu-id="e7048-330">Tider</span><span class="sxs-lookup"><span data-stu-id="e7048-330">Hours</span></span>  <br/> |<span data-ttu-id="e7048-331">100</span><span class="sxs-lookup"><span data-stu-id="e7048-331">100</span></span>  <br/> |<span data-ttu-id="e7048-332">1</span><span class="sxs-lookup"><span data-stu-id="e7048-332">1</span></span>  <br/> |<span data-ttu-id="e7048-333">5061</span><span class="sxs-lookup"><span data-stu-id="e7048-333">5061</span></span>  <br/> |<span data-ttu-id="e7048-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7048-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="e7048-336">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7048-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="e7048-338">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="e7048-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e7048-339">I rutorna för den nya posten skriver du eller kopierar och klistrar in värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="e7048-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7048-p120">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7048-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
