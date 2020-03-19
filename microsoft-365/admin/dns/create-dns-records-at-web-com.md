---
title: Skapa DNS-poster på web.com för Office 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på web.com för Office 365.
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806551"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="5f514-103">Skapa DNS-poster på web.com för Office 365</span><span class="sxs-lookup"><span data-stu-id="5f514-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="5f514-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5f514-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5f514-105">Om web.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="5f514-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5f514-106">När du har lagt till dessa poster på web.com konfigureras domänen så att den fungerar med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="5f514-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5f514-107">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f514-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5f514-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5f514-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5f514-111">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="5f514-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="5f514-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="5f514-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f514-113">Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen.</span><span class="sxs-lookup"><span data-stu-id="5f514-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="5f514-114">När du registrerade dig för web.com har du lagt till en domän med hjälp av web.com **installationsprocessen.**</span><span class="sxs-lookup"><span data-stu-id="5f514-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="5f514-115">Om du vill verifiera och skapa DNS-poster för din domän i Office 365 måste du först ändra namnservrarna hos domänregistratorn så att de använder web.coms namnservrar.</span><span class="sxs-lookup"><span data-stu-id="5f514-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="5f514-116">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="5f514-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="5f514-117">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="5f514-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="5f514-118">Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.</span><span class="sxs-lookup"><span data-stu-id="5f514-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="5f514-119">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="5f514-119">First nameserver</span></span>  <br/> |<span data-ttu-id="5f514-120">Använd namnet servervärdet som tillhandahålls av web.com.</span><span class="sxs-lookup"><span data-stu-id="5f514-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="5f514-121">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="5f514-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="5f514-122">Använd namnet servervärdet som tillhandahålls av web.com.</span><span class="sxs-lookup"><span data-stu-id="5f514-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="5f514-123">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="5f514-123">You should use at least two name server records.</span></span> <span data-ttu-id="5f514-124">Om det finns några andra namnservrar i listan bör du ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="5f514-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="5f514-125">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="5f514-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5f514-p103">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="5f514-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5f514-128">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="5f514-128">Add a TXT record for verification</span></span>
<span data-ttu-id="5f514-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5f514-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5f514-p104">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="5f514-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f514-p105">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="5f514-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5f514-134">Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="5f514-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="5f514-135">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="5f514-135">Log in first.</span></span>
  
2. <span data-ttu-id="5f514-136">På sidan **Kontohanteraren** väljer du **Mina domännamn**.</span><span class="sxs-lookup"><span data-stu-id="5f514-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="5f514-137">Välj **Redigera avancerade DNS-poster**under \*\*Hantera \*\*min domän\*\*\*.under \*\*Hantera \*\*min domän\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="5f514-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="5f514-138">Klicka på **Redigera TXT-poster**under Text (TXT Records) på sidan **Domännamn** och välj sedan värdena i följande tabell under **Text (TXT Records)** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5f514-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="5f514-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="5f514-139">**Host**</span></span>|<span data-ttu-id="5f514-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f514-140">**TTL**</span></span>|<span data-ttu-id="5f514-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="5f514-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="5f514-142">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-142">3600</span></span>  <br/> |<span data-ttu-id="5f514-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5f514-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5f514-p107">**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="5f514-p107">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="5f514-147">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="5f514-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="5f514-148">Vänta några minuter innan du verifierar den nya TXT-posten så att posten du just skapade kan uppdateras över Internet.</span><span class="sxs-lookup"><span data-stu-id="5f514-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5f514-149">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="5f514-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5f514-150">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="5f514-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5f514-151">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="5f514-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5f514-152">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="5f514-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5f514-153">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="5f514-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5f514-154">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="5f514-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5f514-p108">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5f514-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5f514-158">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="5f514-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5f514-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5f514-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5f514-160">Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="5f514-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="5f514-161">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="5f514-161">Log in first.</span></span>
  
