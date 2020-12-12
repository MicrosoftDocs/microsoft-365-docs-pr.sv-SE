---
title: Ändra namnservrar för att konfigurera Microsoft med Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Lär dig hur du kan konfigurera Microsoft för att hantera DNS-posterna för din anpassade domän på Google-domäner.
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658446"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="5eadc-103">Ändra namnservrar för att konfigurera Microsoft med Google Domains</span><span class="sxs-lookup"><span data-stu-id="5eadc-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="5eadc-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5eadc-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5eadc-105">Följ de här anvisningarna om du vill att Microsoft ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="5eadc-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="5eadc-106">(Om du vill kan du [hantera alla dina DNS-poster på Google Domains](create-dns-records-at-google-domains.md).)</span><span class="sxs-lookup"><span data-stu-id="5eadc-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5eadc-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="5eadc-107">Add a TXT record for verification</span></span>

<span data-ttu-id="5eadc-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="5eadc-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5eadc-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="5eadc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5eadc-112">Gå till sidan Domains på Google Domains via [den här länken](https://domains.google.com/registrar)för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="5eadc-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="5eadc-113">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="5eadc-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="5eadc-114">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="5eadc-114">To do so:</span></span>
    
1. <span data-ttu-id="5eadc-115">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="5eadc-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="5eadc-116">Ange dina inloggnings uppgifter och välj **Logga** in igen.</span><span class="sxs-lookup"><span data-stu-id="5eadc-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="5eadc-117">Välj **Konfigurera DNS** för den domän som du vill redigera i avsnittet **Domain** **på sidan** domains.</span><span class="sxs-lookup"><span data-stu-id="5eadc-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5eadc-118">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5eadc-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5eadc-119">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="5eadc-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="5eadc-120">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="5eadc-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5eadc-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="5eadc-121">**Name**</span></span> <br/> |<span data-ttu-id="5eadc-122">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="5eadc-122">**Type**</span></span> <br/> |<span data-ttu-id="5eadc-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5eadc-123">**TTL**</span></span> <br/> |<span data-ttu-id="5eadc-124">**Data**</span><span class="sxs-lookup"><span data-stu-id="5eadc-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="5eadc-125">TXT</span><span class="sxs-lookup"><span data-stu-id="5eadc-125">TXT</span></span>  <br/> |<span data-ttu-id="5eadc-126">1H</span><span class="sxs-lookup"><span data-stu-id="5eadc-126">1H</span></span>  <br/> |<span data-ttu-id="5eadc-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5eadc-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="5eadc-128">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="5eadc-128">**Note:** This is an example.</span></span> <span data-ttu-id="5eadc-129">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="5eadc-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5eadc-130">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="5eadc-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="5eadc-131">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5eadc-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="5eadc-132">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="5eadc-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5eadc-133">Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="5eadc-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="5eadc-134">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="5eadc-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5eadc-135">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="5eadc-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5eadc-136">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="5eadc-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5eadc-137">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="5eadc-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5eadc-138">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="5eadc-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5eadc-p106">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5eadc-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5eadc-142">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="5eadc-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="5eadc-143">För att slutföra konfigurationen av din domän med Microsoft ändrar du domänens NS-poster hos domän registratorn så att de pekar på Microsofts primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="5eadc-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="5eadc-144">Detta konfigurerar Microsoft för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="5eadc-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="5eadc-145">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="5eadc-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5eadc-146">När du ändrar domänens NS-poster så att de pekar på Microsoft Name Server påverkas alla tjänster som är associerade till din domän.</span><span class="sxs-lookup"><span data-stu-id="5eadc-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="5eadc-147">Till exempel, alla e-postmeddelanden som skickas till din domän (som rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="5eadc-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="5eadc-148">com) kommer att komma till Microsoft när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="5eadc-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5eadc-p109">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. > När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra:</span><span class="sxs-lookup"><span data-stu-id="5eadc-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="5eadc-p110">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="5eadc-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="5eadc-154">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="5eadc-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="5eadc-155">Ange dina inloggnings uppgifter och välj sedan **Logga** in igen.</span><span class="sxs-lookup"><span data-stu-id="5eadc-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="5eadc-156">Välj **Konfigurera DNS** för den domän som du vill redigera i avsnittet **Domain** **på sidan** domains.</span><span class="sxs-lookup"><span data-stu-id="5eadc-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5eadc-157">Välj **Use custom name servers** (använd anpassade namnservrar) i området **Name servers** (namnservrar) på sidan **Domains** (domäner).</span><span class="sxs-lookup"><span data-stu-id="5eadc-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="5eadc-159">Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:</span><span class="sxs-lookup"><span data-stu-id="5eadc-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="5eadc-160">Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="5eadc-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="5eadc-161">Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="5eadc-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="5eadc-162">Om INGA namnservrar visas</span><span class="sxs-lookup"><span data-stu-id="5eadc-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="5eadc-163">Lägg till den första namnservern.</span><span class="sxs-lookup"><span data-stu-id="5eadc-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="5eadc-164">I rutan **NAME SERVER** (namnserver) i avsnittet **Name servers** (namnservrar) skriver du in, eller kopierar och klistrar in, det första värdet från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="5eadc-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="5eadc-165">**Första namnservern**</span><span class="sxs-lookup"><span data-stu-id="5eadc-165">**First name server**</span></span> <br/> |<span data-ttu-id="5eadc-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5eadc-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5eadc-167">**Andra namnservern**</span><span class="sxs-lookup"><span data-stu-id="5eadc-167">**Second name server**</span></span> <br/> |<span data-ttu-id="5eadc-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5eadc-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5eadc-169">**Tredje namnservern**</span><span class="sxs-lookup"><span data-stu-id="5eadc-169">**Third name server**</span></span> <br/> |<span data-ttu-id="5eadc-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5eadc-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5eadc-171">**Fjärde namnservern**</span><span class="sxs-lookup"><span data-stu-id="5eadc-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="5eadc-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5eadc-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="5eadc-174">Välj **+ (Lägg till)** för att skapa en tom rad.</span><span class="sxs-lookup"><span data-stu-id="5eadc-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="5eadc-176">Lägg till de andra tre namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="5eadc-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="5eadc-177">I avsnittet **Använd anpassade namnservrar** skapar du en post med värdena från nästa rad i tabellen och väljer sedan **+ (Lägg till)** för att lägga till ytterligare en rad.</span><span class="sxs-lookup"><span data-stu-id="5eadc-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="5eadc-178">Upprepa proceduren tills du har skapat alla fyra namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="5eadc-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="5eadc-179">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5eadc-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="5eadc-181">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="5eadc-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="5eadc-182">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="5eadc-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="5eadc-183">Om det redan FINNS namnservrar listade</span><span class="sxs-lookup"><span data-stu-id="5eadc-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="5eadc-184">Om det finns andra namnservrar i listan väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="5eadc-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5eadc-185">Följ de här stegen endast om du har andra befintliga namnservrar än de fyra korrekta namnservrar.</span><span class="sxs-lookup"><span data-stu-id="5eadc-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="5eadc-186">(Det är bara att ta bort alla aktuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com** eller **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="5eadc-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="5eadc-188">Ta bort var och en genom att markera den och sedan trycka på **Del**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="5eadc-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="5eadc-190">På **NAME SERVER**-raderna i avsnittet **Name servers** (namnservrar) skriver du in, eller kopierar och klistrar in, värdena från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="5eadc-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="5eadc-191">**Första namnservern**</span><span class="sxs-lookup"><span data-stu-id="5eadc-191">**First name server**</span></span> <br/> |<span data-ttu-id="5eadc-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5eadc-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5eadc-193">**Andra namnservern**</span><span class="sxs-lookup"><span data-stu-id="5eadc-193">**Second name server**</span></span> <br/> |<span data-ttu-id="5eadc-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5eadc-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5eadc-195">**Tredje namnservern**</span><span class="sxs-lookup"><span data-stu-id="5eadc-195">**Third name server**</span></span> <br/> |<span data-ttu-id="5eadc-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5eadc-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5eadc-197">**Fjärde namnservern**</span><span class="sxs-lookup"><span data-stu-id="5eadc-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="5eadc-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5eadc-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="5eadc-200">Välj **+ (Lägg till)** för att skapa en tom rad.</span><span class="sxs-lookup"><span data-stu-id="5eadc-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="5eadc-202">Lägg till de andra två namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="5eadc-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="5eadc-203">I avsnittet **Använd anpassade namnservrar** skapar du en post med värdena från nästa rad i tabellen och väljer sedan **+ (Lägg till)** för att lägga till ytterligare en rad.</span><span class="sxs-lookup"><span data-stu-id="5eadc-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="5eadc-204">Upprepa proceduren tills du har skapat alla fyra namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="5eadc-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="5eadc-205">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5eadc-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="5eadc-207">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="5eadc-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="5eadc-208">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="5eadc-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
