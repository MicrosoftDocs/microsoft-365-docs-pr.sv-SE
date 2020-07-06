---
title: Skapa DNS-poster på MyDomain för Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Läs om hur du verifierar din domän och konfigurerar DNS-poster för e-post, Skype för företag – Online och andra tjänster på MyDomain för Microsoft.
ms.openlocfilehash: 1c6edc1e3ad03b0467c70741d4097cf3a3b5e196
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400418"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="0ccd7-103">Skapa DNS-poster på MyDomain för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0ccd7-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="0ccd7-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="0ccd7-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="0ccd7-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="0ccd7-107">Om du väljer att hantera dina egna Microsoft DNS-poster hos MyDomain trots tjänstbegränsningarna utför du stegen i den här artikeln för att konfigurera DNS-posterna för e-post, Skype för företag – Online o.s.v.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="0ccd7-108">När du har lagt till dessa poster på MyDomain är din domän konfigurerad för att fungera med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="0ccd7-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0ccd7-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0ccd7-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0ccd7-112">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="0ccd7-112">Add a TXT record for verification</span></span>
<span data-ttu-id="0ccd7-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0ccd7-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0ccd7-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="0ccd7-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0ccd7-116">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-116">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="0ccd7-117">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-117">You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0ccd7-118">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-118">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="0ccd7-119">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-119">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0ccd7-120">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="0ccd7-121">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="0ccd7-122">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="0ccd7-123">I listrutan **Modify** väljer du **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="0ccd7-124">Under **Content**, i rutan för den nya posten, skriver du in, eller kopierar och klistrar in, värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="0ccd7-125">**Content**</span><span class="sxs-lookup"><span data-stu-id="0ccd7-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="0ccd7-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0ccd7-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0ccd7-127">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-127">**Note:** This is an example.</span></span> <span data-ttu-id="0ccd7-128">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="0ccd7-129">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="0ccd7-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="0ccd7-130">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="0ccd7-131">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0ccd7-132">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="0ccd7-133">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0ccd7-134">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0ccd7-135">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0ccd7-136">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0ccd7-137">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0ccd7-138">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-138">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0ccd7-139">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-139">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0ccd7-140">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-140">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0ccd7-141">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0ccd7-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0ccd7-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0ccd7-143">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-143">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="0ccd7-144">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-144">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0ccd7-145">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="0ccd7-146">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="0ccd7-147">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="0ccd7-148">Välj **MX Record** i listrutan **Modify**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="0ccd7-150">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="0ccd7-151">**Priority**</span><span class="sxs-lookup"><span data-stu-id="0ccd7-151">**Priority**</span></span>|<span data-ttu-id="0ccd7-152">**Värd**</span><span class="sxs-lookup"><span data-stu-id="0ccd7-152">**Host**</span></span>|<span data-ttu-id="0ccd7-153">**Points To: (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="0ccd7-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0ccd7-154">0</span><span class="sxs-lookup"><span data-stu-id="0ccd7-154">0</span></span>  <br/> <span data-ttu-id="0ccd7-155">Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="0ccd7-155">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |@  <br/> | <span data-ttu-id="0ccd7-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0ccd7-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="0ccd7-157">**Obs!** Hämta din \<*domain-key*\> från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="0ccd7-158"> > [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="0ccd7-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="0ccd7-160">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="0ccd7-162">Om det finns andra befintliga MX-poster väljer du **Remove** i kolumnen **Action** för var och en för att ta bort den.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="0ccd7-164">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0ccd7-166">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0ccd7-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0ccd7-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0ccd7-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0ccd7-168">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-168">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="0ccd7-169">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-169">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0ccd7-170">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="0ccd7-171">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="0ccd7-172">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="0ccd7-173">Välj **CNAME Alias** i listrutan **Modify**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="0ccd7-175">Lägg till den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="0ccd7-176">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="0ccd7-177">**Värd**</span><span class="sxs-lookup"><span data-stu-id="0ccd7-177">**Host**</span></span>|<span data-ttu-id="0ccd7-178">**Points To: (pekar på)**</span><span class="sxs-lookup"><span data-stu-id="0ccd7-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0ccd7-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0ccd7-179">autodiscover</span></span>  <br/> |<span data-ttu-id="0ccd7-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0ccd7-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="0ccd7-181">sip</span><span class="sxs-lookup"><span data-stu-id="0ccd7-181">sip</span></span>  <br/> |<span data-ttu-id="0ccd7-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0ccd7-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0ccd7-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0ccd7-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0ccd7-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0ccd7-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0ccd7-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0ccd7-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0ccd7-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0ccd7-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="0ccd7-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0ccd7-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0ccd7-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0ccd7-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="0ccd7-190">Välj **Add** (lägg till) för att lägga till den första posten.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="0ccd7-192">Lägg till den andra CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="0ccd7-193">Använd värden från den andra raden i tabellen ovan och välj sedan **Add** (lägg till) för att lägga till den andra posten.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="0ccd7-194">Lägg till de återstående posterna på samma sätt med värdena från den tredje, fjärde, femte och sjätte raden i tabellen.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0ccd7-195">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="0ccd7-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0ccd7-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0ccd7-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ccd7-197">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0ccd7-198">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0ccd7-199">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0ccd7-200">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="0ccd7-201">Behöver du exempel?</span><span class="sxs-lookup"><span data-stu-id="0ccd7-201">Need examples?</span></span> <span data-ttu-id="0ccd7-202">Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-202">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="0ccd7-203">Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="0ccd7-204">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-204">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="0ccd7-205">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-205">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0ccd7-206">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="0ccd7-207">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="0ccd7-208">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="0ccd7-209">I listrutan **Modify** väljer du **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="0ccd7-211">Under **Content**, i rutan för den nya posten, skriver du in, eller kopierar och klistrar in, värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="0ccd7-212">**Content**</span><span class="sxs-lookup"><span data-stu-id="0ccd7-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="0ccd7-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0ccd7-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0ccd7-214">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="0ccd7-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="0ccd7-216">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0ccd7-218">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="0ccd7-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0ccd7-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0ccd7-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="0ccd7-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="0ccd7-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0ccd7-222">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-222">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0ccd7-223">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="0ccd7-223">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0ccd7-224">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0ccd7-224">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