2. <span data-ttu-id="5f514-162">På sidan **Kontohanteraren** väljer du **Mina domännamn**.</span><span class="sxs-lookup"><span data-stu-id="5f514-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="5f514-163">Välj **Redigera avancerade DNS-poster**under \*\*Hantera \*\*min domän\*\*\*.under \*\*Hantera \*\*min domän\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="5f514-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="5f514-164">Klicka på **Redigera MX Records**under **E-postservrar (MX Records)** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5f514-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="5f514-165">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5f514-165">**Priority**</span></span>|<span data-ttu-id="5f514-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f514-166">**TTL**</span></span>|<span data-ttu-id="5f514-167">**Mail server (postserver)**</span><span class="sxs-lookup"><span data-stu-id="5f514-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5f514-168">1</span><span class="sxs-lookup"><span data-stu-id="5f514-168">1</span></span>  <br/> <span data-ttu-id="5f514-169">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f514-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="5f514-170">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-170">3600</span></span>  <br/> |<span data-ttu-id="5f514-171">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5f514-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5f514-172">**Obs:** Hämta din \* \<domännyckel\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="5f514-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="5f514-173">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="5f514-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="5f514-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5f514-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="5f514-175">Om det finns några andra MX-poster i avsnittet **MX Records** markerar du kryssrutan bredvid posten under **Ta bort**och väljer **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5f514-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="5f514-176">På bekräftelseskärmen väljer du **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="5f514-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5f514-177">Lägga till de sex CNAME-poster som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="5f514-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5f514-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5f514-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5f514-179">Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="5f514-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="5f514-180">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="5f514-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="5f514-181">På sidan **Kontohanteraren** väljer du **Mina domännamn**.</span><span class="sxs-lookup"><span data-stu-id="5f514-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="5f514-182">Välj **Redigera avancerade DNS-poster**under \*\*Hantera \*\*min domän\*\*\*.under \*\*Hantera \*\*min domän\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="5f514-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="5f514-183">Lägg till den första av de sex CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="5f514-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="5f514-184">Klicka på **Redigera CNAME-poster**under **Värdalias (CNAME Records)** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5f514-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="5f514-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5f514-185">**Alias**</span></span>|<span data-ttu-id="5f514-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f514-186">**TTL**</span></span>|<span data-ttu-id="5f514-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="5f514-187">**Refers to Host Name**</span></span>|<span data-ttu-id="5f514-188">**Annan värd**</span><span class="sxs-lookup"><span data-stu-id="5f514-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5f514-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5f514-189">autodiscover</span></span>  <br/> |<span data-ttu-id="5f514-190">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-190">3600</span></span>  <br/> |<span data-ttu-id="5f514-191">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="5f514-191">@ (none)</span></span>  <br/> |<span data-ttu-id="5f514-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5f514-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5f514-193">sip</span><span class="sxs-lookup"><span data-stu-id="5f514-193">sip</span></span>  <br/> |<span data-ttu-id="5f514-194">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-194">3600</span></span>  <br/> |<span data-ttu-id="5f514-195">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="5f514-195">@ (none)</span></span>  <br/> |<span data-ttu-id="5f514-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f514-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5f514-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5f514-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5f514-198">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-198">3600</span></span>  <br/> |<span data-ttu-id="5f514-199">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="5f514-199">@ (none)</span></span>  <br/> | <span data-ttu-id="5f514-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f514-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5f514-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5f514-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5f514-202">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-202">3600</span></span>  <br/> |<span data-ttu-id="5f514-203">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="5f514-203">@ (none)</span></span>  <br/> |<span data-ttu-id="5f514-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5f514-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="5f514-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5f514-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5f514-206">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-206">3600</span></span>  <br/> |<span data-ttu-id="5f514-207">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="5f514-207">@ (none)</span></span>  <br/> |<span data-ttu-id="5f514-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5f514-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="5f514-209">msoid</span><span class="sxs-lookup"><span data-stu-id="5f514-209">msoid</span></span>  <br/> |<span data-ttu-id="5f514-210">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-210">3600</span></span>  <br/> |<span data-ttu-id="5f514-211">@ (ingen)</span><span class="sxs-lookup"><span data-stu-id="5f514-211">@ (none)</span></span>  <br/> |<span data-ttu-id="5f514-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="5f514-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="5f514-213">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="5f514-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="5f514-214">Lägg till de andra fem CNAME-posterna var för sig.</span><span class="sxs-lookup"><span data-stu-id="5f514-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5f514-215">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="5f514-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5f514-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5f514-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f514-217">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="5f514-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5f514-218">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="5f514-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5f514-219">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f514-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5f514-220">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="5f514-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="5f514-221">Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="5f514-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="5f514-222">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="5f514-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="5f514-223">På sidan **Kontohanteraren** väljer du **Mina domännamn**.</span><span class="sxs-lookup"><span data-stu-id="5f514-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="5f514-224">Välj **Redigera avancerade DNS-poster**under \*\*Hantera \*\*min domän\*\*\*.under \*\*Hantera \*\*min domän\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="5f514-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="5f514-225">Klicka på **Redigera TXT-poster**under Text (TXT Records) på sidan **Domännamn** och välj sedan värdena i följande tabell under **Text (TXT Records)** och välj sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5f514-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="5f514-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="5f514-226">**Host**</span></span>|<span data-ttu-id="5f514-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f514-227">**TTL**</span></span>|<span data-ttu-id="5f514-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="5f514-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5f514-229">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-229">3600</span></span>  <br/> |<span data-ttu-id="5f514-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5f514-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5f514-231">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="5f514-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="5f514-232">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="5f514-232">Select **Continue**.</span></span>

