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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster i Azure DNS-zoner för Office 365.
ms.openlocfilehash: 1c9ac04f74b205fa4a099fca634a41207e8083ba
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211056"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="a0699-103">Skapa DNS-poster för Azure DNS-zoner</span><span class="sxs-lookup"><span data-stu-id="a0699-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="a0699-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="a0699-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a0699-105">Om Azure är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="a0699-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a0699-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="a0699-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="a0699-107">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="a0699-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="a0699-108">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="a0699-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="a0699-109">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="a0699-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="a0699-110">Lägga till de fyra CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="a0699-110">Add the four CNAME records that are required for Office 365</span></span>](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="a0699-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="a0699-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="a0699-112">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="a0699-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="a0699-113">När du har lagt till dessa poster i Azure konfigureras domänen så att den fungerar med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="a0699-113">After you add these records at Azure, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0699-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a0699-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a0699-117">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="a0699-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="a0699-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="a0699-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0699-119">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="a0699-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="a0699-120">När du registrerade dig för Azure skapade du en resursgrupp inom en DNS-zon och tilldelade sedan ditt domännamn till den resursgruppen.</span><span class="sxs-lookup"><span data-stu-id="a0699-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="a0699-121">Domännamnet är registrerat hos en extern domänregistristist. Azure erbjuder inte domänregistreringstjänster.</span><span class="sxs-lookup"><span data-stu-id="a0699-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="a0699-122">Om du vill verifiera och skapa DNS-poster för din domän i Office 365 måste du först ändra namnservrarna på domänregistraren så att de använder de Azure-namnservrar som tilldelats din resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="a0699-122">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="a0699-123">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="a0699-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="a0699-124">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="a0699-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="a0699-125">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="a0699-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="a0699-126">Ett exempel på Azure-tilldelade namnservrar visas nedan.</span><span class="sxs-lookup"><span data-stu-id="a0699-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="a0699-127">**Förnamnserver:** Använd namnservervärdet som tilldelats av Azure.</span><span class="sxs-lookup"><span data-stu-id="a0699-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="a0699-128">**Andra namnserver:** Använd namnservervärdet som tilldelats av Azure.</span><span class="sxs-lookup"><span data-stu-id="a0699-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="a0699-130">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="a0699-130">You should use at least two name server records.</span></span> <span data-ttu-id="a0699-131">Om det finns några andra namnservrar som anges på domänregistratorerns webbplats bör du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="a0699-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="a0699-132">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="a0699-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a0699-p105">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="a0699-p105">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a0699-135">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="a0699-135">Add a TXT record for verification</span></span>
<span data-ttu-id="a0699-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a0699-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a0699-p106">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="a0699-p106">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0699-p107">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="a0699-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a0699-141">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a0699-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a0699-142">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a0699-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a0699-144">Skriv i **DNS-zoner**med hjälp av **sökfältet** på **sidan Instrumentpanel** .</span><span class="sxs-lookup"><span data-stu-id="a0699-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="a0699-145">I resultatvisningen väljer du **DNS-zoner** under delen **Tjänster.**</span><span class="sxs-lookup"><span data-stu-id="a0699-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="a0699-146">När du har omdirigerats väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="a0699-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a0699-148">Välj **+ Postuppsättning**i **området DNS-zon** på sidan **Inställningar** för domänen .</span><span class="sxs-lookup"><span data-stu-id="a0699-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="a0699-150">I området **Lägg till postuppsättning** väljer du värdena i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="a0699-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="a0699-151">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="a0699-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a0699-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="a0699-152">**Name**</span></span>|<span data-ttu-id="a0699-153">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="a0699-153">**Type**</span></span>|<span data-ttu-id="a0699-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0699-154">**TTL**</span></span>|<span data-ttu-id="a0699-155">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="a0699-155">**TTL unit**</span></span>|<span data-ttu-id="a0699-156">**Värde**</span><span class="sxs-lookup"><span data-stu-id="a0699-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a0699-157">TXT</span><span class="sxs-lookup"><span data-stu-id="a0699-157">TXT</span></span>  <br/> |<span data-ttu-id="a0699-158">1</span><span class="sxs-lookup"><span data-stu-id="a0699-158">1</span></span>  <br/> |<span data-ttu-id="a0699-159">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-159">Hours</span></span>  <br/> |<span data-ttu-id="a0699-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a0699-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a0699-p110">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="a0699-p110">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Azure-BP-Verifiera-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="a0699-165">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0699-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="a0699-166">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="a0699-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a0699-167">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="a0699-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a0699-168">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="a0699-168">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a0699-169">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="a0699-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a0699-170">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="a0699-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a0699-171">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="a0699-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a0699-172">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="a0699-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a0699-p111">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a0699-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a0699-176">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="a0699-176">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a0699-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a0699-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a0699-178">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a0699-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a0699-179">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a0699-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a0699-181">Välj den domän som du vill uppdatera i området **Alla resurser** på sidan **Instrumentpanel.**</span><span class="sxs-lookup"><span data-stu-id="a0699-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a0699-183">Välj **+ Postuppsättning**i **området DNS-zon** på sidan **Inställningar** för domänen .</span><span class="sxs-lookup"><span data-stu-id="a0699-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="a0699-185">I området **Lägg till postuppsättning** väljer du värdena i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="a0699-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="a0699-186">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="a0699-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a0699-187">**Name**</span><span class="sxs-lookup"><span data-stu-id="a0699-187">**Name**</span></span>|<span data-ttu-id="a0699-188">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="a0699-188">**Type**</span></span>|<span data-ttu-id="a0699-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0699-189">**TTL**</span></span>|<span data-ttu-id="a0699-190">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="a0699-190">**TTL unit**</span></span>|<span data-ttu-id="a0699-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="a0699-191">**Preference**</span></span>|<span data-ttu-id="a0699-192">**Utbyte av e-post**</span><span class="sxs-lookup"><span data-stu-id="a0699-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a0699-193">MX</span><span class="sxs-lookup"><span data-stu-id="a0699-193">MX</span></span>  <br/> |<span data-ttu-id="a0699-194">1</span><span class="sxs-lookup"><span data-stu-id="a0699-194">1</span></span>  <br/> |<span data-ttu-id="a0699-195">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-195">Hours</span></span>  <br/> |<span data-ttu-id="a0699-196">10</span><span class="sxs-lookup"><span data-stu-id="a0699-196">10</span></span>  <br/> <span data-ttu-id="a0699-197">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0699-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="a0699-198">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a0699-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a0699-199">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="a0699-199">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="a0699-200">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="a0699-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="a0699-202">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0699-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="a0699-204">Om det finns några andra MX-poster i avsnittet **MX-poster** måste du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="a0699-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="a0699-205">Välj först **MX-postuppsättningen**i **DNS-zonområdet** .</span><span class="sxs-lookup"><span data-stu-id="a0699-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="a0699-207">Välj sedan den MX-post som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="a0699-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="a0699-209">Markera **snabbmenyn (...)** och välj sedan **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="a0699-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="a0699-211">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a0699-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a0699-213">Lägga till de fyra CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="a0699-213">Add the four CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a0699-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a0699-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a0699-215">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a0699-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a0699-216">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a0699-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a0699-218">Välj den domän som du vill uppdatera i området **Alla resurser** på sidan **Instrumentpanel.**</span><span class="sxs-lookup"><span data-stu-id="a0699-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a0699-220">Välj **+ Postuppsättning**i **området DNS-zon** på sidan **Inställningar** för domänen .</span><span class="sxs-lookup"><span data-stu-id="a0699-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="a0699-222">Lägg till den första av de fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="a0699-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="a0699-223">I området **Lägg till postuppsättning** skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="a0699-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a0699-224">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="a0699-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a0699-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="a0699-225">**Name**</span></span>|<span data-ttu-id="a0699-226">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="a0699-226">**Type**</span></span>|<span data-ttu-id="a0699-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0699-227">**TTL**</span></span>|<span data-ttu-id="a0699-228">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="a0699-228">**TTL unit**</span></span>|<span data-ttu-id="a0699-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a0699-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a0699-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a0699-230">autodiscover</span></span>  <br/> |<span data-ttu-id="a0699-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0699-231">CNAME</span></span>  <br/> |<span data-ttu-id="a0699-232">1</span><span class="sxs-lookup"><span data-stu-id="a0699-232">1</span></span>  <br/> |<span data-ttu-id="a0699-233">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-233">Hours</span></span>  <br/> |<span data-ttu-id="a0699-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a0699-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a0699-235">sip</span><span class="sxs-lookup"><span data-stu-id="a0699-235">sip</span></span>  <br/> |<span data-ttu-id="a0699-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0699-236">CNAME</span></span>  <br/> |<span data-ttu-id="a0699-237">1</span><span class="sxs-lookup"><span data-stu-id="a0699-237">1</span></span>  <br/> |<span data-ttu-id="a0699-238">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-238">Hours</span></span>  <br/> |<span data-ttu-id="a0699-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a0699-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a0699-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a0699-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a0699-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0699-241">CNAME</span></span>  <br/> |<span data-ttu-id="a0699-242">1</span><span class="sxs-lookup"><span data-stu-id="a0699-242">1</span></span>  <br/> |<span data-ttu-id="a0699-243">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-243">Hours</span></span>  <br/> |<span data-ttu-id="a0699-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a0699-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="a0699-246">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0699-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="a0699-248">Lägg till var och en av de tre andra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="a0699-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="a0699-249">I **OMRÅDET DNS-zon** väljer du **+ Postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="a0699-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="a0699-250">Skapa sedan en post i den tomma postuppsättningen med hjälp av värdena från nästa rad i tabellen och välj återigen **OK** för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="a0699-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="a0699-251">Upprepa den här processen tills du har skapat alla fyra CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="a0699-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="a0699-252">(Valfritt) Lägg till 2 CNAME-poster för MDM.</span><span class="sxs-lookup"><span data-stu-id="a0699-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0699-253">Om du har MDM (Mobile Device Management) för Office 365 måste du skapa ytterligare två CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="a0699-253">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="a0699-254">Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a0699-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="a0699-255">(Om du inte har MDM kan du hoppa över det här steget.)</span><span class="sxs-lookup"><span data-stu-id="a0699-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="a0699-256">**Name**</span><span class="sxs-lookup"><span data-stu-id="a0699-256">**Name**</span></span>|<span data-ttu-id="a0699-257">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="a0699-257">**Type**</span></span>|<span data-ttu-id="a0699-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0699-258">**TTL**</span></span>|<span data-ttu-id="a0699-259">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="a0699-259">**TTL unit**</span></span>|<span data-ttu-id="a0699-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a0699-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a0699-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a0699-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a0699-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0699-262">CNAME</span></span>  <br/> |<span data-ttu-id="a0699-263">1</span><span class="sxs-lookup"><span data-stu-id="a0699-263">1</span></span>  <br/> |<span data-ttu-id="a0699-264">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-264">Hours</span></span>  <br/> |<span data-ttu-id="a0699-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a0699-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="a0699-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a0699-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a0699-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0699-267">CNAME</span></span>  <br/> |<span data-ttu-id="a0699-268">1</span><span class="sxs-lookup"><span data-stu-id="a0699-268">1</span></span>  <br/> |<span data-ttu-id="a0699-269">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-269">Hours</span></span>  <br/> |<span data-ttu-id="a0699-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a0699-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a0699-271">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="a0699-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a0699-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a0699-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0699-273">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="a0699-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a0699-274">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="a0699-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a0699-275">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0699-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a0699-276">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="a0699-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a0699-277">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a0699-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a0699-278">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a0699-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a0699-280">Välj den domän som du vill uppdatera i området **Alla resurser** på sidan **Instrumentpanel.**</span><span class="sxs-lookup"><span data-stu-id="a0699-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a0699-282">I **DNS-zonområdet** väljer du **TXT-postuppsättningen**.</span><span class="sxs-lookup"><span data-stu-id="a0699-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="a0699-284">I **egenskapsområdet Postuppsättning** väljer du värdena i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="a0699-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="a0699-285">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="a0699-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a0699-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="a0699-286">**Name**</span></span>|<span data-ttu-id="a0699-287">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="a0699-287">**Type**</span></span>|<span data-ttu-id="a0699-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0699-288">**TTL**</span></span>|<span data-ttu-id="a0699-289">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="a0699-289">**TTL unit**</span></span>|<span data-ttu-id="a0699-290">**Värde**</span><span class="sxs-lookup"><span data-stu-id="a0699-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a0699-291">TXT</span><span class="sxs-lookup"><span data-stu-id="a0699-291">TXT</span></span>  <br/> |<span data-ttu-id="a0699-292">1</span><span class="sxs-lookup"><span data-stu-id="a0699-292">1</span></span>  <br/> |<span data-ttu-id="a0699-293">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-293">Hours</span></span>  <br/> |<span data-ttu-id="a0699-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a0699-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a0699-295">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="a0699-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="a0699-297">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a0699-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a0699-299">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="a0699-299">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a0699-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a0699-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a0699-301">Kom igång genom att gå till domänsidan på Azure med den [här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="a0699-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="a0699-302">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="a0699-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="a0699-304">Välj den domän som du vill uppdatera i området **Alla resurser** på sidan **Instrumentpanel.**</span><span class="sxs-lookup"><span data-stu-id="a0699-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="a0699-306">Välj **+ Postuppsättning**i **området DNS-zon** på sidan **Inställningar** för domänen .</span><span class="sxs-lookup"><span data-stu-id="a0699-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="a0699-308">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="a0699-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a0699-309">I området **Lägg till postuppsättning** väljer du värdena från den första raden i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="a0699-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a0699-310">(Välj värdena **typ** och **TTL-enhet** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="a0699-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a0699-311">**Name**</span><span class="sxs-lookup"><span data-stu-id="a0699-311">**Name**</span></span>|<span data-ttu-id="a0699-312">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="a0699-312">**Type**</span></span>|<span data-ttu-id="a0699-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a0699-313">**TTL**</span></span>|<span data-ttu-id="a0699-314">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="a0699-314">**TTL unit**</span></span>|<span data-ttu-id="a0699-315">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="a0699-315">**Priority**</span></span>|<span data-ttu-id="a0699-316">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="a0699-316">**Weight**</span></span>|<span data-ttu-id="a0699-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="a0699-317">**Port**</span></span>|<span data-ttu-id="a0699-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="a0699-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a0699-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a0699-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="a0699-320">SRV</span><span class="sxs-lookup"><span data-stu-id="a0699-320">SRV</span></span>  <br/> |<span data-ttu-id="a0699-321">1</span><span class="sxs-lookup"><span data-stu-id="a0699-321">1</span></span>  <br/> |<span data-ttu-id="a0699-322">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-322">Hours</span></span>  <br/> |<span data-ttu-id="a0699-323">100</span><span class="sxs-lookup"><span data-stu-id="a0699-323">100</span></span>  <br/> |<span data-ttu-id="a0699-324">1</span><span class="sxs-lookup"><span data-stu-id="a0699-324">1</span></span>  <br/> |<span data-ttu-id="a0699-325">443</span><span class="sxs-lookup"><span data-stu-id="a0699-325">443</span></span>  <br/> |<span data-ttu-id="a0699-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a0699-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a0699-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a0699-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a0699-328">SRV</span><span class="sxs-lookup"><span data-stu-id="a0699-328">SRV</span></span>  <br/> |<span data-ttu-id="a0699-329">1</span><span class="sxs-lookup"><span data-stu-id="a0699-329">1</span></span>  <br/> |<span data-ttu-id="a0699-330">Tider</span><span class="sxs-lookup"><span data-stu-id="a0699-330">Hours</span></span>  <br/> |<span data-ttu-id="a0699-331">100</span><span class="sxs-lookup"><span data-stu-id="a0699-331">100</span></span>  <br/> |<span data-ttu-id="a0699-332">1</span><span class="sxs-lookup"><span data-stu-id="a0699-332">1</span></span>  <br/> |<span data-ttu-id="a0699-333">5061</span><span class="sxs-lookup"><span data-stu-id="a0699-333">5061</span></span>  <br/> |<span data-ttu-id="a0699-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a0699-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="a0699-336">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0699-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="a0699-338">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="a0699-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="a0699-339">I rutorna för den nya posten skriver du eller kopierar och klistrar in värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="a0699-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a0699-p120">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a0699-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
