---
title: Ändra namnservrar för att konfigurera Office 365 med MyDomain
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Läs om hur du kan konfigurera Office 365 för att hantera DNS-posterna för din anpassade domän på MyDomain.
ms.openlocfilehash: 90f1469bdf2f281be14e2a9e15a9fe7ac4a8cbee
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42806527"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a><span data-ttu-id="1ad8c-103">Ändra namnservrar för att konfigurera Office 365 med MyDomain</span><span class="sxs-lookup"><span data-stu-id="1ad8c-103">Change nameservers to set up Office 365 with MyDomain</span></span>

 <span data-ttu-id="1ad8c-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="1ad8c-p101">Följ instruktionerna nedan om du vill att Office 365-DNS-posterna ska hanteras i Office 365. (Om du föredrar det kan du [ hantera alla DNS-poster för Office 365 hos MyDomain ](create-dns-records-at-mydomain.md).)</span><span class="sxs-lookup"><span data-stu-id="1ad8c-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1ad8c-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="1ad8c-107">Add a TXT record for verification</span></span>

<span data-ttu-id="1ad8c-p102">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ad8c-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1ad8c-p104">Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1ad8c-114">Välj **Domain Central**i avsnittet **Mina favoriter** .</span><span class="sxs-lookup"><span data-stu-id="1ad8c-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="1ad8c-115">Under **Domän**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="1ad8c-116">Välj **DNS**på raden **Översikt.**</span><span class="sxs-lookup"><span data-stu-id="1ad8c-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="1ad8c-117">I listrutan **Modify** väljer du **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="1ad8c-118">Under **Content**, i rutan för den nya posten, skriver du in eller kopierar och klistrar in värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="1ad8c-119">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="1ad8c-119">**Content**</span></span> <br/> |
|<span data-ttu-id="1ad8c-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1ad8c-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1ad8c-121">**Obs:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-121">**Note**: This is an example.</span></span> <span data-ttu-id="1ad8c-122">Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-122">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="1ad8c-123">Hur hittar jag det?</span><span class="sxs-lookup"><span data-stu-id="1ad8c-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="1ad8c-124">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="1ad8c-125">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1ad8c-126">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="1ad8c-127">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-127">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1ad8c-128">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="1ad8c-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1ad8c-129">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1ad8c-130">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1ad8c-131">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="1ad8c-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ad8c-p106">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1ad8c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="1ad8c-135">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="1ad8c-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="1ad8c-p107">Om du vill slutföra konfigurationen av domänen med Office 365 kan du ändra domänens NS-poster hos domänregistratorn så att de pekar på de primära och sekundära namnservrarna i Office 365. Då ställs Office 365 in så att domänens DNS-poster uppdateras. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1ad8c-139">Om du ändrar domänens NS-poster så att de pekar på Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-139">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="1ad8c-140">Till exempel alla e-postmeddelanden som skickas till din domän (som rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="1ad8c-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="1ad8c-141">com) börjar komma till Office 365 när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-141">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1ad8c-p109">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. </span></span><br/> <span data-ttu-id="1ad8c-143">När du har slutfört stegen i det här avsnittet är de enda namnservrar na som ska visas dessa fyra:</span><span class="sxs-lookup"><span data-stu-id="1ad8c-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="1ad8c-144">Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="1ad8c-144">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="1ad8c-145">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-145">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1ad8c-146">Välj **Domain Central**i avsnittet **Mina favoriter** .</span><span class="sxs-lookup"><span data-stu-id="1ad8c-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="1ad8c-147">Under **Domän**väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="1ad8c-148">Välj **Namnservrar**på raden **Översikt** .</span><span class="sxs-lookup"><span data-stu-id="1ad8c-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="1ad8c-150">Välj **Use different name servers** i avsnittet **Update Name Servers**.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="1ad8c-152">Beroende på om det redan finns namnservrar som visas på sidan som visas nu, fortsätter du till något av följande två procedurer.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="1ad8c-153">Om rätt namnservrar REDAN LISTAS</span><span class="sxs-lookup"><span data-stu-id="1ad8c-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="1ad8c-154">Om rätt namnservrar redan listas, kan du hoppa över detta steg.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="1ad8c-156">Om rätt namnservrar INTE LISTAS</span><span class="sxs-lookup"><span data-stu-id="1ad8c-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="1ad8c-157">Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="1ad8c-158">(Det vill vill et, ta bara bort alla aktuella namnservrar som *inte* har namnet **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="1ad8c-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="1ad8c-159">Ta bort befintliga namnservrar genom att markera varje post i fältet **Namnserver:** och sedan tryck på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="1ad8c-161">Välj **Lägg till fler** två gånger om du vill lägga till två nya Nameserver-rader.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="1ad8c-163">I rutorna för posterna skriver eller klipper och klistrar du in namnservervärdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="1ad8c-164">**Namnserver 1**</span><span class="sxs-lookup"><span data-stu-id="1ad8c-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="1ad8c-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1ad8c-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1ad8c-166">**Namnserver 2**</span><span class="sxs-lookup"><span data-stu-id="1ad8c-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="1ad8c-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1ad8c-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1ad8c-168">**Namnserver 3**</span><span class="sxs-lookup"><span data-stu-id="1ad8c-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="1ad8c-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1ad8c-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1ad8c-170">**Namnserver 4**</span><span class="sxs-lookup"><span data-stu-id="1ad8c-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="1ad8c-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1ad8c-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-BP-Redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="1ad8c-173">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-173">Select **Save**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="1ad8c-p112">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="1ad8c-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
