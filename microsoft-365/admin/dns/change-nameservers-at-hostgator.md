---
title: Ändra namnservrar för att konfigurera Microsoft med Host Gator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Lär dig hur du kan konfigurera Microsoft för att hantera DNS-posterna för din anpassade domän på Host gator.
ms.openlocfilehash: 34e7bbe3abc084185f72f4fef004ad891492ef3c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658026"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="c23d5-103">Ändra namnservrar för att konfigurera Microsoft 365 med Host Gator</span><span class="sxs-lookup"><span data-stu-id="c23d5-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="c23d5-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="c23d5-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="c23d5-105">Följ de här anvisningarna om du vill att Microsoft ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="c23d5-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="c23d5-106">(Om du vill kan du [hantera alla dina Microsoft DNS-poster på Host Gator](create-dns-records-at-hostgator.md).)</span><span class="sxs-lookup"><span data-stu-id="c23d5-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="c23d5-107">Ange att domänen ska peka på värdkontot.</span><span class="sxs-lookup"><span data-stu-id="c23d5-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c23d5-108">Du måste utföra den här proceduren innan du utför proceduren i följande avsnitt, **Lägga till en TXT-post för verifiering**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="c23d5-109">Följ dessa steg för att associera domänen med värdkontona.</span><span class="sxs-lookup"><span data-stu-id="c23d5-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="c23d5-p102">Kom igång genom att gå till kundportalen på Hostgator genom att klicka på [den här länken](https://portal.hostgator.com/domain/manage). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="c23d5-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="c23d5-113">Välj fliken **domäner** .</span><span class="sxs-lookup"><span data-stu-id="c23d5-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="c23d5-115">Välj den domän som du vill uppdatera i området **Mina domäner** på sidan **hantera domäner** .</span><span class="sxs-lookup"><span data-stu-id="c23d5-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="c23d5-117">På sidan **Domains Overview** i området **Name servers** väljer du **change**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="c23d5-119">Välj det **värd konto** som är kopplat till din domän i list rutan **Välj värd konto** på sidan **namnservrar** för din domän.</span><span class="sxs-lookup"><span data-stu-id="c23d5-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="c23d5-121">Välj **Save Name servers**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c23d5-123">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="c23d5-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c23d5-124">Innan du utför den här proceduren måste du först utföra proceduren i det första avsnittet i den här artikeln, [peka domänen på ditt värd konto.](#point-your-domain-to-your-hosting-account).</span><span class="sxs-lookup"><span data-stu-id="c23d5-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="c23d5-p103">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="c23d5-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c23d5-p104">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="c23d5-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="c23d5-p105">Kom igång genom att gå till sidan cPanel på Hostgator Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="c23d5-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="c23d5-p106">(Varje konto på Hostgator har tilldelats en unik cPanel-adress. cPanel-adressen bör se ut ungefär så här: https://YourSiteAddress:secure-port-number. E-postmeddelandet du fick från Hostgator vid registreringen anger adressen.)</span><span class="sxs-lookup"><span data-stu-id="c23d5-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c23d5-134">Du måste ha ett konto på Hostgator för att associera en cPanel med domänen.</span><span class="sxs-lookup"><span data-stu-id="c23d5-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="c23d5-135">För att komma igång kan du antingen köpa ett värd konto från Host gator eller [ändra domänens namnserver (NS-poster)](#change-your-domains-nameserver-ns-records) så att de pekar på Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c23d5-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="c23d5-136">På sidan **kontroll panelen** i området **domäner** väljer du **avancerad DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="c23d5-137">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="c23d5-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="c23d5-138">Gå till sidan **Advanced DNS Zone Editor** och området **Add a Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c23d5-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c23d5-139">(Välj värdet för **Type** i listrutan.)</span><span class="sxs-lookup"><span data-stu-id="c23d5-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c23d5-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="c23d5-140">**Name**</span></span> <br/> |<span data-ttu-id="c23d5-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c23d5-141">**TTL**</span></span> <br/> |<span data-ttu-id="c23d5-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="c23d5-142">**Type**</span></span> <br/> |<span data-ttu-id="c23d5-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="c23d5-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="c23d5-p108">Använd ditt  *domännamn*  . (Till exempel fourthcoffee.com.)  </span><span class="sxs-lookup"><span data-stu-id="c23d5-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="c23d5-146">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="c23d5-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c23d5-147">9.1</span><span class="sxs-lookup"><span data-stu-id="c23d5-147">1</span></span>  <br/> |<span data-ttu-id="c23d5-148">TXT</span><span class="sxs-lookup"><span data-stu-id="c23d5-148">TXT</span></span>  <br/> |<span data-ttu-id="c23d5-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c23d5-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c23d5-150">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c23d5-150">**Note:** This is an example.</span></span> <span data-ttu-id="c23d5-151">Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="c23d5-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c23d5-152">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="c23d5-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="c23d5-153">Välj **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="c23d5-154">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="c23d5-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c23d5-155">Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="c23d5-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="c23d5-156">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="c23d5-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c23d5-157">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c23d5-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c23d5-158">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="c23d5-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c23d5-159">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c23d5-160">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c23d5-p110">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c23d5-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="c23d5-164">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="c23d5-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="c23d5-165">För att slutföra konfigurationen av din domän med Microsoft ändrar du domänens NS-poster hos domän registratorn så att de pekar på Microsofts primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="c23d5-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="c23d5-166">Detta konfigurerar Microsoft för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="c23d5-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="c23d5-167">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="c23d5-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c23d5-168">När du ändrar domänens NS-poster så att de pekar på Microsoft Name Server påverkas alla tjänster som är associerade till din domän.</span><span class="sxs-lookup"><span data-stu-id="c23d5-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="c23d5-169">Till exempel kommer all e-post som skickas till din domän (som rob@ *your_domain*  . com) att komma till Microsoft när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="c23d5-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c23d5-170">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan.</span><span class="sxs-lookup"><span data-stu-id="c23d5-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="c23d5-171">När du har slutfört stegen i det här avsnittet är de enda namnservrar som ska visas här fyra:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com** och **NS4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="c23d5-p114">Kom igång genom att gå till kundportalen på Hostgator genom att klicka på [den här länken](https://portal.hostgator.com/domain/manage). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="c23d5-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="c23d5-175">Välj fliken **domäner** .</span><span class="sxs-lookup"><span data-stu-id="c23d5-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP - Omdelegera-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="c23d5-177">Välj den domän som du vill uppdatera i området **Mina domäner** på sidan **hantera domäner** .</span><span class="sxs-lookup"><span data-stu-id="c23d5-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="c23d5-179">Välj **ändra** i området **Name servers** på sidan **Domain Overview** .</span><span class="sxs-lookup"><span data-stu-id="c23d5-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="c23d5-181">Välj det **värd konto** som är kopplat till din domän i list rutan **Välj värd konto** på sidan **namnservrar** för din domän.</span><span class="sxs-lookup"><span data-stu-id="c23d5-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP - Omdelegera-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="c23d5-183">Välj **Ange namn** automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c23d5-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="c23d5-185">**Varning**! Följ de här anvisningarna bara om du har en annan namnservrar än de fyra korrekta namnservrar.</span><span class="sxs-lookup"><span data-stu-id="c23d5-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="c23d5-186">(Det är bara att ta bort alla aktuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com** eller **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="c23d5-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="c23d5-187">Fortfarande på sidan **Name Servers** för din domän tar du bort varje namnserver i listan genom att markera den och sedan trycka på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="c23d5-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP - Omdelegera-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="c23d5-189">I listan med namnservrar skriver du in, eller kopierar och klistrar in, de första två värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c23d5-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="c23d5-190">**Name Server 1:**</span><span class="sxs-lookup"><span data-stu-id="c23d5-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="c23d5-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c23d5-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c23d5-192">**Name Server 2:**</span><span class="sxs-lookup"><span data-stu-id="c23d5-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="c23d5-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c23d5-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c23d5-194">**Name Server 3:**</span><span class="sxs-lookup"><span data-stu-id="c23d5-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="c23d5-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c23d5-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c23d5-196">**Name Server 4:**</span><span class="sxs-lookup"><span data-stu-id="c23d5-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="c23d5-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c23d5-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Host Gator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="c23d5-199">Lägg till de andra namnservervärdena.</span><span class="sxs-lookup"><span data-stu-id="c23d5-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="c23d5-200">Välj **(+)** Lägg till och skriv eller kopiera och klistra in värdet från nästa rad i tabellen i rutan för posten.</span><span class="sxs-lookup"><span data-stu-id="c23d5-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="c23d5-201">Upprepa proceduren tills du har skapat alla fyra namnserverposterna.</span><span class="sxs-lookup"><span data-stu-id="c23d5-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="c23d5-203">Välj **Save Name servers**.</span><span class="sxs-lookup"><span data-stu-id="c23d5-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP - Omdelegera-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="c23d5-205">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="c23d5-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="c23d5-206">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="c23d5-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
