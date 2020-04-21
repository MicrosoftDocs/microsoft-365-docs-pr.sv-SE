---
title: Skapa DNS-poster på web.com för Microsoft
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på web.com för Microsoft.
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629257"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="9bf34-103">Skapa DNS-poster på web.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9bf34-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="9bf34-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="9bf34-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9bf34-105">Om web.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="9bf34-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9bf34-106">När du har lagt till dessa poster i web.com konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="9bf34-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="9bf34-107">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bf34-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9bf34-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9bf34-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9bf34-111">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="9bf34-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9bf34-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="9bf34-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bf34-113">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="9bf34-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="9bf34-114">När du registrerade dig för web.com har du lagt till en domän med hjälp av web.com **installationsprogrammet.**</span><span class="sxs-lookup"><span data-stu-id="9bf34-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="9bf34-115">Om du vill verifiera och skapa DNS-poster för din domän i Microsoft måste du först ändra namnservrarna på domänregistraren så att de använder web.coms namnservrar.</span><span class="sxs-lookup"><span data-stu-id="9bf34-115">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="9bf34-116">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="9bf34-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="9bf34-117">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="9bf34-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9bf34-118">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="9bf34-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="9bf34-119">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="9bf34-119">First nameserver</span></span>  <br/> |<span data-ttu-id="9bf34-120">Använd namnservervärdet som anges av web.com.</span><span class="sxs-lookup"><span data-stu-id="9bf34-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="9bf34-121">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="9bf34-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="9bf34-122">Använd namnservervärdet som anges av web.com.</span><span class="sxs-lookup"><span data-stu-id="9bf34-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="9bf34-123">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="9bf34-123">You should use at least two name server records.</span></span> <span data-ttu-id="9bf34-124">Om det finns några andra namnservrar i listan bör du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="9bf34-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="9bf34-125">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9bf34-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9bf34-126">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="9bf34-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9bf34-127">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="9bf34-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9bf34-128">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="9bf34-128">Add a TXT record for verification</span></span>
<span data-ttu-id="9bf34-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9bf34-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9bf34-130">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="9bf34-130">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="9bf34-131">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="9bf34-131">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9bf34-p105">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="9bf34-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9bf34-134">Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="9bf34-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9bf34-135">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="9bf34-135">Log in first.</span></span>
  
2. <span data-ttu-id="9bf34-136">Välj **Mina domännamn på**sidan **Kontohanteraren** .</span><span class="sxs-lookup"><span data-stu-id="9bf34-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9bf34-137">Under \*\*Hantera \*min domän\*\*\*väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="9bf34-138">Klicka på **Redigera TXT-poster**under **Text (TXT-poster)** på sidan **Domännamn** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9bf34-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9bf34-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="9bf34-139">**Host**</span></span>|<span data-ttu-id="9bf34-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9bf34-140">**TTL**</span></span>|<span data-ttu-id="9bf34-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="9bf34-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="9bf34-142">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-142">3600</span></span>  <br/> |<span data-ttu-id="9bf34-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9bf34-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9bf34-144">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="9bf34-144">**Note:** This is an example.</span></span> <span data-ttu-id="9bf34-145">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="9bf34-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9bf34-146">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="9bf34-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="9bf34-147">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="9bf34-148">Vänta några minuter innan du verifierar den nya TXT-posten, så att posten du just skapade kan uppdateras över Internet.</span><span class="sxs-lookup"><span data-stu-id="9bf34-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9bf34-149">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="9bf34-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9bf34-150">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="9bf34-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9bf34-151">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="9bf34-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9bf34-152">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="9bf34-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9bf34-153">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9bf34-154">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9bf34-p108">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9bf34-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9bf34-158">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="9bf34-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9bf34-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9bf34-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9bf34-160">Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="9bf34-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9bf34-161">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="9bf34-161">Log in first.</span></span>
  
