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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Register.com för Microsoft.
ms.openlocfilehash: 7b2353b4b6832c9316e302ace4db948e2550a28f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400334"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="b6333-103">Skapa DNS-poster på Register.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6333-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="b6333-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="b6333-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b6333-105">Om Register.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="b6333-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b6333-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="b6333-106">These are the main records to add.</span></span> <span data-ttu-id="b6333-107">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6333-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="b6333-108">Lägga till en TXT-post på Register.com för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="b6333-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="b6333-109">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6333-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="b6333-110">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6333-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="b6333-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="b6333-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="b6333-112">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6333-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="b6333-113">När du har lagt till dessa poster i Register.com konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="b6333-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="b6333-p102">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b6333-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="b6333-117">Lägga till en TXT-post på Register.com för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="b6333-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="b6333-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b6333-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b6333-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="b6333-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6333-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="b6333-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b6333-123">Följ stegen nedan eller [titta på videon (börja vid 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6333-123">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6333-124">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="b6333-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="b6333-125">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b6333-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b6333-126">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b6333-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b6333-127">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b6333-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b6333-128">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="b6333-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b6333-129">Bläddra ned till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="b6333-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="b6333-130">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b6333-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="b6333-131">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="b6333-131">**Host Name**</span></span> <br/> |<span data-ttu-id="b6333-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="b6333-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b6333-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b6333-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b6333-134">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="b6333-134">**Note:** This is an example.</span></span> <span data-ttu-id="b6333-135">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="b6333-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b6333-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="b6333-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b6333-137">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="b6333-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="b6333-138">På nästa sida väljer du **Fortsätt** igen för att bekräfta dina ändringar.</span><span class="sxs-lookup"><span data-stu-id="b6333-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="b6333-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="b6333-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b6333-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="b6333-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b6333-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="b6333-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b6333-142">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="b6333-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b6333-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="b6333-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b6333-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="b6333-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b6333-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="b6333-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b6333-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b6333-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b6333-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6333-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b6333-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b6333-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b6333-151">Följ stegen nedan eller [titta på videon (börja vid 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6333-151">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6333-152">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="b6333-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="b6333-153">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b6333-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b6333-154">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b6333-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b6333-155">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b6333-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b6333-156">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="b6333-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b6333-157">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **e-postutväxlingsposter**.</span><span class="sxs-lookup"><span data-stu-id="b6333-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Välj Redigera e-postväxlarposter](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="b6333-159">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b6333-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b6333-160">(Välj **prioritetsvärdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b6333-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b6333-161">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="b6333-162">\*\*\*\*Priority\*\* (prioritet)\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="b6333-163">\*\*\*\*E-postserver\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b6333-164">High</span><span class="sxs-lookup"><span data-stu-id="b6333-164">High</span></span>  <br/> <span data-ttu-id="b6333-165">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="b6333-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="b6333-166">*\<domain-key\>*.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b6333-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="b6333-167">**Anm.:** Hämta ditt \<*domain-key*\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="b6333-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="b6333-168">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="b6333-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopiera och klistra in värdet från tabellen](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="b6333-170">Om det redan finns andra MX-poster som visas, väljer du var och en av posterna och tar bort dem.</span><span class="sxs-lookup"><span data-stu-id="b6333-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="b6333-172">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="b6333-172">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="b6333-174">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b6333-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b6333-176">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6333-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b6333-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b6333-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b6333-178">Följ stegen nedan eller [titta på videon (börja vid 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6333-178">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6333-179">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="b6333-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="b6333-180">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b6333-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b6333-181">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b6333-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b6333-182">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b6333-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b6333-183">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="b6333-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b6333-184">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **domänaliasposter**.</span><span class="sxs-lookup"><span data-stu-id="b6333-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Välj Redigera domänaliasposter](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="b6333-186">Välj **Lägg till fler domänalias**.</span><span class="sxs-lookup"><span data-stu-id="b6333-186">Select **Add more domain aliases**.</span></span>
    
    ![Välj Lägg till fler domänalias](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="b6333-188">Lägg till nödvändiga CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="b6333-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="b6333-189">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b6333-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="b6333-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="b6333-191">\*\*\*\*Pekar på\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b6333-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b6333-192">autodiscover</span></span>  <br/> |<span data-ttu-id="b6333-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b6333-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b6333-194">sip</span><span class="sxs-lookup"><span data-stu-id="b6333-194">sip</span></span>  <br/> |<span data-ttu-id="b6333-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b6333-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b6333-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b6333-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b6333-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b6333-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="b6333-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b6333-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b6333-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b6333-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b6333-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b6333-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b6333-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b6333-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Kopiera och klistra in DNS-värdena från tabellen](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="b6333-203">När du har lagt till alla CNAME-poster som du behöver väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="b6333-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="b6333-205">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b6333-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b6333-207">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="b6333-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b6333-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b6333-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6333-209">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="b6333-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b6333-210">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="b6333-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b6333-211">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6333-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b6333-212">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="b6333-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="b6333-213">Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6333-213">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6333-214">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="b6333-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="b6333-215">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b6333-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b6333-216">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b6333-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b6333-217">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b6333-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b6333-218">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="b6333-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b6333-219">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="b6333-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Välj Redigera TXT-poster (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="b6333-221">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b6333-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b6333-222">\*\*\*\*Hostname\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="b6333-223">\*\*\*\*TXT-post\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="b6333-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b6333-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b6333-225">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="b6333-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Kopiera och klistra in värdena från tabellen](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="b6333-227">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="b6333-227">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="b6333-229">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b6333-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b6333-231">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6333-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b6333-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b6333-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b6333-233">Följ stegen nedan eller [titta på videon (börja vid 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6333-233">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6333-p112">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b6333-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b6333-236">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b6333-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b6333-237">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b6333-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b6333-238">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och välj sedan **Hantera**på den raden .</span><span class="sxs-lookup"><span data-stu-id="b6333-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b6333-239">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="b6333-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Välj Redigera SRV-poster](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="b6333-241">Lägg till den första av de två SRV-posterna:</span><span class="sxs-lookup"><span data-stu-id="b6333-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="b6333-242">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b6333-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="b6333-243">(Välj **prioritetsvärdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b6333-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b6333-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="b6333-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="b6333-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="b6333-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="b6333-248">\*\*\*\*Vikt\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="b6333-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="b6333-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6333-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6333-251">_sip</span><span class="sxs-lookup"><span data-stu-id="b6333-251">_sip</span></span>  <br/> |<span data-ttu-id="b6333-252">_tls</span><span class="sxs-lookup"><span data-stu-id="b6333-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="b6333-253">High</span><span class="sxs-lookup"><span data-stu-id="b6333-253">High</span></span>  <br/> |<span data-ttu-id="b6333-254">1</span><span class="sxs-lookup"><span data-stu-id="b6333-254">1</span></span>  <br/> |<span data-ttu-id="b6333-255">443</span><span class="sxs-lookup"><span data-stu-id="b6333-255">443</span></span>  <br/> |<span data-ttu-id="b6333-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b6333-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b6333-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b6333-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b6333-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="b6333-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="b6333-259">High</span><span class="sxs-lookup"><span data-stu-id="b6333-259">High</span></span>  <br/> |<span data-ttu-id="b6333-260">1</span><span class="sxs-lookup"><span data-stu-id="b6333-260">1</span></span>  <br/> |<span data-ttu-id="b6333-261">5061</span><span class="sxs-lookup"><span data-stu-id="b6333-261">5061</span></span>  <br/> |<span data-ttu-id="b6333-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b6333-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="b6333-264">Välj **Lägg till fler SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="b6333-264">Select **Add more SRV records**.</span></span>
    
    ![Välj Lägg till fler SRV-poster](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="b6333-266">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="b6333-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="b6333-267">I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="b6333-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="b6333-268">När du har lagt till båda SRV-posterna väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="b6333-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="b6333-270">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b6333-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="b6333-p113">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b6333-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
