---
title: Ändra namnservrar för att konfigurera Microsoft med 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Lär dig hur du kan konfigurera Office 365 som drivs av 21Vianet för att hantera dina DNS-poster, när 1&1 Internet är DNS-värden.
ms.openlocfilehash: 8a783be20d2f8dbdb26e9826018f911289b35235
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646565"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="0350b-103">Ändra namnservrar för att konfigurera Microsoft 365 med 1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="0350b-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="0350b-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="0350b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0350b-105">Följ de här anvisningarna om du vill att Microsoft 365 ska hantera dina DNS-poster för Microsoft 365 åt dig.</span><span class="sxs-lookup"><span data-stu-id="0350b-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="0350b-106">(Om du vill kan du [hantera alla dina Microsoft 365 DNS-poster på 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span><span class="sxs-lookup"><span data-stu-id="0350b-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0350b-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="0350b-107">Add a TXT record for verification</span></span>


<span data-ttu-id="0350b-p102">Innan du använder din domän med Microsoft 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="0350b-p102">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0350b-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="0350b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="0350b-112">Följ stegen nedan eller [titta på videon (börja vid 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="0350b-112">Follow the steps below or [watch the video (start at 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
1. <span data-ttu-id="0350b-113">Kom igång genom att gå till sidan Domains på 1&1 IONOS via [den här länken](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="0350b-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="0350b-114">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="0350b-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="0350b-115">Under **MY DOMAINS** väljer du **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="0350b-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="0350b-116">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** . Välj sedan **panel** kontrollen ( **v**) för den domänen.</span><span class="sxs-lookup"><span data-stu-id="0350b-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="0350b-117">Välj **Edit DNS Settings**i området **Domain Settings** .</span><span class="sxs-lookup"><span data-stu-id="0350b-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="0350b-118">Välj **Add Record**i avsnittet **txt and SRV Records** .</span><span class="sxs-lookup"><span data-stu-id="0350b-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="0350b-119">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="0350b-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="0350b-120">Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0350b-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="0350b-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="0350b-121">**Type**</span></span> <br/> |<span data-ttu-id="0350b-122">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="0350b-122">**Prefix**</span></span> <br/> |<span data-ttu-id="0350b-123">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="0350b-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="0350b-124">TXT</span><span class="sxs-lookup"><span data-stu-id="0350b-124">TXT</span></span>  <br/> |<span data-ttu-id="0350b-125">(Lämna det här fältet tomt.)</span><span class="sxs-lookup"><span data-stu-id="0350b-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0350b-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0350b-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="0350b-127">**Obs!** det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0350b-127">**Note**: This is an example.</span></span> <span data-ttu-id="0350b-128">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0350b-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="0350b-129">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="0350b-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="0350b-130">Välj **Spara**och sedan **Spara** på nytt.</span><span class="sxs-lookup"><span data-stu-id="0350b-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="0350b-131">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="0350b-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="0350b-132">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="0350b-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0350b-133">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="0350b-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="0350b-134">När Microsoft 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="0350b-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0350b-135">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="0350b-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0350b-136">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="0350b-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0350b-137">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="0350b-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0350b-138">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="0350b-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0350b-139">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom.</span><span class="sxs-lookup"><span data-stu-id="0350b-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0350b-140">Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort.</span><span class="sxs-lookup"><span data-stu-id="0350b-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0350b-141">Om du har problem med e-postflöde eller andra problem efter att du har lagt till DNS-poster läser du [hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0350b-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="0350b-142">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="0350b-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="0350b-143">För att slutföra konfigurationen av din domän med Microsoft 365 ändrar du domänens NS-poster hos domän registratorn så att de pekar på Microsoft 365 primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="0350b-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="0350b-144">Detta konfigurerar Microsoft 365 för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="0350b-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="0350b-145">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="0350b-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0350b-146">När du ändrar domänens NS-poster så att de pekar på Microsoft 365 Name servers påverkas alla tjänster som är associerade till din domän.</span><span class="sxs-lookup"><span data-stu-id="0350b-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="0350b-147">Till exempel kommer all e-post som skickas till din domän (som rob@ *your_domain*  . com) att komma till Microsoft 365 när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="0350b-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="0350b-148">Vill du ändra NAMNSERVER posterna så att du kan konfigurera din domän i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0350b-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="0350b-149">Följ stegen nedan eller [titta på videon (börja vid 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="0350b-149">Follow the steps below or [watch the video (start at 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="0350b-p110">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. >  När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-p110">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="0350b-152">Kom igång genom att gå till sidan Domains på 1&1 IONOS med hjälp av [den här länken](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="0350b-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="0350b-153">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="0350b-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="0350b-154">Under **MY DOMAINS** väljer du **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="0350b-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="0350b-155">Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan **panel** kontrollen ( **v**) för den domänen.</span><span class="sxs-lookup"><span data-stu-id="0350b-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="0350b-156">Välj **Edit DNS Settings**i området **Domain Settings** .</span><span class="sxs-lookup"><span data-stu-id="0350b-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="0350b-157">I avsnittet **Name Server Settings** väljer du **Other name servers**.</span><span class="sxs-lookup"><span data-stu-id="0350b-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="0350b-158">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="0350b-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="0350b-159">Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:</span><span class="sxs-lookup"><span data-stu-id="0350b-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="0350b-160">Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="0350b-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="0350b-161">Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="0350b-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="0350b-162">Om INGA namnservrar visas</span><span class="sxs-lookup"><span data-stu-id="0350b-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="0350b-163">I rutan **Name server 1** skriver du in, eller kopierar och klistrar in, värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0350b-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="0350b-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="0350b-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="0350b-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Ange ett värde i rutan Name Server 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="0350b-167">I listrutan **Additional name servers** väljer du **My secondary name servers**.</span><span class="sxs-lookup"><span data-stu-id="0350b-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="0350b-169">I rutorna **Name server 2, 3 och 4** skriver du in, eller kopierar och klistrar in, värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0350b-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="0350b-170">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="0350b-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="0350b-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0350b-172">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="0350b-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="0350b-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0350b-174">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="0350b-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="0350b-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
![Ange namnserver värden](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="0350b-177">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0350b-177">Select **Save**.</span></span>
    
    ![Välja Spara på sidan Name Server Settings](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="0350b-179">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="0350b-179">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Välja Spara i dialog rutan Edit DNS Settings](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="0350b-181">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="0350b-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="0350b-182">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="0350b-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="0350b-183">Om det redan FINNS namnservrar listade</span><span class="sxs-lookup"><span data-stu-id="0350b-183">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="0350b-p113">Följ de här anvisningarna  *endast*  om det finns andra namnservrar utöver de fyra  *korrekta*  namnservrarna. (Ta alltså  *endast*  bort eventuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="0350b-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="0350b-186">Om det förekommer andra namnservrar i **Name server**-rutorna tar du bort var och en genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="0350b-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="0350b-188">I rutorna **Name server 1, 2, 3 och 4** skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0350b-188">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="0350b-189">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="0350b-189">**Name server 1**</span></span> <br/> |<span data-ttu-id="0350b-190">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-190">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0350b-191">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="0350b-191">**Name server 2**</span></span> <br/> |<span data-ttu-id="0350b-192">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-192">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0350b-193">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="0350b-193">**Name server 3**</span></span> <br/> |<span data-ttu-id="0350b-194">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-194">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0350b-195">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="0350b-195">**Name server 4**</span></span> <br/> |<span data-ttu-id="0350b-196">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0350b-196">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Ange namnserver värden](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="0350b-198">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0350b-198">Select **Save**.</span></span>
    
    ![Välja Spara på sidan Name Server Settings](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="0350b-200">Välj **Ja**i dialog rutan **Edit DNS Settings** .</span><span class="sxs-lookup"><span data-stu-id="0350b-200">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Välja Spara i dialog rutan Edit DNS Settings](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="0350b-202">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="0350b-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="0350b-203">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="0350b-203">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


