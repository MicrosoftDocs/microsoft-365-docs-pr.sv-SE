---
title: Skapa DNS-poster på Register.com för Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Register.com för Microsoft.
ms.openlocfilehash: 8badcff89b2a8d8cc9901ef4f10c0a6b31de13d7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629281"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="84c7d-103">Skapa DNS-poster på Register.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="84c7d-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="84c7d-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="84c7d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="84c7d-105">Om Register.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="84c7d-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="84c7d-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="84c7d-106">These are the main records to add.</span></span> <span data-ttu-id="84c7d-107">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="84c7d-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="84c7d-108">Lägga till en TXT-post på Register.com för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="84c7d-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="84c7d-109">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="84c7d-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="84c7d-110">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="84c7d-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="84c7d-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="84c7d-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="84c7d-112">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="84c7d-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="84c7d-113">När du har lagt till dessa poster i Register.com konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="84c7d-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="84c7d-114">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="84c7d-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="84c7d-115">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="84c7d-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="84c7d-116">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="84c7d-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="84c7d-117">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="84c7d-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="84c7d-118">Lägga till en TXT-post på Register.com för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="84c7d-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="84c7d-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="84c7d-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="84c7d-120">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="84c7d-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="84c7d-121">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="84c7d-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="84c7d-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="84c7d-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="84c7d-124">Följ stegen nedan eller [titta på videon (börja vid 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="84c7d-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="84c7d-125">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="84c7d-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="84c7d-126">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="84c7d-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="84c7d-127">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="84c7d-128">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="84c7d-129">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="84c7d-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="84c7d-130">Bläddra ned till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="84c7d-131">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="84c7d-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="84c7d-132">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="84c7d-132">**Host Name**</span></span> <br/> |<span data-ttu-id="84c7d-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="84c7d-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="84c7d-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="84c7d-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="84c7d-135">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="84c7d-135">**Note:** This is an example.</span></span> <span data-ttu-id="84c7d-136">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="84c7d-136">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="84c7d-137">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="84c7d-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="84c7d-138">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="84c7d-139">På nästa sida väljer du **Fortsätt** igen för att bekräfta dina ändringar.</span><span class="sxs-lookup"><span data-stu-id="84c7d-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="84c7d-140">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="84c7d-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="84c7d-141">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="84c7d-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="84c7d-142">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="84c7d-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="84c7d-143">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="84c7d-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="84c7d-144">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="84c7d-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="84c7d-145">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="84c7d-146">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="84c7d-147">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="84c7d-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="84c7d-148">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="84c7d-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="84c7d-149">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="84c7d-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="84c7d-150">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="84c7d-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="84c7d-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="84c7d-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="84c7d-152">Följ stegen nedan eller [titta på videon (börja vid 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="84c7d-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="84c7d-153">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="84c7d-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="84c7d-154">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="84c7d-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="84c7d-155">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="84c7d-156">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="84c7d-157">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="84c7d-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="84c7d-158">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **e-postutväxlingsposter**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Välj Redigera e-postväxlarposter](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="84c7d-160">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="84c7d-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="84c7d-161">(Välj **prioritetsvärdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="84c7d-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="84c7d-162">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="84c7d-163">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="84c7d-164">\*\*\*\*E-postserver\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="84c7d-165">High</span><span class="sxs-lookup"><span data-stu-id="84c7d-165">High</span></span>  <br/> <span data-ttu-id="84c7d-166">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="84c7d-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="84c7d-167">*\<domännyckel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="84c7d-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="84c7d-168">**Anm.:** Hämta \< *domännyckeln* \> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="84c7d-168">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="84c7d-169">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="84c7d-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopiera och klistra in värdet från tabellen](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="84c7d-171">Om det redan finns andra MX-poster som visas, väljer du var och en av posterna och tar bort dem.</span><span class="sxs-lookup"><span data-stu-id="84c7d-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="84c7d-173">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-173">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="84c7d-175">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="84c7d-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="84c7d-177">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="84c7d-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="84c7d-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="84c7d-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="84c7d-179">Följ stegen nedan eller [titta på videon (börja vid 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="84c7d-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="84c7d-180">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="84c7d-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="84c7d-181">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="84c7d-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="84c7d-182">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="84c7d-183">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="84c7d-184">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="84c7d-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="84c7d-185">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **domänaliasposter**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Välj Redigera domänaliasposter](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="84c7d-187">Välj **Lägg till fler domänalias**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-187">Select **Add more domain aliases**.</span></span>
    
    ![Välj Lägg till fler domänalias](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="84c7d-189">Lägg till nödvändiga CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="84c7d-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="84c7d-190">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="84c7d-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="84c7d-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="84c7d-192">\*\*\*\*Pekar på\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="84c7d-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="84c7d-193">autodiscover</span></span>  <br/> |<span data-ttu-id="84c7d-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="84c7d-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="84c7d-195">sip</span><span class="sxs-lookup"><span data-stu-id="84c7d-195">sip</span></span>  <br/> |<span data-ttu-id="84c7d-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="84c7d-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="84c7d-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="84c7d-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="84c7d-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="84c7d-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="84c7d-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="84c7d-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="84c7d-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="84c7d-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="84c7d-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="84c7d-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="84c7d-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="84c7d-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Kopiera och klistra in DNS-värdena från tabellen](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="84c7d-204">När du har lagt till alla CNAME-poster som du behöver väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="84c7d-206">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="84c7d-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="84c7d-208">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="84c7d-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="84c7d-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="84c7d-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="84c7d-210">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="84c7d-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="84c7d-211">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="84c7d-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="84c7d-212">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="84c7d-212">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="84c7d-213">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en enda SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="84c7d-213">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="84c7d-214">Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="84c7d-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="84c7d-215">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="84c7d-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="84c7d-216">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="84c7d-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="84c7d-217">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="84c7d-218">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="84c7d-219">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="84c7d-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="84c7d-220">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Välj Redigera TXT-poster (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="84c7d-222">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="84c7d-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="84c7d-223">\*\*\*\*Hostname\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="84c7d-224">\*\*\*\*TXT-post\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="84c7d-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="84c7d-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="84c7d-226">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="84c7d-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Kopiera och klistra in värdena från tabellen](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="84c7d-228">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-228">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="84c7d-230">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="84c7d-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="84c7d-232">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="84c7d-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="84c7d-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="84c7d-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="84c7d-234">Följ stegen nedan eller [titta på videon (börja vid 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="84c7d-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="84c7d-p112">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="84c7d-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="84c7d-237">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="84c7d-238">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="84c7d-239">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="84c7d-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="84c7d-240">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Välj Redigera SRV-poster](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="84c7d-242">Lägg till den första av de två SRV-posterna:</span><span class="sxs-lookup"><span data-stu-id="84c7d-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="84c7d-243">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="84c7d-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="84c7d-244">(Välj **prioritetsvärdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="84c7d-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="84c7d-245">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="84c7d-246">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="84c7d-247">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="84c7d-248">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="84c7d-249">\*\*\*\*Vikt\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="84c7d-250">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="84c7d-251">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="84c7d-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="84c7d-252">_sip</span><span class="sxs-lookup"><span data-stu-id="84c7d-252">_sip</span></span>  <br/> |<span data-ttu-id="84c7d-253">_tls</span><span class="sxs-lookup"><span data-stu-id="84c7d-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="84c7d-254">High</span><span class="sxs-lookup"><span data-stu-id="84c7d-254">High</span></span>  <br/> |<span data-ttu-id="84c7d-255">1</span><span class="sxs-lookup"><span data-stu-id="84c7d-255">1</span></span>  <br/> |<span data-ttu-id="84c7d-256">443</span><span class="sxs-lookup"><span data-stu-id="84c7d-256">443</span></span>  <br/> |<span data-ttu-id="84c7d-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="84c7d-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="84c7d-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="84c7d-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="84c7d-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="84c7d-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="84c7d-260">High</span><span class="sxs-lookup"><span data-stu-id="84c7d-260">High</span></span>  <br/> |<span data-ttu-id="84c7d-261">1</span><span class="sxs-lookup"><span data-stu-id="84c7d-261">1</span></span>  <br/> |<span data-ttu-id="84c7d-262">5061</span><span class="sxs-lookup"><span data-stu-id="84c7d-262">5061</span></span>  <br/> |<span data-ttu-id="84c7d-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="84c7d-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="84c7d-265">Välj **Lägg till fler SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-265">Select **Add more SRV records**.</span></span>
    
    ![Välj Lägg till fler SRV-poster](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="84c7d-267">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="84c7d-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="84c7d-268">I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="84c7d-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="84c7d-269">När du har lagt till båda SRV-posterna väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="84c7d-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="84c7d-271">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="84c7d-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="84c7d-273">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="84c7d-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="84c7d-274">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="84c7d-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="84c7d-275">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="84c7d-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
