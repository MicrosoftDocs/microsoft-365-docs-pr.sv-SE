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
ms.openlocfilehash: 7a11fa248f2602eb02fe1242234d26584bd33fd2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780331"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="c57bc-103">Skapa DNS-poster på Register.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c57bc-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="c57bc-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="c57bc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c57bc-105">Om Register.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="c57bc-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c57bc-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="c57bc-106">These are the main records to add.</span></span> <span data-ttu-id="c57bc-107">Följ stegen nedan eller [titta på videon](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="c57bc-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="c57bc-108">Lägga till en TXT-post på Register.com för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="c57bc-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="c57bc-109">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c57bc-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="c57bc-110">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c57bc-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="c57bc-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="c57bc-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="c57bc-112">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c57bc-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="c57bc-113">När du har lagt till dessa poster i Register.com konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="c57bc-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="c57bc-114">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c57bc-114">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c57bc-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c57bc-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c57bc-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c57bc-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="c57bc-117">Lägga till en TXT-post på Register.com för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="c57bc-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="c57bc-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c57bc-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c57bc-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="c57bc-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="c57bc-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="c57bc-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c57bc-121">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="c57bc-121">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="c57bc-122">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="c57bc-122">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="c57bc-123">Följ stegen nedan eller [titta på videon (börja vid 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="c57bc-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c57bc-124">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c57bc-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c57bc-125">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c57bc-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c57bc-126">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c57bc-127">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c57bc-128">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan, på den raden, välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c57bc-129">Bläddra ned till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="c57bc-130">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c57bc-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="c57bc-131">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="c57bc-131">**Host Name**</span></span> <br/> |<span data-ttu-id="c57bc-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="c57bc-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="c57bc-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c57bc-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c57bc-134">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c57bc-134">**Note:** This is an example.</span></span> <span data-ttu-id="c57bc-135">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="c57bc-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c57bc-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="c57bc-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="c57bc-137">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="c57bc-138">På nästa sida väljer du **Fortsätt** igen för att bekräfta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c57bc-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="c57bc-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="c57bc-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c57bc-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="c57bc-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c57bc-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="c57bc-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c57bc-142">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c57bc-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c57bc-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="c57bc-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c57bc-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c57bc-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c57bc-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c57bc-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c57bc-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c57bc-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c57bc-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c57bc-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c57bc-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c57bc-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c57bc-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c57bc-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="c57bc-151">Följ stegen nedan eller [titta på videon (börja vid 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="c57bc-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c57bc-152">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c57bc-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c57bc-153">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c57bc-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c57bc-154">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c57bc-155">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c57bc-156">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan, på den raden, välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c57bc-157">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **e-postutväxlingsposter**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Välj Redigera e-postväxlarposter](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="c57bc-159">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c57bc-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c57bc-160">(Välj **prioritetsvärdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="c57bc-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c57bc-161">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="c57bc-162">\*\*\*\*Priority\*\* (prioritet)\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="c57bc-163">\*\*\*\*E-postserver\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c57bc-164">High</span><span class="sxs-lookup"><span data-stu-id="c57bc-164">High</span></span>  <br/> <span data-ttu-id="c57bc-165">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="c57bc-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="c57bc-166">*\<domain-key\>*.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c57bc-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="c57bc-167">**Obs:** Hämta ditt \<*domain-key*\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="c57bc-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="c57bc-168">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="c57bc-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopiera och klistra in värdet från tabellen](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="c57bc-170">Om det redan finns andra MX-poster som visas, väljer du var och en av posterna och tar bort dem.</span><span class="sxs-lookup"><span data-stu-id="c57bc-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="c57bc-172">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-172">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="c57bc-174">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c57bc-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c57bc-176">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c57bc-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c57bc-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c57bc-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="c57bc-178">Följ stegen nedan eller [titta på videon (börja vid 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="c57bc-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c57bc-179">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c57bc-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c57bc-180">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c57bc-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c57bc-181">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c57bc-182">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c57bc-183">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan, på den raden, välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c57bc-184">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **domänaliasposter**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Välj Redigera domänaliasposter](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="c57bc-186">Välj **Lägg till fler domänalias**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-186">Select **Add more domain aliases**.</span></span>
    
    ![Välj Lägg till fler domänalias](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="c57bc-188">Lägg till nödvändiga CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="c57bc-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="c57bc-189">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c57bc-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="c57bc-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="c57bc-191">\*\*\*\*Pekar på\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="c57bc-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c57bc-192">autodiscover</span></span>  <br/> |<span data-ttu-id="c57bc-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c57bc-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c57bc-194">sip</span><span class="sxs-lookup"><span data-stu-id="c57bc-194">sip</span></span>  <br/> |<span data-ttu-id="c57bc-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c57bc-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c57bc-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c57bc-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c57bc-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c57bc-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="c57bc-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c57bc-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c57bc-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c57bc-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c57bc-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c57bc-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c57bc-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c57bc-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Kopiera och klistra in DNS-värdena från tabellen](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="c57bc-203">När du har lagt till alla CNAME-poster som du behöver väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="c57bc-205">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c57bc-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c57bc-207">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="c57bc-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c57bc-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c57bc-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c57bc-209">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="c57bc-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c57bc-210">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="c57bc-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c57bc-211">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c57bc-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c57bc-212">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="c57bc-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="c57bc-213">Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="c57bc-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c57bc-214">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c57bc-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c57bc-215">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c57bc-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c57bc-216">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c57bc-217">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c57bc-218">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan, på den raden, välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c57bc-219">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Välj Redigera TXT-poster (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="c57bc-221">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c57bc-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="c57bc-222">\*\*\*\*Hostname\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="c57bc-223">\*\*\*\*TXT-post\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="c57bc-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c57bc-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c57bc-225">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="c57bc-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Kopiera och klistra in värdena från tabellen](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="c57bc-227">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-227">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="c57bc-229">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c57bc-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c57bc-231">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="c57bc-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c57bc-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c57bc-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="c57bc-233">Följ stegen nedan eller [titta på videon (börja vid 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="c57bc-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c57bc-234">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c57bc-234">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c57bc-235">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="c57bc-235">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c57bc-236">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c57bc-237">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c57bc-238">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan, på den raden, välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c57bc-239">Bläddra till avsnittet **Avancerade tekniska inställningar** och välj sedan Redigera **SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Välj Redigera SRV-poster](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="c57bc-241">Lägg till den första av de två SRV-posterna:</span><span class="sxs-lookup"><span data-stu-id="c57bc-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="c57bc-242">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c57bc-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="c57bc-243">(Välj **prioritetsvärdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="c57bc-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c57bc-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="c57bc-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="c57bc-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="c57bc-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="c57bc-248">\*\*\*\*Vikt\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="c57bc-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="c57bc-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c57bc-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c57bc-251">_sip</span><span class="sxs-lookup"><span data-stu-id="c57bc-251">_sip</span></span>  <br/> |<span data-ttu-id="c57bc-252">_tls</span><span class="sxs-lookup"><span data-stu-id="c57bc-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="c57bc-253">High</span><span class="sxs-lookup"><span data-stu-id="c57bc-253">High</span></span>  <br/> |<span data-ttu-id="c57bc-254">1</span><span class="sxs-lookup"><span data-stu-id="c57bc-254">1</span></span>  <br/> |<span data-ttu-id="c57bc-255">443</span><span class="sxs-lookup"><span data-stu-id="c57bc-255">443</span></span>  <br/> |<span data-ttu-id="c57bc-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c57bc-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c57bc-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c57bc-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="c57bc-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="c57bc-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="c57bc-259">High</span><span class="sxs-lookup"><span data-stu-id="c57bc-259">High</span></span>  <br/> |<span data-ttu-id="c57bc-260">1</span><span class="sxs-lookup"><span data-stu-id="c57bc-260">1</span></span>  <br/> |<span data-ttu-id="c57bc-261">5061</span><span class="sxs-lookup"><span data-stu-id="c57bc-261">5061</span></span>  <br/> |<span data-ttu-id="c57bc-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c57bc-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="c57bc-264">Välj **Lägg till fler SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-264">Select **Add more SRV records**.</span></span>
    
    ![Välj Lägg till fler SRV-poster](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="c57bc-266">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="c57bc-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="c57bc-267">I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="c57bc-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="c57bc-268">När du har lagt till båda SRV-posterna väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="c57bc-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="c57bc-270">På nästa sida väljer du **Fortsätt** igen för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c57bc-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Fortsätt](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="c57bc-272">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c57bc-272">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c57bc-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c57bc-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c57bc-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c57bc-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
