---
title: Ändra namnservrar för att konfigurera Microsoft med Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Läs om hur du kan konfigurera Microsoft för att hantera dina DNS-poster på Bluehost. '
ms.openlocfilehash: 63084b35c3f0d71764bca1995f25d7c6f0842a86
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629917"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="145cf-103">Ändra namnservrar för att konfigurera Microsoft med Bluehost</span><span class="sxs-lookup"><span data-stu-id="145cf-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="145cf-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="145cf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="145cf-105">Följ dessa instruktioner om du vill att Microsoft ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="145cf-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="145cf-106">(Om du vill kan du [hantera alla DNS-poster på Bluehost](create-dns-records-at-bluehost.md).)</span><span class="sxs-lookup"><span data-stu-id="145cf-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="145cf-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="145cf-107">Add a TXT record for verification</span></span>

<span data-ttu-id="145cf-108">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="145cf-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="145cf-109">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="145cf-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="145cf-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="145cf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="145cf-112">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="145cf-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="145cf-113">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="145cf-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="145cf-114">Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen.</span><span class="sxs-lookup"><span data-stu-id="145cf-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="145cf-115">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="145cf-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="145cf-116">Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området **domain_name** .</span><span class="sxs-lookup"><span data-stu-id="145cf-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="145cf-117">Gå till sidan **DNS Zone Editor** och området Add DNS Record. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="145cf-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="145cf-118">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="145cf-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="145cf-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="145cf-119">**Host Record**</span></span> <br/> |<span data-ttu-id="145cf-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="145cf-120">**TTL**</span></span> <br/> |<span data-ttu-id="145cf-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="145cf-121">**Type**</span></span> <br/> |<span data-ttu-id="145cf-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="145cf-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="145cf-123">14400</span><span class="sxs-lookup"><span data-stu-id="145cf-123">14400</span></span>  <br/> |<span data-ttu-id="145cf-124">TXT</span><span class="sxs-lookup"><span data-stu-id="145cf-124">TXT</span></span>  <br/> |<span data-ttu-id="145cf-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="145cf-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="145cf-126">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="145cf-126">**Note:** This is an example.</span></span> <span data-ttu-id="145cf-127">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.</span><span class="sxs-lookup"><span data-stu-id="145cf-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="145cf-128">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="145cf-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="145cf-129">Välj **lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="145cf-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="145cf-130">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="145cf-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="145cf-131">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="145cf-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="145cf-132">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="145cf-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="145cf-133">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="145cf-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="145cf-134">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="145cf-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="145cf-135">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="145cf-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="145cf-136">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="145cf-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="145cf-137">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="145cf-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="145cf-138">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="145cf-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="145cf-139">Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="145cf-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="145cf-140">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="145cf-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="145cf-141">Om du vill slutföra inrättandet av domänen med Microsoft ändrar du domänens NS-poster på domänregistraren så att de pekar på de primära och sekundära namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="145cf-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="145cf-142">Detta ställer in Microsoft för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="145cf-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="145cf-143">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="145cf-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="145cf-144">När du ändrar domänens NS-poster så att de pekar på Microsofts namnservrar påverkas alla tjänster som för närvarande är associerade med domänen.</span><span class="sxs-lookup"><span data-stu-id="145cf-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="145cf-145">Till exempel börjar all e-post som skickas till din domän (t.ex. *rob@ your_domain* .com) komma till Microsoft när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="145cf-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="145cf-p109">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. >  När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="145cf-148">Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="145cf-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="145cf-149">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="145cf-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="145cf-150">Markera kryssrutan för domänen i **området domain_name** på **domänsidan** och välj sedan **namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="145cf-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP - Omdelegera-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="145cf-152">Välj **Använd anpassade namnservrar**i området **domain_name** .</span><span class="sxs-lookup"><span data-stu-id="145cf-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP - Omdelegera-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="145cf-154">Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:</span><span class="sxs-lookup"><span data-stu-id="145cf-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="145cf-155">Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="145cf-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="145cf-156">Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="145cf-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="145cf-157">Om INGA namnservrar visas</span><span class="sxs-lookup"><span data-stu-id="145cf-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="145cf-158">I avsnittet **Use Custom Nameservers** skriver eller kopierar och klistrar du in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="145cf-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="145cf-159">**Första tomma raden**</span><span class="sxs-lookup"><span data-stu-id="145cf-159">**First empty row**</span></span> <br/> |<span data-ttu-id="145cf-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="145cf-161">**Andra tomma raden**</span><span class="sxs-lookup"><span data-stu-id="145cf-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="145cf-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="145cf-164">Välj **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="145cf-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="145cf-166">I avsnittet **Use Custom Nameservers** skriver eller kopierar och klistrar du in värdena från den första raden i följande tabell på den nya, tomma raden.</span><span class="sxs-lookup"><span data-stu-id="145cf-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="145cf-167">**Tredje tomma raden**</span><span class="sxs-lookup"><span data-stu-id="145cf-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="145cf-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="145cf-169">**Fjärde tomma raden**</span><span class="sxs-lookup"><span data-stu-id="145cf-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="145cf-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="145cf-171">Om du vill lägga till den fjärde namnserverposten väljer du **Lägg till rad** igen och skapar en post med värdena från den sista raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="145cf-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="145cf-172">Välj **spara namnserverinställningar**.</span><span class="sxs-lookup"><span data-stu-id="145cf-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP - Omdelegera-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="145cf-174">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="145cf-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="145cf-175">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="145cf-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="145cf-176">Om det redan FINNS namnservrar listade</span><span class="sxs-lookup"><span data-stu-id="145cf-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="145cf-177">Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="145cf-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="145cf-178">(Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="145cf-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="145cf-179">Om det finns andra namnservrar tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="145cf-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP - Omdelegera-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="145cf-181">I avsnittet **Use Custom Nameservers** skriver eller kopierar och klistrar du in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="145cf-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="145cf-182">**Första tomma raden**</span><span class="sxs-lookup"><span data-stu-id="145cf-182">**First empty row**</span></span> <br/> |<span data-ttu-id="145cf-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="145cf-184">**Andra tomma raden**</span><span class="sxs-lookup"><span data-stu-id="145cf-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="145cf-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="145cf-187">Välj **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="145cf-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="145cf-189">I avsnittet **Use Custom Nameservers** skriver eller kopierar och klistrar du in värdena från den första raden i följande tabell på den nya, tomma raden.</span><span class="sxs-lookup"><span data-stu-id="145cf-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="145cf-190">**Tredje tomma raden**</span><span class="sxs-lookup"><span data-stu-id="145cf-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="145cf-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="145cf-192">**Fjärde tomma raden**</span><span class="sxs-lookup"><span data-stu-id="145cf-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="145cf-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="145cf-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="145cf-195">Om du vill lägga till den fjärde namnserverposten väljer du **Lägg till rad** igen och skapar en post med värdena från den sista raden i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="145cf-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="145cf-196">Välj **spara namnserverinställningar**.</span><span class="sxs-lookup"><span data-stu-id="145cf-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP - Omdelegera-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="145cf-198">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="145cf-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="145cf-199">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="145cf-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
