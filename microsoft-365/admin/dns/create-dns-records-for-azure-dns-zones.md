---
title: Skapa DNS-poster för Azure DNS-zoner
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster i Azure DNS Zones för Microsoft.
ms.openlocfilehash: c276570ec1d5ff079348bd8202ea597ef61e88f6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656873"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="e02b5-103">Skapa DNS-poster för Azure DNS-zoner</span><span class="sxs-lookup"><span data-stu-id="e02b5-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="e02b5-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="e02b5-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e02b5-105">Om Azure är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e02b5-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e02b5-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="e02b5-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="e02b5-107">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="e02b5-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="e02b5-108">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="e02b5-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="e02b5-109">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e02b5-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="e02b5-110">Lägga till de fyra CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e02b5-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="e02b5-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="e02b5-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="e02b5-112">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e02b5-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="e02b5-113">När du har lagt till dessa poster på Azure är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="e02b5-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e02b5-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e02b5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e02b5-117">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="e02b5-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="e02b5-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="e02b5-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e02b5-119">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="e02b5-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="e02b5-120">När du registrerade dig för Azure skapade du en resurs grupp i en DNS-zon och kopplade sedan domän namnet till den resurs gruppen.</span><span class="sxs-lookup"><span data-stu-id="e02b5-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="e02b5-121">Domän namnet är registrerat i en extern domän registrator; Azure erbjuder inte tjänster för domän registrering.</span><span class="sxs-lookup"><span data-stu-id="e02b5-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="e02b5-122">Om du vill verifiera och skapa DNS-poster för din domän i Microsoft måste du först ändra namnservrar hos din domän registrator så att de använder Azure-namnservrar som är tilldelad till din resurs grupp.</span><span class="sxs-lookup"><span data-stu-id="e02b5-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="e02b5-123">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="e02b5-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="e02b5-124">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="e02b5-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="e02b5-125">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="e02b5-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="e02b5-126">Ett exempel på en Azure-tilldelad namnservrar visas nedan.</span><span class="sxs-lookup"><span data-stu-id="e02b5-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="e02b5-127">**Första Namnserver:** Använd värdet Name Server som tilldelats av Azure.</span><span class="sxs-lookup"><span data-stu-id="e02b5-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="e02b5-128">**Andra Namnserver:** Använd värdet Name Server som tilldelats av Azure.</span><span class="sxs-lookup"><span data-stu-id="e02b5-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-omdelegera-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="e02b5-130">Du bör använda minst två namnserver poster.</span><span class="sxs-lookup"><span data-stu-id="e02b5-130">You should use at least two name server records.</span></span> <span data-ttu-id="e02b5-131">Om det finns fler namnservrar på din domän registrators webbplats ska du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="e02b5-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="e02b5-132">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="e02b5-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e02b5-133">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="e02b5-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e02b5-134">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="e02b5-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e02b5-135">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="e02b5-135">Add a TXT record for verification</span></span>
<span data-ttu-id="e02b5-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e02b5-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e02b5-p106">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="e02b5-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e02b5-p107">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="e02b5-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e02b5-141">Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e02b5-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e02b5-142">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e02b5-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e02b5-144">I **Sök fältet** på sidan **instrument panel** skriver du in **DNS Zones**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="e02b5-145">I resultat visningen väljer du **DNS Zones** under **tjänste** delen.</span><span class="sxs-lookup"><span data-stu-id="e02b5-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="e02b5-146">När du har omdirigerats väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="e02b5-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e02b5-148">Välj **+ Record set** i området **DNS Zone** på sidan **Inställningar** för din domän.</span><span class="sxs-lookup"><span data-stu-id="e02b5-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e02b5-150">I rutan **Lägg till post uppsättning** väljer du värden från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="e02b5-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e02b5-151">(Välj värdena **Type** och **TTL** i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="e02b5-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e02b5-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="e02b5-152">**Name**</span></span>|<span data-ttu-id="e02b5-153">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e02b5-153">**Type**</span></span>|<span data-ttu-id="e02b5-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e02b5-154">**TTL**</span></span>|<span data-ttu-id="e02b5-155">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e02b5-155">**TTL unit**</span></span>|<span data-ttu-id="e02b5-156">**Värde**</span><span class="sxs-lookup"><span data-stu-id="e02b5-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e02b5-157">TXT</span><span class="sxs-lookup"><span data-stu-id="e02b5-157">TXT</span></span>  <br/> |<span data-ttu-id="e02b5-158">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-158">1</span></span>  <br/> |<span data-ttu-id="e02b5-159">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-159">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e02b5-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e02b5-161">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="e02b5-161">**Note:** This is an example.</span></span> <span data-ttu-id="e02b5-162">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="e02b5-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e02b5-163">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e02b5-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="e02b5-165">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="e02b5-166">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="e02b5-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e02b5-167">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="e02b5-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e02b5-168">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="e02b5-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e02b5-169">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="e02b5-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e02b5-170">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="e02b5-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e02b5-171">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e02b5-172">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e02b5-p111">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e02b5-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e02b5-176">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e02b5-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e02b5-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e02b5-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e02b5-178">Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e02b5-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e02b5-179">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e02b5-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e02b5-181">På sidan **instrument panel** i området **alla resurser** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="e02b5-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e02b5-183">Välj **+ Record set** i området **DNS Zone** på sidan **Inställningar** för din domän.</span><span class="sxs-lookup"><span data-stu-id="e02b5-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e02b5-185">I rutan **Lägg till post uppsättning** väljer du värden från följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="e02b5-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e02b5-186">(Välj värdena **Type** och **TTL** i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="e02b5-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e02b5-187">**Name**</span><span class="sxs-lookup"><span data-stu-id="e02b5-187">**Name**</span></span>|<span data-ttu-id="e02b5-188">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e02b5-188">**Type**</span></span>|<span data-ttu-id="e02b5-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e02b5-189">**TTL**</span></span>|<span data-ttu-id="e02b5-190">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e02b5-190">**TTL unit**</span></span>|<span data-ttu-id="e02b5-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="e02b5-191">**Preference**</span></span>|<span data-ttu-id="e02b5-192">**E-postutbyte**</span><span class="sxs-lookup"><span data-stu-id="e02b5-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e02b5-193">MX</span><span class="sxs-lookup"><span data-stu-id="e02b5-193">MX</span></span>  <br/> |<span data-ttu-id="e02b5-194">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-194">1</span></span>  <br/> |<span data-ttu-id="e02b5-195">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-195">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-196">10.3</span><span class="sxs-lookup"><span data-stu-id="e02b5-196">10</span></span>  <br/> <span data-ttu-id="e02b5-197">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e02b5-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="e02b5-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e02b5-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e02b5-199">**Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="e02b5-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="e02b5-200">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="e02b5-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="e02b5-202">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="e02b5-204">Om det finns andra MX-poster i avsnittet **MX Records** måste du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="e02b5-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="e02b5-205">I området **DNS Zone** väljer du först **MX-postuppsättningen**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="e02b5-207">Välj sedan den MX-post som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="e02b5-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="e02b5-209">Välj **snabb menyn (...)** och välj sedan **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="e02b5-211">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e02b5-213">Lägga till de fyra CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e02b5-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e02b5-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e02b5-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e02b5-215">Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e02b5-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e02b5-216">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e02b5-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e02b5-218">På sidan **instrument panel** i området **alla resurser** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="e02b5-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e02b5-220">Välj **+ Record set** i området **DNS Zone** på sidan **Inställningar** för din domän.</span><span class="sxs-lookup"><span data-stu-id="e02b5-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e02b5-222">Lägg till den första av de fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e02b5-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="e02b5-223">I rutan **Lägg till post uppsättning** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="e02b5-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e02b5-224">(Välj värdena **Type** och **TTL** i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="e02b5-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e02b5-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="e02b5-225">**Name**</span></span>|<span data-ttu-id="e02b5-226">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e02b5-226">**Type**</span></span>|<span data-ttu-id="e02b5-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e02b5-227">**TTL**</span></span>|<span data-ttu-id="e02b5-228">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e02b5-228">**TTL unit**</span></span>|<span data-ttu-id="e02b5-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e02b5-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e02b5-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e02b5-230">autodiscover</span></span>  <br/> |<span data-ttu-id="e02b5-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="e02b5-231">CNAME</span></span>  <br/> |<span data-ttu-id="e02b5-232">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-232">1</span></span>  <br/> |<span data-ttu-id="e02b5-233">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-233">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e02b5-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e02b5-235">sip</span><span class="sxs-lookup"><span data-stu-id="e02b5-235">sip</span></span>  <br/> |<span data-ttu-id="e02b5-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="e02b5-236">CNAME</span></span>  <br/> |<span data-ttu-id="e02b5-237">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-237">1</span></span>  <br/> |<span data-ttu-id="e02b5-238">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-238">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e02b5-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e02b5-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e02b5-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e02b5-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="e02b5-241">CNAME</span></span>  <br/> |<span data-ttu-id="e02b5-242">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-242">1</span></span>  <br/> |<span data-ttu-id="e02b5-243">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-243">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e02b5-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="e02b5-246">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="e02b5-248">Lägg till de andra tre CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e02b5-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="e02b5-249">Välj **+ Record set** i området **DNS Zone** .</span><span class="sxs-lookup"><span data-stu-id="e02b5-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="e02b5-250">I den tomma post uppsättningen skapar du en post med värdena från nästa rad i tabellen och väljer sedan **OK** för att slutföra den posten.</span><span class="sxs-lookup"><span data-stu-id="e02b5-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="e02b5-251">Upprepa proceduren tills du har skapat alla fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="e02b5-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="e02b5-252">Skriver Lägga till 2 CNAME-poster för MDM.</span><span class="sxs-lookup"><span data-stu-id="e02b5-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e02b5-253">Om du har Mobile Device Management (MDM) för Microsoft måste du skapa ytterligare två CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="e02b5-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="e02b5-254">Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e02b5-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="e02b5-255">(Om du inte har MDM kan du hoppa över det här steget.)</span><span class="sxs-lookup"><span data-stu-id="e02b5-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="e02b5-256">**Name**</span><span class="sxs-lookup"><span data-stu-id="e02b5-256">**Name**</span></span>|<span data-ttu-id="e02b5-257">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e02b5-257">**Type**</span></span>|<span data-ttu-id="e02b5-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e02b5-258">**TTL**</span></span>|<span data-ttu-id="e02b5-259">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e02b5-259">**TTL unit**</span></span>|<span data-ttu-id="e02b5-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e02b5-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e02b5-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e02b5-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e02b5-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="e02b5-262">CNAME</span></span>  <br/> |<span data-ttu-id="e02b5-263">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-263">1</span></span>  <br/> |<span data-ttu-id="e02b5-264">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-264">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e02b5-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="e02b5-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e02b5-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e02b5-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="e02b5-267">CNAME</span></span>  <br/> |<span data-ttu-id="e02b5-268">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-268">1</span></span>  <br/> |<span data-ttu-id="e02b5-269">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-269">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e02b5-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e02b5-271">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="e02b5-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e02b5-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e02b5-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e02b5-273">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="e02b5-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e02b5-274">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="e02b5-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e02b5-275">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e02b5-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e02b5-276">I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.</span><span class="sxs-lookup"><span data-stu-id="e02b5-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e02b5-277">Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e02b5-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e02b5-278">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e02b5-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e02b5-280">På sidan **instrument panel** i området **alla resurser** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="e02b5-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e02b5-282">I området **DNS Zone** väljer du txt- **postuppsättningen**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="e02b5-284">I rutorna för den nya post uppsättningen i området **Egenskaper för post uppsättning** väljer du värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e02b5-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e02b5-285">(Välj värdena **Type** och **TTL** i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="e02b5-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e02b5-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="e02b5-286">**Name**</span></span>|<span data-ttu-id="e02b5-287">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e02b5-287">**Type**</span></span>|<span data-ttu-id="e02b5-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e02b5-288">**TTL**</span></span>|<span data-ttu-id="e02b5-289">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e02b5-289">**TTL unit**</span></span>|<span data-ttu-id="e02b5-290">**Värde**</span><span class="sxs-lookup"><span data-stu-id="e02b5-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e02b5-291">TXT</span><span class="sxs-lookup"><span data-stu-id="e02b5-291">TXT</span></span>  <br/> |<span data-ttu-id="e02b5-292">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-292">1</span></span>  <br/> |<span data-ttu-id="e02b5-293">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-293">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e02b5-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e02b5-295">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="e02b5-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="e02b5-297">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e02b5-299">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="e02b5-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e02b5-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e02b5-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e02b5-301">Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="e02b5-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e02b5-302">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="e02b5-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e02b5-304">På sidan **instrument panel** i området **alla resurser** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="e02b5-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e02b5-306">Välj **+ Record set** i området **DNS Zone** på sidan **Inställningar** för din domän.</span><span class="sxs-lookup"><span data-stu-id="e02b5-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e02b5-308">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="e02b5-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="e02b5-309">Markera värdena från den första raden i följande tabell i rutorna för den nya posten i avsnittet **Lägg till post uppsättning** .</span><span class="sxs-lookup"><span data-stu-id="e02b5-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e02b5-310">(Välj värdena **Type** och **TTL** i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="e02b5-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e02b5-311">**Name**</span><span class="sxs-lookup"><span data-stu-id="e02b5-311">**Name**</span></span>|<span data-ttu-id="e02b5-312">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="e02b5-312">**Type**</span></span>|<span data-ttu-id="e02b5-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e02b5-313">**TTL**</span></span>|<span data-ttu-id="e02b5-314">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="e02b5-314">**TTL unit**</span></span>|<span data-ttu-id="e02b5-315">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="e02b5-315">**Priority**</span></span>|<span data-ttu-id="e02b5-316">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="e02b5-316">**Weight**</span></span>|<span data-ttu-id="e02b5-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="e02b5-317">**Port**</span></span>|<span data-ttu-id="e02b5-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="e02b5-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e02b5-319">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="e02b5-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="e02b5-320">SRV</span><span class="sxs-lookup"><span data-stu-id="e02b5-320">SRV</span></span>  <br/> |<span data-ttu-id="e02b5-321">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-321">1</span></span>  <br/> |<span data-ttu-id="e02b5-322">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-322">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-323">100</span><span class="sxs-lookup"><span data-stu-id="e02b5-323">100</span></span>  <br/> |<span data-ttu-id="e02b5-324">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-324">1</span></span>  <br/> |<span data-ttu-id="e02b5-325">443</span><span class="sxs-lookup"><span data-stu-id="e02b5-325">443</span></span>  <br/> |<span data-ttu-id="e02b5-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e02b5-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e02b5-327">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e02b5-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e02b5-328">SRV</span><span class="sxs-lookup"><span data-stu-id="e02b5-328">SRV</span></span>  <br/> |<span data-ttu-id="e02b5-329">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-329">1</span></span>  <br/> |<span data-ttu-id="e02b5-330">Tider</span><span class="sxs-lookup"><span data-stu-id="e02b5-330">Hours</span></span>  <br/> |<span data-ttu-id="e02b5-331">100</span><span class="sxs-lookup"><span data-stu-id="e02b5-331">100</span></span>  <br/> |<span data-ttu-id="e02b5-332">9.1</span><span class="sxs-lookup"><span data-stu-id="e02b5-332">1</span></span>  <br/> |<span data-ttu-id="e02b5-333">5061</span><span class="sxs-lookup"><span data-stu-id="e02b5-333">5061</span></span>  <br/> |<span data-ttu-id="e02b5-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e02b5-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="e02b5-336">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e02b5-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="e02b5-338">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="e02b5-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e02b5-339">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="e02b5-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e02b5-p120">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e02b5-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
