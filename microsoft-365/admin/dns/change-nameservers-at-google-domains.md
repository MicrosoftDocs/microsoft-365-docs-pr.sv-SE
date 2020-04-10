---
title: Ändra namnservrar för att konfigurera Office 365 med Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Lär dig hur du kan konfigurera Office 365 för att hantera DNS-posterna för din anpassade domän på Google Domains.
ms.openlocfilehash: 86dd1745fdc85c9837e5c20844427768d4c74a81
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211937"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a><span data-ttu-id="c074f-103">Ändra namnservrar för att konfigurera Office 365 med Google Domains</span><span class="sxs-lookup"><span data-stu-id="c074f-103">Change nameservers to set up Office 365 with Google Domains</span></span>

 <span data-ttu-id="c074f-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="c074f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c074f-p101">Följ instruktionerna nedan om du vill att Office 365-DNS-posterna ska hanteras i Office 365. (Om du föredrar det kan du [ hantera alla DNS-poster för Office 365 hos Google Domains ](create-dns-records-at-google-domains.md).)</span><span class="sxs-lookup"><span data-stu-id="c074f-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c074f-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="c074f-107">Add a TXT record for verification</span></span>

<span data-ttu-id="c074f-p102">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="c074f-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c074f-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="c074f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c074f-112">För att komma igång, gå till din domänsida på Google Domains via [denna länk](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="c074f-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="c074f-113">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="c074f-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="c074f-114">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="c074f-114">To do so:</span></span>
    
