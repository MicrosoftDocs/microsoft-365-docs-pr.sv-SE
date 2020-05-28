---
title: Ändra namnservrar för att konfigurera Microsoft med Hostgator
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Lär dig hur du kan konfigurera Microsoft för att hantera DNS-posterna för din anpassade domän hos Hostgator.
ms.openlocfilehash: 787fe5f5e768d9d93cfca9d1644037142822216e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400647"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="efa87-103">Ändra namnservrar för att konfigurera Microsoft 365 med Hostgator</span><span class="sxs-lookup"><span data-stu-id="efa87-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="efa87-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="efa87-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="efa87-105">Följ dessa instruktioner om du vill att Microsoft ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="efa87-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="efa87-106">(Om du vill kan du [hantera alla Dina Microsoft DNS-poster hos Hostgator](create-dns-records-at-hostgator.md).)</span><span class="sxs-lookup"><span data-stu-id="efa87-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="efa87-107">Ange att domänen ska peka på värdkontot.</span><span class="sxs-lookup"><span data-stu-id="efa87-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efa87-108">Du måste utföra den här proceduren innan du utför proceduren i följande avsnitt, **Lägga till en TXT-post för verifiering**.</span><span class="sxs-lookup"><span data-stu-id="efa87-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="efa87-109">Följ dessa steg för att associera domänen med värdkontona.</span><span class="sxs-lookup"><span data-stu-id="efa87-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="efa87-p102">Kom igång genom att gå till kundportalen på Hostgator genom att klicka på [den här länken](https://portal.hostgator.com/domain/manage). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="efa87-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="efa87-113">Välj fliken **Domäner.**</span><span class="sxs-lookup"><span data-stu-id="efa87-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="efa87-115">Välj den domän som du vill uppdatera i området **Mina domäner** på sidan Hantera **domäner.**</span><span class="sxs-lookup"><span data-stu-id="efa87-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="efa87-117">Välj **Ändra**i området **Namnservrar** på sidan **Domains Overview** .</span><span class="sxs-lookup"><span data-stu-id="efa87-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="efa87-119">På sidan **Namnservrar** för din domän väljer du det värdkonto som är kopplat till domänen i listrutan **Välj värdkonto.** **hosting account**</span><span class="sxs-lookup"><span data-stu-id="efa87-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="efa87-121">Välj **Spara namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="efa87-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="efa87-123">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="efa87-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efa87-124">Innan du utför den här proceduren måste du först utföra proceduren i det första avsnittet i den här artikeln, [Peka din domän till ditt värdkonto.](#point-your-domain-to-your-hosting-account).</span><span class="sxs-lookup"><span data-stu-id="efa87-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="efa87-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="efa87-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="efa87-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="efa87-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="efa87-p105">Kom igång genom att gå till sidan cPanel på Hostgator Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="efa87-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="efa87-p106">(Varje konto på Hostgator har tilldelats en unik cPanel-adress. cPanel-adressen bör se ut ungefär så här: https://YourSiteAddress:secure-port-number. E-postmeddelandet du fick från Hostgator vid registreringen anger adressen.)</span><span class="sxs-lookup"><span data-stu-id="efa87-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="efa87-134">Du måste ha ett konto på Hostgator för att associera en cPanel med domänen.</span><span class="sxs-lookup"><span data-stu-id="efa87-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="efa87-135">För att komma igång kan du antingen köpa ett värdkonto från Hostgator eller [ändra domänens namnserverposter (NS)](#change-your-domains-nameserver-ns-records) så att de pekar på Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efa87-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="efa87-136">Välj **Avancerad DNS Zone Editor**i området **Domäner** på sidan **Kontrollpanelen** .</span><span class="sxs-lookup"><span data-stu-id="efa87-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="efa87-137">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="efa87-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="efa87-138">Gå till sidan **Advanced DNS Zone Editor** och området **Add a Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="efa87-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="efa87-139">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="efa87-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="efa87-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="efa87-140">**Name**</span></span> <br/> |<span data-ttu-id="efa87-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="efa87-141">**TTL**</span></span> <br/> |<span data-ttu-id="efa87-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="efa87-142">**Type**</span></span> <br/> |<span data-ttu-id="efa87-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="efa87-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="efa87-p108">Använd ditt  *domännamn*  . (Till exempel fourthcoffee.com.)  </span><span class="sxs-lookup"><span data-stu-id="efa87-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="efa87-146">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="efa87-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efa87-147">1</span><span class="sxs-lookup"><span data-stu-id="efa87-147">1</span></span>  <br/> |<span data-ttu-id="efa87-148">TXT</span><span class="sxs-lookup"><span data-stu-id="efa87-148">TXT</span></span>  <br/> |<span data-ttu-id="efa87-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="efa87-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="efa87-150">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="efa87-150">**Note:** This is an example.</span></span> <span data-ttu-id="efa87-151">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="efa87-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="efa87-152">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="efa87-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="efa87-153">Välj **Lägg till post**.</span><span class="sxs-lookup"><span data-stu-id="efa87-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="efa87-154">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="efa87-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="efa87-155">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="efa87-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="efa87-156">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="efa87-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="efa87-157">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="efa87-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="efa87-158">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="efa87-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="efa87-159">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="efa87-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="efa87-160">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="efa87-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="efa87-p110">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="efa87-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="efa87-164">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="efa87-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="efa87-165">Om du vill slutföra inrättandet av domänen med Microsoft ändrar du domänens NS-poster på domänregistraren så att de pekar på Microsofts primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="efa87-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="efa87-166">Detta ställer in Microsoft för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="efa87-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="efa87-167">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="efa87-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="efa87-168">När du ändrar domänens NS-poster så att de pekar på Microsofts namnservrar påverkas alla tjänster som för närvarande är associerade med domänen.</span><span class="sxs-lookup"><span data-stu-id="efa87-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="efa87-169">Till exempel börjar all e-post som skickas till din domän (t.ex. *rob@ your_domain* .com) komma till Microsoft när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="efa87-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="efa87-170">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan.</span><span class="sxs-lookup"><span data-stu-id="efa87-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="efa87-171">När du har slutfört stegen i det här avsnittet är de enda namnservrarna som ska visas dessa fyra: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**och **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="efa87-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="efa87-p114">Kom igång genom att gå till kundportalen på Hostgator genom att klicka på [den här länken](https://portal.hostgator.com/domain/manage). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="efa87-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="efa87-175">Välj fliken **Domäner.**</span><span class="sxs-lookup"><span data-stu-id="efa87-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP - Omdelegera-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="efa87-177">Välj den domän som du vill uppdatera i området **Mina domäner** på sidan Hantera **domäner.**</span><span class="sxs-lookup"><span data-stu-id="efa87-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="efa87-179">Välj **Ändra**i området **Namnservrar** på sidan **Domain Overview** .</span><span class="sxs-lookup"><span data-stu-id="efa87-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="efa87-181">På sidan **Namnservrar** för din domän väljer du det värdkonto som är kopplat till domänen i listrutan **Välj värdkonto.** **hosting account**</span><span class="sxs-lookup"><span data-stu-id="efa87-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP - Omdelegera-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="efa87-183">Välj **Ange manuellt mina namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="efa87-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="efa87-185">**VARNING**: Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="efa87-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="efa87-186">(Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="efa87-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="efa87-187">Fortfarande på sidan **Name Servers** för din domän tar du bort varje namnserver i listan genom att markera den och sedan trycka på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="efa87-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP - Omdelegera-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="efa87-189">I listan med namnservrar skriver du in, eller kopierar och klistrar in, de första två värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="efa87-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="efa87-190">**Name Server 1:**</span><span class="sxs-lookup"><span data-stu-id="efa87-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="efa87-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="efa87-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="efa87-192">**Name Server 2:**</span><span class="sxs-lookup"><span data-stu-id="efa87-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="efa87-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="efa87-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="efa87-194">**Name Server 3:**</span><span class="sxs-lookup"><span data-stu-id="efa87-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="efa87-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="efa87-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="efa87-196">**Name Server 4:**</span><span class="sxs-lookup"><span data-stu-id="efa87-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="efa87-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="efa87-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="efa87-199">Lägg till de andra namnservervärdena.</span><span class="sxs-lookup"><span data-stu-id="efa87-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="efa87-200">Markera **(+)** lägg till och skriv eller kopiera och klistra in värdet från nästa rad i tabellen i rutan för posten.</span><span class="sxs-lookup"><span data-stu-id="efa87-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="efa87-201">Upprepa proceduren tills du har skapat alla fyra namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="efa87-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="efa87-203">Välj **Spara namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="efa87-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="efa87-205">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="efa87-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="efa87-206">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="efa87-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