2. <span data-ttu-id="9bf34-162">Välj **Mina domännamn på**sidan **Kontohanteraren** .</span><span class="sxs-lookup"><span data-stu-id="9bf34-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9bf34-163">Under \*\*Hantera \*min domän\*\*\*väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="9bf34-164">Klicka på **Redigera MX-poster**under **E-postservrar (MX-poster)** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9bf34-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9bf34-165">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="9bf34-165">**Priority**</span></span>|<span data-ttu-id="9bf34-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9bf34-166">**TTL**</span></span>|<span data-ttu-id="9bf34-167">**Mail server (postserver)**</span><span class="sxs-lookup"><span data-stu-id="9bf34-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9bf34-168">1</span><span class="sxs-lookup"><span data-stu-id="9bf34-168">1</span></span>  <br/> <span data-ttu-id="9bf34-169">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="9bf34-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="9bf34-170">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-170">3600</span></span>  <br/> |<span data-ttu-id="9bf34-171">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9bf34-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9bf34-172">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="9bf34-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="9bf34-173">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="9bf34-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="9bf34-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="9bf34-175">Om det finns andra MX-poster i avsnittet **MX-poster** markerar du kryssrutan bredvid posten under **Ta bort**och väljer **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="9bf34-176">Välj **Spara ändringar**på bekräftelseskärmen .</span><span class="sxs-lookup"><span data-stu-id="9bf34-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9bf34-177">Lägga till de sex CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9bf34-177">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9bf34-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9bf34-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9bf34-179">Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="9bf34-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9bf34-180">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="9bf34-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="9bf34-181">Välj **Mina domännamn på**sidan **Kontohanteraren** .</span><span class="sxs-lookup"><span data-stu-id="9bf34-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9bf34-182">Under \*\*Hantera \*min domän\*\*\*väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="9bf34-183">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="9bf34-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="9bf34-184">Klicka på **Redigera CNAME-poster** **under Värdalias (CNAME Records)** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9bf34-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="9bf34-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9bf34-185">**Alias**</span></span>|<span data-ttu-id="9bf34-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9bf34-186">**TTL**</span></span>|<span data-ttu-id="9bf34-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="9bf34-187">**Refers to Host Name**</span></span>|<span data-ttu-id="9bf34-188">**Annan värd**</span><span class="sxs-lookup"><span data-stu-id="9bf34-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9bf34-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9bf34-189">autodiscover</span></span>  <br/> |<span data-ttu-id="9bf34-190">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-190">3600</span></span>  <br/> |<span data-ttu-id="9bf34-191">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="9bf34-191">@ (none)</span></span>  <br/> |<span data-ttu-id="9bf34-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9bf34-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9bf34-193">sip</span><span class="sxs-lookup"><span data-stu-id="9bf34-193">sip</span></span>  <br/> |<span data-ttu-id="9bf34-194">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-194">3600</span></span>  <br/> |<span data-ttu-id="9bf34-195">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="9bf34-195">@ (none)</span></span>  <br/> |<span data-ttu-id="9bf34-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9bf34-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9bf34-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9bf34-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9bf34-198">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-198">3600</span></span>  <br/> |<span data-ttu-id="9bf34-199">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="9bf34-199">@ (none)</span></span>  <br/> | <span data-ttu-id="9bf34-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9bf34-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9bf34-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9bf34-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9bf34-202">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-202">3600</span></span>  <br/> |<span data-ttu-id="9bf34-203">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="9bf34-203">@ (none)</span></span>  <br/> |<span data-ttu-id="9bf34-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9bf34-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9bf34-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9bf34-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9bf34-206">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-206">3600</span></span>  <br/> |<span data-ttu-id="9bf34-207">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="9bf34-207">@ (none)</span></span>  <br/> |<span data-ttu-id="9bf34-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bf34-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="9bf34-209">msoid</span><span class="sxs-lookup"><span data-stu-id="9bf34-209">msoid</span></span>  <br/> |<span data-ttu-id="9bf34-210">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-210">3600</span></span>  <br/> |<span data-ttu-id="9bf34-211">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="9bf34-211">@ (none)</span></span>  <br/> |<span data-ttu-id="9bf34-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="9bf34-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="9bf34-213">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="9bf34-214">Lägg till de andra fem CNAME-posterna var för sig.</span><span class="sxs-lookup"><span data-stu-id="9bf34-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9bf34-215">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="9bf34-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9bf34-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9bf34-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bf34-217">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="9bf34-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9bf34-218">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="9bf34-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9bf34-219">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9bf34-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9bf34-220">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="9bf34-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9bf34-221">Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="9bf34-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9bf34-222">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="9bf34-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="9bf34-223">Välj **Mina domännamn på**sidan **Kontohanteraren** .</span><span class="sxs-lookup"><span data-stu-id="9bf34-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9bf34-224">Under \*\*Hantera \*min domän\*\*\*väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="9bf34-225">Klicka på **Redigera TXT-poster**under **Text (TXT-poster)** på sidan **Domännamn** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9bf34-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="9bf34-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="9bf34-226">**Host**</span></span>|<span data-ttu-id="9bf34-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9bf34-227">**TTL**</span></span>|<span data-ttu-id="9bf34-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="9bf34-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9bf34-229">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-229">3600</span></span>  <br/> |<span data-ttu-id="9bf34-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9bf34-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9bf34-231">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="9bf34-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="9bf34-232">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-232">Select **Continue**.</span></span>