6. <span data-ttu-id="5f514-233">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="5f514-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5f514-234">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="5f514-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5f514-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5f514-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f514-236">Tänk på att web.com är ansvarig för att göra den här funktionen tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="5f514-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="5f514-237">Om du ser avvikelser mellan stegen nedan och det aktuella web.com GUI(Grafiskt användargränssnitt) kan du utnyttja [web.com community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="5f514-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="5f514-238">Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="5f514-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="5f514-239">Logga in först.</span><span class="sxs-lookup"><span data-stu-id="5f514-239">Log in first.</span></span>
      
2. <span data-ttu-id="5f514-240">På sidan **Kontohanteraren** väljer du **Mina domännamn**.</span><span class="sxs-lookup"><span data-stu-id="5f514-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="5f514-241">Välj **Redigera avancerade DNS-poster**under \*\*Hantera \*\*min domän\*\*\*.under \*\*Hantera \*\*min domän\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="5f514-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="5f514-242">Lägg till den första av de två SRV-posterna.</span><span class="sxs-lookup"><span data-stu-id="5f514-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="5f514-243">Under **Service (SRV Records)** klickar du på **Redigera SRV Records**och väljer sedan värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5f514-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="5f514-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="5f514-244">**Service**</span></span>|<span data-ttu-id="5f514-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="5f514-245">**Protocol**</span></span>|<span data-ttu-id="5f514-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f514-246">**TTL**</span></span>|<span data-ttu-id="5f514-247">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5f514-247">**Priority**</span></span>|<span data-ttu-id="5f514-248">**Weight**</span><span class="sxs-lookup"><span data-stu-id="5f514-248">**Weight**</span></span>|<span data-ttu-id="5f514-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="5f514-249">**Port**</span></span>|<span data-ttu-id="5f514-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="5f514-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5f514-251">_sip</span><span class="sxs-lookup"><span data-stu-id="5f514-251">_sip</span></span> |<span data-ttu-id="5f514-252">_tls</span><span class="sxs-lookup"><span data-stu-id="5f514-252">_tls</span></span> |<span data-ttu-id="5f514-253">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-253">3600</span></span> | <span data-ttu-id="5f514-254">100</span><span class="sxs-lookup"><span data-stu-id="5f514-254">100</span></span>|<span data-ttu-id="5f514-255">1</span><span class="sxs-lookup"><span data-stu-id="5f514-255">1</span></span> |<span data-ttu-id="5f514-256">443</span><span class="sxs-lookup"><span data-stu-id="5f514-256">443</span></span> |<span data-ttu-id="5f514-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f514-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="5f514-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="5f514-258">_sipfederationtls</span></span> |<span data-ttu-id="5f514-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="5f514-259">_tcp</span></span> |<span data-ttu-id="5f514-260">3600</span><span class="sxs-lookup"><span data-stu-id="5f514-260">3600</span></span> |<span data-ttu-id="5f514-261">100</span><span class="sxs-lookup"><span data-stu-id="5f514-261">100</span></span> |<span data-ttu-id="5f514-262">1</span><span class="sxs-lookup"><span data-stu-id="5f514-262">1</span></span> |<span data-ttu-id="5f514-263">5061</span><span class="sxs-lookup"><span data-stu-id="5f514-263">5061</span></span> | <span data-ttu-id="5f514-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f514-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="5f514-265">Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="5f514-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="5f514-266">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="5f514-266">Select **Continue**.</span></span>

7. <span data-ttu-id="5f514-267">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="5f514-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="5f514-p116">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5f514-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
