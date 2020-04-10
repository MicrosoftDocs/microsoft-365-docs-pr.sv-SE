---
title: Skapa DNS-poster på Network Solutions för Office 365
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Network Solutions för Office 365.
ms.openlocfilehash: 6bbe954f763e0cb06e9bf32b991e60da34393c57
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211128"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="48150-103">Skapa DNS-poster på Network Solutions för Office 365</span><span class="sxs-lookup"><span data-stu-id="48150-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="48150-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="48150-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="48150-105">Om Network Solutions är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="48150-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="48150-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="48150-106">These are the main records to add.</span></span> <span data-ttu-id="48150-107">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="48150-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="48150-108">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="48150-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="48150-109">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="48150-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="48150-110">Lägg till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="48150-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="48150-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="48150-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="48150-112">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="48150-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="48150-113">När du har lagt till dessa poster på Network Solutions är din domän konfigurerad för att fungera med Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="48150-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="48150-114">Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="48150-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="48150-p102">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="48150-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="48150-118">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="48150-118">Add a TXT record for verification</span></span>
<span data-ttu-id="48150-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="48150-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="48150-p103">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="48150-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48150-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="48150-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="48150-124">Följ stegen nedan eller [titta på videon (börja vid 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="48150-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="48150-125">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="48150-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="48150-126">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="48150-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="48150-127">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="48150-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="48150-129">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="48150-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="48150-131">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="48150-131">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="48150-133">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="48150-134">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="48150-134">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="48150-136">Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Redigera TXT-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Välj Redigera TXT-poster](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="48150-138">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="48150-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="48150-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="48150-139">**Host**</span></span>|<span data-ttu-id="48150-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48150-140">**TTL**</span></span>|<span data-ttu-id="48150-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="48150-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="48150-142">(Värdet ändras till **@ (None)** när du sparar posten.)</span><span class="sxs-lookup"><span data-stu-id="48150-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="48150-143">3600</span><span class="sxs-lookup"><span data-stu-id="48150-143">3600</span></span>  <br/> |<span data-ttu-id="48150-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="48150-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="48150-145">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="48150-145">**Note:** This is an example.</span></span> <span data-ttu-id="48150-146">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="48150-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="48150-147">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="48150-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Skriva eller klistra in värden i rutorna för den nya posten](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="48150-149">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="48150-149">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="48150-151">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="48150-151">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="48150-153">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="48150-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="48150-154">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="48150-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="48150-155">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="48150-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="48150-156">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="48150-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="48150-157">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="48150-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="48150-158">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="48150-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="48150-159">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="48150-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="48150-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="48150-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="48150-163">Lägga till en MX-post så att e-post för din domän kommer till Office 365</span><span class="sxs-lookup"><span data-stu-id="48150-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="48150-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="48150-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="48150-165">Följ stegen nedan eller [titta på videon (börja vid 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="48150-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="48150-166">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="48150-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="48150-167">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="48150-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="48150-168">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="48150-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="48150-170">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="48150-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="48150-172">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="48150-172">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="48150-174">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="48150-175">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="48150-175">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="48150-177">Bläddra ned till avsnittet **E-postservrar (MX Records)** och välj sedan **Redigera MX-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Välj Redigera MX-poster](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="48150-179">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="48150-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="48150-180">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="48150-180">**Priority**</span></span>|<span data-ttu-id="48150-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48150-181">**TTL**</span></span>|<span data-ttu-id="48150-182">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="48150-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="48150-183">10</span><span class="sxs-lookup"><span data-stu-id="48150-183">10</span></span>  <br/> <span data-ttu-id="48150-184">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="48150-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="48150-185">3600</span><span class="sxs-lookup"><span data-stu-id="48150-185">3600</span></span>  <br/> | <span data-ttu-id="48150-186">*\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="48150-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="48150-187">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48150-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="48150-188">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Office 365-konto.</span><span class="sxs-lookup"><span data-stu-id="48150-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="48150-189">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="48150-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Skriva eller klistra in värden i rutorna för den nya posten](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="48150-191">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="48150-191">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="48150-193">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="48150-193">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="48150-195">Om det finns andra MX-poster tar du bort alla genom att välja **Delete** för varje post.</span><span class="sxs-lookup"><span data-stu-id="48150-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="48150-197">När alla är markerade väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="48150-197">When they are all selected, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="48150-199">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="48150-199">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="48150-201">Lägga till CNAME-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="48150-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="48150-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="48150-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="48150-203">Följ stegen nedan eller [titta på videon (börja vid 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="48150-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="48150-204">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="48150-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="48150-205">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="48150-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="48150-206">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="48150-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="48150-208">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="48150-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="48150-210">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="48150-210">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="48150-212">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="48150-213">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="48150-213">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="48150-215">Bläddra ned till avsnittet **Värdalias (CNAME Records)** och välj sedan **Redigera CNAME-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Välj Redigera CNAME-poster under Värdalias](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="48150-217">I rutorna för de fyra nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="48150-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="48150-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="48150-218">**Alias**</span></span>|<span data-ttu-id="48150-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48150-219">**TTL**</span></span>|<span data-ttu-id="48150-220">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="48150-220">**Refers to Host Name**</span></span>|<span data-ttu-id="48150-221">**Other Host          (välj alternativknappen **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="48150-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48150-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="48150-222">autodiscover</span></span>  <br/> |<span data-ttu-id="48150-223">3600</span><span class="sxs-lookup"><span data-stu-id="48150-223">3600</span></span>  <br/> |<span data-ttu-id="48150-224">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="48150-224">(No setting)</span></span>  <br/> |<span data-ttu-id="48150-225">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="48150-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="48150-226">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48150-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48150-227">sip</span><span class="sxs-lookup"><span data-stu-id="48150-227">sip</span></span>  <br/> |<span data-ttu-id="48150-228">3600</span><span class="sxs-lookup"><span data-stu-id="48150-228">3600</span></span>  <br/> |<span data-ttu-id="48150-229">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="48150-229">(No setting)</span></span>  <br/> |<span data-ttu-id="48150-230">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48150-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="48150-231">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48150-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48150-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="48150-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="48150-233">3600</span><span class="sxs-lookup"><span data-stu-id="48150-233">3600</span></span>  <br/> |<span data-ttu-id="48150-234">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="48150-234">(No setting)</span></span>  <br/> |<span data-ttu-id="48150-235">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48150-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="48150-236">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48150-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48150-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="48150-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="48150-238">3600</span><span class="sxs-lookup"><span data-stu-id="48150-238">3600</span></span>  <br/> |<span data-ttu-id="48150-239">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="48150-239">(No setting)</span></span>  <br/> |<span data-ttu-id="48150-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="48150-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="48150-241">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48150-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48150-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="48150-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="48150-243">3600</span><span class="sxs-lookup"><span data-stu-id="48150-243">3600</span></span>  <br/> |<span data-ttu-id="48150-244">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="48150-244">(No setting)</span></span>  <br/> |<span data-ttu-id="48150-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="48150-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="48150-246">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48150-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Skriva eller klistra in värden för de nya posterna](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="48150-248">När du har lagt till alla CNAME-poster som du behöver väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="48150-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="48150-250">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="48150-250">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="48150-252">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="48150-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="48150-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="48150-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="48150-254">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="48150-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="48150-255">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="48150-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="48150-256">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365.</span><span class="sxs-lookup"><span data-stu-id="48150-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="48150-257">Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="48150-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="48150-258">Följ stegen nedan eller [titta på videon (börja vid 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="48150-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="48150-259">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="48150-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="48150-260">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="48150-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="48150-261">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="48150-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="48150-263">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="48150-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="48150-265">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="48150-265">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="48150-267">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="48150-268">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="48150-268">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="48150-270">Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Redigera TXT-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Välj Redigera TXT-poster under text](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="48150-272">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="48150-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="48150-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="48150-273">**Host**</span></span>|<span data-ttu-id="48150-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48150-274">**TTL**</span></span>|<span data-ttu-id="48150-275">**Text**</span><span class="sxs-lookup"><span data-stu-id="48150-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="48150-276">(Värdet ändras till **@ (None)** när du sparar posten.)</span><span class="sxs-lookup"><span data-stu-id="48150-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="48150-277">3600</span><span class="sxs-lookup"><span data-stu-id="48150-277">3600</span></span>  <br/> |<span data-ttu-id="48150-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="48150-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="48150-279">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="48150-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Skriva eller klistra in värden för den nya posten](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="48150-281">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="48150-281">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="48150-283">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="48150-283">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="48150-285">Lägga till de två SRV-posterna som krävs för Office 365</span><span class="sxs-lookup"><span data-stu-id="48150-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="48150-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="48150-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="48150-287">Följ stegen nedan eller [titta på videon (börja vid 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="48150-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="48150-p113">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="48150-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="48150-290">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="48150-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="48150-292">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="48150-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="48150-294">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="48150-294">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="48150-296">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="48150-297">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="48150-297">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="48150-299">Bläddra ned till avsnittet **Service (SRV Records)** och välj sedan **Redigera SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="48150-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Välj Redigera SRV-poster under Tjänst](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="48150-301">I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="48150-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="48150-302">(Välj värdena för **Service** och **Protocol** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="48150-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="48150-303">**Service**</span><span class="sxs-lookup"><span data-stu-id="48150-303">**Service**</span></span>|<span data-ttu-id="48150-304">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="48150-304">**Protocol**</span></span>|<span data-ttu-id="48150-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48150-305">**TTL**</span></span>|<span data-ttu-id="48150-306">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="48150-306">**Priority**</span></span>|<span data-ttu-id="48150-307">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="48150-307">**Weight**</span></span>|<span data-ttu-id="48150-308">**Port**</span><span class="sxs-lookup"><span data-stu-id="48150-308">**Port**</span></span>|<span data-ttu-id="48150-309">**Target**</span><span class="sxs-lookup"><span data-stu-id="48150-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48150-310">_sip</span><span class="sxs-lookup"><span data-stu-id="48150-310">_sip</span></span>  <br/> |<span data-ttu-id="48150-311">_tls</span><span class="sxs-lookup"><span data-stu-id="48150-311">_tls</span></span>  <br/> |<span data-ttu-id="48150-312">3600</span><span class="sxs-lookup"><span data-stu-id="48150-312">3600</span></span>  <br/> |<span data-ttu-id="48150-313">100</span><span class="sxs-lookup"><span data-stu-id="48150-313">100</span></span>  <br/> |<span data-ttu-id="48150-314">1</span><span class="sxs-lookup"><span data-stu-id="48150-314">1</span></span>  <br/> |<span data-ttu-id="48150-315">443</span><span class="sxs-lookup"><span data-stu-id="48150-315">443</span></span>  <br/> |<span data-ttu-id="48150-316">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48150-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="48150-317">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48150-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48150-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="48150-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="48150-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="48150-319">_tcp</span></span>  <br/> |<span data-ttu-id="48150-320">3600</span><span class="sxs-lookup"><span data-stu-id="48150-320">3600</span></span>  <br/> |<span data-ttu-id="48150-321">100</span><span class="sxs-lookup"><span data-stu-id="48150-321">100</span></span>  <br/> |<span data-ttu-id="48150-322">1</span><span class="sxs-lookup"><span data-stu-id="48150-322">1</span></span>  <br/> |<span data-ttu-id="48150-323">5061</span><span class="sxs-lookup"><span data-stu-id="48150-323">5061</span></span>  <br/> |<span data-ttu-id="48150-324">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48150-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="48150-325">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="48150-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Skriva eller klistra in värden för de nya posterna](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="48150-327">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="48150-327">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="48150-329">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="48150-329">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="48150-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="48150-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