6. <span data-ttu-id="9bf34-233">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9bf34-234">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="9bf34-234">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9bf34-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9bf34-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bf34-236">Tänk på att web.com är ansvarig för att göra den här funktionen tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9bf34-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="9bf34-237">Om du ser avvikelser mellan stegen nedan och den aktuella web.com GUI (Grafiskt användargränssnitt), vänligen utnyttja [web.com community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="9bf34-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="9bf34-238">Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="9bf34-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9bf34-239">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="9bf34-239">Log in first.</span></span>
      
2. <span data-ttu-id="9bf34-240">Välj **Mina domännamn på**sidan **Kontohanteraren** .</span><span class="sxs-lookup"><span data-stu-id="9bf34-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9bf34-241">Under \*\*Hantera \*min domän\*\*\*väljer du **Redigera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="9bf34-242">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="9bf34-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="9bf34-243">Klicka på **Redigera SRV-poster** **under Service (SRV Records)** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9bf34-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="9bf34-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="9bf34-244">**Service**</span></span>|<span data-ttu-id="9bf34-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="9bf34-245">**Protocol**</span></span>|<span data-ttu-id="9bf34-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9bf34-246">**TTL**</span></span>|<span data-ttu-id="9bf34-247">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="9bf34-247">**Priority**</span></span>|<span data-ttu-id="9bf34-248">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="9bf34-248">**Weight**</span></span>|<span data-ttu-id="9bf34-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="9bf34-249">**Port**</span></span>|<span data-ttu-id="9bf34-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="9bf34-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9bf34-251">_sip</span><span class="sxs-lookup"><span data-stu-id="9bf34-251">_sip</span></span> |<span data-ttu-id="9bf34-252">_tls</span><span class="sxs-lookup"><span data-stu-id="9bf34-252">_tls</span></span> |<span data-ttu-id="9bf34-253">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-253">3600</span></span> | <span data-ttu-id="9bf34-254">100</span><span class="sxs-lookup"><span data-stu-id="9bf34-254">100</span></span>|<span data-ttu-id="9bf34-255">1</span><span class="sxs-lookup"><span data-stu-id="9bf34-255">1</span></span> |<span data-ttu-id="9bf34-256">443</span><span class="sxs-lookup"><span data-stu-id="9bf34-256">443</span></span> |<span data-ttu-id="9bf34-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9bf34-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="9bf34-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9bf34-258">_sipfederationtls</span></span> |<span data-ttu-id="9bf34-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="9bf34-259">_tcp</span></span> |<span data-ttu-id="9bf34-260">3600</span><span class="sxs-lookup"><span data-stu-id="9bf34-260">3600</span></span> |<span data-ttu-id="9bf34-261">100</span><span class="sxs-lookup"><span data-stu-id="9bf34-261">100</span></span> |<span data-ttu-id="9bf34-262">1</span><span class="sxs-lookup"><span data-stu-id="9bf34-262">1</span></span> |<span data-ttu-id="9bf34-263">5061</span><span class="sxs-lookup"><span data-stu-id="9bf34-263">5061</span></span> | <span data-ttu-id="9bf34-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9bf34-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="9bf34-265">Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="9bf34-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="9bf34-266">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-266">Select **Continue**.</span></span>

7. <span data-ttu-id="9bf34-267">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="9bf34-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="9bf34-p116">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9bf34-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
