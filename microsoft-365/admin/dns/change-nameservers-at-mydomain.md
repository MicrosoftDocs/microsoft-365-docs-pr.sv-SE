---
title: Ändra namnservrar för att konfigurera Microsoft med MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Lär dig hur du kan konfigurera Microsoft för att hantera DNS-posterna för din anpassade domän på MyDomain.
ms.openlocfilehash: 8f4a72aa0ece24ed09c4d036239a2a13c196be6c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629797"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="12117-103">Ändra namnservrar för att konfigurera Microsoft med MyDomain</span><span class="sxs-lookup"><span data-stu-id="12117-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="12117-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="12117-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="12117-105">Följ dessa instruktioner om du vill att Microsoft ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="12117-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="12117-106">(Om du vill kan du [hantera alla dina Microsoft DNS-poster på MyDomain](create-dns-records-at-mydomain.md).)</span><span class="sxs-lookup"><span data-stu-id="12117-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="12117-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="12117-107">Add a TXT record for verification</span></span>

<span data-ttu-id="12117-108">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="12117-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="12117-109">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="12117-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="12117-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="12117-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="12117-p104">Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="12117-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="12117-114">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="12117-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="12117-115">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="12117-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="12117-116">På raden **Overview** väljer du **DNS**.</span><span class="sxs-lookup"><span data-stu-id="12117-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="12117-117">I listrutan **Modify** väljer du **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="12117-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="12117-118">Under **Content**, i rutan för den nya posten, skriver du in, eller kopierar och klistrar in, värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="12117-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="12117-119">**Content**</span><span class="sxs-lookup"><span data-stu-id="12117-119">**Content**</span></span> <br/> |
|<span data-ttu-id="12117-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="12117-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="12117-121">**Obs:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="12117-121">**Note**: This is an example.</span></span> <span data-ttu-id="12117-122">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="12117-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="12117-123">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="12117-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="12117-124">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="12117-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="12117-125">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="12117-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="12117-126">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 ska söka efter posten.</span><span class="sxs-lookup"><span data-stu-id="12117-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="12117-127">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="12117-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="12117-128">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="12117-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="12117-129">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="12117-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="12117-130">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="12117-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="12117-131">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="12117-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="12117-132">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="12117-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="12117-133">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="12117-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="12117-134">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="12117-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="12117-135">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="12117-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="12117-136">Om du vill slutföra inrättandet av domänen med Microsoft ändrar du domänens NS-poster på domänregistraren så att de pekar på Microsofts primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="12117-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="12117-137">Detta ställer in Microsoft för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="12117-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="12117-138">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="12117-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="12117-139">När du ändrar domänens NS-poster så att de pekar på Microsofts namnservrar påverkas alla tjänster som för närvarande är associerade med domänen.</span><span class="sxs-lookup"><span data-stu-id="12117-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="12117-140">Till exempel alla e-postmeddelanden som skickas till din domän (t.ex. *rob@ your_domain.*</span><span class="sxs-lookup"><span data-stu-id="12117-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="12117-141">com) börjar komma till Microsoft när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="12117-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="12117-p109">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan.</span><span class="sxs-lookup"><span data-stu-id="12117-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. </span></span><br/> <span data-ttu-id="12117-143">När du har slutfört stegen i det här avsnittet är de enda namnservrarna som ska visas dessa fyra:</span><span class="sxs-lookup"><span data-stu-id="12117-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="12117-p110">Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="12117-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="12117-146">Välj **Domain Central** under **My Favorites**.</span><span class="sxs-lookup"><span data-stu-id="12117-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="12117-147">Under **Domain** väljer du namnet på den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="12117-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="12117-148">Välj **Namnservrar**på raden **Översikt** .</span><span class="sxs-lookup"><span data-stu-id="12117-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="12117-150">Välj **Use different name servers** i avsnittet **Update Name Servers**.</span><span class="sxs-lookup"><span data-stu-id="12117-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="12117-152">Beroende på om det redan finns namnservrar listade på sidan som visas nu fortsätter du till någon av följande två procedurer.</span><span class="sxs-lookup"><span data-stu-id="12117-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="12117-153">Om rätt namnservrar REDAN LISTAS</span><span class="sxs-lookup"><span data-stu-id="12117-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="12117-154">Om rätt namnservrar redan listas, kan du hoppa över detta steg.</span><span class="sxs-lookup"><span data-stu-id="12117-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="12117-156">Om rätt namnservrar INTE LISTAS</span><span class="sxs-lookup"><span data-stu-id="12117-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="12117-157">Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="12117-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="12117-158">(Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="12117-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="12117-159">Ta bort befintliga namnservrar genom att markera varje post i fältet **Namnserver:** och sedan tryck på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="12117-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="12117-161">Välj **Lägg till fler** två gånger om du vill lägga till två nya namnserverrader.</span><span class="sxs-lookup"><span data-stu-id="12117-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="12117-163">I rutorna för posterna skriver eller klipper och klistrar du in namnservervärdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="12117-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="12117-164">**Namnserver 1**</span><span class="sxs-lookup"><span data-stu-id="12117-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="12117-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12117-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="12117-166">**Namnserver 2**</span><span class="sxs-lookup"><span data-stu-id="12117-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="12117-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12117-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="12117-168">**Namnserver 3**</span><span class="sxs-lookup"><span data-stu-id="12117-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="12117-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12117-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="12117-170">**Namnserver 4**</span><span class="sxs-lookup"><span data-stu-id="12117-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="12117-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="12117-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-BP-Redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="12117-173">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="12117-173">Select **Save**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="12117-175">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="12117-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="12117-176">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="12117-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
