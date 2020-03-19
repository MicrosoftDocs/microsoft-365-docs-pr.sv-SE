---
title: Ändra namnservrar för att konfigurera Office 365 med Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Lär dig att konfigurera din anpassade Office 365-domän med Namecheap om du vill att Office 365 ska hantera dina DNS-poster. '
ms.openlocfilehash: 3a26f2acb9bb52d05974f050b265dd3e1a0fc0cb
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812315"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a><span data-ttu-id="97ac5-103">Ändra namnservrar för att konfigurera Office 365 med Namecheap</span><span class="sxs-lookup"><span data-stu-id="97ac5-103">Change nameservers to set up Office 365 with Namecheap</span></span>

 <span data-ttu-id="97ac5-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="97ac5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="97ac5-105">Följ instruktionerna nedan om du vill att Office 365-DNS-posterna ska hanteras i Office 365.</span><span class="sxs-lookup"><span data-stu-id="97ac5-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="97ac5-106">(Om du vill kan du [hantera alla dina Office 365 DNS-poster på Namecheap](create-dns-records-at-namecheap.md).)</span><span class="sxs-lookup"><span data-stu-id="97ac5-106">(If you prefer, you can [manage all your Office 365 DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="97ac5-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="97ac5-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="97ac5-p102">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="97ac5-p102">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="97ac5-111">Välj **Domänlista** i listrutan under **Konto**på **målsidan.**</span><span class="sxs-lookup"><span data-stu-id="97ac5-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="97ac5-113">Leta reda på namnet på den domän som du vill redigera på sidan **Domänlista** och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="97ac5-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="97ac5-115">Välj **Avancerad DNS**.</span><span class="sxs-lookup"><span data-stu-id="97ac5-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="97ac5-117">Välj **LÄGG TILL NY POST**i avsnittet **Värdposter.**</span><span class="sxs-lookup"><span data-stu-id="97ac5-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="97ac5-119">Välj **TXT Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="97ac5-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97ac5-120">Listrutan **Typ** visas automatiskt när du väljer **Lägg till ny post**.</span><span class="sxs-lookup"><span data-stu-id="97ac5-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="97ac5-122">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="97ac5-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="97ac5-123">(Välj **TTL-värdet** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="97ac5-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="97ac5-124">**Typ**</span><span class="sxs-lookup"><span data-stu-id="97ac5-124">**Type**</span></span>|<span data-ttu-id="97ac5-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="97ac5-125">**Host**</span></span>|<span data-ttu-id="97ac5-126">**Value**</span><span class="sxs-lookup"><span data-stu-id="97ac5-126">**Value**</span></span>|<span data-ttu-id="97ac5-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="97ac5-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="97ac5-128">TXT</span><span class="sxs-lookup"><span data-stu-id="97ac5-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="97ac5-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="97ac5-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="97ac5-130">**Obs:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="97ac5-130">**Note**: This is an example.</span></span> <span data-ttu-id="97ac5-131">Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="97ac5-131">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="97ac5-132">Hur hittar jag detta?</span><span class="sxs-lookup"><span data-stu-id="97ac5-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="97ac5-133">30 min</span><span class="sxs-lookup"><span data-stu-id="97ac5-133">30 min</span></span>  <br/> |
   
   ![Namncheap-BP-Verifiera-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="97ac5-135">Markera kontrollen **Spara ändringar** (markera).</span><span class="sxs-lookup"><span data-stu-id="97ac5-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="97ac5-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="97ac5-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="97ac5-138">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="97ac5-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="97ac5-139">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="97ac5-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="97ac5-140">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="97ac5-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="97ac5-141">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="97ac5-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="97ac5-142">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="97ac5-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="97ac5-143">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="97ac5-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="97ac5-p104">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="97ac5-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="97ac5-147">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="97ac5-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="97ac5-p105">Om du vill slutföra konfigurationen av domänen med Office 365 kan du ändra domänens NS-poster hos domänregistratorn så att de pekar på de primära och sekundära namnservrarna i Office 365. Då ställs Office 365 in så att domänens DNS-poster uppdateras. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="97ac5-p105">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="97ac5-p106">Om du ändrar domänens NS-poster så att de pekar på Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen. Till exempel kommer all e-post som skickas till din domän (till exempel rob@ *your_domain*  .com) till Office 365 när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="97ac5-p106">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="97ac5-153">När du har utfört stegen i det här avsnittet är de  *enda*  namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till  *korrekta*  namnservrar om de inte redan finns i listan.</span><span class="sxs-lookup"><span data-stu-id="97ac5-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="97ac5-p107">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="97ac5-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="97ac5-157">Välj **Domänlista** i listrutan under **Konto**på **målsidan.**</span><span class="sxs-lookup"><span data-stu-id="97ac5-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="97ac5-159">Leta reda på namnet på den domän som du vill redigera på sidan **Domänlista** och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="97ac5-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="97ac5-161">Välj **domän**.</span><span class="sxs-lookup"><span data-stu-id="97ac5-161">Select **Domain**.</span></span>
    
    ![Namncheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="97ac5-163">Leta reda på avsnittet **NAMESERVERS** och välj sedan **Anpassad** i listrutan **Namecheap Default.**</span><span class="sxs-lookup"><span data-stu-id="97ac5-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namncheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="97ac5-165">Beroende på om det redan finns namnservrar som visas på sidan som visas nu, fortsätter du till något av följande två procedurer.</span><span class="sxs-lookup"><span data-stu-id="97ac5-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="97ac5-166">Om INGA namnservrar visas</span><span class="sxs-lookup"><span data-stu-id="97ac5-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="97ac5-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="97ac5-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="97ac5-168">Välj **LÄGG TILL NAMNSERVER** två gånger om du vill lägga till två nya rader.</span><span class="sxs-lookup"><span data-stu-id="97ac5-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namncheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="97ac5-170">Skriv eller kopiera och klistra in värdena i följande tabell i rutorna **Nameserver.**</span><span class="sxs-lookup"><span data-stu-id="97ac5-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="97ac5-171">**Namnserver 1**</span><span class="sxs-lookup"><span data-stu-id="97ac5-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="97ac5-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="97ac5-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="97ac5-173">**Namnserver 2**</span><span class="sxs-lookup"><span data-stu-id="97ac5-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="97ac5-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="97ac5-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="97ac5-175">**Namnserver 3**</span><span class="sxs-lookup"><span data-stu-id="97ac5-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="97ac5-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="97ac5-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="97ac5-177">**Namnserver 4**</span><span class="sxs-lookup"><span data-stu-id="97ac5-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="97ac5-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="97ac5-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namncheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="97ac5-180">Markera **kontrollen Spara** (markera).</span><span class="sxs-lookup"><span data-stu-id="97ac5-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namnbillig-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="97ac5-p108">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="97ac5-p108">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="97ac5-184">Om det redan FINNS namnservrar listade</span><span class="sxs-lookup"><span data-stu-id="97ac5-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="97ac5-p109">Följ de här anvisningarna  *endast*  om det finns andra namnservrar utöver de fyra  *korrekta*  namnservrarna. (Ta alltså  *endast*  bort eventuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="97ac5-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="97ac5-187">Om det finns några andra namnservrar i rutorna **Nameserver** tar du bort var och en genom att markera den och trycker sedan på **Delete-tangenten** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="97ac5-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namncheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="97ac5-189">Välj **LÄGG TILL NAMNSERVER** två gånger om du vill lägga till två nya rader.</span><span class="sxs-lookup"><span data-stu-id="97ac5-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namncheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="97ac5-191">Skriv eller kopiera och klistra in värdena i följande tabell i rutorna **Nameserver.**</span><span class="sxs-lookup"><span data-stu-id="97ac5-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="97ac5-192">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="97ac5-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="97ac5-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="97ac5-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="97ac5-194">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="97ac5-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="97ac5-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="97ac5-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="97ac5-196">**Namnserver 3**</span><span class="sxs-lookup"><span data-stu-id="97ac5-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="97ac5-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="97ac5-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="97ac5-198">**Namnserver 4**</span><span class="sxs-lookup"><span data-stu-id="97ac5-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="97ac5-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="97ac5-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namncheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="97ac5-201">Markera **kontrollen Spara** (markera).</span><span class="sxs-lookup"><span data-stu-id="97ac5-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namnbillig-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="97ac5-p110">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="97ac5-p110">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>
