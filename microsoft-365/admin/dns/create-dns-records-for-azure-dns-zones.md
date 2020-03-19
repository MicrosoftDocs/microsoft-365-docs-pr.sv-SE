---
title: Skapa DNS-poster för Azure DNS-zoner
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
- BCS160
- MET150
- MOE150
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster i Azure DNS-zoner för Office 365.
ms.openlocfilehash: 30e54da8ffd51165b1cc0d2eb82d9d02eefdaf4d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807040"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="5ea54-103">Skapa DNS-poster för Azure DNS-zoner</span><span class="sxs-lookup"><span data-stu-id="5ea54-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="5ea54-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5ea54-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5ea54-105">Om Azure är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="5ea54-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5ea54-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="5ea54-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="5ea54-107">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="5ea54-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="5ea54-108">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="5ea54-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="5ea54-109">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="5ea54-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="5ea54-110">Lägga till de fyra CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="5ea54-110">Add the four CNAME records that are required for Office 365</span></span>](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="5ea54-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="5ea54-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="5ea54-112">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="5ea54-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="5ea54-113">När du har lagt till dessa poster på Azure konfigureras domänen så att den fungerar med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="5ea54-113">After you add these records at Azure, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ea54-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5ea54-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5ea54-117">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="5ea54-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="5ea54-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea54-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ea54-119">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="5ea54-120">När du registrerade dig för Azure skapade du en resursgrupp inom en DNS-zon och tilldelade sedan domännamnet till den resursgruppen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="5ea54-121">Domännamnet är registrerat hos en extern domänregistrator. Azure erbjuder inte domänregistreringstjänster.</span><span class="sxs-lookup"><span data-stu-id="5ea54-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="5ea54-122">Om du vill verifiera och skapa DNS-poster för din domän i Office 365 måste du först ändra namnservrarna hos domänregistratorn så att de använder De Azure-namnservrar som tilldelats resursgruppen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-122">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="5ea54-123">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="5ea54-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="5ea54-124">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="5ea54-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="5ea54-125">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="5ea54-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="5ea54-126">Ett exempel på Azure-tilldelade namnservrar visas nedan.</span><span class="sxs-lookup"><span data-stu-id="5ea54-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="5ea54-127">**Förnamnsserver:** Använd namnservervärdet som tilldelats av Azure.</span><span class="sxs-lookup"><span data-stu-id="5ea54-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="5ea54-128">**Andra namnserver:** Använd namnservervärdet som tilldelats av Azure.</span><span class="sxs-lookup"><span data-stu-id="5ea54-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="5ea54-130">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="5ea54-130">You should use at least two name server records.</span></span> <span data-ttu-id="5ea54-131">Om det finns några andra namnservrar listade på domänregistratorns webbplats bör du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="5ea54-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="5ea54-132">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="5ea54-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5ea54-p105">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="5ea54-p105">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5ea54-135">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="5ea54-135">Add a TXT record for verification</span></span>
<span data-ttu-id="5ea54-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea54-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5ea54-p106">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-p106">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ea54-p107">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="5ea54-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5ea54-141">Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="5ea54-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5ea54-142">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5ea54-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5ea54-144">Skriv in **DNS-zoner**med **sökfältet** på **instrumentpanelssidan** .</span><span class="sxs-lookup"><span data-stu-id="5ea54-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="5ea54-145">I resultatvisningen väljer du **DNS-zoner** under delen **Tjänster.**</span><span class="sxs-lookup"><span data-stu-id="5ea54-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="5ea54-146">När du har omdirigerats markerar du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="5ea54-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5ea54-148">Välj **+ Postuppsättning**i **OMRÅDET DNS-zon** på sidan **Inställningar** för domänen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Konfigurera-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="5ea54-150">Markera värdena i tabellen **Lägg till postuppsättning** i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="5ea54-151">(Välj enhetsvärden för **typ** och **TTL** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="5ea54-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5ea54-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="5ea54-152">**Name**</span></span>|<span data-ttu-id="5ea54-153">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5ea54-153">**Type**</span></span>|<span data-ttu-id="5ea54-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ea54-154">**TTL**</span></span>|<span data-ttu-id="5ea54-155">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="5ea54-155">**TTL unit**</span></span>|<span data-ttu-id="5ea54-156">**Värde**</span><span class="sxs-lookup"><span data-stu-id="5ea54-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5ea54-157">TXT</span><span class="sxs-lookup"><span data-stu-id="5ea54-157">TXT</span></span>  <br/> |<span data-ttu-id="5ea54-158">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-158">1</span></span>  <br/> |<span data-ttu-id="5ea54-159">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-159">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5ea54-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5ea54-p110">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="5ea54-p110">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Azure-BP-Verifiera-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="5ea54-165">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="5ea54-166">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="5ea54-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5ea54-167">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="5ea54-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5ea54-168">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="5ea54-168">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5ea54-169">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="5ea54-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5ea54-170">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="5ea54-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5ea54-171">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5ea54-172">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="5ea54-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5ea54-p111">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5ea54-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5ea54-176">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="5ea54-176">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5ea54-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea54-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5ea54-178">Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="5ea54-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5ea54-179">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5ea54-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5ea54-181">På sidan **Instrumentpanel** i området **Alla resurser** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="5ea54-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5ea54-183">Välj **+ Postuppsättning**i **OMRÅDET DNS-zon** på sidan **Inställningar** för domänen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Konfigurera-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="5ea54-185">Markera värdena i tabellen **Lägg till postuppsättning** i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="5ea54-186">(Välj enhetsvärden för **typ** och **TTL** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="5ea54-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5ea54-187">**Name**</span><span class="sxs-lookup"><span data-stu-id="5ea54-187">**Name**</span></span>|<span data-ttu-id="5ea54-188">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5ea54-188">**Type**</span></span>|<span data-ttu-id="5ea54-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ea54-189">**TTL**</span></span>|<span data-ttu-id="5ea54-190">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="5ea54-190">**TTL unit**</span></span>|<span data-ttu-id="5ea54-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="5ea54-191">**Preference**</span></span>|<span data-ttu-id="5ea54-192">**Utbyte av e-post**</span><span class="sxs-lookup"><span data-stu-id="5ea54-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5ea54-193">MX</span><span class="sxs-lookup"><span data-stu-id="5ea54-193">MX</span></span>  <br/> |<span data-ttu-id="5ea54-194">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-194">1</span></span>  <br/> |<span data-ttu-id="5ea54-195">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-195">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-196">10</span><span class="sxs-lookup"><span data-stu-id="5ea54-196">10</span></span>  <br/> <span data-ttu-id="5ea54-197">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ea54-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5ea54-198">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5ea54-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5ea54-199">**Obs:** Hämta din \* \<domännyckel\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="5ea54-199">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="5ea54-200">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="5ea54-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Konfigurera-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="5ea54-202">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-202">Select **OK**.</span></span>
    
    ![Azure-BP-Konfigurera-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="5ea54-204">Om det finns några andra MX-poster i avsnittet **MX Records** måste du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="5ea54-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="5ea54-205">Först, i **DNS-zonområdet,** välj **MX Record-uppsättningen**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Konfigurera-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="5ea54-207">Markera sedan den MX-post som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="5ea54-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Konfigurera-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="5ea54-209">Markera **snabbmenyn (...)** och välj sedan **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Konfigurera-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="5ea54-211">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-211">Select **Save**.</span></span>
    
    ![Azure-BP-Konfigurera-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5ea54-213">Lägga till de fyra CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="5ea54-213">Add the four CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5ea54-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea54-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5ea54-215">Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="5ea54-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5ea54-216">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5ea54-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5ea54-218">På sidan **Instrumentpanel** i området **Alla resurser** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="5ea54-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5ea54-220">Välj **+ Postuppsättning**i **OMRÅDET DNS-zon** på sidan **Inställningar** för domänen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Konfigurera-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="5ea54-222">Lägg till den första av de fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="5ea54-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="5ea54-223">Skriv eller kopiera värdena från den första raden i följande tabell i rutorna för den nya postuppsättningen i området **Lägg till postuppsättning.**</span><span class="sxs-lookup"><span data-stu-id="5ea54-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="5ea54-224">(Välj enhetsvärden för **typ** och **TTL** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="5ea54-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5ea54-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="5ea54-225">**Name**</span></span>|<span data-ttu-id="5ea54-226">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5ea54-226">**Type**</span></span>|<span data-ttu-id="5ea54-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ea54-227">**TTL**</span></span>|<span data-ttu-id="5ea54-228">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="5ea54-228">**TTL unit**</span></span>|<span data-ttu-id="5ea54-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5ea54-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5ea54-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5ea54-230">autodiscover</span></span>  <br/> |<span data-ttu-id="5ea54-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="5ea54-231">CNAME</span></span>  <br/> |<span data-ttu-id="5ea54-232">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-232">1</span></span>  <br/> |<span data-ttu-id="5ea54-233">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-233">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5ea54-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5ea54-235">sip</span><span class="sxs-lookup"><span data-stu-id="5ea54-235">sip</span></span>  <br/> |<span data-ttu-id="5ea54-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="5ea54-236">CNAME</span></span>  <br/> |<span data-ttu-id="5ea54-237">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-237">1</span></span>  <br/> |<span data-ttu-id="5ea54-238">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-238">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5ea54-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5ea54-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5ea54-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5ea54-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="5ea54-241">CNAME</span></span>  <br/> |<span data-ttu-id="5ea54-242">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-242">1</span></span>  <br/> |<span data-ttu-id="5ea54-243">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-243">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5ea54-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Konfigurera-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="5ea54-246">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-246">Select **OK**.</span></span>
    
    ![Azure-BP-Konfigurera-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="5ea54-248">Lägg till var och en av de andra tre CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="5ea54-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="5ea54-249">Välj **+ Postuppsättning i**området **DNS-zon** .</span><span class="sxs-lookup"><span data-stu-id="5ea54-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="5ea54-250">Skapa sedan en post med värdena från nästa rad i tabellen i den tomma postuppsättningen och välj återigen **OK** för att slutföra posten.</span><span class="sxs-lookup"><span data-stu-id="5ea54-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="5ea54-251">Upprepa den här processen tills du har skapat alla fyra CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="5ea54-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="5ea54-252">(Valfritt) Lägg till 2 CNAME-poster för MDM.</span><span class="sxs-lookup"><span data-stu-id="5ea54-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ea54-253">Om du har MDM (Mobile Device Management) för Office 365 måste du skapa ytterligare två CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="5ea54-253">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="5ea54-254">Följ proceduren som används för de andra fyra CNAME-posterna, men använd värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5ea54-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="5ea54-255">(Om du inte har MDM kan du hoppa över det här steget.)</span><span class="sxs-lookup"><span data-stu-id="5ea54-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="5ea54-256">**Name**</span><span class="sxs-lookup"><span data-stu-id="5ea54-256">**Name**</span></span>|<span data-ttu-id="5ea54-257">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5ea54-257">**Type**</span></span>|<span data-ttu-id="5ea54-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ea54-258">**TTL**</span></span>|<span data-ttu-id="5ea54-259">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="5ea54-259">**TTL unit**</span></span>|<span data-ttu-id="5ea54-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5ea54-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ea54-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5ea54-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5ea54-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="5ea54-262">CNAME</span></span>  <br/> |<span data-ttu-id="5ea54-263">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-263">1</span></span>  <br/> |<span data-ttu-id="5ea54-264">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-264">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5ea54-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="5ea54-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5ea54-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5ea54-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="5ea54-267">CNAME</span></span>  <br/> |<span data-ttu-id="5ea54-268">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-268">1</span></span>  <br/> |<span data-ttu-id="5ea54-269">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-269">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5ea54-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5ea54-271">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="5ea54-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5ea54-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea54-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ea54-273">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="5ea54-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5ea54-274">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="5ea54-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5ea54-275">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ea54-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5ea54-276">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="5ea54-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="5ea54-277">Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="5ea54-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5ea54-278">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5ea54-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5ea54-280">På sidan **Instrumentpanel** i området **Alla resurser** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="5ea54-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5ea54-282">Markera **TXT-postuppsättningen i** **zonen DNS** .</span><span class="sxs-lookup"><span data-stu-id="5ea54-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Konfigurera-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="5ea54-284">Markera värdena i följande tabell i rutorna för den nya postuppsättningen i området Egenskaper för **postuppsättning.**</span><span class="sxs-lookup"><span data-stu-id="5ea54-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="5ea54-285">(Välj enhetsvärden för **typ** och **TTL** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="5ea54-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5ea54-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="5ea54-286">**Name**</span></span>|<span data-ttu-id="5ea54-287">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5ea54-287">**Type**</span></span>|<span data-ttu-id="5ea54-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ea54-288">**TTL**</span></span>|<span data-ttu-id="5ea54-289">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="5ea54-289">**TTL unit**</span></span>|<span data-ttu-id="5ea54-290">**Värde**</span><span class="sxs-lookup"><span data-stu-id="5ea54-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5ea54-291">TXT</span><span class="sxs-lookup"><span data-stu-id="5ea54-291">TXT</span></span>  <br/> |<span data-ttu-id="5ea54-292">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-292">1</span></span>  <br/> |<span data-ttu-id="5ea54-293">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-293">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5ea54-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5ea54-295">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="5ea54-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Konfigurera-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="5ea54-297">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-297">Select **Save**.</span></span>
    
    ![Azure-BP-Konfigurera-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5ea54-299">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="5ea54-299">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5ea54-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5ea54-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5ea54-301">Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="5ea54-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5ea54-302">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5ea54-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5ea54-304">På sidan **Instrumentpanel** i området **Alla resurser** väljer du den domän som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="5ea54-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5ea54-306">Välj **+ Postuppsättning**i **OMRÅDET DNS-zon** på sidan **Inställningar** för domänen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Konfigurera-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="5ea54-308">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="5ea54-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5ea54-309">I området **Lägg till postuppsättning** markerar du värdena från den första raden i följande tabell i rutorna för den nya postuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5ea54-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="5ea54-310">(Välj enhetsvärden för **typ** och **TTL** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="5ea54-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5ea54-311">**Name**</span><span class="sxs-lookup"><span data-stu-id="5ea54-311">**Name**</span></span>|<span data-ttu-id="5ea54-312">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5ea54-312">**Type**</span></span>|<span data-ttu-id="5ea54-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ea54-313">**TTL**</span></span>|<span data-ttu-id="5ea54-314">**TTL-enhet**</span><span class="sxs-lookup"><span data-stu-id="5ea54-314">**TTL unit**</span></span>|<span data-ttu-id="5ea54-315">**Priority (prioritet)**</span><span class="sxs-lookup"><span data-stu-id="5ea54-315">**Priority**</span></span>|<span data-ttu-id="5ea54-316">**Weight**</span><span class="sxs-lookup"><span data-stu-id="5ea54-316">**Weight**</span></span>|<span data-ttu-id="5ea54-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="5ea54-317">**Port**</span></span>|<span data-ttu-id="5ea54-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="5ea54-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5ea54-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="5ea54-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="5ea54-320">SRV</span><span class="sxs-lookup"><span data-stu-id="5ea54-320">SRV</span></span>  <br/> |<span data-ttu-id="5ea54-321">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-321">1</span></span>  <br/> |<span data-ttu-id="5ea54-322">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-322">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-323">100</span><span class="sxs-lookup"><span data-stu-id="5ea54-323">100</span></span>  <br/> |<span data-ttu-id="5ea54-324">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-324">1</span></span>  <br/> |<span data-ttu-id="5ea54-325">443</span><span class="sxs-lookup"><span data-stu-id="5ea54-325">443</span></span>  <br/> |<span data-ttu-id="5ea54-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5ea54-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5ea54-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="5ea54-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5ea54-328">SRV</span><span class="sxs-lookup"><span data-stu-id="5ea54-328">SRV</span></span>  <br/> |<span data-ttu-id="5ea54-329">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-329">1</span></span>  <br/> |<span data-ttu-id="5ea54-330">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ea54-330">Hours</span></span>  <br/> |<span data-ttu-id="5ea54-331">100</span><span class="sxs-lookup"><span data-stu-id="5ea54-331">100</span></span>  <br/> |<span data-ttu-id="5ea54-332">1</span><span class="sxs-lookup"><span data-stu-id="5ea54-332">1</span></span>  <br/> |<span data-ttu-id="5ea54-333">5061</span><span class="sxs-lookup"><span data-stu-id="5ea54-333">5061</span></span>  <br/> |<span data-ttu-id="5ea54-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5ea54-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Konfigurera-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="5ea54-336">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ea54-336">Select **OK**.</span></span>
    
    ![Azure-BP-Konfigurera-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="5ea54-338">Lägg till den andra SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="5ea54-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5ea54-339">Skriv eller kopiera värdena från den andra raden i tabellen i rutorna för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="5ea54-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5ea54-p120">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5ea54-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
