---
title: Skapa DNS-poster på Register.com för Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Register.com för Microsoft.
ms.openlocfilehash: 439b96ef7ad2fd70b94c3945519d4fa270e43fd2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910060"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="b9c59-103">Skapa DNS-poster på Register.com för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9c59-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="b9c59-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="b9c59-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b9c59-105">Om Register.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="b9c59-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b9c59-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="b9c59-106">These are the main records to add.</span></span> <span data-ttu-id="b9c59-107">Följ stegen nedan eller [titta på videon](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b9c59-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="b9c59-108">Lägga till en TXT-post på Register.com för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="b9c59-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="b9c59-109">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9c59-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="b9c59-110">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9c59-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="b9c59-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="b9c59-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="b9c59-112">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9c59-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="b9c59-113">När du har lagt till dessa poster Register.com domän är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="b9c59-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="b9c59-p102">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b9c59-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="b9c59-117">Lägga till en TXT-post på Register.com för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="b9c59-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="b9c59-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c59-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b9c59-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="b9c59-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9c59-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="b9c59-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b9c59-123">Följ stegen nedan eller [titta på videon (börja vid 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b9c59-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b9c59-p105">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b9c59-p105">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b9c59-126">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b9c59-127">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b9c59-128">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b9c59-129">Bläddra ned till **avsnittet Advanced Technical Settings** och välj sedan Edit TXT Records **(SPF).**</span><span class="sxs-lookup"><span data-stu-id="b9c59-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="b9c59-130">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b9c59-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="b9c59-131">**Värdnamn**</span><span class="sxs-lookup"><span data-stu-id="b9c59-131">**Host Name**</span></span> <br/> |<span data-ttu-id="b9c59-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="b9c59-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b9c59-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b9c59-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b9c59-134">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="b9c59-134">**Note:** This is an example.</span></span> <span data-ttu-id="b9c59-135">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="b9c59-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b9c59-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="b9c59-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b9c59-137">Välj **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="b9c59-138">På nästa sida väljer du **Continue igen** för att bekräfta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b9c59-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="b9c59-139">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="b9c59-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b9c59-140">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="b9c59-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b9c59-141">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="b9c59-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b9c59-142">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="b9c59-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b9c59-143">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="b9c59-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b9c59-144">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b9c59-145">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b9c59-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b9c59-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b9c59-149">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9c59-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b9c59-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c59-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b9c59-151">Följ stegen nedan eller [titta på videon (börja vid 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b9c59-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b9c59-p108">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b9c59-p108">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b9c59-154">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b9c59-155">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b9c59-156">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b9c59-157">Bläddra till avsnittet **Advanced Technical Settings** och välj sedan Edit Mail **Exchanger Records.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Välj Redigera e-postutväxlingsposter](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="b9c59-159">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b9c59-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b9c59-160">(Välj **värdet Priority** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b9c59-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b9c59-161">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="b9c59-162">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="b9c59-163">\*\*\*\*E-postserver\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b9c59-164">High</span><span class="sxs-lookup"><span data-stu-id="b9c59-164">High</span></span>  <br/> <span data-ttu-id="b9c59-165">Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="b9c59-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="b9c59-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b9c59-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="b9c59-167">**Obs!** Hämta din \<*domain-key*\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="b9c59-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="b9c59-168">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="b9c59-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopiera och klistra in värdet från tabellen](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="b9c59-170">Om det redan finns andra MX-poster som visas, väljer du var och en av posterna och tar bort dem.</span><span class="sxs-lookup"><span data-stu-id="b9c59-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="b9c59-172">Välj **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-172">Select **Continue**.</span></span>
    
    ![Välj Continue](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="b9c59-174">På nästa sida väljer du **Fortsätt igen** för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b9c59-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Continue](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b9c59-176">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9c59-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b9c59-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c59-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b9c59-178">Följ stegen nedan eller [titta på videon (börja vid 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b9c59-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b9c59-p109">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b9c59-p109">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b9c59-181">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b9c59-182">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b9c59-183">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b9c59-184">Bläddra till avsnittet **Advanced Technical Settings** och välj sedan Edit Domain **Aliases Records**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Välj Edit Domain Aliases Records](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="b9c59-186">Välj **Lägg till fler domänalias**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-186">Select **Add more domain aliases**.</span></span>
    
    ![Välj Lägg till fler domänalias](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="b9c59-188">Lägg till nödvändiga CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="b9c59-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="b9c59-189">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b9c59-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="b9c59-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="b9c59-191">\*\*\*\*Pekar på\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b9c59-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b9c59-192">autodiscover</span></span>  <br/> |<span data-ttu-id="b9c59-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b9c59-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b9c59-194">sip</span><span class="sxs-lookup"><span data-stu-id="b9c59-194">sip</span></span>  <br/> |<span data-ttu-id="b9c59-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b9c59-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b9c59-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b9c59-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b9c59-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b9c59-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="b9c59-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b9c59-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b9c59-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b9c59-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b9c59-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b9c59-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b9c59-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b9c59-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Kopiera och klistra in DNS-värdena från tabellen](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="b9c59-203">När du har lagt till alla CNAME-poster som du behöver väljer du **Continue**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Välj Continue](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="b9c59-205">På nästa sida väljer du **Fortsätt igen** för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b9c59-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Continue](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b9c59-207">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="b9c59-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b9c59-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c59-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9c59-209">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="b9c59-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b9c59-210">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="b9c59-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b9c59-211">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9c59-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b9c59-212">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="b9c59-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="b9c59-213">Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b9c59-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b9c59-p111">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b9c59-p111">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b9c59-216">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b9c59-217">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b9c59-218">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b9c59-219">Bläddra till avsnittet **Advanced Technical Settings** och välj sedan Edit TXT Records **(SPF).**</span><span class="sxs-lookup"><span data-stu-id="b9c59-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Välj Edit TXT Records (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="b9c59-221">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b9c59-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b9c59-222">\*\*\*\*Hostname\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="b9c59-223">\*\*\*\*TXT-post\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="b9c59-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b9c59-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b9c59-225">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="b9c59-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Kopiera och klistra in värdena från tabellen](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="b9c59-227">Välj **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-227">Select **Continue**.</span></span>
    
    ![Välj Continue](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="b9c59-229">På nästa sida väljer du **Fortsätt igen** för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b9c59-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Continue](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b9c59-231">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9c59-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b9c59-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c59-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b9c59-233">Följ stegen nedan eller [titta på videon (börja vid 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="b9c59-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="b9c59-p112">Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="b9c59-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="b9c59-236">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="b9c59-237">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="b9c59-238">Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**</span><span class="sxs-lookup"><span data-stu-id="b9c59-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="b9c59-239">Bläddra till avsnittet **Advanced Technical Settings** och välj sedan Edit **SRV Records**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Välj Edit SRV Records](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="b9c59-241">Lägg till den första av de två SRV-posterna:</span><span class="sxs-lookup"><span data-stu-id="b9c59-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="b9c59-242">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b9c59-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="b9c59-243">(Välj **värdet Priority** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="b9c59-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b9c59-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="b9c59-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="b9c59-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="b9c59-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="b9c59-248">\*\*\*\*Vikt\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="b9c59-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="b9c59-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9c59-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b9c59-251">_sip</span><span class="sxs-lookup"><span data-stu-id="b9c59-251">_sip</span></span>  <br/> |<span data-ttu-id="b9c59-252">_tls</span><span class="sxs-lookup"><span data-stu-id="b9c59-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="b9c59-253">High</span><span class="sxs-lookup"><span data-stu-id="b9c59-253">High</span></span>  <br/> |<span data-ttu-id="b9c59-254">1</span><span class="sxs-lookup"><span data-stu-id="b9c59-254">1</span></span>  <br/> |<span data-ttu-id="b9c59-255">443</span><span class="sxs-lookup"><span data-stu-id="b9c59-255">443</span></span>  <br/> |<span data-ttu-id="b9c59-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b9c59-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="b9c59-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b9c59-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b9c59-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="b9c59-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="b9c59-259">High</span><span class="sxs-lookup"><span data-stu-id="b9c59-259">High</span></span>  <br/> |<span data-ttu-id="b9c59-260">1</span><span class="sxs-lookup"><span data-stu-id="b9c59-260">1</span></span>  <br/> |<span data-ttu-id="b9c59-261">5061</span><span class="sxs-lookup"><span data-stu-id="b9c59-261">5061</span></span>  <br/> |<span data-ttu-id="b9c59-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b9c59-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="b9c59-264">Välj **Add more SRV records**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-264">Select **Add more SRV records**.</span></span>
    
    ![Välj Lägg till fler SRV-poster](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="b9c59-266">Lägg till den andra SRV-posten:</span><span class="sxs-lookup"><span data-stu-id="b9c59-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="b9c59-267">I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="b9c59-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="b9c59-268">När du har lagt till båda SRV-posterna väljer du **Continue**.</span><span class="sxs-lookup"><span data-stu-id="b9c59-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Välj Continue](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="b9c59-270">På nästa sida väljer du **Fortsätt igen** för att bekräfta och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b9c59-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Välj Continue](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="b9c59-p113">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b9c59-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
