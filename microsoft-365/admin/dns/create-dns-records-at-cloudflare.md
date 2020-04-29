---
title: Skapa DNS-poster på Cloudflare för Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Cloudflare för Microsoft.
ms.openlocfilehash: ccd629dfdec24e509144c205b748a883cb65d554
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919633"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="9b4ce-103">Skapa DNS-poster på Cloudflare för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b4ce-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="9b4ce-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9b4ce-105">Om Cloudflare är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9b4ce-106">När du har lagt till dessa poster på Cloudflare konfigureras domänen så att den fungerar med Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="9b4ce-107">Mer information om webbvärdverktyg och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9b4ce-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9b4ce-111">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="9b4ce-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9b4ce-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4ce-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b4ce-113">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="9b4ce-114">När du registrerade dig för Cloudflare lade du till en domän med hjälp av Cloudflares **konfigurationsprocess**.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="9b4ce-115">Domänen som du lade till köptes från Cloudflare eller en separat domänregistrare.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-115">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="9b4ce-116">Om du vill verifiera och skapa DNS-poster för din domän i Microsoft 365 måste du först ändra namnservrarna hos domänregistraren så att de använder Cloudflares namnservrar.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="9b4ce-117">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="9b4ce-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="9b4ce-118">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9b4ce-119">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="9b4ce-120">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="9b4ce-120">First nameserver</span></span>  <br/> |<span data-ttu-id="9b4ce-121">Använd namnservervärdet från Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="9b4ce-122">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="9b4ce-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="9b4ce-123">Använd namnservervärdet från Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="9b4ce-124">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-124">You should use at least two name server records.</span></span> <span data-ttu-id="9b4ce-125">Om det finns några andra namnservrar i listan bör du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="9b4ce-126">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9b4ce-127">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9b4ce-128">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9b4ce-129">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="9b4ce-129">Add a TXT record for verification</span></span>
<span data-ttu-id="9b4ce-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4ce-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9b4ce-p105">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b4ce-p106">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9b4ce-135">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9b4ce-136">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="9b4ce-137">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b4ce-138">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="9b4ce-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9b4ce-139">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9b4ce-140">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-140">**Type**</span></span>|<span data-ttu-id="9b4ce-141">**Name (namn)**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-141">**Name**</span></span>|<span data-ttu-id="9b4ce-142">**Automatic TTL (automatisk TTL)**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-142">**Automatic TTL**</span></span>|<span data-ttu-id="9b4ce-143">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="9b4ce-144">TXT</span><span class="sxs-lookup"><span data-stu-id="9b4ce-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="9b4ce-145">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-145">30 minutes</span></span>  <br/> |<span data-ttu-id="9b4ce-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9b4ce-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9b4ce-147">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-147">**Note:** This is an example.</span></span> <span data-ttu-id="9b4ce-148">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9b4ce-149">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="9b4ce-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="9b4ce-150">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="9b4ce-151">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9b4ce-152">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och söker efter posten.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="9b4ce-153">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9b4ce-154">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9b4ce-155">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9b4ce-156">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9b4ce-157">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9b4ce-p109">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9b4ce-161">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9b4ce-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4ce-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9b4ce-p110">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="9b4ce-165">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b4ce-166">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="9b4ce-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9b4ce-167">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9b4ce-168">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-168">**Type**</span></span>|<span data-ttu-id="9b4ce-169">**Namn**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-169">**Name**</span></span>|<span data-ttu-id="9b4ce-170">**Mail server (postserver)**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-170">**Mail server**</span></span>|<span data-ttu-id="9b4ce-171">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-171">**Priority**</span></span>|<span data-ttu-id="9b4ce-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b4ce-173">MX</span><span class="sxs-lookup"><span data-stu-id="9b4ce-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="9b4ce-174">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9b4ce-175">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft 365-konto.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="9b4ce-176">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="9b4ce-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="9b4ce-177">1</span><span class="sxs-lookup"><span data-stu-id="9b4ce-177">1</span></span>  <br/> <span data-ttu-id="9b4ce-178">[Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet?</span><span class="sxs-lookup"><span data-stu-id="9b4ce-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="9b4ce-179">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="9b4ce-180">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="9b4ce-181">Om det finns andra MX-poster som i avsnittet **MX Records** (MX-poster) ska du ta bort alla genom att välja ikonen **Delete (X)** (ta bort (X)).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="9b4ce-182">Välj Ta bort i **bekräftelsedialogrutan** för att bekräfta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9b4ce-183">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b4ce-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9b4ce-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4ce-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9b4ce-p112">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="9b4ce-187">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b4ce-188">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="9b4ce-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9b4ce-189">Lägg till den första av de fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="9b4ce-190">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="9b4ce-191">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-191">**Type**</span></span>|<span data-ttu-id="9b4ce-192">**Namn**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-192">**Name**</span></span>|<span data-ttu-id="9b4ce-193">**Mål**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-193">**Target**</span></span>|<span data-ttu-id="9b4ce-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b4ce-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b4ce-195">CNAME</span></span>  <br/> |<span data-ttu-id="9b4ce-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9b4ce-196">autodiscover</span></span>  <br/> |<span data-ttu-id="9b4ce-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="9b4ce-198">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b4ce-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b4ce-199">CNAME</span></span>  <br/> |<span data-ttu-id="9b4ce-200">sip</span><span class="sxs-lookup"><span data-stu-id="9b4ce-200">sip</span></span>  <br/> |<span data-ttu-id="9b4ce-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9b4ce-202">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b4ce-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b4ce-203">CNAME</span></span>  <br/> |<span data-ttu-id="9b4ce-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9b4ce-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9b4ce-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9b4ce-206">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b4ce-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b4ce-207">CNAME</span></span>  <br/> |<span data-ttu-id="9b4ce-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9b4ce-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9b4ce-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9b4ce-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="9b4ce-210">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b4ce-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b4ce-211">CNAME</span></span>  <br/> |<span data-ttu-id="9b4ce-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9b4ce-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9b4ce-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="9b4ce-214">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b4ce-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b4ce-215">CNAME</span></span>  <br/> |<span data-ttu-id="9b4ce-216">msoid</span><span class="sxs-lookup"><span data-stu-id="9b4ce-216">msoid</span></span>  <br/> |<span data-ttu-id="9b4ce-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="9b4ce-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="9b4ce-218">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="9b4ce-219">Välj **DNS Traffic-ikonen** (orange moln) för att kringgå Cloudflare-servrarna.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="9b4ce-220">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="9b4ce-221">Lägg till de andra fem CNAME-posterna var för sig.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9b4ce-222">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="9b4ce-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9b4ce-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4ce-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b4ce-224">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9b4ce-225">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9b4ce-226">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="9b4ce-227">Lägg istället till de obligatoriska Microsoft 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9b4ce-228">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9b4ce-229">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="9b4ce-230">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b4ce-231">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="9b4ce-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9b4ce-232">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="9b4ce-233">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-233">**Type**</span></span>|<span data-ttu-id="9b4ce-234">**Namn**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-234">**Name**</span></span>|<span data-ttu-id="9b4ce-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-235">**TTL**</span></span>|<span data-ttu-id="9b4ce-236">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b4ce-237">TXT</span><span class="sxs-lookup"><span data-stu-id="9b4ce-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="9b4ce-238">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-238">30 minutes</span></span>  <br/> |<span data-ttu-id="9b4ce-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9b4ce-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9b4ce-240">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="9b4ce-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="9b4ce-241">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9b4ce-242">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b4ce-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9b4ce-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4ce-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b4ce-244">Tänk på att Cloudflare är ansvarigt för att göra den här funktionen tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="9b4ce-245">Om du ser avvikelser mellan stegen nedan och det aktuella Cloudflare GUI (Grafiskt användargränssnitt), vänligen utnyttja [Cloudflare-communityn](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="9b4ce-246">Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9b4ce-247">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="9b4ce-248">Välj den domän som du vill uppdatera på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b4ce-249">Välj **DNS**på sidan **Översikt** för din domän .</span><span class="sxs-lookup"><span data-stu-id="9b4ce-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="9b4ce-250">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="9b4ce-251">Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="9b4ce-252">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-252">**Type**</span></span>|<span data-ttu-id="9b4ce-253">**Service (tjänst)**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-253">**Service**</span></span>|<span data-ttu-id="9b4ce-254">**Protocol (protokoll)**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-254">**Protocol**</span></span>|<span data-ttu-id="9b4ce-255">**Namn**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-255">**Name**</span></span>|<span data-ttu-id="9b4ce-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-256">**TTL**</span></span>|<span data-ttu-id="9b4ce-257">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-257">**Priority**</span></span>|<span data-ttu-id="9b4ce-258">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-258">**Weight**</span></span>|<span data-ttu-id="9b4ce-259">**Port**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-259">**Port**</span></span>|<span data-ttu-id="9b4ce-260">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="9b4ce-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b4ce-261">SRV</span><span class="sxs-lookup"><span data-stu-id="9b4ce-261">SRV</span></span>|<span data-ttu-id="9b4ce-262">_sip</span><span class="sxs-lookup"><span data-stu-id="9b4ce-262">_sip</span></span> |<span data-ttu-id="9b4ce-263">TLS</span><span class="sxs-lookup"><span data-stu-id="9b4ce-263">TLS</span></span> |<span data-ttu-id="9b4ce-264">Använd din *domain_name;* till exempel contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="9b4ce-265">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-265">30 minutes</span></span> | <span data-ttu-id="9b4ce-266">100</span><span class="sxs-lookup"><span data-stu-id="9b4ce-266">100</span></span>|<span data-ttu-id="9b4ce-267">1</span><span class="sxs-lookup"><span data-stu-id="9b4ce-267">1</span></span> |<span data-ttu-id="9b4ce-268">443</span><span class="sxs-lookup"><span data-stu-id="9b4ce-268">443</span></span> |<span data-ttu-id="9b4ce-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="9b4ce-270">SRV</span><span class="sxs-lookup"><span data-stu-id="9b4ce-270">SRV</span></span>|<span data-ttu-id="9b4ce-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9b4ce-271">_sipfederationtls</span></span> | <span data-ttu-id="9b4ce-272">TCP</span><span class="sxs-lookup"><span data-stu-id="9b4ce-272">TCP</span></span>|<span data-ttu-id="9b4ce-273">Använd din *domain_name;* till exempel contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="9b4ce-274">30 minuter</span><span class="sxs-lookup"><span data-stu-id="9b4ce-274">30 minutes</span></span> |<span data-ttu-id="9b4ce-275">100</span><span class="sxs-lookup"><span data-stu-id="9b4ce-275">100</span></span> |<span data-ttu-id="9b4ce-276">1</span><span class="sxs-lookup"><span data-stu-id="9b4ce-276">1</span></span> |<span data-ttu-id="9b4ce-277">5061</span><span class="sxs-lookup"><span data-stu-id="9b4ce-277">5061</span></span> | <span data-ttu-id="9b4ce-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b4ce-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="9b4ce-279">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="9b4ce-280">Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="9b4ce-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="9b4ce-p117">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9b4ce-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
