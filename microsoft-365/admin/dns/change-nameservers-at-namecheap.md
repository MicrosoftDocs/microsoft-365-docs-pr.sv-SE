---
title: Ändra namnservrar för att konfigurera Microsoft med NameCheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Lär dig hur du konfigurerar din Microsoft Custom Domain med NameCheap om du vill att Microsoft ska hantera dina DNS-poster. '
ms.openlocfilehash: 0dec28c99bd49d3ba558e11afac8142c7df96591
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657990"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a><span data-ttu-id="eab6c-103">Ändra namnservrar för att konfigurera Microsoft med NameCheap</span><span class="sxs-lookup"><span data-stu-id="eab6c-103">Change nameservers to set up Microsoft with Namecheap</span></span>

 <span data-ttu-id="eab6c-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="eab6c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="eab6c-105">Följ de här anvisningarna om du vill att Microsoft ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="eab6c-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="eab6c-106">(Om du vill kan du [hantera alla dina Microsoft DNS-poster på NameCheap](create-dns-records-at-namecheap.md).)</span><span class="sxs-lookup"><span data-stu-id="eab6c-106">(If you prefer, you can [manage all your Microsoft DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="eab6c-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="eab6c-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="eab6c-p102">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="eab6c-p102">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="eab6c-111">Välj **domän lista** i list rutan under **konto** **på Start sidan.**</span><span class="sxs-lookup"><span data-stu-id="eab6c-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="eab6c-113">Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.</span><span class="sxs-lookup"><span data-stu-id="eab6c-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="eab6c-115">Välj **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="eab6c-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="eab6c-117">Välj **Add New Record** i avsnittet **Host Records** .</span><span class="sxs-lookup"><span data-stu-id="eab6c-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="eab6c-119">Välj **TXT Record** i listrutan **Type**.</span><span class="sxs-lookup"><span data-stu-id="eab6c-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eab6c-120">List rutan **typ** visas automatiskt när du väljer **Lägg till ny post**.</span><span class="sxs-lookup"><span data-stu-id="eab6c-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="eab6c-122">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="eab6c-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="eab6c-123">(Välj **TTL** -värdet i list rutan.)</span><span class="sxs-lookup"><span data-stu-id="eab6c-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="eab6c-124">**Typ**</span><span class="sxs-lookup"><span data-stu-id="eab6c-124">**Type**</span></span>|<span data-ttu-id="eab6c-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="eab6c-125">**Host**</span></span>|<span data-ttu-id="eab6c-126">**Värde**</span><span class="sxs-lookup"><span data-stu-id="eab6c-126">**Value**</span></span>|<span data-ttu-id="eab6c-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eab6c-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eab6c-128">TXT</span><span class="sxs-lookup"><span data-stu-id="eab6c-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="eab6c-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="eab6c-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="eab6c-130">**Obs!** det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="eab6c-130">**Note**: This is an example.</span></span> <span data-ttu-id="eab6c-131">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="eab6c-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="eab6c-132">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="eab6c-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="eab6c-133">30 min</span><span class="sxs-lookup"><span data-stu-id="eab6c-133">30 min</span></span>  <br/> |
   
   ![NameCheap-BP-verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="eab6c-135">Markera kontrollen **Spara ändringar** (bock markering).</span><span class="sxs-lookup"><span data-stu-id="eab6c-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="eab6c-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="eab6c-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="eab6c-138">Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="eab6c-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="eab6c-139">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="eab6c-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="eab6c-140">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="eab6c-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="eab6c-141">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="eab6c-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="eab6c-142">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="eab6c-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="eab6c-143">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="eab6c-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="eab6c-p104">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eab6c-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="eab6c-147">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="eab6c-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="eab6c-148">För att slutföra konfigurationen av din domän med Microsoft ändrar du domänens NS-poster hos domän registratorn så att de pekar på Microsofts primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="eab6c-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="eab6c-149">Detta konfigurerar Microsoft för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="eab6c-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="eab6c-150">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="eab6c-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="eab6c-151">När du ändrar domänens NS-poster så att de pekar på Microsoft Name Server påverkas alla tjänster som är associerade till din domän.</span><span class="sxs-lookup"><span data-stu-id="eab6c-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="eab6c-152">Till exempel kommer all e-post som skickas till din domän (som rob@ *your_domain*  . com) att komma till Microsoft när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="eab6c-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="eab6c-153">När du har utfört stegen i det här avsnittet är de  *enda*  namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till  *korrekta*  namnservrar om de inte redan finns i listan.</span><span class="sxs-lookup"><span data-stu-id="eab6c-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="eab6c-p107">Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="eab6c-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="eab6c-157">Välj **domän lista** i list rutan under **konto** **på Start sidan.**</span><span class="sxs-lookup"><span data-stu-id="eab6c-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="eab6c-159">Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.</span><span class="sxs-lookup"><span data-stu-id="eab6c-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="eab6c-161">Välj **domän**.</span><span class="sxs-lookup"><span data-stu-id="eab6c-161">Select **Domain**.</span></span>
    
    ![NameCheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="eab6c-163">Leta reda på avsnittet **namnservrar** och välj sedan **anpassad** från List rutan **NameCheap default** .</span><span class="sxs-lookup"><span data-stu-id="eab6c-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![NameCheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="eab6c-165">Beroende på om det redan finns namnservrar på sidan som visas nu går du vidare till något av de två följande procedurerna.</span><span class="sxs-lookup"><span data-stu-id="eab6c-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="eab6c-166">Om INGA namnservrar visas</span><span class="sxs-lookup"><span data-stu-id="eab6c-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="eab6c-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="eab6c-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="eab6c-168">Välj **Lägg till namnserver** två gånger för att lägga till två nya rader.</span><span class="sxs-lookup"><span data-stu-id="eab6c-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![NameCheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="eab6c-170">Skriv in, eller kopiera och klistra in, värdena från följande tabell i rutorna **namnserver** .</span><span class="sxs-lookup"><span data-stu-id="eab6c-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="eab6c-171">**Namnserver 1**</span><span class="sxs-lookup"><span data-stu-id="eab6c-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="eab6c-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="eab6c-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="eab6c-173">**Namnserver 2**</span><span class="sxs-lookup"><span data-stu-id="eab6c-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="eab6c-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="eab6c-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="eab6c-175">**Namnserver 3**</span><span class="sxs-lookup"><span data-stu-id="eab6c-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="eab6c-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="eab6c-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="eab6c-177">**Namnserver 4**</span><span class="sxs-lookup"><span data-stu-id="eab6c-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="eab6c-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="eab6c-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![NameCheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="eab6c-180">Markera kontrollen **Spara** (bock markering).</span><span class="sxs-lookup"><span data-stu-id="eab6c-180">Select the **Save** (check mark) control.</span></span> 
    
    ![NameCheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="eab6c-182">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="eab6c-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="eab6c-183">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="eab6c-183">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="eab6c-184">Om det redan FINNS namnservrar listade</span><span class="sxs-lookup"><span data-stu-id="eab6c-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="eab6c-p109">Följ de här anvisningarna  *endast*  om det finns andra namnservrar utöver de fyra  *korrekta*  namnservrarna. (Ta alltså  *endast*  bort eventuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="eab6c-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="eab6c-187">Om det finns andra namnservrar i **namnserver** rutor tar du bort var och en genom att markera den och sedan trycka på **Delete** -tangenten på tangent bordet.</span><span class="sxs-lookup"><span data-stu-id="eab6c-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NameCheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="eab6c-189">Välj **Lägg till namnserver** två gånger för att lägga till två nya rader.</span><span class="sxs-lookup"><span data-stu-id="eab6c-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![NameCheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="eab6c-191">Skriv in, eller kopiera och klistra in, värdena från följande tabell i rutorna **namnserver** .</span><span class="sxs-lookup"><span data-stu-id="eab6c-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="eab6c-192">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="eab6c-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="eab6c-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="eab6c-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="eab6c-194">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="eab6c-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="eab6c-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="eab6c-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="eab6c-196">**Namnserver 3**</span><span class="sxs-lookup"><span data-stu-id="eab6c-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="eab6c-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="eab6c-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="eab6c-198">**Namnserver 4**</span><span class="sxs-lookup"><span data-stu-id="eab6c-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="eab6c-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="eab6c-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![NameCheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="eab6c-201">Markera kontrollen **Spara** (bock markering).</span><span class="sxs-lookup"><span data-stu-id="eab6c-201">Select the **Save** (check mark) control.</span></span> 
    
    ![NameCheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="eab6c-203">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="eab6c-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="eab6c-204">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="eab6c-204">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
