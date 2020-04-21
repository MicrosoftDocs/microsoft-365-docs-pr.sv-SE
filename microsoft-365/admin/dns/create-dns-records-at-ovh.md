---
title: Skapa DNS-poster på OVH för Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på OVH för Microsoft.
ms.openlocfilehash: 01c455f54a7ee2efc6114dba1c01170b97ea5f71
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629293"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="74d52-103">Skapa DNS-poster på OVH för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74d52-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="74d52-104">[Läs frågor och svar om domäner](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="74d52-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="74d52-105">Om OVH är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="74d52-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="74d52-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="74d52-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="74d52-107">Skapa DNS-poster på OVH för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74d52-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="74d52-108">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="74d52-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="74d52-109">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74d52-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="74d52-110">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="74d52-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="74d52-111">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74d52-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="74d52-112">När du har lagt till dessa poster på OVH konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="74d52-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="74d52-113">Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="74d52-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="74d52-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="74d52-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="74d52-117">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="74d52-117">Add a TXT record for verification</span></span>
<span data-ttu-id="74d52-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="74d52-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="74d52-119">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="74d52-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="74d52-120">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="74d52-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74d52-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="74d52-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="74d52-p104">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="74d52-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="74d52-126">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="74d52-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="74d52-128">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="74d52-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="74d52-130">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="74d52-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="74d52-132">Välj **TXT**</span><span class="sxs-lookup"><span data-stu-id="74d52-132">Select **TXT**</span></span>
    
    ![OVH välj TXT-post](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="74d52-134">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="74d52-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="74d52-135">Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan.</span><span class="sxs-lookup"><span data-stu-id="74d52-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="74d52-136">**Record type**</span><span class="sxs-lookup"><span data-stu-id="74d52-136">**Record type**</span></span>|<span data-ttu-id="74d52-137">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="74d52-137">**Sub-domain**</span></span>|<span data-ttu-id="74d52-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="74d52-138">**TTL**</span></span>|<span data-ttu-id="74d52-139">**Värde**</span><span class="sxs-lookup"><span data-stu-id="74d52-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74d52-140">TXT</span><span class="sxs-lookup"><span data-stu-id="74d52-140">TXT</span></span>  <br/> |<span data-ttu-id="74d52-141">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="74d52-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="74d52-142">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="74d52-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="74d52-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="74d52-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="74d52-144">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="74d52-144">**Note:** This is an example.</span></span> <span data-ttu-id="74d52-145">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="74d52-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="74d52-146">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="74d52-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="74d52-147">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="74d52-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="74d52-149">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="74d52-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="74d52-150">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="74d52-150">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="74d52-151">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="74d52-151">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="74d52-152">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="74d52-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="74d52-153">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="74d52-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="74d52-154">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="74d52-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="74d52-155">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="74d52-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="74d52-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="74d52-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="74d52-159">Lägg till en MX-post så att e-post för din domän kommer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="74d52-159">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="74d52-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="74d52-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="74d52-p108">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="74d52-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="74d52-164">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="74d52-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="74d52-166">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="74d52-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="74d52-168">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="74d52-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="74d52-170">Välj **MX**.</span><span class="sxs-lookup"><span data-stu-id="74d52-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="74d52-172">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="74d52-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="74d52-173">Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan.</span><span class="sxs-lookup"><span data-stu-id="74d52-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="74d52-174">Som standard använder OVH relativ notation för målet, som lägger till domännamnet i slutet av målposten.</span><span class="sxs-lookup"><span data-stu-id="74d52-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="74d52-175">Lägg till en punkt i målposten, som visas i tabellen nedan, om du vill använda absolut notation i stället.</span><span class="sxs-lookup"><span data-stu-id="74d52-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="74d52-176">**Record type**</span><span class="sxs-lookup"><span data-stu-id="74d52-176">**Record type**</span></span>|<span data-ttu-id="74d52-177">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="74d52-177">**Sub-domain**</span></span>|<span data-ttu-id="74d52-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="74d52-178">**TTL**</span></span>|<span data-ttu-id="74d52-179">**Priority**</span><span class="sxs-lookup"><span data-stu-id="74d52-179">**Priority**</span></span>|<span data-ttu-id="74d52-180">**Target**</span><span class="sxs-lookup"><span data-stu-id="74d52-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74d52-181">MX</span><span class="sxs-lookup"><span data-stu-id="74d52-181">MX</span></span>  <br/> |<span data-ttu-id="74d52-182">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="74d52-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="74d52-183">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="74d52-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="74d52-184">10</span><span class="sxs-lookup"><span data-stu-id="74d52-184">10</span></span>  <br/> <span data-ttu-id="74d52-185">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="74d52-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="74d52-186">\<domännyckel\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="74d52-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="74d52-187">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="74d52-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="74d52-188">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="74d52-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX rekord för post](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="74d52-190">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74d52-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="74d52-192">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="74d52-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="74d52-194">Om det finns andra MX-poster kan du ta bort alla i listan på sidan **DNS Zone**.</span><span class="sxs-lookup"><span data-stu-id="74d52-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="74d52-195">Markera varje post och välj sedan ikonen Papperskorgen **Ta bort** i kolumnen **Åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="74d52-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="74d52-197">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="74d52-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="74d52-198">Lägga till CNAME-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74d52-198">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="74d52-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="74d52-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="74d52-p113">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="74d52-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="74d52-203">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="74d52-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="74d52-205">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="74d52-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="74d52-207">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="74d52-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="74d52-209">Välj **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="74d52-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="74d52-211">Skapa den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="74d52-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="74d52-212">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="74d52-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="74d52-213">Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan.</span><span class="sxs-lookup"><span data-stu-id="74d52-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="74d52-214">**Record type**</span><span class="sxs-lookup"><span data-stu-id="74d52-214">**Record type**</span></span>|<span data-ttu-id="74d52-215">**Sub-domain (Underdomän)**</span><span class="sxs-lookup"><span data-stu-id="74d52-215">**Sub-domain**</span></span>|<span data-ttu-id="74d52-216">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="74d52-216">**Target**</span></span>|<span data-ttu-id="74d52-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="74d52-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74d52-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="74d52-218">CNAME</span></span>  <br/> |<span data-ttu-id="74d52-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="74d52-219">autodiscover</span></span>  <br/> |<span data-ttu-id="74d52-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="74d52-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="74d52-221">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="74d52-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="74d52-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="74d52-222">CNAME</span></span>  <br/> |<span data-ttu-id="74d52-223">sip</span><span class="sxs-lookup"><span data-stu-id="74d52-223">sip</span></span>  <br/> |<span data-ttu-id="74d52-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="74d52-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="74d52-225">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="74d52-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="74d52-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="74d52-226">CNAME</span></span>  <br/> |<span data-ttu-id="74d52-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="74d52-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="74d52-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="74d52-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="74d52-229">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="74d52-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="74d52-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="74d52-230">CNAME</span></span>  <br/> |<span data-ttu-id="74d52-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="74d52-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="74d52-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="74d52-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="74d52-233">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="74d52-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="74d52-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="74d52-234">CNAME</span></span>  <br/> |<span data-ttu-id="74d52-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="74d52-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="74d52-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="74d52-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="74d52-237">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="74d52-237">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME-post](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="74d52-239">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74d52-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="74d52-241">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="74d52-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="74d52-242">Upprepa föregående steg för att skapa de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="74d52-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="74d52-243">För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.</span><span class="sxs-lookup"><span data-stu-id="74d52-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="74d52-244">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="74d52-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="74d52-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="74d52-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="74d52-246">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="74d52-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="74d52-247">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="74d52-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="74d52-248">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74d52-248">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="74d52-249">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="74d52-249">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="74d52-p116">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="74d52-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="74d52-253">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="74d52-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="74d52-255">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="74d52-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="74d52-257">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="74d52-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="74d52-259">Välj **TXT**.</span><span class="sxs-lookup"><span data-stu-id="74d52-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="74d52-260">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="74d52-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="74d52-261">**Record type**</span><span class="sxs-lookup"><span data-stu-id="74d52-261">**Record type**</span></span>|<span data-ttu-id="74d52-262">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="74d52-262">**Sub-domain**</span></span>|<span data-ttu-id="74d52-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="74d52-263">**TTL**</span></span>|<span data-ttu-id="74d52-264">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="74d52-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74d52-265">TXT</span><span class="sxs-lookup"><span data-stu-id="74d52-265">TXT</span></span>  <br/> |<span data-ttu-id="74d52-266">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="74d52-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="74d52-267">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="74d52-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="74d52-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="74d52-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="74d52-269">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="74d52-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Lägg till TXT-post för SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="74d52-271">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74d52-271">Select **Next**.</span></span>
    
    ![OVH Lägg till TXT-post för SPF och välj Nästa](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="74d52-273">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="74d52-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="74d52-275">Lägg till de två SRV-poster som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="74d52-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="74d52-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="74d52-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="74d52-p117">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="74d52-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="74d52-280">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="74d52-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="74d52-282">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="74d52-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="74d52-284">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="74d52-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="74d52-286">Välj **SRV**.</span><span class="sxs-lookup"><span data-stu-id="74d52-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="74d52-288">Skapa den första SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="74d52-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="74d52-289">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="74d52-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="74d52-290">Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan.</span><span class="sxs-lookup"><span data-stu-id="74d52-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="74d52-291">**Record type**</span><span class="sxs-lookup"><span data-stu-id="74d52-291">**Record type**</span></span>|<span data-ttu-id="74d52-292">**Sub-domain (Underdomän)**</span><span class="sxs-lookup"><span data-stu-id="74d52-292">**Sub-domain**</span></span>|<span data-ttu-id="74d52-293">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="74d52-293">**Priority**</span></span>|<span data-ttu-id="74d52-294">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="74d52-294">**Weight**</span></span>|<span data-ttu-id="74d52-295">**Port**</span><span class="sxs-lookup"><span data-stu-id="74d52-295">**Port**</span></span>|<span data-ttu-id="74d52-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="74d52-296">**TTL**</span></span>|<span data-ttu-id="74d52-297">**Target**</span><span class="sxs-lookup"><span data-stu-id="74d52-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="74d52-298">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="74d52-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="74d52-299">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="74d52-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="74d52-300">100</span><span class="sxs-lookup"><span data-stu-id="74d52-300">100</span></span>  <br/> |<span data-ttu-id="74d52-301">1</span><span class="sxs-lookup"><span data-stu-id="74d52-301">1</span></span>  <br/> |<span data-ttu-id="74d52-302">443</span><span class="sxs-lookup"><span data-stu-id="74d52-302">443</span></span>  <br/> |<span data-ttu-id="74d52-303">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="74d52-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="74d52-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="74d52-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="74d52-305">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="74d52-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="74d52-306">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="74d52-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="74d52-307">100</span><span class="sxs-lookup"><span data-stu-id="74d52-307">100</span></span>  <br/> |<span data-ttu-id="74d52-308">1</span><span class="sxs-lookup"><span data-stu-id="74d52-308">1</span></span>  <br/> |<span data-ttu-id="74d52-309">5061</span><span class="sxs-lookup"><span data-stu-id="74d52-309">5061</span></span>  <br/> |<span data-ttu-id="74d52-310">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="74d52-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="74d52-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="74d52-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV-rekord](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="74d52-313">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74d52-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="74d52-315">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="74d52-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="74d52-p119">Upprepa stegen för att skapa den andra SRV-posten. I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="74d52-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="74d52-p120">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="74d52-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
