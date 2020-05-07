---
title: Skapa DNS-poster på Network Solutions för Microsoft
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Network Solutions för Microsoft.
ms.openlocfilehash: fb5fd2d2bcb263a62306617d728f08b07bb6da34
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048933"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="140f0-103">Skapa DNS-poster på Network Solutions för Microsoft</span><span class="sxs-lookup"><span data-stu-id="140f0-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="140f0-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="140f0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="140f0-105">Om Network Solutions är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="140f0-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="140f0-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="140f0-106">These are the main records to add.</span></span> <span data-ttu-id="140f0-107">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="140f0-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="140f0-108">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="140f0-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="140f0-109">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="140f0-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="140f0-110">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="140f0-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="140f0-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="140f0-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="140f0-112">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="140f0-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="140f0-113">När du har lagt till dessa poster på Network Solutions konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="140f0-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="140f0-p102">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="140f0-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="140f0-117">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="140f0-117">Add a TXT record for verification</span></span>
<span data-ttu-id="140f0-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="140f0-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="140f0-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="140f0-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="140f0-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="140f0-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="140f0-123">Följ stegen nedan eller [titta på videon (börja vid 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="140f0-123">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="140f0-124">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="140f0-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="140f0-125">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="140f0-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="140f0-126">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="140f0-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="140f0-128">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="140f0-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="140f0-130">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="140f0-130">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="140f0-132">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="140f0-133">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="140f0-133">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="140f0-135">Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Redigera TXT-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Välj Redigera TXT-poster](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="140f0-137">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="140f0-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="140f0-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="140f0-138">**Host**</span></span>|<span data-ttu-id="140f0-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="140f0-139">**TTL**</span></span>|<span data-ttu-id="140f0-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="140f0-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="140f0-141">(Värdet ändras till **@ (None)** när du sparar posten.)</span><span class="sxs-lookup"><span data-stu-id="140f0-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="140f0-142">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-142">3600</span></span>  <br/> |<span data-ttu-id="140f0-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="140f0-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="140f0-144">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="140f0-144">**Note:** This is an example.</span></span> <span data-ttu-id="140f0-145">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="140f0-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="140f0-146">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="140f0-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Skriva eller klistra in värden i rutorna för den nya posten](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="140f0-148">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="140f0-148">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="140f0-150">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="140f0-150">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="140f0-152">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="140f0-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="140f0-153">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="140f0-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="140f0-154">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="140f0-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="140f0-155">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="140f0-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="140f0-156">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="140f0-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="140f0-157">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="140f0-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="140f0-158">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="140f0-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="140f0-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="140f0-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="140f0-162">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="140f0-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="140f0-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="140f0-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="140f0-164">Följ stegen nedan eller [titta på videon (börja vid 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="140f0-164">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="140f0-165">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="140f0-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="140f0-166">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="140f0-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="140f0-167">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="140f0-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="140f0-169">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="140f0-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="140f0-171">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="140f0-171">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="140f0-173">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="140f0-174">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="140f0-174">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="140f0-176">Bläddra ned till avsnittet **E-postservrar (MX Records)** och välj sedan **Redigera MX-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Välj Redigera MX-poster](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="140f0-178">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="140f0-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="140f0-179">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="140f0-179">**Priority**</span></span>|<span data-ttu-id="140f0-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="140f0-180">**TTL**</span></span>|<span data-ttu-id="140f0-181">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="140f0-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="140f0-182">10</span><span class="sxs-lookup"><span data-stu-id="140f0-182">10</span></span>  <br/> <span data-ttu-id="140f0-183">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="140f0-183">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="140f0-184">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-184">3600</span></span>  <br/> | <span data-ttu-id="140f0-185">*\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="140f0-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="140f0-186">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="140f0-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="140f0-187">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="140f0-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="140f0-188">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="140f0-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Skriva eller klistra in värden i rutorna för den nya posten](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="140f0-190">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="140f0-190">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="140f0-192">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="140f0-192">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="140f0-194">Om det finns andra MX-poster tar du bort alla genom att välja **Delete** för varje post.</span><span class="sxs-lookup"><span data-stu-id="140f0-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="140f0-196">När alla är markerade väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="140f0-196">When they are all selected, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="140f0-198">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="140f0-198">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="140f0-200">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="140f0-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="140f0-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="140f0-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="140f0-202">Följ stegen nedan eller [titta på videon (börja vid 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="140f0-202">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="140f0-203">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="140f0-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="140f0-204">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="140f0-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="140f0-205">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="140f0-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="140f0-207">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="140f0-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="140f0-209">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="140f0-209">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="140f0-211">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="140f0-212">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="140f0-212">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="140f0-214">Bläddra ned till avsnittet **Värdalias (CNAME Records)** och välj sedan **Redigera CNAME-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Välj Redigera CNAME-poster under Värdalias](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="140f0-216">I rutorna för de fyra nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="140f0-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="140f0-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="140f0-217">**Alias**</span></span>|<span data-ttu-id="140f0-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="140f0-218">**TTL**</span></span>|<span data-ttu-id="140f0-219">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="140f0-219">**Refers to Host Name**</span></span>|<span data-ttu-id="140f0-220">**Other Host          (välj alternativknappen **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="140f0-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="140f0-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="140f0-221">autodiscover</span></span>  <br/> |<span data-ttu-id="140f0-222">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-222">3600</span></span>  <br/> |<span data-ttu-id="140f0-223">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="140f0-223">(No setting)</span></span>  <br/> |<span data-ttu-id="140f0-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="140f0-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="140f0-225">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="140f0-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="140f0-226">sip</span><span class="sxs-lookup"><span data-stu-id="140f0-226">sip</span></span>  <br/> |<span data-ttu-id="140f0-227">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-227">3600</span></span>  <br/> |<span data-ttu-id="140f0-228">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="140f0-228">(No setting)</span></span>  <br/> |<span data-ttu-id="140f0-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="140f0-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="140f0-230">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="140f0-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="140f0-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="140f0-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="140f0-232">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-232">3600</span></span>  <br/> |<span data-ttu-id="140f0-233">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="140f0-233">(No setting)</span></span>  <br/> |<span data-ttu-id="140f0-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="140f0-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="140f0-235">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="140f0-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="140f0-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="140f0-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="140f0-237">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-237">3600</span></span>  <br/> |<span data-ttu-id="140f0-238">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="140f0-238">(No setting)</span></span>  <br/> |<span data-ttu-id="140f0-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="140f0-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="140f0-240">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="140f0-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="140f0-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="140f0-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="140f0-242">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-242">3600</span></span>  <br/> |<span data-ttu-id="140f0-243">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="140f0-243">(No setting)</span></span>  <br/> |<span data-ttu-id="140f0-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="140f0-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="140f0-245">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="140f0-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Skriva eller klistra in värden för de nya posterna](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="140f0-247">När du har lagt till alla CNAME-poster som du behöver väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="140f0-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="140f0-249">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="140f0-249">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="140f0-251">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="140f0-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="140f0-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="140f0-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="140f0-253">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="140f0-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="140f0-254">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="140f0-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="140f0-255">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="140f0-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="140f0-256">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="140f0-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="140f0-257">Följ stegen nedan eller [titta på videon (börja vid 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="140f0-257">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="140f0-258">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="140f0-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="140f0-259">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="140f0-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="140f0-260">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="140f0-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="140f0-262">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="140f0-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="140f0-264">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="140f0-264">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="140f0-266">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="140f0-267">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="140f0-267">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="140f0-269">Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Redigera TXT-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Välj Redigera TXT-poster under text](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="140f0-271">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="140f0-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="140f0-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="140f0-272">**Host**</span></span>|<span data-ttu-id="140f0-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="140f0-273">**TTL**</span></span>|<span data-ttu-id="140f0-274">**Text**</span><span class="sxs-lookup"><span data-stu-id="140f0-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="140f0-275">(Värdet ändras till **@ (None)** när du sparar posten.)</span><span class="sxs-lookup"><span data-stu-id="140f0-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="140f0-276">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-276">3600</span></span>  <br/> |<span data-ttu-id="140f0-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="140f0-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="140f0-278">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="140f0-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Skriva eller klistra in värden för den nya posten](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="140f0-280">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="140f0-280">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="140f0-282">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="140f0-282">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="140f0-284">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="140f0-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="140f0-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="140f0-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="140f0-286">Följ stegen nedan eller [titta på videon (börja vid 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="140f0-286">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="140f0-p113">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="140f0-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="140f0-289">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="140f0-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="140f0-291">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="140f0-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="140f0-293">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="140f0-293">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="140f0-295">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="140f0-296">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="140f0-296">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="140f0-298">Bläddra ned till avsnittet **Service (SRV Records)** och välj sedan **Redigera SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="140f0-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Välj Redigera SRV-poster under Tjänst](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="140f0-300">I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="140f0-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="140f0-301">(Välj värdena för **Service** och **Protocol** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="140f0-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="140f0-302">**Service**</span><span class="sxs-lookup"><span data-stu-id="140f0-302">**Service**</span></span>|<span data-ttu-id="140f0-303">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="140f0-303">**Protocol**</span></span>|<span data-ttu-id="140f0-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="140f0-304">**TTL**</span></span>|<span data-ttu-id="140f0-305">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="140f0-305">**Priority**</span></span>|<span data-ttu-id="140f0-306">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="140f0-306">**Weight**</span></span>|<span data-ttu-id="140f0-307">**Port**</span><span class="sxs-lookup"><span data-stu-id="140f0-307">**Port**</span></span>|<span data-ttu-id="140f0-308">**Target**</span><span class="sxs-lookup"><span data-stu-id="140f0-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="140f0-309">_sip</span><span class="sxs-lookup"><span data-stu-id="140f0-309">_sip</span></span>  <br/> |<span data-ttu-id="140f0-310">_tls</span><span class="sxs-lookup"><span data-stu-id="140f0-310">_tls</span></span>  <br/> |<span data-ttu-id="140f0-311">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-311">3600</span></span>  <br/> |<span data-ttu-id="140f0-312">100</span><span class="sxs-lookup"><span data-stu-id="140f0-312">100</span></span>  <br/> |<span data-ttu-id="140f0-313">1</span><span class="sxs-lookup"><span data-stu-id="140f0-313">1</span></span>  <br/> |<span data-ttu-id="140f0-314">443</span><span class="sxs-lookup"><span data-stu-id="140f0-314">443</span></span>  <br/> |<span data-ttu-id="140f0-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="140f0-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="140f0-316">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="140f0-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="140f0-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="140f0-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="140f0-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="140f0-318">_tcp</span></span>  <br/> |<span data-ttu-id="140f0-319">3600</span><span class="sxs-lookup"><span data-stu-id="140f0-319">3600</span></span>  <br/> |<span data-ttu-id="140f0-320">100</span><span class="sxs-lookup"><span data-stu-id="140f0-320">100</span></span>  <br/> |<span data-ttu-id="140f0-321">1</span><span class="sxs-lookup"><span data-stu-id="140f0-321">1</span></span>  <br/> |<span data-ttu-id="140f0-322">5061</span><span class="sxs-lookup"><span data-stu-id="140f0-322">5061</span></span>  <br/> |<span data-ttu-id="140f0-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="140f0-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="140f0-324">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="140f0-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Skriva eller klistra in värden för de nya posterna](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="140f0-326">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="140f0-326">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="140f0-328">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="140f0-328">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="140f0-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="140f0-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
