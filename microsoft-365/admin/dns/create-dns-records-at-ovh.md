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
ms.openlocfilehash: a1f29b6f6464e781768997be0969914771ec5703
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939137"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="7130b-103">Skapa DNS-poster på OVH för Microsoft</span><span class="sxs-lookup"><span data-stu-id="7130b-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="7130b-104">[Läs frågor och svar om domäner](../setup/domains-faq.md) om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="7130b-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7130b-105">Om OVH är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="7130b-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7130b-106">Det här är de viktigaste posterna att lägga till.</span><span class="sxs-lookup"><span data-stu-id="7130b-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="7130b-107">Skapa DNS-poster på OVH för Microsoft</span><span class="sxs-lookup"><span data-stu-id="7130b-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="7130b-108">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7130b-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="7130b-109">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="7130b-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="7130b-110">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="7130b-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="7130b-111">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="7130b-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="7130b-112">När du har lagt till dessa poster på OVH konfigureras domänen så att den fungerar med Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="7130b-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="7130b-p101">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7130b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7130b-116">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="7130b-116">Add a TXT record for verification</span></span>
<span data-ttu-id="7130b-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="7130b-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="7130b-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="7130b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7130b-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="7130b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7130b-p104">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="7130b-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="7130b-125">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="7130b-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="7130b-127">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="7130b-127">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="7130b-129">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="7130b-129">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="7130b-131">Välj **TXT**</span><span class="sxs-lookup"><span data-stu-id="7130b-131">Select **TXT**</span></span>
    
    ![OVH välj TXT-post](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="7130b-133">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="7130b-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="7130b-134">Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan.</span><span class="sxs-lookup"><span data-stu-id="7130b-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="7130b-135">**Record type**</span><span class="sxs-lookup"><span data-stu-id="7130b-135">**Record type**</span></span>|<span data-ttu-id="7130b-136">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="7130b-136">**Sub-domain**</span></span>|<span data-ttu-id="7130b-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7130b-137">**TTL**</span></span>|<span data-ttu-id="7130b-138">**Värde**</span><span class="sxs-lookup"><span data-stu-id="7130b-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7130b-139">TXT</span><span class="sxs-lookup"><span data-stu-id="7130b-139">TXT</span></span>  <br/> |<span data-ttu-id="7130b-140">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="7130b-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="7130b-141">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="7130b-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7130b-142">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="7130b-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="7130b-143">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="7130b-143">**Note:** This is an example.</span></span> <span data-ttu-id="7130b-144">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="7130b-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="7130b-145">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="7130b-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="7130b-146">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="7130b-146">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="7130b-148">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="7130b-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7130b-149">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.</span><span class="sxs-lookup"><span data-stu-id="7130b-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="7130b-150">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="7130b-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7130b-151">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="7130b-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="7130b-152">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="7130b-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7130b-153">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="7130b-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7130b-154">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="7130b-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7130b-p107">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7130b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7130b-158">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7130b-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7130b-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="7130b-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="7130b-p108">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="7130b-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="7130b-163">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="7130b-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="7130b-165">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="7130b-165">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="7130b-167">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="7130b-167">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="7130b-169">Välj **MX**.</span><span class="sxs-lookup"><span data-stu-id="7130b-169">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="7130b-171">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="7130b-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="7130b-172">Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan.</span><span class="sxs-lookup"><span data-stu-id="7130b-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7130b-173">Som standard använder OVH relativ notation för målet, som lägger till domännamnet i slutet av målposten.</span><span class="sxs-lookup"><span data-stu-id="7130b-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="7130b-174">Lägg till en punkt i målposten, som visas i tabellen nedan, om du vill använda absolut notation i stället.</span><span class="sxs-lookup"><span data-stu-id="7130b-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="7130b-175">**Record type**</span><span class="sxs-lookup"><span data-stu-id="7130b-175">**Record type**</span></span>|<span data-ttu-id="7130b-176">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="7130b-176">**Sub-domain**</span></span>|<span data-ttu-id="7130b-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7130b-177">**TTL**</span></span>|<span data-ttu-id="7130b-178">**Priority**</span><span class="sxs-lookup"><span data-stu-id="7130b-178">**Priority**</span></span>|<span data-ttu-id="7130b-179">**Target**</span><span class="sxs-lookup"><span data-stu-id="7130b-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7130b-180">MX</span><span class="sxs-lookup"><span data-stu-id="7130b-180">MX</span></span>  <br/> |<span data-ttu-id="7130b-181">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="7130b-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="7130b-182">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="7130b-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7130b-183">10</span><span class="sxs-lookup"><span data-stu-id="7130b-183">10</span></span>  <br/> <span data-ttu-id="7130b-184">Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="7130b-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="7130b-185">\<domännyckel\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7130b-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7130b-186">**Anm.:** Hämta \* \<domännyckeln\> \* från ditt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="7130b-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="7130b-187">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="7130b-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX rekord för post](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="7130b-189">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7130b-189">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="7130b-191">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="7130b-191">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="7130b-193">Om det finns andra MX-poster kan du ta bort alla i listan på sidan **DNS Zone**.</span><span class="sxs-lookup"><span data-stu-id="7130b-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="7130b-194">Markera varje post och välj sedan ikonen Papperskorgen **Ta bort** i kolumnen **Åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="7130b-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="7130b-196">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="7130b-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7130b-197">Lägga till CNAME-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="7130b-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7130b-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="7130b-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="7130b-p113">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="7130b-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="7130b-202">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="7130b-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="7130b-204">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="7130b-204">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="7130b-206">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="7130b-206">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="7130b-208">Välj **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="7130b-208">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="7130b-210">Skapa den första CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="7130b-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="7130b-211">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="7130b-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="7130b-212">Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan.</span><span class="sxs-lookup"><span data-stu-id="7130b-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="7130b-213">**Record type**</span><span class="sxs-lookup"><span data-stu-id="7130b-213">**Record type**</span></span>|<span data-ttu-id="7130b-214">**Sub-domain (Underdomän)**</span><span class="sxs-lookup"><span data-stu-id="7130b-214">**Sub-domain**</span></span>|<span data-ttu-id="7130b-215">**Target (mål)**</span><span class="sxs-lookup"><span data-stu-id="7130b-215">**Target**</span></span>|<span data-ttu-id="7130b-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7130b-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7130b-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="7130b-217">CNAME</span></span>  <br/> |<span data-ttu-id="7130b-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7130b-218">autodiscover</span></span>  <br/> |<span data-ttu-id="7130b-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7130b-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="7130b-220">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="7130b-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="7130b-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="7130b-221">CNAME</span></span>  <br/> |<span data-ttu-id="7130b-222">sip</span><span class="sxs-lookup"><span data-stu-id="7130b-222">sip</span></span>  <br/> |<span data-ttu-id="7130b-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7130b-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="7130b-224">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="7130b-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="7130b-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="7130b-225">CNAME</span></span>  <br/> |<span data-ttu-id="7130b-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7130b-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7130b-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7130b-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="7130b-228">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="7130b-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="7130b-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="7130b-229">CNAME</span></span>  <br/> |<span data-ttu-id="7130b-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7130b-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7130b-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7130b-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="7130b-232">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="7130b-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="7130b-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="7130b-233">CNAME</span></span>  <br/> |<span data-ttu-id="7130b-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7130b-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7130b-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7130b-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="7130b-236">3600 sekunder</span><span class="sxs-lookup"><span data-stu-id="7130b-236">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME-post](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="7130b-238">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7130b-238">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="7130b-240">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="7130b-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="7130b-241">Upprepa föregående steg för att skapa de andra fem CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="7130b-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="7130b-242">För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.</span><span class="sxs-lookup"><span data-stu-id="7130b-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7130b-243">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="7130b-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7130b-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="7130b-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7130b-245">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="7130b-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7130b-246">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="7130b-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7130b-247">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7130b-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7130b-248">Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.</span><span class="sxs-lookup"><span data-stu-id="7130b-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="7130b-p116">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="7130b-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="7130b-252">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="7130b-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="7130b-254">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="7130b-254">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="7130b-256">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="7130b-256">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="7130b-258">Välj **TXT**.</span><span class="sxs-lookup"><span data-stu-id="7130b-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="7130b-259">I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.</span><span class="sxs-lookup"><span data-stu-id="7130b-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="7130b-260">**Record type**</span><span class="sxs-lookup"><span data-stu-id="7130b-260">**Record type**</span></span>|<span data-ttu-id="7130b-261">**Underdomän**</span><span class="sxs-lookup"><span data-stu-id="7130b-261">**Sub-domain**</span></span>|<span data-ttu-id="7130b-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7130b-262">**TTL**</span></span>|<span data-ttu-id="7130b-263">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="7130b-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7130b-264">TXT</span><span class="sxs-lookup"><span data-stu-id="7130b-264">TXT</span></span>  <br/> |<span data-ttu-id="7130b-265">(lämna tomt)</span><span class="sxs-lookup"><span data-stu-id="7130b-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="7130b-266">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="7130b-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7130b-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7130b-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7130b-268">**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    </span><span class="sxs-lookup"><span data-stu-id="7130b-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Lägg till TXT-post för SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="7130b-270">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7130b-270">Select **Next**.</span></span>
    
    ![OVH Lägg till TXT-post för SPF och välj Nästa](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="7130b-272">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="7130b-272">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7130b-274">Lägga till de två SRV-posterna som krävs för Microsoft</span><span class="sxs-lookup"><span data-stu-id="7130b-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7130b-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="7130b-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="7130b-p117">Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="7130b-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="7130b-279">Under **Domäner**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="7130b-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="7130b-281">Välj **DNS-zon**.</span><span class="sxs-lookup"><span data-stu-id="7130b-281">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="7130b-283">Välj **Lägg till en post**.</span><span class="sxs-lookup"><span data-stu-id="7130b-283">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="7130b-285">Välj **SRV**.</span><span class="sxs-lookup"><span data-stu-id="7130b-285">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="7130b-287">Skapa den första SRV-posten.</span><span class="sxs-lookup"><span data-stu-id="7130b-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="7130b-288">I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="7130b-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="7130b-289">Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan.</span><span class="sxs-lookup"><span data-stu-id="7130b-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="7130b-290">**Record type**</span><span class="sxs-lookup"><span data-stu-id="7130b-290">**Record type**</span></span>|<span data-ttu-id="7130b-291">**Sub-domain (Underdomän)**</span><span class="sxs-lookup"><span data-stu-id="7130b-291">**Sub-domain**</span></span>|<span data-ttu-id="7130b-292">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="7130b-292">**Priority**</span></span>|<span data-ttu-id="7130b-293">**Vikt**</span><span class="sxs-lookup"><span data-stu-id="7130b-293">**Weight**</span></span>|<span data-ttu-id="7130b-294">**Port**</span><span class="sxs-lookup"><span data-stu-id="7130b-294">**Port**</span></span>|<span data-ttu-id="7130b-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7130b-295">**TTL**</span></span>|<span data-ttu-id="7130b-296">**Target**</span><span class="sxs-lookup"><span data-stu-id="7130b-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7130b-297">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="7130b-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="7130b-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="7130b-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="7130b-299">100</span><span class="sxs-lookup"><span data-stu-id="7130b-299">100</span></span>  <br/> |<span data-ttu-id="7130b-300">1</span><span class="sxs-lookup"><span data-stu-id="7130b-300">1</span></span>  <br/> |<span data-ttu-id="7130b-301">443</span><span class="sxs-lookup"><span data-stu-id="7130b-301">443</span></span>  <br/> |<span data-ttu-id="7130b-302">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="7130b-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7130b-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7130b-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="7130b-304">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="7130b-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="7130b-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7130b-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="7130b-306">100</span><span class="sxs-lookup"><span data-stu-id="7130b-306">100</span></span>  <br/> |<span data-ttu-id="7130b-307">1</span><span class="sxs-lookup"><span data-stu-id="7130b-307">1</span></span>  <br/> |<span data-ttu-id="7130b-308">5061</span><span class="sxs-lookup"><span data-stu-id="7130b-308">5061</span></span>  <br/> |<span data-ttu-id="7130b-309">3600 (sekunder)</span><span class="sxs-lookup"><span data-stu-id="7130b-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7130b-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7130b-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV-rekord](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="7130b-312">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7130b-312">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="7130b-314">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="7130b-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="7130b-p119">Upprepa stegen för att skapa den andra SRV-posten. I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="7130b-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="7130b-p120">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7130b-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