1. <span data-ttu-id="c074f-115">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="c074f-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="c074f-116">Ange dina inloggningsuppgifter och välj **logga in igen**.</span><span class="sxs-lookup"><span data-stu-id="c074f-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="c074f-117">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="c074f-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="c074f-118">Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c074f-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c074f-119">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="c074f-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="c074f-120">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="c074f-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c074f-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="c074f-121">**Name**</span></span> <br/> |<span data-ttu-id="c074f-122">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="c074f-122">**Type**</span></span> <br/> |<span data-ttu-id="c074f-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c074f-123">**TTL**</span></span> <br/> |<span data-ttu-id="c074f-124">**Data**</span><span class="sxs-lookup"><span data-stu-id="c074f-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="c074f-125">TXT</span><span class="sxs-lookup"><span data-stu-id="c074f-125">TXT</span></span>  <br/> |<span data-ttu-id="c074f-126">1H (1H)</span><span class="sxs-lookup"><span data-stu-id="c074f-126">1H</span></span>  <br/> |<span data-ttu-id="c074f-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c074f-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="c074f-128">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c074f-128">**Note:** This is an example.</span></span> <span data-ttu-id="c074f-129">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="c074f-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="c074f-130">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="c074f-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="c074f-131">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c074f-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="c074f-132">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="c074f-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c074f-133">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="c074f-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c074f-134">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="c074f-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c074f-135">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c074f-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c074f-136">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="c074f-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c074f-137">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="c074f-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c074f-138">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="c074f-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c074f-p106">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c074f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="c074f-142">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="c074f-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="c074f-p107">Om du vill slutföra konfigurationen av domänen med Office 365 kan du ändra domänens NS-poster hos domänregistratorn så att de pekar på de primära och sekundära namnservrarna i Office 365. Då ställs Office 365 in så att domänens DNS-poster uppdateras. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="c074f-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c074f-146">Om du ändrar domänens NS-poster så att de pekar på Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen.</span><span class="sxs-lookup"><span data-stu-id="c074f-146">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="c074f-147">Till exempel alla e-postmeddelanden som skickas till din domän (t.ex. *rob@ your_domain.*</span><span class="sxs-lookup"><span data-stu-id="c074f-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="c074f-148">com) börjar komma till Office 365 när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="c074f-148">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c074f-p109">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. > När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra:</span><span class="sxs-lookup"><span data-stu-id="c074f-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="c074f-p110">Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:</span><span class="sxs-lookup"><span data-stu-id="c074f-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="c074f-154">Välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="c074f-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="c074f-155">Ange dina inloggningsuppgifter och välj sedan **logga in**igen .</span><span class="sxs-lookup"><span data-stu-id="c074f-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="c074f-156">På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="c074f-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="c074f-157">Välj **Use custom name servers** (använd anpassade namnservrar) i området **Name servers** (namnservrar) på sidan **Domains** (domäner).</span><span class="sxs-lookup"><span data-stu-id="c074f-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="c074f-159">Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:</span><span class="sxs-lookup"><span data-stu-id="c074f-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="c074f-160">Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="c074f-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="c074f-161">Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="c074f-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="c074f-162">Om INGA namnservrar visas</span><span class="sxs-lookup"><span data-stu-id="c074f-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="c074f-163">Lägg till den första namnservern.</span><span class="sxs-lookup"><span data-stu-id="c074f-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="c074f-164">I rutan **NAME SERVER** (namnserver) i avsnittet **Name servers** (namnservrar) skriver du in, eller kopierar och klistrar in, det första värdet från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="c074f-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="c074f-165">**Första namnservern**</span><span class="sxs-lookup"><span data-stu-id="c074f-165">**First name server**</span></span> <br/> |<span data-ttu-id="c074f-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c074f-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c074f-167">**Andra namnservern**</span><span class="sxs-lookup"><span data-stu-id="c074f-167">**Second name server**</span></span> <br/> |<span data-ttu-id="c074f-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c074f-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c074f-169">**Tredje namnservern**</span><span class="sxs-lookup"><span data-stu-id="c074f-169">**Third name server**</span></span> <br/> |<span data-ttu-id="c074f-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c074f-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c074f-171">**Fjärde namnservern**</span><span class="sxs-lookup"><span data-stu-id="c074f-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="c074f-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c074f-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domäner-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="c074f-174">Markera kontrollen **+ (lägg till)** om du vill skapa en tom rad.</span><span class="sxs-lookup"><span data-stu-id="c074f-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="c074f-176">Lägg till de andra tre namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="c074f-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="c074f-177">Skapa en post i avsnittet **Använd anpassade namnservrar** med hjälp av värdena från nästa rad i tabellen och välj sedan kontrollen **+ (lägg till)** för att lägga till en annan rad.</span><span class="sxs-lookup"><span data-stu-id="c074f-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="c074f-178">Upprepa proceduren tills du har skapat alla fyra namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="c074f-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="c074f-179">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c074f-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="c074f-p111">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="c074f-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="c074f-183">Om det redan FINNS namnservrar listade</span><span class="sxs-lookup"><span data-stu-id="c074f-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="c074f-184">Om det finns några andra namnservrar i listan väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="c074f-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="c074f-185">Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="c074f-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="c074f-186">(Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="c074f-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="c074f-188">Ta bort var och en genom att markera den och sedan trycka på **Del**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="c074f-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="c074f-190">På **NAME SERVER**-raderna i avsnittet **Name servers** (namnservrar) skriver du in, eller kopierar och klistrar in, värdena från tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="c074f-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="c074f-191">**Första namnservern**</span><span class="sxs-lookup"><span data-stu-id="c074f-191">**First name server**</span></span> <br/> |<span data-ttu-id="c074f-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c074f-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c074f-193">**Andra namnservern**</span><span class="sxs-lookup"><span data-stu-id="c074f-193">**Second name server**</span></span> <br/> |<span data-ttu-id="c074f-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c074f-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c074f-195">**Tredje namnservern**</span><span class="sxs-lookup"><span data-stu-id="c074f-195">**Third name server**</span></span> <br/> |<span data-ttu-id="c074f-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c074f-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c074f-197">**Fjärde namnservern**</span><span class="sxs-lookup"><span data-stu-id="c074f-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="c074f-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c074f-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domäner-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="c074f-200">Markera kontrollen **+(add)** om du vill skapa en tom rad.</span><span class="sxs-lookup"><span data-stu-id="c074f-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="c074f-202">Lägg till de andra två namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="c074f-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="c074f-203">Skapa en post i avsnittet **Använd anpassade namnservrar** med hjälp av värdena från nästa rad i tabellen och välj sedan kontrollen **+(add)** för att lägga till en annan rad.</span><span class="sxs-lookup"><span data-stu-id="c074f-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="c074f-204">Upprepa proceduren tills du har skapat alla fyra namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="c074f-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="c074f-205">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c074f-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="c074f-p113">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="c074f-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
