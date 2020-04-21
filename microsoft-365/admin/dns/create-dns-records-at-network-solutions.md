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
ms.openlocfilehash: e7ce1dd633aa916643f3dcbf7900fa7831608e78
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629305"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="bf9a8-103">Skapa DNS-poster på Network Solutions för Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf9a8-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="bf9a8-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bf9a8-105">Om Network Solutions är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="bf9a8-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-106">These are the main records to add.</span></span> <span data-ttu-id="bf9a8-107">Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="bf9a8-108">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="bf9a8-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="bf9a8-109">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf9a8-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="bf9a8-110">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf9a8-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="bf9a8-111">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="bf9a8-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="bf9a8-112">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf9a8-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="bf9a8-113">När du har lagt till dessa poster på Network Solutions konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="bf9a8-114">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="bf9a8-p102">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="bf9a8-118">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="bf9a8-118">Add a TXT record for verification</span></span>
<span data-ttu-id="bf9a8-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9a8-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="bf9a8-120">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="bf9a8-121">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf9a8-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="bf9a8-124">Följ stegen nedan eller [titta på videon (börja vid 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bf9a8-125">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="bf9a8-126">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf9a8-127">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="bf9a8-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="bf9a8-129">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="bf9a8-131">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-131">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="bf9a8-133">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="bf9a8-134">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-134">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="bf9a8-136">Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Redigera TXT-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Välj Redigera TXT-poster](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="bf9a8-138">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="bf9a8-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-139">**Host**</span></span>|<span data-ttu-id="bf9a8-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-140">**TTL**</span></span>|<span data-ttu-id="bf9a8-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="bf9a8-142">(Värdet ändras till **@ (None)** när du sparar posten.)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="bf9a8-143">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-143">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bf9a8-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bf9a8-145">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-145">**Note:** This is an example.</span></span> <span data-ttu-id="bf9a8-146">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-146">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="bf9a8-147">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="bf9a8-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Skriva eller klistra in värden i rutorna för den nya posten](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="bf9a8-149">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-149">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="bf9a8-151">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-151">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="bf9a8-153">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="bf9a8-154">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="bf9a8-155">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="bf9a8-156">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="bf9a8-157">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="bf9a8-158">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="bf9a8-159">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="bf9a8-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="bf9a8-163">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf9a8-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="bf9a8-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9a8-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="bf9a8-165">Följ stegen nedan eller [titta på videon (börja vid 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bf9a8-166">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="bf9a8-167">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf9a8-168">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="bf9a8-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="bf9a8-170">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="bf9a8-172">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-172">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="bf9a8-174">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="bf9a8-175">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-175">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="bf9a8-177">Bläddra ned till avsnittet **E-postservrar (MX Records)** och välj sedan **Redigera MX-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Välj Redigera MX-poster](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="bf9a8-179">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="bf9a8-180">**Priority**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-180">**Priority**</span></span>|<span data-ttu-id="bf9a8-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-181">**TTL**</span></span>|<span data-ttu-id="bf9a8-182">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="bf9a8-183">10</span><span class="sxs-lookup"><span data-stu-id="bf9a8-183">10</span></span>  <br/> <span data-ttu-id="bf9a8-184">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="bf9a8-185">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-185">3600</span></span>  <br/> | <span data-ttu-id="bf9a8-186">*\<domännyckel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="bf9a8-187">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="bf9a8-188">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-188">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="bf9a8-189">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="bf9a8-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Skriva eller klistra in värden i rutorna för den nya posten](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="bf9a8-191">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-191">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="bf9a8-193">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-193">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="bf9a8-195">Om det finns andra MX-poster tar du bort alla genom att välja **Delete** för varje post.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="bf9a8-197">När alla är markerade väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-197">When they are all selected, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="bf9a8-199">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-199">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="bf9a8-201">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf9a8-201">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="bf9a8-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9a8-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="bf9a8-203">Följ stegen nedan eller [titta på videon (börja vid 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bf9a8-204">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="bf9a8-205">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf9a8-206">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="bf9a8-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="bf9a8-208">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="bf9a8-210">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-210">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="bf9a8-212">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="bf9a8-213">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-213">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="bf9a8-215">Bläddra ned till avsnittet **Värdalias (CNAME Records)** och välj sedan **Redigera CNAME-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Välj Redigera CNAME-poster under Värdalias](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="bf9a8-217">I rutorna för de fyra nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="bf9a8-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-218">**Alias**</span></span>|<span data-ttu-id="bf9a8-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-219">**TTL**</span></span>|<span data-ttu-id="bf9a8-220">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-220">**Refers to Host Name**</span></span>|<span data-ttu-id="bf9a8-221">**Other Host          (välj alternativknappen **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bf9a8-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bf9a8-222">autodiscover</span></span>  <br/> |<span data-ttu-id="bf9a8-223">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-223">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-224">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-224">(No setting)</span></span>  <br/> |<span data-ttu-id="bf9a8-225">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="bf9a8-226">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bf9a8-227">sip</span><span class="sxs-lookup"><span data-stu-id="bf9a8-227">sip</span></span>  <br/> |<span data-ttu-id="bf9a8-228">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-228">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-229">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-229">(No setting)</span></span>  <br/> |<span data-ttu-id="bf9a8-230">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bf9a8-231">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bf9a8-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bf9a8-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="bf9a8-233">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-233">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-234">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-234">(No setting)</span></span>  <br/> |<span data-ttu-id="bf9a8-235">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bf9a8-236">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bf9a8-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="bf9a8-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="bf9a8-238">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-238">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-239">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-239">(No setting)</span></span>  <br/> |<span data-ttu-id="bf9a8-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="bf9a8-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="bf9a8-241">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bf9a8-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="bf9a8-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="bf9a8-243">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-243">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-244">(Ingen inställning)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-244">(No setting)</span></span>  <br/> |<span data-ttu-id="bf9a8-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bf9a8-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="bf9a8-246">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Skriva eller klistra in värden för de nya posterna](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="bf9a8-248">När du har lagt till alla CNAME-poster som du behöver väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="bf9a8-250">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-250">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="bf9a8-252">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="bf9a8-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="bf9a8-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9a8-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf9a8-254">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="bf9a8-255">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="bf9a8-256">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-256">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="bf9a8-257">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-257">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="bf9a8-258">Följ stegen nedan eller [titta på videon (börja vid 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bf9a8-259">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="bf9a8-260">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf9a8-261">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="bf9a8-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="bf9a8-263">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="bf9a8-265">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-265">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="bf9a8-267">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="bf9a8-268">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-268">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="bf9a8-270">Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Redigera TXT-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Välj Redigera TXT-poster under text](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="bf9a8-272">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="bf9a8-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-273">**Host**</span></span>|<span data-ttu-id="bf9a8-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-274">**TTL**</span></span>|<span data-ttu-id="bf9a8-275">**Text**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="bf9a8-276">(Värdet ändras till **@ (None)** när du sparar posten.)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="bf9a8-277">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-277">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="bf9a8-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="bf9a8-279">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="bf9a8-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Skriva eller klistra in värden för den nya posten](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="bf9a8-281">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-281">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="bf9a8-283">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-283">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="bf9a8-285">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf9a8-285">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="bf9a8-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9a8-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="bf9a8-287">Följ stegen nedan eller [titta på videon (börja vid 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bf9a8-p113">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf9a8-290">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="bf9a8-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="bf9a8-292">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="bf9a8-294">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-294">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="bf9a8-296">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="bf9a8-297">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-297">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="bf9a8-299">Bläddra ned till avsnittet **Service (SRV Records)** och välj sedan **Redigera SRV-poster**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Välj Redigera SRV-poster under Tjänst](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="bf9a8-301">I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="bf9a8-302">(Välj värdena för **Service** och **Protocol** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="bf9a8-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="bf9a8-303">**Service**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-303">**Service**</span></span>|<span data-ttu-id="bf9a8-304">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-304">**Protocol**</span></span>|<span data-ttu-id="bf9a8-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-305">**TTL**</span></span>|<span data-ttu-id="bf9a8-306">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-306">**Priority**</span></span>|<span data-ttu-id="bf9a8-307">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-307">**Weight**</span></span>|<span data-ttu-id="bf9a8-308">**Port**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-308">**Port**</span></span>|<span data-ttu-id="bf9a8-309">**Target**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bf9a8-310">_sip</span><span class="sxs-lookup"><span data-stu-id="bf9a8-310">_sip</span></span>  <br/> |<span data-ttu-id="bf9a8-311">_tls</span><span class="sxs-lookup"><span data-stu-id="bf9a8-311">_tls</span></span>  <br/> |<span data-ttu-id="bf9a8-312">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-312">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-313">100</span><span class="sxs-lookup"><span data-stu-id="bf9a8-313">100</span></span>  <br/> |<span data-ttu-id="bf9a8-314">1</span><span class="sxs-lookup"><span data-stu-id="bf9a8-314">1</span></span>  <br/> |<span data-ttu-id="bf9a8-315">443</span><span class="sxs-lookup"><span data-stu-id="bf9a8-315">443</span></span>  <br/> |<span data-ttu-id="bf9a8-316">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bf9a8-317">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bf9a8-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="bf9a8-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="bf9a8-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="bf9a8-319">_tcp</span></span>  <br/> |<span data-ttu-id="bf9a8-320">3600</span><span class="sxs-lookup"><span data-stu-id="bf9a8-320">3600</span></span>  <br/> |<span data-ttu-id="bf9a8-321">100</span><span class="sxs-lookup"><span data-stu-id="bf9a8-321">100</span></span>  <br/> |<span data-ttu-id="bf9a8-322">1</span><span class="sxs-lookup"><span data-stu-id="bf9a8-322">1</span></span>  <br/> |<span data-ttu-id="bf9a8-323">5061</span><span class="sxs-lookup"><span data-stu-id="bf9a8-323">5061</span></span>  <br/> |<span data-ttu-id="bf9a8-324">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="bf9a8-325">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="bf9a8-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Skriva eller klistra in värden för de nya posterna](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="bf9a8-327">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-327">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="bf9a8-329">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="bf9a8-329">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="bf9a8-p114">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bf9a8-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
